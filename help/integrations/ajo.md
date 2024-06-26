---
title: 將 Adobe Journey Optimizer 與 Customer Journey Analytics 整合
description: 導入 Adobe Journey Optimizer 產生的資料，並使用 Customer Journey Analytics 中的 Analysis Workspace 進行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 529dd2ed2af60f8b417a5bf7d728a201dad70218
workflow-type: tm+mt
source-wordcount: '1547'
ht-degree: 54%

---

# 將Journey Optimizer與Customer Journey Analytics整合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/get-started) 可幫助您提供連線、情境式和個人化的體驗。 它有助於讓您的客戶了解其客戶歷程中的下一步。

您可以設定Journey Optimizer產生的資料，以在Customer Journey Analytics中執行進階分析。 您可以自動設定這項整合。 如有需要，您可以對連線或資料檢視中可用的資料集、維度或量度進行其他手動自訂。

## 自動設定Journey Optimizer整合

{{release-limited-testing-section}}

Journey Optimizer支援使用Customer Journey Analytics做為報表引擎。 另請參閱 [開始使用新的報告介面](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja) (位於Journey Optimizer檔案中)。

當您啟用Journey Optimizer的Customer Journey Analytics報表功能後， [連線](/help/connections/overview.md) 和 [資料檢視](/help/data-views/data-views.md) 會針對特定沙箱建立。

### 連線

連線的名稱為 **[!UICONTROL 啟用AJO的連線(*沙箱名稱*)]** 和擁有下列立即可用的設定和資料集值：

| **連線設定** | 值 |
|---|---| 
| [!UICONTROL 連線名稱] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 連線說明] | [!UICONTROL *在這裡說明您的連線*] |
| [!UICONTROL 標記] | [!UICONTROL *選取標籤*] |


| **資料設定** | 值 |
|---|---| 
| [!UICONTROL 啟用滾動資料時間窗口] | 已啟用。 [!UICONTROL 選取的月數] `13`. |
| [!UICONTROL 沙箱] | [!UICONTROL *沙箱的名稱*] （已停用；您無法修改此設定）。 |
| [!UICONTROL 每日事件平均數量] | 少於100萬（已停用；您無法修改此設定）。 |


| 資料集名稱 | 綱要 | 資料集類型 | 資料來源類型 | 人員Id | 金鑰 | 比對索引鍵 | 匯入新資料 | 回填資料 |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO實體資料集] | [!UICONTROL AJO實體記錄結構描述] | [!UICONTROL 查詢] | [!UICONTROL 其他] | - | ` _id` | `_experience.decisioning.`<br/>`propositions.scopeDetails.`<br/>`correlationID` | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |
| [!UICONTROL 歷程步驟事件] | [!UICONTROL Journey Orchestration的歷程步驟事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |
| [!UICONTROL AJO電子郵件追蹤體驗事件資料集] | [!UICONTROL AJO電子郵件追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |
| [!UICONTROL AJO電子郵件追蹤體驗事件資料集] | [!UICONTROL AJO電子郵件追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |
| [!UICONTROL AJO訊息回饋事件資料集] | [!UICONTROL AJO訊息回饋事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |
| [!UICONTROL AJO推播追蹤體驗事件資料集] | [!UICONTROL AJO推播追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg) 開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg) 關閉 |


### 資料檢視

資料檢視具有名稱 **AJO啟用資料檢視(*沙箱名稱*)**.

- 在 **[!UICONTROL 設定]** 索引標籤中，下列值是現成可設定的。

  | 設定 | 值 |
  |---|---|
  | [!UICONTROL 連線] | 啟用AJO的連線(*沙箱名稱*) |
  | [!UICONTROL 名稱] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 外部 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` （衍生自名稱） |
  | [!UICONTROL 說明] | `undefined` |

  {style="table-layout:fixed"}

  | 相容性 | 值 |
  |---|---|
  | [!UICONTROL 設為 Adobe Journey Optimizer 中的預設資料視圖] | 已啟用（預設）。<br/><br/>此設定選項可讓您指定要與Journey Optimizer搭配使用的資料檢視，而不需要手動設定。 如需如何啟用此組態選項（如果預設尚未啟用）的詳細資訊，請參閱 [相容性](/help/data-views/create-dataview.md#compatibility) 中的區段 [建立或編輯資料檢視](/help/data-views/create-dataview.md). <br/><br/>當您停用選項時，對話方塊會提示您是否要繼續變更預設資料檢視。 當您選取 **[!UICONTROL 繼續]**，您必須選取其他資料檢視作為預設資料檢視。 選取 **[!UICONTROL 確認]** 以確認您的選取。 選取 **[!UICONTROL 取消]** 以取消變更預設資料檢視。 |

  | 容器 | 值 |
  |---|---|
  | [!UICONTROL 人員容器名稱] | `Person` |
  | [!UICONTROL 工作階段容器名稱] | `Session` |
  | [!UICONTROL 事件容器名稱] | `Event` |

  | 行事曆 | 值 |
  |---|---|
  | [!UICONTROL 時區] | 符合您所在位置的時區 |
  | [!UICONTROL 行事曆型別] | 公曆 |
  | [!UICONTROL 一年的第一個月] | 1 月 |
  | [!UICONTROL 一週的第一天] | 星期日 |


- 在 **元件** 標籤：
   - 所有具備以下條件的量度和維度 **[!UICONTROL (AJO)]** 附加至其名稱的專案會自動新增為此自動設定的一部分。
   - 有些已自動新增的量度或維度是根據衍生欄位。 這些衍生欄位是專門為此整合建立的。 例如，量度登陸頁麵點按次數(AJO)是根據登陸頁麵點按次數衍生欄位。
   - 部分量度或維度有其他設定。 例如，垃圾訊息申訴(AJO)已套用格式和包含排除值設定。
   - 所有自動新增的量度和維度都有名為的內容標籤 **[!UICONTROL ：*metric_or_dimension的名稱&#x200B;*]**. 例如，[!UICONTROL 登陸頁麵點按次數(AJO)] 量度具有內容標籤 [!UICONTROL ：登陸頁麵點按次數(AJO)].

- 在 **[!UICONTROL 設定]** 索引標籤中，不會套用任何特定設定值

>[!IMPORTANT]
>
>修改連線和資料檢視的任何自動設定值，對於所依賴並使用自動設定Customer Journey Analytics整合的Journey Optimizer報表會有影響。


## 手動設定要與Journey Optimizer搭配使用的資料檢視

以下各節說明如何手動使用Journey Optimizer產生的資料，以在Customer Journey Analytics中執行進階分析。 只有當「[自動設定選項](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)」無法滿足您的需求時，才需要執行此操作。

### 從Journey Optimizer傳送資料給Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及 Journey Optimizer 與 Customer Journey Analytics 之間的連結。 另請參閱 [開始使用資料集](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/data-management/datasets/get-started-datasets) Journey Optimizer使用手冊中的，以取得如何將Journey Optimizer資料當作資料集傳送給Experience Platform的步驟。

### 在 Customer Journey Analytics 中建立連線

將 Journey Optimizer 資料導入 Adobe Experience Platform 後，您就可以根據 Journey Optimizer 資料集來[建立連線](/help/connections/create-connection.md)。您也可以將 Journey Optimizer 資料集新增到現有的連線中。

選取並設定以下資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| AJO 訊息意見回饋事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含訊息傳送事件，例如「[!UICONTROL 傳送數]」和「[!UICONTROL 退回數]」。 |
| AJO 電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含電子郵件追蹤事件，例如「[!UICONTROL 開啟數]」、「[!UICONTROL 點擊數]」和「[!UICONTROL 取消訂閱數]」。 |
| AJO 推播追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含推播追蹤事件，例如「[!UICONTROL 應用程式啟動數]」。 |
| 歷程步驟事件 | 事件 | 人員 ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含顯示哪個設定檔參與過歷程各個節點的事件。 |
| AJO 實體資料集 | 查詢 | 索引鍵：`_id`<br>相符的索引鍵：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將Journey和Campaign中繼資料與所有Journey Optimizer事件資料建立關聯的分類。 |

{style="table-layout:auto"}


### 設定資料檢視，以容納 Journey Optimizer 維度和量度

在建立連線後，您可以建立一個或多個[資料檢視](/help/data-views/create-dataview.md)來設定 Customer Journey Analytics 中可用的所需維度和量度。

>[!NOTE]
>
>Journey Optimizer和Customer Journey Analytics之間的資料差異通常少於1-2%。 過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。


#### 在資料檢視中設定維度

您可以在資料檢視中建立以下維度，以實現與 Journey Optimizer 中類似維度的近似同位。另請參閱 [元件設定](/help/data-views/component-settings/overview.md) 資料檢視管理器中，以取得維度自訂選項的詳細資訊。

| 維度 | 結構描述元素 | 元件設定 |
| --- | --- | --- |
| 歷程名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyName` | 元件類型：維度 |
| 歷程名稱和版本 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNameAndVersion` | 元件類型：維度 |
| 歷程節點名稱 | `_experience.customerJourneyManagement.`<br>`entities.journey.journeyNodeName` | 元件類型：維度 |
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
| 元素標籤 | `_experience.decisioning.propositionAction.label` | 元件類型：維度 |

{style="table-layout:auto"}

#### 在資料檢視中設定量度

您可以在資料檢視中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 結構描述元素 | 元件設定 |
| --- | --- | --- | --- |
| 退回數 | 退回的訊息數量，包括立即退回和傳送之後退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：如果任何條件滿足<br>等於：`bounce`，等於：`denylist` |
| 傳遞後退回 | 有些電子郵件服務會報告電子郵件已傳遞，然後再將其退回。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.messageFailure.category` | 元件類型：計量<br>包括排除值：等於 `async` |
| 電子郵件點擊計數 | 訊息內的點擊計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `click` |
| 電子郵件開啟次數 | 開啟的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `open` |
| 錯誤 | 發生錯誤的訊息數量。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `error` |
| 排除數 | 已排除的訊息數量。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `exclude` |
| 傳送數 | 電子郵件提供者接受的訊息數。 | `_experience.customerJourneyManagement.`<br>`messageDeliveryfeedback.feedbackStatus` | 元件類型：計量<br>包括排除值：等於 `sent` |
| 垃圾郵件投訴 | 垃圾郵件投訴計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：計量<br>包括排除值：等於 `spam_complaint` |
| 取消訂閱數 | 取消訂閱的計數。 | `_experience.customerJourneyManagement.`<br>`messageInteraction.interactionType` | 元件類型：量度<br>包括排除值：等於 `unsubscribe` |
| 邊緣傳送次數 | 邊緣網路傳送訊息至 Web 或 Mobile SDK 的次數 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.send` | |
| 傳入顯示次數 | 對使用者顯示 Web 或應用程式內訊息的次數 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.display` | |
| 傳入點擊數 | Web 或應用程式內訊息點擊的計數 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.interact` | |
| 應用程式內觸發次數 | 決策引擎建議應顯示訊息的次數。行動SDK可以覆寫決定，減少實際顯示的數量。 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.trigger` | |
| 應用程式內關閉次數 | SDL 從 UI 中移除應用程式內訊息的次數 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### 設定 Analysis Workspace 中的計算量度

為 Journey Optimizer 資料集設定所需的維度和量度後，您也可以設定[計算量度](/help/components/calc-metrics/calc-metr-overview.md)以取得有關該資料的其他見解。 計算量度是根據上面在資料檢視管理器中建立的量度。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 訊息已傳送 | 已傳送的訊息總數。包括成功或失敗的訊息。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 訊息已傳遞 | 傳遞給客戶的電子郵件數。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
