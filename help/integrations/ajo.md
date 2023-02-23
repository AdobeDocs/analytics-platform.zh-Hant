---
title: 將Adobe Journey Optimizer(AJO)與Customer Journey Analytics(CJA)整合
description: 引進 AJO 產生的資料並在 CJA 內使用 Analysis Workspace 加以分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 9aed4e724c564272071b96c037f4eb0e82572e6f
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 53%

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

>!![NOTE]
AJO和CJA之間的資料差異通常不到1-2%。 過去兩小時內收集的資料可能會出現較大差異。 使用不包括今天的日期範圍來減少與處理時間有關的差異。

### 在資料檢視中設定維度

您可以在資料檢視中建立下列維度，以使用Journey Optimizer中類似的維度來達成近似對等。 請參閱 [元件設定](/help/data-views/component-settings/overview.md) 在「資料檢視管理員」中，以取得有關維度自訂選項的詳細資訊。

| 維度 | 綱要元素 | 元件設定 |
| --- | --- | --- |
| 歷程名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 元件類型：Dimension |
| 歷程名稱和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 元件類型：Dimension |
| 歷程節點名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 元件類型：Dimension |
| 歷程節點類型 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 元件類型：Dimension |
| 行銷活動名稱 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 元件類型：Dimension |
| 管道 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 元件類型：Dimension |
| 推播標題 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 元件類型：Dimension |
| 電子郵件主旨 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 元件類型：Dimension |
| 連結標籤 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 元件類型：Dimension |
| 實驗名稱 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 元件類型：Dimension<br>內容標籤：實驗實驗 |
| 處理名稱 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 元件類型：Dimension<br>內容標籤：實驗變體 |
| 電子郵件傳送失敗原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 元件類型：Dimension |
| 電子郵件傳送排除原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 元件類型：Dimension |

{style=&quot;table-layout:auto&quot;}

### 在資料檢視中設定量度

您可以在資料檢視中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。 請參閱 [元件設定](/help/data-views/component-settings/overview.md) 在「資料檢視管理器」中，以取得量度自訂選項的詳細資訊。

| 量度 | 說明 | 綱要元素 | 元件設定 |
| --- | --- | --- | --- |
| 退回數 | 退回的訊息數，包括傳送後的立即退回和退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度<br>包含排除值：如果符合任何條件<br>等於： `bounce`，等於： `denylist` |
| 傳送後跳出 | 有些電子郵件服務會報告傳送的電子郵件，稍後再退信。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 元件類型：量度<br>包含排除值：等於 `async` |
| 電子郵件點按次數 | 訊息內的點擊計數. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：量度<br>包含排除值：等於 `click` |
| 電子郵件開啟 | 開啟的訊息數. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：量度<br>包含排除值：等於 `open` |
| 錯誤 | 出錯的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度<br>包含排除值：等於 `error` |
| 排除 | 排除的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度<br>包含排除值：等於 `exclude` |
| 傳送數 | 電子郵件提供者接受的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度<br>包含排除值：等於 `sent` |
| 垃圾郵件投訴 | 垃圾郵件投訴計數. | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：量度<br>包含排除值：等於 `spam_complaint` |
| 取消訂閱數 | 取消訂閱的計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：量度<br>包含排除值：等於 `unsubscribe` |

{style=&quot;table-layout:auto&quot;}

### 在Analysis Workspace中設定計算量度

為 Journey Optimizer 資料集設定所需的維度和量度後，您也可以設定[計算量度](/help/components/calc-metrics/calc-metr-overview.md)以取得有關該資料的其他見解。 計算量度是根據上面在資料檢視管理器中建立的量度。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 已傳送的訊息 | 已傳送的訊息總數。 包括成功或失敗的消息。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 傳遞的訊息 | 傳送給客戶的電子郵件數量。 | `[Sends] - [Bounces After Delivery]` |

{style=&quot;table-layout:auto&quot;}
