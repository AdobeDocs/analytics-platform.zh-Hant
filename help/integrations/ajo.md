---
title: 將 Adobe Journey Optimizer (AJO) 與 Customer Journey Analytics (CJA) 整合
description: 引進 AJO 產生的資料並在 CJA 內使用 Analysis Workspace 加以分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
source-git-commit: 933f3f0336c325bf0973a0379532b3e19f1c6d68
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 84%

---

# 將 Adobe Journey Optimizer 與 Customer Journey Analytics 整合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html) 可幫助您提供連線、情境式和個人化的體驗。 它有助於讓您的客戶了解其客戶歷程中的下一步。

您可以匯入 Journey Optimizer 產生的資料，以透過以下步驟在 Customer Journey Analytics 中執行進階分析：

## 將 Journey Optimizer 中的資料傳送到 Adobe Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及 Journey Optimizer 與 Customer Journey Analytics 之間的連結。 請參閱 Journey Optimizer 使用手冊中的[開始使用資料集](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html)，以取得如何將 Journey Optimizer 資料當作資料集傳送給 Platform 的相關步驟。

## 在 Customer Journey Analytics 中建立連線

Journey Optimizer資料放入Adobe Experience Platform後，您就可以 [建立連線](/help/connections/create-connection.md) 根據Journey Optimizer資料集。 或者，您可以將Journey Optimizer資料集新增至現有連線。

選取並設定下列資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| AJO訊息意見事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含訊息傳送事件，例如「[!UICONTROL 傳送]&#39;和&#39;[!UICONTROL 跳出數]&#39;。 |
| AJO電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含電子郵件追蹤事件，例如「[!UICONTROL 開啟]&#39;, &#39;[!UICONTROL 點按次數]&#39;和&#39;[!UICONTROL 取消訂閱數]&#39;。 |
| AJO推播追蹤體驗事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含推播追蹤事件，例如「[!UICONTROL 應用程式啟動]&#39;。 |
| 歷程步驟事件 | 事件 | 人員 ID: `_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含事件，顯示哪些設定檔參與歷程的每個節點。 |
| AJO實體資料集 | 查詢 | 索引鍵： `_id`<br>匹配密鑰： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將歷程和促銷活動中繼資料與所有AJO事件資料建立關聯的分類。 |

{style="table-layout:auto"}


## 設定資料檢視，以容納 Journey Optimizer 維度和量度

在建立連線後，您可以建立一個或多個[資料檢視](/help/data-views/create-dataview.md)來設定 Customer Journey Analytics 中可用的所需維度和量度。

>[!NOTE]
>
>AJO 和 CJA 之間的資料差異通常小於 1-2%。過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。


### 在資料檢視中設定維度

您可以在資料檢視中建立以下維度，以實現與 Journey Optimizer 中類似維度的近似同位。請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關維度自訂選項的詳細資料。

| 維度 | 綱要元素 | 元件設定 |
| --- | --- | --- |
| 歷程名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 元件類型：維度 |
| 歷程名稱和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 元件類型：維度 |
| 歷程節點名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 元件類型：維度 |
| 歷程節點類型 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeType` | 元件類型：維度 |
| 行銷活動名稱 | `_experience.customerJourneyManagement.`<br>`entities.campaign.name` | 元件類型：維度 |
| 管道 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.channel._id` | 元件類型：維度 |
| 推送標題 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.push.title` | 元件類型：維度 |
| 電子郵件主旨 | `_experience.customerJourneyManagement.`<br>`entities.channelDetails.email.subject` | 元件類型：維度 |
| 連結標籤 | `_experience.customerJourneyManagement.`<br>`messageInteraction.label` | 元件類型：維度 |
| 實驗名稱 | `_experience.customerJourneyManagement.`<br>`entities.experiment.experimentName` | 元件類型：維度<br>內容標籤：實驗 |
| 處理名稱 | `_experience.customerJourneyManagement.`<br>`entities.experiment.treatmentName` | 元件類型：維度<br>內容標籤：實驗變體 |
| 電子郵件傳遞失敗原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.reason` | 元件類型：維度 |
| 電子郵件傳遞排除原因 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageExclusion.reason` | 元件類型：維度 |

{style="table-layout:auto"}

### 在資料檢視中設定量度

您可以在資料檢視中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 綱要元素 | 元件設定 |
| --- | --- | --- | --- |
| 退回數 | 退回的訊息數，包括立即退回和傳遞後退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：如果任何條件滿足<br>等於：`bounce`，等於：`denylist` |
| 傳遞後退回 | 有些電子郵件服務會報告電子郵件已傳遞，然後再將其退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 元件類型：計量<br>包括排除值：等於 `async` |
| 電子郵件點擊計數 | 訊息內的點擊計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `click` |
| 電子郵件開啟次數 | 開啟的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `open` |
| 錯誤 | 出錯的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `error` |
| 排除 | 排除的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `exclude` |
| 傳送數 | 電子郵件提供者接受的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `sent` |
| 垃圾郵件申訴 | 垃圾郵件投訴計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `spam_complaint` |
| 取消訂閱數 | 取消訂閱的計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `unsubscribe` |

{style="table-layout:auto"}

### 設定 Analysis Workspace 中的計算量度

為 Journey Optimizer 資料集設定所需的維度和量度後，您也可以設定[計算量度](/help/components/calc-metrics/calc-metr-overview.md)以取得有關該資料的其他見解。 計算量度是根據上面在資料檢視管理器中建立的量度。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 訊息已傳送 | 已傳送的訊息總數。包括成功或失敗的訊息。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 訊息已傳遞 | 傳遞給客戶的電子郵件數。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
