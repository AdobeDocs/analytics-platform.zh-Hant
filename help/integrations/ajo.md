---
title: 將 Adobe Journey Optimizer 與 Customer Journey Analytics 整合
description: 引進 AJO 產生的資料並在 CJA 內使用 Analysis Workspace 加以分析。
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 100%

---


# 將 Adobe Journey Optimizer 與 Customer Journey Analytics 整合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 可幫助您提供連線、情境式和個人化的體驗。 它有助於讓您的客戶了解其客戶歷程中的下一步。

您可以匯入 Journey Optimizer 產生的資料，以透過以下步驟在 Customer Journey Analytics 中執行進階分析：

## 將 Journey Optimizer 中的資料傳送到 Adobe Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及 Journey Optimizer 與 Customer Journey Analytics 之間的連結。 請參閱 Journey Optimizer 使用手冊中的[開始使用資料集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)，以取得如何將 Journey Optimizer 資料當作資料集傳送給 Platform 的相關步驟。

## 在 Customer Journey Analytics 中建立連線

當 Journey Optimizer 資料引進 Adobe Experience Platform 後，您就可以根據您的 Journey Optimizer 資料集[建立連線](/help/connections/create-connection.md)。 選取要傳送給 Platform 的資料集。

## 設定資料檢視，以容納 Journey Optimizer 維度和量度

在建立連線後，您可以建立一個或多個[資料檢視](/help/data-views/create-dataview.md)來設定 Customer Journey Analytics 中可用的所需維度和量度。

您可以在資料檢視中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。 請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關如何自訂維度和量度的細節。

| 量度 | 說明 | 資料檢視設定 |
| --- | --- | --- |
| 退回數 | 退回的訊息數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>元件類型：量度<br>包含排除值：如果符合任何條件<br>等於：`bounce`<br>等於：`denylist` |
| 錯誤 | 出錯的訊息數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>元件類型：量度<br>包含排除值：等於 `error` |
| 排除 | 排除的訊息數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>元件類型：量度<br>包含排除值：等於 `exclude` |
| 取消訂閱數 | 取消訂閱的計數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>元件類型：量度<br>包含排除值：等於 `unsubscribe` |
| 點擊數 | 訊息內的點擊計數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>元件類型：量度<br>包含排除值：等於 `click` |
| 開啟數 | 開啟的訊息數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>元件類型：量度<br>包含排除值：等於 `open` |
| 垃圾郵件投訴數 | 垃圾郵件投訴計數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType`：<br>元件類型：量度<br>包含排除值：等於 `spam_complaint` |
| 已成功傳送的訊息數 | 已成功傳送的訊息數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus`：<br>元件類型：量度<br>包含排除值：等於 `sent` |
| 同步失敗數 | 同步失敗的訊息總數 | 搭配以下設定使用結構描述字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category`：<br>元件類型：量度<br>包含排除值：等於 `sync` |

{style=&quot;table-layout:auto&quot;}

## 使用 Journey Optimizer 量度設定計算量度

為 Journey Optimizer 資料集設定所需的維度和量度後，您也可以設定[計算量度](/help/components/calc-metrics/calc-metr-overview.md)以取得有關該資料的其他見解。 計算量度是根據上面在資料檢視管理器中建立的量度。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 傳送的訊息總數 | 傳送的訊息總數，無論成功還是失敗 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer 與 Customer Journey Analytics 之間的報告差異

不同產品之間的資料差異通常是在 1-2%。 不同產品之間的較大差異可能歸因於以下因素：

* 不同產品的傳入資料處理時間可能略有不同，尤其是在過去兩小時內收集的資料。 使用不包括今天的日期範圍來減少與處理時間有關的差異。
* 計算量度「傳送的訊息總數」不包含「重試」量度。 資料集中不包含「重試」量度的資料，這表明 CJA 報告中的數字可能低於 AJO 報告中的數字。 不過，重試資料會融合到「已成功傳送的訊息數」或「退回數」量度中。 使用一週或更早的日期範圍來減少不同產品之間「傳送的訊息總數」量度的差異。
