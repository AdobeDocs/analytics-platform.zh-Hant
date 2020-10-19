---
title: Customer Journey Analytics 常見問題集
description: Customer Journey Analytics - 常見問題集。
translation-type: tm+mt
source-git-commit: eb7d7d80ee07298f7d0fe308bdc93a3435f2c381
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 96%

---


# 常見問題集

| 問題 | 回答 |
| --- | --- |
| **必要條件** |  |
| 是否需要 Device Graph 或 Device Coop 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，[!UICONTROL Customer Journey Analytics] 不需要 Private Device Graph 或 Device Coop。事實上，目前尚未支援這兩項功能。 |
| 是否需要 Experience Cloud ID (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的任何其他 ID。 |
| 如果我需要在使用 Customer Journey Analytics 之前對我的資料進行 ETL (擷取、轉換、載入)，該怎麼辦？ | 現在，如果您需要在將資料放入 AEP 之前先轉換資料，您必須與 ETL 合作夥伴 (Unifi 或 Informatica) 合作。如果您需要在資料已內嵌之後進行 ETL，則 AEP Query Services 會提供一些有限選項。 |
| **拼接** |  |
| [!UICONTROL Customer Journey Analytics] 可以在裝置或資料集之間「拼接」嗎？ | 不可以，[!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。我們正在規劃適當的拼接方法。 |
| 是否支援拼接匿名行為與已驗證的行為？ | 否，尚未支援。 |
| **將資料帶入 [!UICONTROL Customer Journey Analytics]** |  |
| 是否能在一個 CJA 連線中合併不同 Experience Platform 沙箱的資料？ | 否，您無法一次存取多個沙箱內的資料。您只能合併位於同一個沙箱中的資料集。[深入了解...](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Experience Platform] 上 [!UICONTROL Customer Journey Analytics] 的預期延遲為何？ | <ul><li>正常負載下：&lt; 60 分鐘&#x200B;<br>**注意：**&#x200B;如果透過管道的資料流量異常高，最多可能需要 24 小時。</li><li>回填資料（最多13個月的資料，不論大小）:&lt; 4週</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？ | [!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。只要人員 ID 在資料集之間相符，[!UICONTROL Customer Journey Analytics] 就可以在資料集之間連結區段、歸因、流量、流失等等。 |
| 如何將離線資料帶入 Customer Journey Analytics？ | 您必須先將資料帶入 Experience Platform，才能透過 Customer Journey Analytics 使用。如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。 |
| 如何將 Analytics 資料帶入 Customer Journey Analytics？ | 可透過 [Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/connectors/adobe-applications/analytics.html) 將 Analytics 資料連結至 Experience Platform。大部分的 Analytics 欄位都是以 XDM 格式帶入，但其他欄位尚不可使用 (例如「行銷管道」維度)。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |
| **傳統 Analytics 元件** |  |
| 這對我們傳統的 Adobe Analytics 產品有何意義？ | 客戶歷程分析是我們的新一代分析產品。 從我們目前的產品演進到 Customer Journey Analytics 需要數年時間，且同時需要進行大量協調。如需詳細資訊，請檢閱 [客戶歷程分析功能支援](/help/getting-started/cja-aa.md). |
| 我是否可以將區段從 Customer Journey Analytics 分享至 AEP 或其他解決方案？ | 還不可以。我們正在研究新的創新方法，以便在日後將區段從 Customer Journey Analytics 分享至 AEP，且不會有這麼長的延遲。也就是說，您可以將 Query Service 的輸出分享至整合設定檔，作為可能的因應措施。 |
| 我的舊 eVar 設定有什麼改變？ | Customer Journey Analytics 中不再有 Adobe Analytics 傳統意義上的 eVar、prop 和事件。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會在「資料檢視」中顯示。這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。這表示，現有的區段或計算量度都與 Customer Journey Analytics 不相容。 |
| Customer Journey Analytics 如何處理 `Uniques Exceeded` 限制？ | Customer Journey Analytics 沒有唯一值限制，因此無需擔心這些限制！ |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 視情況而定。如果您重度依賴整合客戶流程 (UCP)，建議您等到我們實施拼接之後再改用。如果您已有高客戶驗證率、想將所有資料集中在一處，或是想要移除 eVar，Customer Journey Analytics 可能非常適合您。 |

