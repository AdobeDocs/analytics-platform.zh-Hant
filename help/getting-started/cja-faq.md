---
title: Customer Journey Analytics 常見問題集
description: Customer Journey Analytics - 常見問題集。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: bf8864103dc4e52734952c0c93d49f97e35b2817
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 60%

---

# 常見問題集

[!UICONTROL Customer Journey Analytics] (CJA)是我們的新一代分析產品。以下是有關CJA的常見問題解答。 如需詳細資訊，請參閱 [Customer Journey Analytics 功能支援](/help/getting-started/cja-aa.md)。

## 1.必要條件

| 問題 | 回答 |
| --- | --- |
| 是否需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop] 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，使用 [!UICONTROL Customer Journey Analytics] 不需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop]。事實上，目前系統尚未支援這兩項功能。 |
| 是否需要 [!UICONTROL Experience Cloud ID] (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的其他任何 ID 皆可使用。 |
| 如果我需要在使用 [!UICONTROL Customer Journey Analytics] 之前對我的資料執行 ETL 作業 (擷取、轉換、載入)，該怎麼辦？ | Customer Journey Analytics包含[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html)功能，可協助您在將資料放入Adobe Experience Platform資料湖之前轉換資料。 如果您在已收錄資料後需要ETL,[Adobe Experience Platform查詢服務](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries)會提供一些有限的選項，不過可能會涉及額外費用。 |

{style=&quot;table-layout:auto&quot;}

## 2.拼接資料（跨通道分析）

| 問題 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 可以在裝置或資料集之間「拼接」(彙整) 資料嗎？ | 可以。[!UICONTROL 客戶歷程] 分析是稱為跨通道 [分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) (CCA)的聯繫解決方案。它可讓您重新鍵入資料集的人員ID，讓多個資料集的組合更順暢。 |
| 是否支援彙整匿名行為與已驗證的行為？ | 可以。[跨通道分](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) 析會從已驗證和未驗證的作業中檢視使用者資料，以產生銜接ID。 |
| &quot;重播&quot;在CCA中如何運作？ | CCA會根據它所學到的獨特識別碼來「重放」資料。 重播會導致連接的新設備被縫合。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| 在CCA中如何拼接歷史資料（回填）? | 首次開啟時，Adobe會提供銜接資料的回填，可追溯至前一個月的開始（最多60天）。 若要進行此回填，暫時ID必須存在於遠在過去的未連結資料中。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3.將資料導入[!UICONTROL Customer Journey Analytics]

| # | 問題 | 回答 |
| --- | --- | --- |
| 我可以合併同一個 [!UICONTROL Customer Journey Analytics] 連線中不同 [!UICONTROL Adobe Experience Platform] 沙箱的資料嗎？ | 不可以，您無法一次存取多個沙箱內的資料，只能合併同一個沙箱中的資料集。[了解更多](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform] 上 [!UICONTROL Customer Journey Analytics] 的延遲時間預計會多久？ | <ul><li>正常負載下：小於 60 分鐘&#x200B;<br>**注意：**&#x200B;如果通過管道的資料流量特別多，則最多可能需要 24 小時。</li><li>回填資料 (無論大小，最多 13 個月的資料)：小於 4 週</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？ | 只要資料集之間的個人 ID 相符，[!UICONTROL Customer Journey Analytics] 就可連接篩選器、歸因、流量、流失等。。 |
| 如何將離線資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您的Customer Journey Analytics權益可讓您將資料內嵌至Experience Platform。 然後，您可以在[!UICONTROL Customer Journey Analytics]中建立到該資料和資料視圖的連接，以便在Analysis Workspace報告。 如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。 |
| 如何將 [!UICONTROL Adobe Analytics] 資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您可透過 [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/connectors/adobe-applications/analytics.html)，將 [!UICONTROL Adobe Analytics] 資料連結至 Experience Platform。大多數[!UICONTROL Adobe Analytics]欄位都以XDM格式轉換，但其他欄位尚未可用。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |

{style=&quot;table-layout:auto&quot;}

## 4.傳統[!UICONTROL Adobe Analytics]元件

| 問題 | 回答 |
| --- | --- |
| 我是否可以從Customer Journey Analytics共用／發佈篩選器（區段）到Experience Platform統一設定檔或其他Experience Cloud應用程式？ | 目前還沒有，但我們正積極致力於提供此項功能。 |
| 我的舊 eVar 設定有什麼改變？ | [!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 eVar、prop 和事件。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | [!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會顯示於「資料檢視」。]這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]換句話說，現有的區段或計算量度都會與 [!UICONTROL Customer Journey Analytics] 不相容。 |
| [!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！] |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 視您的使用案例而定——請與您的Adobe帳戶團隊合作。 您目前的使用案例可能已非常適合Customer Journey Analytics! |

{style=&quot;table-layout:auto&quot;}

## 5.刪除資料元件的含意

在資料刪除方面，我們關注6種類型的元件：沙盒、架構、資料集、連線、資料檢視和工作區專案。 刪除其中任一元件的部分可能情況如下：

| 若您... | 就會發生下列情形... |
| --- | --- |
| 刪除[!UICONTROL Adobe Experience Platform]中的沙盒 | 刪除沙箱會讓傳送到任一 [!UICONTROL Customer Journey Analytics] 連線的資料停止傳輸至該沙箱中的資料集。目前，系結至已刪除沙盒的CJA中的連線不會自動刪除。 |
| 刪除[!UICONTROL Adobe Experience Platform]中的架構，但不刪除與此架構關聯的資料集 | [!UICONTROL Adobe Experience Platform] 不允許刪除與一或多個資料集相關聯的結構描述。不過，擁有適當權限的管理員可以先刪除資料集，再刪除結構描述。 |
| 刪除[!UICONTROL Adobe Experience Platform]資料湖中的資料集 | 刪除AEP資料湖中的資料集將會停止資料從該資料集流向包含該資料集的任何CJA連線。 該資料集中的任何資料不會從關聯的 CJA 連線中自動刪除。 |
| 刪除[!UICONTROL Customer Journey Analytics]中的資料集 | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(但是，購買CJA SKU的客戶可以刪除[!UICONTROL Adobe Experience Platform]使用者介面中的資料集。) |
| 從資料集刪除批次(在[!UICONTROL Adobe Experience Platform]中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 CJA 連線中移除。[!UICONTROL Adobe Experience Platform] 中的批次資料刪除後，CJA 會收到相關通知。 |
| 將批&#x200B;**裝入[!UICONTROL Customer Journey Analytics]時刪除該批** | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除[!UICONTROL Customer Journey Analytics]中的連接 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何 Analysis Workspace 專案需仰賴所刪除連線中的資料檢視，也將停止運作。</li></ul> |
| 刪除[!UICONTROL Customer Journey Analytics]中的資料視圖 | 錯誤訊息會指出，仰賴這個已刪除資料檢視的 Analysis Workspace 專案會停止運作。 |
