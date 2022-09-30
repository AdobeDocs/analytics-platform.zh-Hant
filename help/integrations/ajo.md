---
title: 將Adobe Journey Optimizer與Customer Journey Analytics整合
description: 匯入AJO產生的資料，並在CJA中使用Analysis Workspace進行分析。
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---


# 將Adobe Journey Optimizer與Customer Journey Analytics整合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=zh-Hant) 可協助您提供連結、情境式和個人化的體驗。 它有助於讓客戶了解其客戶歷程的下一步。

您可以透過執行下列步驟，匯入Journey Optimizer產生的資料，以在Customer Journey Analytics中執行進階分析：

## 將資料從Journey Optimizer傳送至Adobe Experience Platform

Adobe Experience Platform是Journey Optimizer和Customer Journey Analytics之間的中央資料來源和連結。 請參閱 [開始使用資料集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) 在Journey Optimizer使用指南中，取得如何將Journey Optimizer資料傳送至Platform as a Dataset的步驟。

## 在Customer Journey Analytics中建立連線

Journey Optimizer資料放入Adobe Experience Platform後，您就可以 [建立連線](/help/connections/create-connection.md) 根據您的Journey Optimizer資料集。 選取您傳送至Platform的資料集。

## 設定資料檢視以容納Journey Optimizer維度和量度

建立連線後，您可以建立一或多個 [資料檢視](/help/data-views/create-dataview.md) 設定所需的Customer Journey Analytics和量度。

您可以在資料檢視中建立下列量度，以與Journey Optimizer中的類似量度達成近似對等。 請參閱 [元件設定](/help/data-views/component-settings/overview.md) 以取得如何自訂維度和量度的詳細資訊。

| 量度 | 說明 | 資料檢視設定 |
| --- | --- | --- |
| 跳出數 | 跳出的郵件數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` （使用下列設定）:<br>元件類型：量度<br>包含排除值：如果符合任何條件<br>等於： `bounce`<br>等於： `denylist` |
| 錯誤 | 出錯的郵件數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `error` |
| 排除 | 排除的訊息數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `exclude` |
| 取消訂閱數 | 取消訂閱的計數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `unsubscribe` |
| 點擊次數 | 訊息內的點按次數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `click` |
| 開啟數 | 已開啟的訊息數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `open` |
| 垃圾郵件投訴 | 垃圾郵件投訴的計數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageInteraction.interactionType` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `spam_complaint` |
| 已成功發送消息 | 已成功發送的消息數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `sent` |
| 同步失敗 | 無法同步的消息總數 | 使用結構字串元素 `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` （使用下列設定）:<br>元件類型：量度<br>包含排除值：等於 `sync` |

{style=&quot;table-layout:auto&quot;}

## 使用Journey Optimizer量度設定計算量度

設定好所需Journey Optimizer資料集的維度和量度後，您也可以設定 [計算量度](/help/components/calc-metrics/calc-metr-overview.md) 以取得有關該資料的其他深入分析。 這些計算量度是以上述在「資料檢視管理員」中建立的量度為基礎。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 已傳送的郵件總數 | 已傳送、成功或失敗的訊息總數 | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Journey Optimizer與Customer Journey Analytics之間的報表差異

產品之間的資料差異通常介於1-2%之間。 產品之間較大的差異可能歸因於以下原因：

* 產品之間傳入資料的處理時間可能會稍有不同，尤其是過去兩小時內收集的資料。 使用排除今天的日期範圍，減少與處理時間相關的差異。
* 計算量度「已傳送總訊息」不包含「重試」量度。 「重試」量度的資料不包含在資料集中，在CJA報表與AJO報表中顯示的數字可能較低。 不過，重試資料會聚合至「已成功傳送訊息」或「彈回數」量度。 使用一週或更舊的日期範圍，以緩解產品之間「已傳送總訊息」量度的差異。
