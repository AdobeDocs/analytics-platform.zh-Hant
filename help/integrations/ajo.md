---
title: 將 Adobe Journey Optimizer 與 Customer Journey Analytics 整合
description: 導入 Adobe Journey Optimizer 產生的資料，並使用 Customer Journey Analytics 中的 Analysis Workspace 進行分析。
exl-id: 9333ada2-b4d6-419e-9ee1-5c96f06a3bfd
feature: Experience Platform Integration
role: Admin
source-git-commit: 13c3f99dba7725553c775df4492803f759ebead5
workflow-type: ht
source-wordcount: '1541'
ht-degree: 100%

---

# 將 Journey Optimizer 與 Customer Journey Analytics 整合

[Adobe Journey Optimizer](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/get-started/get-started) 可幫助您提供連線、情境式和個人化的體驗。 它有助於讓您的客戶了解其客戶歷程中的下一步。

您可以設定 Journey Optimizer 產生的資料，用於在 Customer Journey Analytics 中執行進階分析。您可以自動設定此整合。如果需要，您可以對連線或資料視圖中可用的資料集、維度或量度進行額外的手動自訂。

## 自動設定 Journey Optimizer 整合

{{release-limited-testing-section}}

Journey Optimizer 支援使用 Customer Journey Analytics 作為報告引擎。請參閱 Journey Optimizer 文件中的[開始使用新報告介面](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/channel-report/report-gs-cja)。

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
| [!UICONTROL AJO 電子郵件追蹤體驗事件資料集] | [!UICONTROL AJO 電子郵件追蹤體驗事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
| [!UICONTROL AJO 訊息意見回饋事件資料集] | [!UICONTROL AJO 訊息意見回饋事件結構描述] | [!UICONTROL 事件] | [!UICONTROL 其他] | [!UICONTROL IdentityMap(\&lt;primary\>)] | - | - | ![狀態綠色](assets/../../connections/assets/status-green.svg)開啟 | ![狀態灰色](assets/../../connections/assets/status-gray.svg)關閉 |
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

以下幾節說明如何手動使用 Journey Optimizer 產生的資料，用於在 Customer Journey Analytics 中執行進階分析。只有當「[自動設定選項](#automatically-configure-a-customer-journey-analytics-data-view-to-be-used-with-adobe-journey-optimizer)」無法滿足您的需求時，才需要執行此操作。

### 將 Journey Optimizer 中的資料傳送到 Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及 Journey Optimizer 與 Customer Journey Analytics 之間的連結。請參閱 Journey Optimizer 使用手冊中的[開始使用資料集](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/data-management/datasets/get-started-datasets)，以取得如何將 Journey Optimizer 資料當作資料集傳送給 Experience Platform 的相關步驟。

### 在 Customer Journey Analytics 中建立連線

將 Journey Optimizer 資料導入 Adobe Experience Platform 後，您就可以根據 Journey Optimizer 資料集來[建立連線](/help/connections/create-connection.md)。您也可以將 Journey Optimizer 資料集新增到現有的連線中。

選取並設定以下資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| AJO 訊息意見回饋事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含訊息傳送事件，例如「[!UICONTROL 傳送數]」和「[!UICONTROL 退回數]」。 |
| AJO 電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含電子郵件追蹤事件，例如「[!UICONTROL 開啟數]」、「[!UICONTROL 點擊數]」和「[!UICONTROL 取消訂閱數]」。 |
| AJO 推播追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含推播追蹤事件，例如「[!UICONTROL 應用程式啟動數]」。 |
| 歷程步驟事件 | 事件 | 人員 ID：`_experience.journeyOrchestration.`<br>`stepEvents.profileID` | 包含顯示哪個設定檔參與過歷程各個節點的事件。 |
| AJO 實體資料集 | 查詢 | 索引鍵：`_id`<br>相符的索引鍵：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將 Journey 和 Campaign 中繼資料與所有 Journey Optimizer 事件資料建立關聯的分類。 |

{style="table-layout:auto"}


### 設定資料視圖，以容納 Journey Optimizer 維度和量度

在建立連線後，您可以建立一個或多個[資料視圖](/help/data-views/create-dataview.md)來設定 Customer Journey Analytics 中可用的所需維度和量度。

>[!NOTE]
>
>Journey Optimizer 和 Customer Journey Analytics 之間的資料差異通常小於 1 到 2%。過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。


#### 在資料視圖中設定維度

您可以在資料視圖中建立以下維度，以實現與 Journey Optimizer 中類似維度的近似同位。請參閱資料視圖管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得維度自訂選項的詳細資料。

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

#### 在資料視圖中設定量度

您可以在資料視圖中建立以下量度，以實現與 Journey Optimizer 中類似量度的近似同位。請參閱資料視圖管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

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
| 應用程式內觸發次數 | 決策引擎建議應顯示訊息的次數。Mobile SDK 可能會覆寫決策，使實際的顯示次數減少。 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.trigger` | |
| 應用程式內關閉次數 | SDL 從 UI 中移除應用程式內訊息的次數 | 使用結構描述字串元素 `_experience.decisioning.propositionEventType.dismiss` | |

{style="table-layout:auto"}

#### 設定 Analysis Workspace 中的計算量度

為 Journey Optimizer 資料集設定所需的維度和量度後，您也可以設定[計算量度](/help/components/calc-metrics/calc-metr-overview.md)以取得有關該資料的其他見解。 計算量度是根據上面在資料視圖管理器中建立的量度。

| 計算量度 | 說明 | 公式 |
| --- | --- | --- |
| 訊息已傳送 | 已傳送的訊息總數。包括成功或失敗的訊息。 | `[Sends] + [Bounces] - [Bounces After Delivery]` |
| 訊息已傳遞 | 傳遞給客戶的電子郵件數。 | `[Sends] - [Bounces After Delivery]` |

{style="table-layout:auto"}
