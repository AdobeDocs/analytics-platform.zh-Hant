---
title: 整合 Adobe Journey Optimizer
description: 導入 Adobe Journey Optimizer 產生的資料，並使用 Customer Journey Analytics 中的 Analysis Workspace 進行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 9149a072dc8af3fac0d5272fe84baabca7fb6058
workflow-type: ht
source-wordcount: '3514'
ht-degree: 100%

---

# 整合 Journey Optimizer

[Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/get-started/get-started) 可幫助您提供連線、情境式和個人化的體驗。 它有助於讓您的客戶了解其客戶歷程中的下一步。

您可以設定 Journey Optimizer 產生的資料，用於在 Customer Journey Analytics 中執行進階分析。您可以自動設定此整合。如果需要，您可以對連線或資料視圖中可用的資料集、維度或量度進行額外的手動自訂。

## 自動設定 Journey Optimizer 整合

Journey Optimizer 支援使用 Customer Journey Analytics 作為報告引擎。請參閱 Journey Optimizer 文件中的[開始使用新報告介面](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja)。

當您為 Journey Optimizer 啟用 Customer Journey Analytics 報告時，系統會自動為特定沙箱建立[連線](/help/connections/overview.md)和[資料視圖](/help/data-views/data-views.md)。

### 連線

連線的名稱為 **[!UICONTROL AJO 啟用的連線 (*沙箱名稱*)]**，並具有以下現成可用的設定和資料集值：

| **連線設定** | 值 |
|---|---| 
| [!UICONTROL 連線名稱] | `AJO Enabled Connection (`_`sandbox name`_`)` |
| [!UICONTROL 連線說明] | [!UICONTROL *在這裡說明您的連線*] |
| [!UICONTROL 標記] | [!UICONTROL *選取標記*] |


| **資料設定** | 值 |
|---|---| 
| [!UICONTROL 啟用滾動資料時間窗口] | 啟用。[!UICONTROL 選取的月數] `13`。 |
| [!UICONTROL 沙箱] | [!UICONTROL *沙箱名稱*] (已停用；您無法修改此設定)。 |
| [!UICONTROL 每日事件平均數量] | 小於 100 萬 (已停用；您無法修改此設定)。 |


| 資料集名稱 | 結構描述 | 資料集類型 | 資料來源類型 | 人員 ID | 金鑰 | 比對索引鍵 | 匯入新資料 | 回填資料 |
|---|---|---|---|---|---|---|---|---|
| [!UICONTROL AJO 實體資料集] | [!UICONTROL AJO 實體記錄結構描述] | [!UICONTROL 查詢] | [!UICONTROL 其他] | - | ` _id` | `_experience. decisioning. propositions. scopeDetails. correlationID` | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
| [!UICONTROL 歷程步驟事件] | [!UICONTROL Journey Orchestration 的歷程步驟事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL  IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
| [!UICONTROL AJO 電子郵件追蹤體驗事件資料集] | [!UICONTROL AJO 電子郵件追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
| [!UICONTROL AJO 訊息意見反應事件資料集] | [!UICONTROL AJO 訊息意見反應事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
| [!UICONTROL AJO 推播追蹤體驗事件資料集] | [!UICONTROL AJO 推播追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |


### 資料視圖

資料視圖的名稱為 **AJO 啟用的資料視圖 (*沙箱名稱*)**。

- 在&#x200B;**[!UICONTROL 設定]**&#x200B;標籤中，以下值是現成的。

  | 設定 | 值 |
  |---|---|
  | [!UICONTROL 連線] | AJO 啟用的連線 (*沙箱名稱*) |
  | [!UICONTROL 名稱] | `AJO Enabled Data View (`_`sandbox name`_`)` |
  | [!UICONTROL 外部 ID] | `AJO_Enabled_Data_View__`_`sandbox_name`_`_` (衍生自名稱) |
  | [!UICONTROL 說明] | `undefined` |

  {style="table-layout:fixed"}

  | 相容性 | 值 |
  |---|---|
  | [!UICONTROL 設為 Adobe Journey Optimizer 中的預設資料視圖] | 已啟用 (預設)。<br/><br/>此設定選項可讓您指定與 Journey Optimizer 搭配使用的資料視圖，以免除手動設定的麻煩。如需有關如何啟用此設定選項 (如果未依預設啟用) 的資訊，請參閱「[建立或編輯資料視圖](/help/data-views/create-dataview.md)」中的「[相容性](/help/data-views/create-dataview.md#compatibility)」部分。<br/><br/>當您停用該選項時，將出現一個對話框，提示您是否要繼續變更預設資料視圖。如果選取&#x200B;**[!UICONTROL 繼續]**，您需要選取另一個資料視圖作為預設資料視圖。選取&#x200B;**[!UICONTROL 確認]**&#x200B;以確認您的選擇。選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消變更預設資料視圖。 |

  | 容器 | 值 |
  |---|---|
  | [!UICONTROL 人員容器名稱] | `Person` |
  | [!UICONTROL 工作階段容器名稱] | `Session` |
  | [!UICONTROL 事件容器名稱] | `Event` |

  | 行事曆 | 值 |
  |---|---|
  | [!UICONTROL 時區] | 與您所在位置相符的時區 |
  | [!UICONTROL 行事曆類型] | 公曆 |
  | [!UICONTROL 一年的第一個月] | 1 月 |
  | [!UICONTROL 一週的第一天] | 星期日 |


- 在&#x200B;**元件**&#x200B;索引標籤中：
   - 名稱後面附加有 [!UICONTROL (AJO)] 的所有量度和維度都會自動新增為此自動設定的一部分。
   - 一些自動新增的量度和維度是以衍生欄位為基礎。這些衍生欄位是專門為此整合而建立的。例如，量度[!UICONTROL 「登陸頁面點按」(AJO)] 是以[!UICONTROL 「登陸頁面點按」]衍生欄位為基礎。
   - 某些量度或維度具有額外的設定。例如，[!UICONTROL 「垃圾郵件投訴計數」(AJO)] 有套用「[!UICONTROL 格式]」和「[!UICONTROL 包含排除值]」設定。
   - 所有自動新增的量度或維度都有名稱為 `:`*`name_of_metric_or_dimension`*的內容標籤。例如，[!UICONTROL 「登陸頁面點按」(AJO)] 量度具有內容標籤 `:Landing page clicks (AJO)`。

- 在&#x200B;**[!UICONTROL 設定]**&#x200B;標籤中，未套用任何特定設定值

>[!IMPORTANT]
>
>修改連線和資料視圖的任何自動設定值確實會影響依賴並使用自動設定之 Customer Journey Analytics 整合的 Journey Optimizer 報告。


## 手動設定與 Journey Optimizer 搭配使用的資料視圖

以下幾節說明如何手動使用 Journey Optimizer 產生的資料，用於在 Customer Journey Analytics 中執行進階分析。只有當「[自動設定選項](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)」無法滿足您的需求時，才需要進行這項手動設定。

### 將 Journey Optimizer 中的資料傳送到 Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及 Journey Optimizer 與 Customer Journey Analytics 之間的連結。請參閱 Journey Optimizer 使用手冊中的[開始使用資料集](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)，以取得如何將 Journey Optimizer 資料當作資料集傳送給 Experience Platform 的相關步驟。

### 建立連線

將 Journey Optimizer 資料導入 Adobe Experience Platform 後，您就可以根據 Journey Optimizer 資料集來[建立連線](/help/connections/create-connection.md)。您也可以將 Journey Optimizer 資料集新增到現有的連線中。

選取並設定以下資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| AJO 訊息意見反應事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含訊息傳送事件，例如「[!UICONTROL 傳送數]」和「[!UICONTROL 退回數]」。 |
| AJO 電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含電子郵件追蹤事件，例如「[!UICONTROL 開啟數]」、「[!UICONTROL 點擊數]」和「[!UICONTROL 取消訂閱數]」。 |
| AJO 推播追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含推播追蹤事件，例如「[!UICONTROL 應用程式啟動數]」。 |
| 歷程步驟事件 | 事件 | 人員 ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含顯示哪個輪廓參與過歷程各個節點的事件。 |
| AJO 實體資料集 | 查詢 | 索引鍵：`_id`<br>相符的索引鍵：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將 Journey 和 Campaign 中繼資料與所有 Journey Optimizer 事件資料建立關聯的分類。 |

{style="table-layout:auto"}


### 設定資料視圖

在建立連線後，您可以建立一個或多個[資料視圖](/help/data-views/create-dataview.md)來設定 Customer Journey Analytics 中可用的所需維度和量度。

>[!NOTE]
>
>Journey Optimizer 和 Customer Journey Analytics 之間的資料差異通常小於 1 到 2%。過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。


#### 設定維度

您可以在資料視圖中建立以下維度，以實現與 Journey Optimizer 中類似維度的近似同位。請參閱資料視圖管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得維度自訂選項的詳細資料。

| 維度 | 說明 | 資料集 | 結構描述元素 | 元件設定 |
| --- | --- | --- | --- | --- |
| 動作執行錯誤 (AJO) | 阻止歷程執行階段執行動作的錯誤條件。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.actionExecutionError ` | 元件類型：維度 |
| 動作標籤 (AJO) | 客戶為與一般使用者互動的元素所產生的顯示名稱。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionAction.label` | 元件類型：維度 |
| 批次 ID (AJO) | GUID 在為排程的歷程或行銷活動動作調用每個新批次執行個體時建立。例如，如果排程的歷程或行銷活動動作在上午 8 點和 10 點執行，則會有兩個單獨且不同的 batchInstanceID。 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | ` _experience.customerJourneyManagement.`<br/>`messageExecution.batchInstanceID` | 元件類型：維度 |
| 批次執行個體時間戳記 (AJO) | 批次執行個體的時間戳記。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：維度 (衍生欄位) |
| 行銷活動 ID (AJO) | 行銷活動的 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.campaignID` | 元件類型：維度 |
| 行銷活動名稱 (AJO) | 行銷活動的名稱。 | AJO 實體資料集 | `_experience.customerJourneyManagement.entities.`<br/>`campaign.name` | 元件類型：維度 |
| 行銷活動版本 ID (AJO) | 行銷活動的版本 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.campaign.campaignVersionID` | 元件類型：維度 |
| 管道 (AJO) | 應和此資料相關聯的管道。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.channel._id` | 元件類型：維度 |
| 關聯 ID (AJO) | 關聯 ID。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.propositions.`<br/>`scopeDetails.correlationID` | 元件類型：維度 |
| 決定原則 ID (AJO) | 決定此提議中包含哪些項目時所使用的決定原則的 ID。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：維度 (衍生欄位) |
| 電子郵件收件者網域 (AJO) | 電子郵件地址的網域 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`emailChannelContext.address` | 元件類型：維度 |
| 電子郵件主旨 (AJO) | 電子郵件主旨，非個人化 | AJO 實體資料集 | `_experience.customerJourneyManagement.entities.`<br/>`channelDetails.email.subject` | 元件類型：維度 |
| 事件 ID (AJO) | 時間系列事件的唯一識別碼。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_id` | 元件類型：維度 (衍生欄位) |
| 退出條件 ID (AJO) | 用於確定歷程是否應退出的退出條件 ID。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaID` | 元件類型：維度 |
| 退出條件名稱 (AJO) | 退出條件的名稱。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.exitCriteriaName` | 元件類型：維度 |
| 實驗 ID (AJO) | 實驗的 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 元件類型：維度 |
| 實驗名稱 (AJO) | 實驗的名稱。 | AJO 實體資料集 | `_experience.customerJourneyManagement.entities.`<br/>`experiment.experimentName` | 元件類型：維度內容標籤：實驗 |
| 擷取錯誤 (AJO) | 阻止歷程執行階段執行擷取的錯誤條件。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.fetchError` | 元件類型：維度 |
| 傳送時間是否已最佳化 (AJO) | 訊息執行的傳送時間是否已最佳化 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isSendTimeOptimized` | 元件類型：維度 |
| 是測試歷程 (AJO) | 事件是否為測試歷程執行的一部分 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.inTest` | 元件類型：維度 |
| 是測試訊息 (AJO) | 訊息是否作為測試執行傳送 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageProfile.isTestExecution` | 元件類型：維度 |
| 項目 ID (AJO) | 項目的 ID。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositions.items.id` | 元件類型：維度 |
| 項目名稱 (AJO) | 項目的名稱 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositions.items.name` | 元件類型：維度 |
| 歷程動作 ID | 歷程動作 ID，為該 ID 觸發 MessageExecution。 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageExecution.journeyActionID` | 元件類型：維度 |
| 歷程動作節點名稱 (AJO) | 歷程的動作節點名稱。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集、AJO 實體資料集 | 衍生欄位 | 元件類型：維度 (衍生欄位) |
| 歷程事件節點名稱 (AJO) | 每當歷程中發生區段或外部事件時，都會設定此值。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集、AJO 實體資料集 | 衍生欄位 | 元件類型：維度 (衍生欄位) |
| 歷程 ID (AJO) | 歷程的 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyID` | 元件類型：維度 |
| 歷程名稱 (AJO) | 歷程的名稱。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyName` | 元件類型：維度 |
| 歷程名稱和版本 (AJO) | 歷程的名稱和版本。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNameAndVersion` | 元件類型：維度 |
| 歷程版本 ID (AJO) | 歷程的版本 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.entities.`<br/>`journey.journeyVersionID` | 元件類型：維度 |
| 登陸頁面 ID (AJO) | 登陸頁面的唯一識別碼。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.landingpage.landingPageID` | 元件類型：維度 |
| 登陸頁面來源 (AJO) | 登陸頁面的來源。 | AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：維度 (衍生欄位) |
| 連結 URL (AJO) | 由使用者點按的 URL。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | 元件類型：維度 |
| 訊息排除原因 (AJO) | 排除原因 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageExclusion.reason` | 元件類型：維度 |
| 訊息失敗類別 (AJO) | 失敗類別 | AJO 訊息意見反應事件資料集 | ` _experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.category` | 元件類型：維度 |
| 訊息失敗原因 (AJO) | 失敗原因 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.reason` | 元件類型：維度 |
| 訊息失敗類型 (AJO) | 失敗類型 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.type` | 元件類型：維度 |
| 訊息失敗狀態 (AJO) | 失敗狀態 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.`<br/>`messageFailure.status` | 元件類型：維度 |
| 訊息 ID (AJO) | 應和此資料相關聯的訊息 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.messageID` | 元件類型：維度 |
| 訊息重試 (AJO) | 重試次數 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.retryCount` | 元件類型：維度 |
| 節點 ID (AJO) | 歷程節點的節點 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeID` | 元件類型：維度 |
| 節點名稱 (AJO) | 歷程節點的節點名稱。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeName` | 元件類型：維度 |
| 節點類型 (AJO) | 歷程節點的節點類型。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.journey.journeyNodeID` | 元件類型：維度 |
| 作業系統 (AJO) | 作業系統的名稱。 | AJO 推播追蹤體驗事件資料集 | `environment.operatingSystem` | 元件類型：維度 |
| 作業系統版本 (AJO) | 作業系統的版本。 | AJO 推播追蹤體驗事件資料集 | environment.operatingSystemVersion | 元件類型：維度 |
| 推播平台 (AJO) | 推播提供者服務，例如 apns 或 fcm。 | AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`pushChannelContext.platform` | 元件類型：維度 |
| 推播標題 (AJO) | 推播標題，非個人化。 | AJO 實體資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`entities.channelDetails.push.title | Component type: Dimension` |
| 拒絕同意原則 (AJO) | 對應的拒絕同意原則的名稱。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.consent.rejectedPolicies.name` | 元件類型：維度 |
| 簡訊傳入訊息 (AJO) | 簡訊傳入回覆，例如停止、開始、訂閱等 | AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | 元件類型：維度 |
| 簡訊類型 (AJO) | 簡訊提供者，例如傳入、傳入回覆或傳送。 | AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | ` _experience.customerJourneyManagement.`<br/>`smsChannelContext.messageType` | 元件類型：維度 |
| 簡訊提供者 (AJO) | 簡訊提供者，例如 sinch 或 twilio。 | AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.messageType` | 元件類型：維度 |
| 選擇類型 (AJO) | 顯示訊息的管道表面。 | 歷程步驟事件、AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.decisioning.propositions.`<br/>`items.itemSelection.`<br/>`selectionDetail.selectionType` | 元件類型：維度 |
| 訂閱清單 ID (AJO) | 訂閱清單的唯一識別碼。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.subscription.`<br/>` subscriptionListID` | 元件類型：維度 |
| 表面 (AJO) |  | 歷程步驟事件、AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 推播追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositions.scope` | 元件類型：維度 |
| 處理 ID (AJO) | 實驗的選定處理的 ID。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.treatmentID` | 元件類型：維度 |
| 處理名稱 (AJO) | 實驗的選定處理的名稱。 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.treatmentName` | 元件類型：維度 |
| URL ID (AJO) | 使用者點按的 URL 的唯一識別碼。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.urlID` | 元件類型：維度 |
| URL 標籤 (AJO) | URL 的人類易記標籤。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.label` | 元件類型：維度 |

{style="table-layout:auto"}

#### 設定度量

您可以在資料視圖中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。請參閱資料視圖管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 資料集 | 結構描述元素 | 元件設定 |
| --- | --- | --- | --- | --- |
| 應用程式安裝次數 (AJO) | 應用程式安裝次數 | AJO 推播追蹤體驗事件資料集 | `application.installs.value` | 元件類型：量度 |
| 應用程式啟動次數 (AJO) | 行動應用程式啟動的次數 | AJO 推播追蹤體驗事件資料集 | `application.launches.value` | 元件類型：量度 |
| 傳出管道的退回 (AJO) | 跨傳出管道退回的訊息總數 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度 |
| 點按 (AJO) | 跨所有管道的點按總數 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 後備產品建議的計數 (AJO) | 後備產品建議的計數。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.propositions.items.`<br/>`itemSelection.selectionDetail.selectionType` | 元件類型：量度 |
| 產品建議的計數 (AJO) | 產品建議的計數。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | ` _experience.decisioning.`<br/>`propositions.items.id` | 元件類型：量度 |
| 重複資料刪除量度 (AJO) | 重複資料刪除量度 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_id` | 元件類型：量度 |
| 已傳遞 (AJO) | 已傳遞的訊息總數。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 已關閉 (AJO) | 每次 Adobe SDK 關閉應用程式內訊息時都會進行計數，無論一般使用者選擇使用哪種動作來關閉它。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 元件類型：量度 |
| 展示次數 (AJO) | 此計數會顯示 AJO 訊息數。這包括電子郵件開啟次數、網頁展示次數和應用程式內展示次數。行動平台不會報告簡訊和推播訊息展示次數，因此不計算在內。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 電子郵件追蹤體驗事件資料集、AJO 訊息意見反應事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 電子郵件開啟次數 (AJO) | 電子郵件開啟總數 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |
| 傳入點按次數 (AJO) | 跨傳入管道的點按總數 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 元件類型：量度 |
| 傳入解除次數 (AJO) | 跨傳入管道的關閉總數 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 元件類型：量度 |
| 傳入曝光 (AJO) | 跨傳入管道的曝光總數 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件類型：量度 |
| 歷程結束 (AJO) | 如果目前步驟會結束歷程執行個體，則為 True。該特定輪廓歷程的最後一個步驟已成功執行。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 元件類型：量度 |
| 歷程進入 (AJO) | 如果步驟事件是輪廓的歷程進入事件，則為真。 | 歷程步驟事件 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 歷程退出 (AJO) | 如果目前步驟會結束歷程執行個體，則為 True。該特定輪廓歷程的最後一個步驟已成功執行。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.instanceEnded` | 元件類型：量度 |
| 歷程失敗 (AJO) | 給予已完成執行之步驟的目前狀態。可能的值：`Transitions` (下一個步驟將在事件轉變時發生)、`EndStep` (此歷程執行個體中的最後步驟已執行)、`Error` (此步驟遇到錯誤條件，並結束目前歷程執行個體)、`TimedOut` (目前步驟因擷取或動作逾時而結束)。 | 歷程步驟事件 | `_experience.journeyOrchestration.`<br/>`stepEvents.stepStatus` | 元件類型：量度 |
| 登陸頁面點按 (AJO) | 登陸頁面的點按總數。 | AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 登陸頁面轉換 (AJO) | 登陸頁面的轉換總數。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |
| 登陸頁面檢視 (AJO) | 登陸頁面的檢視總數。 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |
| 節點進入 (AJO) | 如果步驟事件是輪廓的節點進入事件，則為真。 | 歷程步驟事件 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 傳出點按次數 (AJO) | 跨傳出管道的點按總數 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |
| 傳出錯誤 (AJO) | 跨傳出管道出現錯誤的訊息總數 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度 |
| 傳出排除 (AJO) | 跨傳出管道的排除事件總數 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度 |
| 傳出傳送次數 (AJO) | 跨傳出管道傳送的訊息總數 | AJO 訊息意見反應事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageDeliveryfeedback.feedbackStatus` | 元件類型：量度 |
| 推播自訂動作 (AJO) | 推播互動中的自訂動作總數。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `eventType` | 元件類型：量度 |
| 推播互動次數 (AJO) | 因直接推播訊息互動而導致行動應用程式啟動的次數 | AJO 推播追蹤體驗事件資料集 | `application.launches.value` | 元件類型：量度 |
| 傳送 (AJO) | 跨所有管道傳送的訊息總數 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 簡訊傳入訊息 (AJO) | 簡訊傳入回覆。例如停止、啟動、訂閱等。 | AJO 推播追蹤體驗事件資料集、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`smsChannelContext.inboundMessage` | 元件類型：量度 |
| 垃圾訊息申訴 (AJO) | 垃圾訊息投訴總數 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |
| 訂閱清單新增 (AJO) | 新增到訂閱清單的總數。 | AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 訂閱清單移除 (AJO) | 從訂閱清單中移除的總數。 | AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 已鎖定 (AJO) | 這會計算針對某人展示某個提議的次數。這是考慮向某人展示某個提議的次數。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | 衍生欄位 | 元件類型：量度 (衍生欄位) |
| 已觸發 (AJO) | 提議已被選擇由 Adobe SDK 顯示。其他因素可能會阻止其實際顯示。 | AJO 推播追蹤體驗事件資料集、歷程步驟事件、AJO 訊息意見反應事件資料集、AJO 電子郵件追蹤體驗事件資料集 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件類型：量度 |
| 實驗中的不重複訪客 (AJO) | 實驗中的不重複訪客 | AJO 實體資料集 | `_experience.customerJourneyManagement.`<br/>`entities.experiment.experimentId` | 元件類型：量度 |
| 取消訂閱 (AJO) | 取消訂閱總數 | AJO 電子郵件追蹤體驗事件資料集 | `_experience.customerJourneyManagement.`<br/>`messageInteraction.interactionType` | 元件類型：量度 |

{style="table-layout:auto"}
