---
title: 整合 Adobe Journey Optimizer 決策管理
description: 導入 Adobe Journey Optimizer 決策管理產生的資料，並使用 Customer Journey Analytics 中的 Analysis Workspace 進行分析。
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 100%

---

# 整合決策管理


Adobe Journey Optimizer [決策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html)透過集中行銷產品建議資料庫和決策引擎來輕鬆實現個人化；該決策引擎會將規則和限制套用至 Adobe Experience Platform 建立的豐富即時輪廓，協助您在適當的時間向客戶傳送適合的產品建議。

決策管理是 Adobe Journey Optimizer 的一部分，且與其整合。它也可以在 Adobe Journey Optimizer 定義的歷程和行銷活動以外獨立使用，從而運用其豐富的 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html) 支援。

您可以匯入決策管理產生的資料，以透過以下步驟在 Customer Journey Analytics 中執行進階分析：

## 將資料從決策管理傳送到 Adobe Experience Platform

Adobe Experience Platform 會當作中央資料來源，以及決策管理與 Customer Journey Analytics 之間的連結。來自決策管理的資料是在 Experience Platform 中&#x200B;**自動**&#x200B;收集，或作為&#x200B;**明確傳送體驗事件** (例如曝光次數或點擊次數) 來收集。請參閱[開始使用資料收集](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html)以了解更多詳細資料。

## 建立連線

決策管理資料導入 Adobe Experience Platform 後，您就可以根據決策管理資料集建立[連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant)。您也可以將決策管理資料集新增到現有連線。

選取並設定以下資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| ODE 決策事件 - _沙箱_&#x200B;決策 | 事件 | 人員 ID：`IdentityMap` | 包含針對決策管理決策事件自動產生的資料。_沙箱_&#x200B;是指特定的沙箱名稱。 |
| Adobe Journey Optimizer 訊息意見回饋事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含訊息傳送事件。 |
| Adobe Journey Optimizer 電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含電子郵件追蹤事件。 |
| Adobe Journey Optimizer 推播追蹤體驗事件資料集 | 事件 | 人員 ID：`IdentityMap` | 包含推播追蹤事件。 |
| Adobe Journey Optimizer 實體資料集 | 查詢 | 索引鍵：`_id`<br>相符的索引鍵：`_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將 Journey 和 Campaign 中繼資料與所有 Adobe Journey Optimizer 事件資料建立關聯的分類。 |

{style="table-layout:auto"}

## 建立資料視圖

建立連線後，您可以建立一或多個[資料視圖](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html)，以設定可在 Customer Journey Analytics 中使用的所需維度和量度。

>[!NOTE]
>
>Adobe Journey Optimizer 和 Customer Journey Analytics 之間的資料差異通常小於 1 到 2%。過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。

### 設定維度

您可以在資料視圖中建立以下維度，以實現與決策管理中類似維度的近似同位。請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關維度自訂選項的詳細資料。

| 維度 | 結構描述元素 | 元件設定 |
| --- | --- | --- |
| 活動名稱 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 元件類型：維度 |
| 容器識別碼 | `_experience.decisioning.containerID` | 元件類型：維度 |
| 關聯識別碼 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 元件類型：維度 |
| 決策選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 元件類型：維度 |
| 備援決策選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 元件類型：維度 |
| 位置名稱 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 元件類型：維度 |

{style="table-layout:auto"}


### 設定度量

您可以在資料視圖中建立以下量度，以實現與決策管理中類似量度的近似同位。請參閱資料視圖管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 結構描述元素 | 元件設定 |
| --- | --- | --- | --- |
| 事件類型 (重新命名以參照特定事件，例如 `Feedback` (用於 `message.feedback`)) [ 1] | 特定事件類型的數量 | `eventType` | 元件類型：量度<br/>**[!UICONTROL 設定包含排除值&#x200B;]**：開啟<br/>**[!UICONTROL 符合]**：[!UICONTROL 如果所有條件都滿足]<br/>**[!UICONTROL 標準&#x200B;]**：**[!UICONTROL &#x200B;等於&#x200B;]**`message.feedback` |
| 決策選項分數 | 單一範圍情境中決策選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 元件類型：量度 |
| 備援決策選項分數 | 單一範圍情境中備援決策選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 元件類型：量度 |
| 產品建議關閉 | 在沒有任何其他直接互動的情況下關閉或拒絕的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.dismiss` | 元件類型：量度 |
| 產品建議顯示 | 對輪廓顯示的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件類型：量度 |
| 產品建議互動 | 與輪廓互動的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 元件類型：量度 |
| 產品建議傳送 | 對輪廓傳送的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 元件類型：量度 |
| 產品建議觸發 | 選擇透過用戶端 SDK 顯示的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件類型：量度 |
| 產品建議取消訂閱 | 輪廓要求未來不要顯示的產品建議數量。 | `_experience.decisioning.`<br/>`propositionEventType.unsubscribe` | 元件類型：量度 |

{style="table-layout:auto"}

[1] 您可以為各種可用事件類型定義多個量度。請參閱[包含排除值元件設定](/help/data-views/component-settings/include-exclude-values.md)以了解更多資訊。
