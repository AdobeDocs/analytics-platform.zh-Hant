---
title: Adobe Analytics 至 Customer Journey Analytics 的發展進程
description: 從 Adobe Analytics 資料轉換為 Customer Journey Analytics 資料的步驟
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '1420'
ht-degree: 100%

---

# Adobe Analytics 至 Customer Journey Analytics 的發展進程

隨著您的組織發展為使用 Customer Journey Analytics，請探索這些步驟以準備您的資料，並了解這兩種技術之間的關鍵差異。 本文內容主要針對管理員對象。

## 準備資料

準備您的 Adobe Analytics 資料以無縫移前往 Customer Journey Analytics，對資料完整性和報告一致性至關重要。

### 1. 收集身分 {#identities}

了解客戶歷程的最關鍵部分，或許是了解在每一步驟中的目標客戶。對於 Customer Journey Analytics，擁有跨所有管道和對應資料的識別碼，允許在 CJA 內將多個來源拼接在一起。
身分範例可能是客戶 ID、帳戶 ID 或電子郵件 ID。無論是什麼身分 (可能有多個)，請務必為每個 ID 考慮以下內容：

* ID 存在或可新增到要引入 CJA 的所有資料來源
* 在每個資料列上填入 ID
* ID 不包含 PII。對任何可能的敏感內容套用雜湊處理。
* ID 在所有來源上使用相同格式 (相同長度、相同雜湊方法等)

在像 Adobe Analytics 這樣的資料集，身分不一定存在於每個資料列中，但是次要身分一定存在。在這種情況下，在只由 ECID 識別客戶和在收集身分時，跨管道分析 (以前稱為「欄位型拼接」) 可用於 (例如，當客戶驗證時) 彌合資料列之間的差距。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)

### 2. 對應變數 {#variables}

將 Adobe Analytics 資料轉換為 Customer Journey Analytics 資料的最直接方法，是使用 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)將[全域報告套裝](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)擷取到 Experience Platform。 此連接器會將您的 Adobe Analytics 變數直接對應到 Experience Platform 中的 XDM 結構描述和資料集，這些結構描述和資料集可輕鬆連接到 Customer Journey Analytics。

完整的全域報告套裝並不總能用於實施。如果您計劃將多個報表套件引入 Customer Journey Analytics，則有 2 個選項：

* 提前規劃，使變數在這些報告套件中保持一致。 例如，報告套裝 1 中的 eVar1 可能指向[!UICONTROL 頁面]。報告套裝 2 中的 eVar1 可能指向[!UICONTROL 內部行銷活動]。在將報告套裝引入 CJA 時，這些變數將混合到單一 eVar1 維度中，導致可能的混淆和不準確的報告。

* 使用[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)功能來對應變數。假設所有報告套裝都使用相同的通用變數設計時，這項功能會使過程更容易些；但是如果您使用新的 Experience Platform [資料準備](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html#mapping)功能，則不需要使用這項功能。這項功能允許您透過變數的對應值 (位於資料流 (或屬性) 級別) 來引用變數。

如果您由於[!UICONTROL 已超出不重複限制]或[!UICONTROL 低流量]問題，而避免使用全域報告套裝，請了解 CJA 沒有[維度上的基數限制](/help/components/dimensions/high-cardinality.md)。它允許顯示和計數任何唯一值。

以下是[結合報告套裝與不同的結構描述](/help/use-cases/aa-data/combine-report-suites.md)的使用案例。

### 3. (重新) 設定行銷管道 {#marketing-channels}

傳統的 Adobe Analytics 行銷管道設定在 CJA 中的執行方式不同。有兩個原因：

* 擷取到 Adobe Experience Platform 的 Adobe Analytics 資料的處理層級，以及

* Customer Journey Analytics 的報告時間性質

Adobe 已發佈[行銷管道實施的更新最佳實務](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html)。這些更新的推薦可幫助您透過 Attribution IQ 充分利用 Adobe Analytics 的現有功能。此外也為成功轉換到 Customer Journey Analytics 做好準備。

### 4. 決定使用 Analytics 來源連接器或 Experience Platform SDK {#connector-vs-sdk}

Adobe Analytics 客戶可以使用 Analytics 來源連接器輕鬆地在 Adobe Experience Platform 和 Customer Journey Analytics 中利用他們的報告套裝。如需有關使用 Analytics 來源連接器的資訊，請參閱[在 UI 中建立 Adobe Analytics 來源連線](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。

隨著 [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) 資料收集的發展，您可能會移前往 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html) 或 [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html) (搭配 Adobe Experience Platform Edge Network)。SDK 的典型實施是將資料傳送到 Adobe Analytics，但直接將資料傳送到 Adobe Experience Platform 的新機會也隨之而來。然後，可將資料擷取到 Customer Journey Analytics，同時保留傳送到 Adobe Analytics 的資料。

這種方法大幅擴展了資料收集的可能性：欄位數不再有限制，也不再需要將資料元素對應到 Analytics 中的 prop、eVar 和 event 等變數。可以使用不同類型的無限結構描述元素，並使用 CJA [資料檢視](/help/data-views/data-views.md)以多種方式表示它們。當直接傳送到 Adobe Experience Platform 時，資料可用性的速度會加快，因為移除了透過 Adobe Analytics 進行資料處理的時間。

**使用 Experience Platform SDK 的優勢:**

* 靈活的結構描述，可定義所需的任何欄位
* 不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)
* 無字元限制問題 (prop 有 100 個字元)
* 加快提供 Adobe Experience Platform 中的資料可用性來推動[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hant)
* [第一方裝置 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=zh-Hant)，用於強化訪客識別的準確性

**使用 Experience Platform SDK 的缺點**

不支援以下 Adobe Analytics 功能或元件：

* 行銷管道
* 機器人篩選
* 地理位置、網域、裝置查詢
* Analytics for Target (A4T)

## 為重大差異做好準備

### 適應報告時間處理 {#report-time}

Adobe Analytics 的報告依賴大量資料前置處理來產生結果，如您在 [!UICONTROL eVar] 中看到的持續性。反之，Customer Journey Analytics 在報告執行階段時執行這些計算。

[!UICONTROL 報告時間處理]開啟以下能力：套用可追溯的設定，以及建立多個版本的變數持續性，而無需變更基礎資料的收集方式。

此轉換將導致報告資料的方式出現一些差異，特別是對於有效期較長的任何變數。一開始可使用[虛擬報表套件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html)，來評估報告時間處理可能產生的報告影響。

### 確定關鍵區段和計算量度 {#segments-calcmetrics}

Adobe Analytics 區段 (在 CJA 中稱為[!UICONTROL 篩選器]) 和計算量度與 Customer Journey Analytics 不相容。在許多情況下，可在 CJA 中使用新的結構描述和可用資料重建這些元件。

為了讓使用者在系統之間轉換時盡可能順利地進行轉換，請提前規劃

1. 確定這些元件中最關鍵的元件。

1. 記錄它們的定義，以及

1. 確定資料中所需的欄位，以便在 CJA 中複寫為[篩選器](/help/components/filters/filters-overview.md)和[計算量度](/help/components/calc-metrics/calc-metr-overview.md)。

以下兩段影片協助提供指引：

* [將 Adobe Analytics 區段移至 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html)

* [將計算量度從 Adobe Analytics 移至 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=zh-Hant)

### 其他考量

* 運用 CJA 資料檢視的力量，您有更大的彈性來定義 Customer Journey Analytics 的量度和維度。例如，維度值可做為量度的定義。[了解更多](/help/use-cases/data-views/data-views-usecases.md)

* 如果您在 Adobe Analytics 定義了自訂行事曆，則 CJA 中將具有類似的[自訂行事曆功能](/help/components/date-ranges/custom-date-ranges.md)。 您需要確保行事曆已正確定義。

* 在 Customer Journey Analytics 中，可以定義自訂造訪/工作階段逾時，並定義將啟動新工作階段的量度。您可以建立具有不同工作階段定義的資料檢視，以獲得超越 Adobe Analytics 可能的見解。此功能對行動資料集尤其有益。

* 請考慮為使用者提供資料字典，或擴展 SDR 以包括結構描述元素的 Experience Platform 欄位名稱。

## 後續步驟

移前往 CJA 後，如果您發現任何資料差異，您可以將原始的 Adobe Analytics 資料與現在位於 Customer Journey Analytics 中的 Adobe Analytics 資料進行比較。[了解更多](/help/troubleshooting/compare.md)
