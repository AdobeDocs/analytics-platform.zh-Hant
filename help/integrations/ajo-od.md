---
title: 將Adobe Journey Optimizer決策管理與Customer Journey Analytics(CJA)整合
description: 將Adobe Journey Optimizer決策管理產生的資料帶入Customer Journey Analytics，並使用Analysis Workspace進行分析。
source-git-commit: 00a87f5f370310672ca37ab9df08350d14fc6a91
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 18%

---

# 將決策管理與Customer Journey Analytics整合


Adobe Journey Optimizer [決策管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) 透過集中的行銷優惠方案資料庫和決策引擎，將規則和限制套用至Adobe Experience Platform建立的豐富即時設定檔，協助您在適當的時間為客戶傳送正確的優惠方案，讓個人化更輕鬆。

決策管理是Adobe Journey Optimizer(AJO)的一部分，並與之整合。 它也可獨立於AJO中定義的歷程和行銷活動，使用豐富的 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 支援。

您可以匯入決策管理產生的資料，以透過下列步驟在Customer Journey Analytics(CJA)中執行進階分析：

## 將資料從Decision Management傳送至Adobe Experience Platform

Adobe Experience Platform是決策管理與Customer Journey Analytics之間的中央資料來源和連結。 決策管理中的資料會以Experience Platform **自動** 或作為 **明確傳送的體驗事件** （例如曝光數或點按次數）。 請參閱 [資料收集快速入門](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 以取得更多詳細資訊。

## 建立連線

決策管理資料放入Adobe Experience Platform後，您就可以建立 [連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant) 根據您的Decision Management資料集。 或者，您可以將Decision Management資料集新增至現有連線。

選取並設定下列資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| ODE決策事件 —  _沙箱_ 決策 | 事件 | 人員 ID: `IdentityMap` | 包含自動產生的決策管理決策事件資料。 _沙箱_ 是指特定的沙箱名稱。 |
| AJO訊息意見事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含訊息傳送事件。 |
| AJO電子郵件追蹤體驗事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含電子郵件追蹤事件。 |
| AJO推播追蹤體驗事件資料集 | 事件 | 人員 ID: `IdentityMap` | 包含推播追蹤事件。 |
| AJO實體資料集 | 查詢 | 索引鍵： `_id`<br>匹配密鑰： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將歷程和促銷活動中繼資料與所有AJO事件資料建立關聯的分類。 |

{style="table-layout:auto"}

## 建立資料檢視

建立連線後，您可以建立一或多個 [資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant) 設定CJA中可用的維度和量度。

>[!NOTE]
>
>AJO 和 CJA 之間的資料差異通常小於 1-2%。過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。

### 設定維度

您可以在資料檢視中建立下列維度，以便與Decision Management中的類似維度達成近似對等。 請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關維度自訂選項的詳細資料。

| 維度 | 綱要元素 | 元件設定 |
| --- | --- | --- |
| 活動名稱 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 元件類型：維度 |
| 容器識別碼 | `_experience.decisioning.containerID` | 元件類型：維度 |
| 關聯識別碼 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 元件類型：維度 |
| 決策選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 元件類型：維度 |
| 備援決策選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 元件類型：維度 |
| 版位名稱 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 元件類型：維度 |

{style="table-layout:auto"}


### 設定量度

您可以在資料檢視中建立下列量度，以便與Decision Management中類似的量度達成近似對等。 請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 綱要元素 | 元件設定 |
| --- | --- | --- | --- |
| 事件類型(重新命名為特定事件，例如 `Feedback` for `message.feedback`) [1] | 特定事件類型的量 | `eventType` | 元件類型：量度<br/>**[!UICONTROL 設定包含排除值&#x200B;]**:開啟<br/>**[!UICONTROL 符合]**: [!UICONTROL 如果滿足所有條件]<br/>**[!UICONTROL 條件&#x200B;]**:**[!UICONTROL &#x200B;等於&#x200B;]**`message.feedback` |
| 決策選項分數 | 單一範圍內決策選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 元件類型：量度 |
| 備援決策選項分數 | 在單一範圍內後援決策選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 元件類型：量度 |
| 優惠方案關閉 | 未進行任何其他直接互動就關閉或拒絕的優惠方案數量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件類型：量度 |
| 選件顯示 | 顯示至設定檔的選件數。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件類型：量度 |
| 選件互動 | 顯示至設定檔的選件數。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 元件類型：量度 |
| 選件傳送 | 傳送至設定檔的選件數。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 元件類型：量度 |
| 選件觸發器 | 用戶端SDK要顯示的選件數。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件類型：量度 |
| 取消訂閱優惠方案 | 設定檔要求的選件數量，將來不會顯示。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件類型：量度 |

{style="table-layout:auto"}

[1] 您可以為各種可用事件類型定義多個量度。 請參閱 [包含排除值元件設定](/help/data-views/component-settings/include-exclude-values.md) 以取得更多資訊。
