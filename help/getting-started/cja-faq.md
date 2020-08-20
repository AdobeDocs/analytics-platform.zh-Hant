---
title: Customer Journey Analytics 常見問題集
description: Customer Journey Analytics - 常見問題集。
translation-type: tm+mt
source-git-commit: 297ed03ff59cc8d719a6bf0984e82597e8d33392
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 69%

---


# 常見問題集

| 問題 | 回答 |
| --- | --- |
| **必要條件** |  |
| 我是否需要裝置圖表或裝置合作基金 [!UICONTROL 客戶歷程分析]? | 否，私人裝置圖表或裝置合作社區 [!UICONTROL 客戶歷程分析]. 事實上，目前尚未支援這兩項功能。 |
| 我是否需要Experience Cloud ID(ECID) [!UICONTROL 客戶歷程分析]? | 不， [!UICONTROL 客戶歷程分析] 支援資料集中的任何ID，不論是ECID或您選擇的任何其他ID。 |
| 如果我需要在客戶歷程分析之前對資料進行ETL（擷取、轉換、載入），該怎麼辦？ | 現在，如果您需要在將資料放入 AEP 之前先轉換資料，您必須與 ETL 合作夥伴 (Unifi 或 Informatica) 合作。如果您在資料已收錄後需要ETL,AEP查詢服務會提供一些有限的選項。 |
| **拼接** |  |
| 可 [!UICONTROL 客戶歷程分析] 跨裝置或跨資料集「拼接」? | 不可以，[!UICONTROL Customer Journey Analytics 是「自攜 ID」的分析系統。]我們正在規劃適當的拼接方法。 |
| 是否支援拼接匿名行為與已驗證的行為？ | 否，尚未支援。 |
| **[!UICONTROL 將資料帶入 Customer Journey Analytics]** |  |
| 我可以將不同Experience Platform沙盒的資料合併為一個CJA連線嗎？ | 不行，您無法跨沙盒存取資料。 您只能結合位於相同沙盒中的資料集。 [更多詳情...](https://docs.adobe.com/content/help/en/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 預期延遲的時間 [!UICONTROL 客戶歷程分析] on [!UICONTROL 體驗平台]? | <ul><li>正常負載下：&lt; 60 分鐘&#x200B;<br>**注意：**&#x200B;如果透過管道的資料流量異常高，最多可能需要 24 小時。</li><li>回填資料 (最多 100 億件事件)：&lt; 4 週</li></ul> |
| 如何將線上資料連接至 [!UICONTROL 客戶歷程分析]? | [!UICONTROL Customer Journey Analytics 是「自攜 ID」的分析系統。]只要人員ID在資料集之間相符， [!UICONTROL 客戶歷程分析] 可以連接區段、歸因、流量、流失等。 。 |
| 如何將離線資料帶入 Customer Journey Analytics？ | 您必須先將任何資料帶入Experience Platform，才能與客戶歷程分析搭配使用。 Experience Platform的資料入門團隊可協助您提供建議或諮詢（如有需要）。 |
| 如何將 Analytics 資料帶入 Customer Journey Analytics？ | Analytics資料可透過 [Analytics資料連接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html). 大部分的 Analytics 欄位都是以 XDM 格式帶入，但其他欄位尚不可使用 (例如「行銷管道」維度)。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |
| **傳統 Analytics 元件** |  |
| 這對我們傳統的 Adobe Analytics 產品有何意義？ | Customer Journey Analytics 是我們新一代的分析產品。從我們目前的產品演進到 Customer Journey Analytics 需要數年時間，且同時需要進行大量協調。 |
| 我是否可以將區段從 Customer Journey Analytics 分享至 AEP 或其他解決方案？ | 還不可以。我們正在研究新的創新方法，以便在日後將區段從 Customer Journey Analytics 分享至 AEP，且不會有這麼長的延遲。也就是說，您可以將 Query Service 的輸出分享至整合設定檔，作為可能的因應措施。 |
| 我的舊 eVar 設定有什麼改變？ | Customer Journey Analytics 中不再有 Adobe Analytics 傳統意義上的 eVar、prop 和事件。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會在「資料檢視」中顯示。這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。這表示，現有的區段或計算量度都與 Customer Journey Analytics 不相容。 |
| Customer Journey Analytics 如何處理 `Uniques Exceeded` 限制？ | Customer Journey Analytics 沒有唯一值限制，因此無需擔心這些限制！ |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 視情況而定。如果您重度依賴整合客戶流程 (UCP)，建議您等到我們實施拼接之後再改用。如果您已有高客戶驗證率、想將所有資料集中在一處，或是想要移除 eVar，Customer Journey Analytics 可能非常適合您。 |

