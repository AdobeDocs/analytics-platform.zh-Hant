---
title: 將Adobe Journey Optimizer決策管理與Adobe Customer Journey Analytics整合
description: 引進Adobe Journey Optimizer決策管理產生的資料，並在Customer Journey Analytics內使用Analysis Workspace加以分析。
exl-id: fde45264-46cf-4c68-9872-7fb739748f21
feature: Experience Platform Integration
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 17%

---

# 將決定管理與Adobe Customer Journey Analytics整合


Adobe Journey Optimizer [決定管理](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) 透過集中行銷優惠資料庫和決定引擎輕鬆實現個人化，決定引擎將規則和限制套用於Adobe Experience Platform建立的豐富即時設定檔，以幫助您在適當的時間向客戶傳送合適的優惠。

決定管理是Adobe Journey Optimizer的一部分，並與之整合。 此外，它也可以透過其豐富功能，與Adobe Journey Optimizer中定義的歷程和行銷活動分開使用 [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) 支援。

您可以匯入「決定管理」產生的資料，以透過下列步驟在Customer Journey Analytics中執行進階分析：

## 將資料從決定管理傳送至Adobe Experience Platform

Adobe Experience Platform會當作中央資料來源，以及介於決定管理和Customer Journey Analytics之間的連結。 來自「決定管理」的資料是以Experience Platform收集 **自動** 或當作 **明確傳送的體驗事件** （例如曝光數或點按數）。 另請參閱 [資料收集快速入門](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) 以取得更多詳細資料。

## 建立連線

一旦決定管理資料進入Adobe Experience Platform，您就可以建立 [連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant) 根據您的決定管理資料集而定。 或者，您也可以將決定管理資料集新增到現有連線。

選取並設定下列資料集：

| 資料集 | 資料集類型 | 連線設定 | 說明 |
| --- | --- | --- | --- |
| ODE Decisionevents - _沙箱_ 決策 | 事件 | 人員ID： `IdentityMap` | 包含用於決定管理決定事件的自動產生資料。 _Sandbox_ 是指特定的沙箱名稱。 |
| Adobe Journey Optimizer訊息回饋事件資料集 | 事件 | 人員ID： `IdentityMap` | 包含訊息傳遞事件。 |
| Adobe Journey Optimizer電子郵件追蹤體驗事件資料集 | 事件 | 人員ID： `IdentityMap` | 包含電子郵件追蹤事件。 |
| Adobe Journey Optimizer推播追蹤體驗事件資料集 | 事件 | 人員ID： `IdentityMap` | 包含推播追蹤事件。 |
| Adobe Journey Optimizer實體資料集 | 查詢 | 索引鍵： `_id`<br>比對索引鍵： `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | 包含將Journey和Campaign中繼資料與所有Adobe Journey Optimizer事件資料建立關聯的分類。 |

{style="table-layout:auto"}

## 建立資料檢視

在建立連線後，您可以建立一個或多個[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en)來設定 Customer Journey Analytics 中可用的所需維度和量度。

>[!NOTE]
>
>Adobe Journey Optimizer和Customer Journey Analytics之間的資料差異通常少於1-2%。 過去兩小時內收集的資料可能存在較大差異。使用不包括今天的日期範圍來減少與處理時間有關的差異。

### 設定維度

您可以在資料檢視中建立以下維度，以實現與決策管理中類似維度的近似同位。 請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關維度自訂選項的詳細資料。

| 維度 | 綱要元素 | 元件設定 |
| --- | --- | --- |
| 活動名稱 | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | 元件類型：維度 |
| 容器識別碼 | `_experience.decisioning.containerID` | 元件類型：維度 |
| 關聯識別碼 | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | 元件類型：維度 |
| 決定選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | 元件類型：維度 |
| 遞補決定選項名稱 | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | 元件類型：維度 |
| 位置名稱 | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | 元件類型：維度 |

{style="table-layout:auto"}


### 設定量度

您可以在資料檢視中建立以下量度，以實現與決策管理中類似量度的近似同位。 請參閱資料檢視管理器中的[元件設定](/help/data-views/component-settings/overview.md)，以取得有關量度自訂選項的詳細資料。

| 量度 | 說明 | 綱要元素 | 元件設定 |
| --- | --- | --- | --- |
| 事件型別(重新命名以參考特定事件，例如 `Feedback` 的 `message.feedback`) [1] | 特定型別事件的金額 | `eventType` | 元件型別：量度<br/>**[!UICONTROL 設定包含排除值&#x200B;]**：開啟<br/>**[!UICONTROL 符合]**： [!UICONTROL 如果滿足所有條件]<br/>**[!UICONTROL 條件&#x200B;]**：**[!UICONTROL &#x200B;等於&#x200B;]**`message.feedback` |
| 決定選項分數 | 單一範圍內容中決策選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | 元件型別：量度 |
| 遞補決定選項分數 | 單一範圍內容中遞補決定選項的計算值。 | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | 元件型別：量度 |
| 優惠已關閉 | 在沒有任何其他直接互動的情況下駁回或拒絕的優惠方案數量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件型別：量度 |
| 優惠方案顯示 | 顯示給設定檔的優惠方案數量。 | `_experience.decisioning.`<br/>`propositionEventType.display` | 元件型別：量度 |
| 優惠互動 | 顯示給設定檔的優惠方案數量。 | `_experience.decisioning.`<br/>`propositionEventType.interact` | 元件型別：量度 |
| 優惠傳送 | 傳送至設定檔的優惠方案數量。 | `_experience.decisioning.`<br/>`propositionEventType.send` | 元件型別：量度 |
| 優惠方案觸發器 | 選擇由使用者端SDK顯示的選件數目。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件型別：量度 |
| 優惠取消訂閱 | 設定檔要求未來不顯示的選件數量。 | `_experience.decisioning.`<br/>`propositionEventType.trigger` | 元件型別：量度 |

{style="table-layout:auto"}

[1] 您可以為可用的各種事件型別定義多個量度。 另請參閱 [包含排除值元件設定](/help/data-views/component-settings/include-exclude-values.md) 以取得詳細資訊。
