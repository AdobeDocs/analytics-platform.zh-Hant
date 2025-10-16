---
title: Customer Journey Analytics 常見問題
description: Customer Journey Analytics - 常見問題。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 99%

---

# 常見問題

Adobe Customer Journey Analytics 是新一代的分析產品。本文章提供有關 Customer Journey Analytics 常見問題的解答。如需詳細資訊，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)」。

## &#x200B;1. 先決條件 {#prerequisites}

+++**是否需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop] 才能使用 [!UICONTROL Customer Journey Analytics]？**

否，使用 [!UICONTROL Customer Journey Analytics] 不需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop]。事實上，目前系統尚未支援這兩項功能。

+++


+++**是否需要 [!UICONTROL Experience Cloud ID] (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？**

否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的其他任何 ID 皆可使用。

+++


+++**如果我需要在使用 [!UICONTROL Customer Journey Analytics] 之前對我的資料執行 ETL 作業 (擷取、轉換、載入)，該怎麼辦？**

Customer Journey Analytics 包含[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-hant)功能，可協助您先轉換資料，再將資料放到 Adobe Experience Platform Data Lake 中。如果您在擷取資料後需要 ETL，[Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-hant#queries) 提供一些有限的選項，但可能需要額外付費。

+++


## &#x200B;2. 拼接資料 {#stitching}

+++**[!UICONTROL Customer Journey Analytics] 是否可以在裝置或資料集之間「拼接」(彙整) 資料嗎？**

是。[!UICONTROL Customer Journey Analytics] 具有[拼接](../stitching/overview.md)功能，可跨資料集中經過身分驗證和未經身分驗證的事件運作。此拼接可將分散的記錄解析至單一拼接 ID，以進行人員層級的跨裝置分析。
此外，在[連線](/help/connections/overview.md)中的資料集之間使用通用命名空間 ID (人員 ID) 時，您可以對多個資料集 (以人員層級「拼接」) 的無縫組合執行分析。

+++


+++**是否支援拼接匿名行為與已驗證的行為？**

是。[拼接](../stitching/overview.md)功能會檢視已驗證和未驗證工作階段的使用者資料，以產生拼接 ID。

+++


+++**拼接中的「重播」是如何運作的？**

拼接會根據所掌握的唯一識別碼來「重播」資料。重播的目的是從已識別的裝置中拼接最初未經身分驗證的事件。[了解更多](../stitching/overview.md)

+++


+++**拼接歷史 (回填) 資料是如何運作的？**

首次開啟時，Adobe 會提供拼接資料的回填，可回溯到您選取的時間 (最多 25 個月，視您有權使用的 Customer Journey Analytics 套件而定)。為了執行此回填，當時的未拼接資料中必須存在暫時性 ID。[了解更多](../stitching/overview.md)

+++


+++**非拼接輪廓資料集記錄的預期行為是什麼？**

**範例情境**：透過將 `CRMid` 用作人員 ID，在 Customer Journey Analytics 連線中連結兩個資料集。一種是在所有記錄中具有 `CRMid`的 Web 事件資料集。另一個資料集是 CRM 輪廓資料集。40% 的 CRM 資料集在 Web 事件資料集中存在 `CRMid`。其他 60% 不存在於 Web 事件資料集中 - 這些記錄是否出現在 Analysis Workspace 的報告中？<p> **答案**：沒有事件關聯的輪廓列儲存在 Customer Journey Analytics 中。但是，在與該 ID 關聯的事件出現之前，您無法在 Analysis Workspace 中查看它們。

+++

## &#x200B;3. 將資料帶入 [!UICONTROL Customer Journey Analytics] {#ingest}

+++**我可以合併同一個 [!UICONTROL Customer Journey Analytics] 連線中不同 [!UICONTROL Adobe Experience Platform] 沙箱的資料嗎？**

不可以，您無法一次存取多個沙箱內的資料，只能合併同一個沙箱中的資料集。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-hant#select-sandbox-and-datasets)

+++


+++**如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？**

只要資料集之間的人員 ID 相符，[!UICONTROL Customer Journey Analytics] 就可以在資料集之間連結區段、歸因、流量、流失等。

+++


+++**如何將離線資料帶入 [!UICONTROL Customer Journey Analytics]？**

您對 Customer Journey Analytics 的權益可讓您將資料擷取到 Experience Platform。然後您可以在 [!UICONTROL Customer Journey Analytics] 中建立與該資料和資料檢視的連線，以便在 Analysis Workspace 中報告。如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。

+++


+++**如何將 [!UICONTROL Adobe Analytics] 資料帶入 [!UICONTROL Customer Journey Analytics]？**

您可透過 [!UICONTROL  Analytics 來源連接器]，將 [Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-hant) 資料連結至 Experience Platform。大部分的 [!UICONTROL Adobe Analytics] 欄位都會以 XDM 格式帶入，但其他欄位則尚未開放使用。

+++


+++**將資料集元素組合成資料檢視需要多久時間？**

需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。

+++


+++**是否需要帶入 PII 資料來建立資料之間的連結？**

否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。

+++


+++**擷取過去或未來的日期/時間戳記至 Customer Journey Analytics 事件資料集有哪些限制？**

* 在過去日期/時間戳記方面：事件資料最久為十年。
* 在未來日期/時間戳記方面：事件資料 (預測性) 最久為未來一個月。

+++


## &#x200B;4. 延遲的注意事項 {#latency}

>[!NOTE]
>
>Customer Journey Analytics 中沒有固定的資料大小，因此 Adobe 無法指定標準的擷取時間。Adobe 正在積極努力透過新的更新和擷取最佳化來減少這些延遲。

* 即時資料或事件：資料可在 Adobe Experience Platform 上使用時，在 90 分鐘內完成處理和擷取。(批次大小 > 5000 萬列：超過 90 分鐘。) 如果啟用拼接，則擷取可能需要長達 4 小時。如需詳細資料，請參閱[護欄](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/technotes/guardrails)。
* 小量回填：七天內
* 大量回填：30 天內

Adobe 最近變更了在 Customer Journey Analytics 中處理資料的方式：

* 「當天」的事件資料作為即時資料進行串流。任何事件時間早於前一天晚上 11:59:59 (23:59:59) 的資料都將被視為回填。
* 任何時間戳記超過 24 小時的事件資料 (即使與較新的資料屬於同一批次) 都視為回填，並以較低的優先順序擷取。

## &#x200B;5. 設定「[!UICONTROL 連線]」資料保留的滾動時段 {#data-retention}

「[**[!UICONTROL 啟用滾動資料時段&#x200B;]**」設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)可讓您將 Customer Journey Analytics 資料保留定義為單位為幾個月的滾動時段 (三個月、六個月等)。這是在[!UICONTROL 連接]層級設定，而不是[!UICONTROL 資料集]層級。資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此輪廓或查詢資料集不存在資料保留設定。

主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。

## &#x200B;6. 刪除資料元件的影響 {#deletion}

對於資料刪除，您應該考慮六種元件：沙箱、結構描述、資料集、連線、資料檢視和 Workspace 專案。以下是刪除上述任何元件後的一些可能情況：

| 若您... | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的沙箱 | 刪除沙箱時，資料會停止流向該沙箱中資料集的任何 [!UICONTROL Customer Journey Analytics] 連線。與此刪除的沙箱相關的連線、資料視圖、量度和維度也將被刪除。 | |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的結構描述，但不刪除與此結構描述相關聯的資料集 | [!UICONTROL Adobe Experience Platform] 不允許刪除與一或多個[!UICONTROL 資料集]相關聯的[!UICONTROL 結構描述]。不過，擁有適當權限的管理員可以先刪除資料集，再刪除結構描述。 |
| 刪除 [!UICONTROL Adobe Experience Platform] Data Lake 中的資料集 | 刪除 Adobe Experience Platform Data Lake 的資料集時，資料會停止從該資料集流向包含該資料集的任何 Customer Journey Analytics 連線。系統會從相關聯的 Customer Journey Analytics 連線自動刪除該資料集中的任何資料。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 請與您的 Adobe 帳戶團隊聯絡，以便展開刪除已儲存連線中的資料集流程。 |
| 從資料集中刪除批次 (在 [!UICONTROL Adobe Experience Platform] 中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除某個批次，該批次資料就會從包含該特定批次的所有 Customer Journey Analytics 連線中移除。[!UICONTROL Adobe Experience Platform] 中的批次資料刪除後，Customer Journey Analytics 會收到相關通知。 |
| 在批次&#x200B;**正被擷取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中時將其刪除 | 如果資料集中只有一個批次，則該批次中的所有或部分資料都不會顯示在 [!UICONTROL Customer Journey Analytics] 中。擷取會收回。舉例來說，如果資料集含有五個批次，其中三個在資料集刪除之前就已擷取完成，則該 3 個批次的資料就會顯示在 [!UICONTROL Customer Journey Analytics] 中。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息指出：<ul><li>任何針對已刪除連線建立的資料檢視都不會再運作。</li><li> 同樣地，如果有任何 Workspace 專案與所刪除連線中的資料檢視相依，也會停止運作。</li></ul> |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視 | 此時會顯示一個錯誤訊息，指出與這個已刪除之資料檢視相依的任何 Workspace 專案都將停止運作。 |

## &#x200B;7. 在 Customer Journey Analytics 合併報告套裝時的考量 {#merge-reportsuite}

如果您計劃透過 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)擷取 Adobe Analytics 資料，請在合併二個或更多 Adobe Analytics 報告套裝時考慮這些後果。

| 問題 | 考量事項 |
| --- | --- |
| 變數 | [!UICONTROL eVars] 等變數可能不會跨報表套裝排列。例如，報表套裝 1 中的 eVar1 可能指向&#x200B;**[!UICONTROL 頁面]**。在報表套裝 2 中，eVar1 可能指向&#x200B;**[!UICONTROL 內部行銷活動]**，因而導致混合和不準確的報表。 |
| [!UICONTROL 工作階段]和[!UICONTROL 人員]計數 | 它們會跨報表套裝進行重複資料刪除。因此，計數可能不相符。 |
| 量度重複資料刪除 | 如果多列具有相同的交易 ID (例如，[!UICONTROL 購買 ID])，則對量度的實例 (例如[!UICONTROL 訂單]) 進行重複資料刪除。這可以防止過度計算關鍵量度。因此，像[!UICONTROL 訂單]這樣的量度可能不會跨報表套裝累加。 |
| 貨幣 | Customer Journey Analytics 尚不支援貨幣換算。如果您嘗試合併的報表套裝使用不同的基礎貨幣，則可能會出現問題。 |
| [!UICONTROL 持續性] | [持續性](../data-views/component-settings/persistence.md)會跨報告套裝進行擴展，因而影響到[!UICONTROL 區段]、[!UICONTROL 歸因]等。數字可能無法正確相加。 |
| [!UICONTROL 分類] | 合併報表套裝時，[!UICONTROL 分類]不會自動進行重複資料刪除。將多個分類檔案合併為單一[!UICONTROL 查閱]資料集時，您可能會遇到問題。 |

## &#x200B;8. [!UICONTROL Adobe Analytics] 元件

+++**我可以將[!UICONTROL 客群]從 [!DNL Customer Journey Analytics] 共用/發佈到 Experience Platform Real-Time CDP 或其他 Experience Cloud 應用程式嗎？**

您可以將 Customer Journey Analytics 中發現的[客群建立並發佈](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-components/audiences/publish)到 Adobe Experience Platform 中的即時客戶輪廓，以用於客戶目標選擇和個人化。

+++

+++**我的舊 [!UICONTROL eVar] 設定有何改變？**

[!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 中的 [!UICONTROL eVar]、[!UICONTROL prop] 和 [!UICONTROL 事件]。您有不限數量的結構描述元素 (維度、量度、清單欄位)。因此，您用來在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。

+++

+++**我所有的工作階段和變數持續性設定現在位於何處？**

[!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會顯示於「資料檢視」。]這些設定的變更現在可回溯，使用多個資料檢視即可擁有多個版本！

+++

+++**您現有的區段/計算量度有何改變？**

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、屬性或事件，而是使用任何 Adobe Experience Platform 結構描述。也就是說，現有的區段或計算量度都與 [!UICONTROL Customer Journey Analytics] 不相容。

+++

+++**[!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？**

[!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！]

+++

+++**如果我是現有 [!DNL Data Workbench]客戶，現在是否可以改用 Customer Journey Analytics？**

這取決於您的使用案例，因此請與您的 Adobe 帳戶團隊合作。您目前的使用案例可能已經很適合使用 Customer Journey Analytics！

+++

## &#x200B;9. 估算連線規模 {#estimate-size}

請參閱[連線使用情況](/help/connections/manage-connections.md#usage)。

## &#x200B;10. 關於使用超額 {#overage}

Adobe 會定期監控和執行使用量限額。「資料列」指可用於 Customer Journey Analytics 中分析的每日平均資料列。

例如，您的合約讓您有權使用 100 萬筆資料列。假設在使用 Customer Journey Analytics 的第 1 天，您可以上傳 200 萬筆資料列。您在第 2 天刪除 100 萬筆資料列，並在剩餘的授權期限內將使用量維持在承諾的最大使用量 (亦即 100 萬筆資料列) 以內。根據您的合約條款，由於您超出了「資料列」授權權利，您仍然可能需支付按比例計算的第 1 天超額使用費。

## &#x200B;11. 診斷資料差異 {#discrepancies}

有時候，您可能會發現連線所擷取的事件總數與 [!UICONTROL Adobe Experience Platform] 資料集中的列數不同。在此範例中，資料集「B2B Impression」有 7,650 列，但資料集在 [!UICONTROL Adobe Experience Platform] 中僅有 3,830 列。數據不一致有幾個原因，您可採取下列步驟加以診斷：

1. 依「**[!UICONTROL Platform 資料集 ID]**」劃分此維度，您會發現兩個資料集具有相同大小，但「**[!UICONTROL Platform 資料集 ID]**」不同。每個資料集都有 3825 筆記錄。這表示有五筆記錄缺少人員 ID 或時間戳記，因此遭到 [!UICONTROL Customer Journey Analytics] 忽略：

   ![劃分](assets/data-size2.png)

1. 此外，如果您查看 [!UICONTROL Adobe Experience Platform]，會發現沒有 ID 為「5f21c12b732044194bffc1d0」的資料集，因此建立初始連線時，已有其他人從 [!UICONTROL Adobe Experience Platform] 中刪除了這個資料集。之後，雖然有人將資料集重新新增至 Customer Journey Analytics，但 [!UICONTROL Adobe Experience Platform] 產生的 [!UICONTROL Platform 資料集 ID] 不同。

深入了解在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[刪除資料集和連線可能造成的後果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components)。


## &#x200B;12. 地區資料收集

Adobe Experience Cloud 使用地區資料收集 (RDC) 功能，因此您的訪客與 Adobe 及非 Adobe 解決方案之間的互動會盡可能貼近訪客的需求。資料在資料收集中心 (DCC，也稱為 Edge 網站，是 Platform Edge Network 的一部分) 以區域方式收集之後，會依據資料流和/或事件轉送的設定，透過安全連線轉送給相關解決方案。

![使用 Edge Network 的資料流](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

區域資料收集流程使用以下步驟：

1. DNS 會自動將收集主機名稱解析為最接近訪客的資料收集中心的 IP 位址。
1. 訪客將資料傳送至該位置。
1. 資料立即透過安全連線轉送到資料流或事件轉送設定所定義的解決方案。

使用區域資料收集有幾個優點：

* **效能**：透過 RDC，訪客可連接至最近的 DCC。 此最佳化可提供最快的回應時間，進而實現更準確的追蹤並加快載入時間。
* **備援**：如果 DCC 與 DPC 之間的通訊發生中斷，Adobe 的 RDC 基礎結構會在本機儲存資料，然後在通訊還原時將資料轉送至 DPC。

RDC 目前包括下列位置 (可能隨時變更)：


| RDC型別 | 資料收集中心 |
| --- | --- |
| 全域 (預設值) | 奧勒岡州、維吉尼亞州、愛爾蘭、巴黎、孟買、新加坡、東京、雪梨 |
| 僅限美洲 | 奧勒岡州、維吉尼亞州 |
| 僅限歐洲 | 愛爾蘭、巴黎 |
| 僅限亞太地區 | 孟買、新加坡、東京、雪梨 |

{style="table-layout:auto"}

資料到達區域資料中心時，資料流設定會決定資料如何進一步路由。

Customer Journey Analytics 需要來自 Adobe Experience Platform 的資料集，因此您的資料流/事件轉送設定需要 Adobe Experience Platform 服務將資料從區域資料中心路由到 Adobe Experience Platform 執行個體所在的資料中心。Customer Journey Analytics 及其支援服務和基礎架構都部署在同一個 Adobe Experience Platform 執行個體中。


請參閱[資料收集概觀](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html)，深入了解有關在 Adobe Experience Platform Edge Network 及其區域資料中心之外執行資料收集程序的資訊。
