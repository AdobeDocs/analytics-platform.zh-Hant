---
title: 從 Adobe Analytics 升級至 Customer Journey Analytics
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics的建議步驟
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d35f8615-66f5-4823-b0b8-433852246dd2
source-git-commit: dfc9ba843fbddc135c0f8160fb672adb36e9146f
workflow-type: tm+mt
source-wordcount: '3281'
ht-degree: 57%

---

# 從 Adobe Analytics 升級至 Customer Journey Analytics

從 Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics 時，您可以按照[建議的升級步驟](#recommended-upgrade-steps-for-most-organizations)進行。或者您可以根據本身組織的獨特情況[以動態方式產生升級步驟](#dynamically-generate-upgrade-steps-for-your-organization)。

## 適用於大多數組織的建議升級步驟 {#upgrade-process}

從 Adobe Analytics 升級到 Customer Journey Analytics 的推薦流程是 Experience Platform Web SDK 的新實施，這是最適月合 Customer Journey Analytics 的資料收集方法。若結合 Web SDK，Adobe 也建議使用 Analytics 來源連接器來幫助您轉變為 Customer Journey Analytics。使用 Analytics 來源連接器保留歷史 Adob&#x200B;&#x200B;e Analytics 資料並執行並排資料比較。

在您使用 Experience Platform Web SDK 獲得足夠的歷史資料並完全轉變為 Customer Journey Analytics 後，即可關閉 Analytics 來源連接器並單獨使用 Web SDK。

>[!NOTE]
>
>如果本節所述的升級步驟對貴組織而言並不實際，請使用Customer Journey Analytics升級指南以動態方式產生針對貴組織獨特環境量身打造的升級步驟。 (若要從Customer Journey Analytics存取指南，請選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 請依照熒幕上的指示進行。)

### 高階建議升級流程 {#high-level-upgade-process}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-historical-data"
>title="Adobe Analytics 的歷史資料"
>abstract="將歷史 Adobe Analytics 報告套裝資料匯入至 Adobe Experience Platform 和 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

1. **實施 Experience Platform Web SDK (可持續進行資料收集)**

   Experience Platform Web SDK 的新實施是收集 Customer Journey Analytics 資料的最佳方式。這可為充分利用 Customer Journey Analytics 提供最佳基礎，因為這是實施 Customer Journey Analytics 的最高效、最直接、最具前瞻性的方法。

   * Adobe Experience Platform 是為支援 即時個人化使用案例而建立，因此具有高效能報告和資料可用性

   * 在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施

   * 不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)

1. **設定 Adob&#x200B;&#x200B;e Analytics 來源連接器 (可轉變歷史資料)**

   為了幫助順利轉變為使用帶有 Customer Journey Analytics 的 Experience Platform Web SDK，Adobe 也建議使用 Adob&#x200B;&#x200B;e Analytics 來源連接器。這樣可以保留歷史資料，並在 Customer Journey Analytics 中檢視來自現有 Adob&#x200B;&#x200B;e Analytics 實施的資料，以及可並排檢視來自 Experience Platform Web SDK 新實施的資料。

   Analytics 來源連接器可讓您：

   * 將歷史 Adobe Analytics 報告套裝資料匯入至 Adobe Experience Platform 和 Customer Journey Analytics。

     只要您需要保留歷史 Adob&#x200B;&#x200B;e Analytics 資料，您就可以讓 Analytics 來源連接器持續運作。

   * 在 Customer Journey Analytics 中檢視透過原始 Adob&#x200B;&#x200B;e Analytics 實施 (AppMeasurement、Analytics 擴充功能或 Web SDK 擴充功能) 收集的資料。您可以將此資料與 Web SDK 新實施的資料並排進行比較。

     您可以讓 Analytics 來源連接器繼續運作，直到您熟悉並適應這些差異為止。 <!--elaborate on what those differences are? -->

   獨立實施 Analytics 來源連接器並不是使用 Customer Journey Analytics 的長期建議方法。這是因為高度延遲、混亂複雜的結構描述、依賴 Adob&#x200B;&#x200B;e Analytics 命名法 (prop、eVar 等)，以及最後從 Analytics 來源連接器轉移到建議的 Web SDK 實施很困難。

### 詳細的建議升級步驟

以下步驟概述了從 Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics 的建議流程。

每個步驟都提供更詳細過程的高層解釋。按照每個步驟的連結完成其相關任務，然後返回此頁面並繼續執行該流程的下一步。

1. [規劃您的 XDM 結構描述架構](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)。

1. [在 Adobe Experience Platform 中建立您所要的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   建立結構描述時，請考慮以下選項：

   * 如果要將 Customer Journey Analytics 與 RTCDP 整合，您必須在結構描述啟用&#x200B;**[!UICONTROL 設定檔]**&#x200B;選項，如「[建立 XDM 結構描述以搭配 Customer Journey Analytics 使用](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)」中所述。啟用此選項後，根據此結構將資料攝取至資料集時，該資料就會合併至即時客戶輪廓中。

   * 如果你想包含串流媒體資料，你必須[設定結構描述以攝取和使用串流資料](/help/data-ingestion/streaming.md)。

1. [在 Adobe Experience Platform 中建立資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)。

1. (選用) 如果您在 Adob&#x200B;&#x200B;e Analytics 中使用分類資料，則可以將分類資料新增至 Customer Journey Analytics 中的資料集。

   若要如此做，[要為每個含有分類資料的維度建立查詢資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

1. 對於使用 AppMeasurement 或 Analytics 擴充功能 (標記) 的 Adob&#x200B;&#x200B;e Analytics 實施，[在 Adob&#x200B;&#x200B;e Experience Platform 中建立資料流](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)。 <!-- Is this correct? Will customers on the Web SDK already have a datastream that they only need to add AEP as a service to? Or does this step apply to everyone?-->

   對於使用Web SDK的Adobe Analytics實作，資料流已存在。 如需詳細資訊，請參閱[設定您現有的Adobe Analytics Web SDK實作以傳送資料至Platform](/help/getting-started/cja-upgrade/cja-upgrade-existing-adobe-analytics-websdk.md)。

1. [將 Adobe Experience Platform 即服務新增至資料流](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)。

1. (選用) 如果您想將 Customer Journey Analytics 與 Adob&#x200B;&#x200B;e Journey Optimizer 整合，請在實施中使用個人化物件以便在 Adob&#x200B;&#x200B;e Journey Optimizer 中使用。

1. 展開描述如何為 Customer Journey Analytics 實施 Experience Platform Web SDK 的部分，然後完成相關步驟：

   +++手動實施 (JS 檔案)

   1. [將 alloy.js 新增至您的網站](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/edge/fundamentals/installing-the-sdk#option-2-installing-the-prebuilt-standalone-version%22)。

   1. 填入 XDM 物件並將其傳送至資料流。

+++

   +++標記

   1. [建立標記屬性並新增 Adobe Experience Platform Web SDK 擴充功能](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)。

   1. [將 Adobe Experience Platform Web SDK 擴充功能新增至您的標記屬性](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)

   1. [在您的網站上實施載入程式標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)。

   1. [新增 XDM 資料收集邏輯至您的標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)。

+++

+++ API

   1. 使用 Edge Network API 將資料傳送到所需的資料流。

+++

1. [驗證您的 Web SDK 實施是否正在將資料傳送到資料集](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)。

1. [在 Customer Journey Analytics 中建立連線](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)。

1. (選用) 將網路資料與其他管道的資料 (例如呼叫中心資料) 連結起來。

   您可以透過為 Customer Journey Analytics 連線新增其他資料集來實現此目的，如[匯入呼叫中心和網頁資料](/help/use-cases/cross-channel/call-center.md)所述。

1. [在 Customer Journey Analytics 中建立資料檢視](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)。

1. [驗證資料是否流入 Customer Journey Analytics 中的資料檢視](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)。

1. 在您的Adobe Analytics環境中，[使用Analytics詳細目錄](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/analytics-inventory)檢視您的Adobe Analytics環境的完整總覽，包括專案和元件數量、報表套裝數量、使用者數量等。

1. [移轉專案和元件](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)。

   <!-- You might not want to do this, based on the schema? Ask Zach. Will it work if you have all new schema fields? What would you want to just build from scratch. Maybe everything? -->

1. (選用) 如果您使用 Adob&#x200B;&#x200B;e Analytics 中的行銷管道，則可以[在 Customer Journey Analytics 中建立行銷管道派生欄位](/help/data-views/derived-fields/derived-fields.md#marketing-channels)。

   派生欄位是 Adob&#x200B;&#x200B;e Customer Journey Analytics 中即時報告的重要層面。衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。

   派生欄位的用途是定義派生行銷管道欄位，該欄位會根據一個或多個條件 (例如，URL 參數、頁面 URL 或頁面名稱) 來確定適當的行銷管道。

   使用衍生欄位中的[行銷管道功能範本](/help/data-views/derived-fields/derived-fields.md#marketing-channels)，可以快速建立行銷管道的衍生欄位。

1. 將舊實施 Adob&#x200B;&#x200B;e Analytics 中的資料與新實施 Customer Journey Analytics 中的資料進行比較，確保您了解所有差異及其存在的原因。 <!-- Expound on this. Link to somewhere? There will be a lot of differences. -->

1. 使用 Analytics 來源連接器從 Adob&#x200B;&#x200B;e Analytics 提取歷史資料：

   >[!NOTE]
   >
   >如果您之前尚未建立 Analytics 來源連接器，請依照下列步驟進行。
   >
   >如果您已將 Analytics 來源連接器與 Customer Journey Analytics 結合使用，請依照[從 Analytics 來源連接器轉換至適用於 Customer Journey Analytics 的 Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)」中的步驟進行。

   1. [建立 Analytics 來源連接器的 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

   1. 如果您還沒有 Analytics 來源連接器，可[建立 Analytics 來源連接器並將欄位對應到 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

      或

      如果您已擁有 Analytics 來源連接器，則可[將欄位從來源連接器對應到 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

   1. [將 Analytics 來源連接器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. 規劃使用者上線。

   如同在 Adobe Analytics 一樣，Analysis Workspace 是 Customer Journey Analytics 中面向使用者的主要工具。不過，在 Customer Journey Analytics 中使用 Analysis Workspace 時，使用者需要注意一些主要差異。

   您應該給使用者充足的時間 (3 - 6 個月) 來熟悉 Analysis Workspace 在 Customer Journey Analytics 中的主要差異。

   有關 Adobe Analytics 和 Customer Journey Analytics 之間一些主要差異的資訊，請參閱「[Adobe Analytics 使用者的使用手冊](/help/getting-started/aa-to-cja-user.md)」。

1. 了解關於 [Customer Journey Analytics 中的功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。Customer Journey Analytics 支援大多數 Adob&#x200B;&#x200B;e Analytics 功能，Customer Journey Analytics 還提供了許多附加功能。

1. 當您的 Customer Journey Analytics Web SDK 實施完成並且您對所收集的資料感到滿意時，可停用 Adob&#x200B;&#x200B;e Analytics。

   Adobe 建議您在實施 Customer Journey Analytics 後，讓 Adob&#x200B;&#x200B;e Analytics 環境持續執行一段時間。

   若要了解更多有關升級期間和升級後 Adob&#x200B;&#x200B;e Analytics 的使用情況，以及停用 Adob&#x200B;&#x200B;e Analytics 的建議時間，請參閱「[評估升級至 Customer Journey Analytics 後需要使用 Adobe Analytics 多長的時間](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md)」。

## 以動態方式為您的組織產生升級步驟

根據數個因素，例如時間表和資源限制，[瞭解建議的升級步驟](#recommended-upgrade-steps-for-most-organizations)中所述的建議升級步驟可能對您的組織不實用。 在這種情況下，您可以根據組織獨特的情況動態產生升級步驟。 產生這些步驟的程式會依您是否已存取Customer Journey Analytics而有所不同。

### 適用於有權存取Customer Journey Analytics的客戶

若要根據本身組織的獨特情況以動態方式產生升級步驟：

1. 完成Customer Journey Analytics升級指南。

   在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 請依照熒幕上的指示操作。

   完成本升級指南後，系統會提供逐步指示，概述組織需求專屬的最佳升級步驟。 這些升級步驟最能符合您現有的Adobe Analytics環境和Customer Journey Analytics的目標。 升級步驟可作為分享連結或可下載的.csv檔案提供。

1. 按照產生的步驟說明來升級至 Customer Journey Analytics。

### 針對尚未存取Customer Journey Analytics的客戶

若要根據本身組織的獨特情況以動態方式產生升級步驟：

1. 請聯絡您的Adobe客戶團隊，以完成Customer Journey Analytics升級指南。

   您的Adobe帳戶團隊可以協助您完成升級指南，並提供一個.csv檔案給您，檔案中包含您的問題、您的回答以及貴組織專屬的動態產生升級步驟。

   在聯絡您的Adobe客戶團隊之前，請熟悉Customer Journey Analytics升級指南中包含的問題並確定您的答案。 Customer Journey Analytics升級指南包含下列問題和可能的答案：


   | 問題 | 可用答案 | 其他資訊 |
   |---------|----------|---------|
   | 選取描述您目前 Adobe Analytics 實作的選項。此資訊可能會影響您升級到 Customer Journey Analytics 時可用的替代升級選項。 | 選取一項： <ul><li>**AppMeasurement：**<br/>&#x200B;在頁面上載入AppMeasurement.js，並使用s物件(例如s.eVar1)傳送資料至Adobe的JavaScript實作。</li><li>**Adobe Analytics擴充功能（標籤）：** <br/>載入Adobe Experience Platform Data Collection （先前稱為Launch）的標籤實作。 此標籤已安裝 Adobe Analytics 擴充功能。</li><li>**Experience Platform Web SDK擴充功能（標籤）：**<br/>&#x200B;載入Adobe Experience Platform Data Collection （先前稱為Launch）的標籤實作。 此標籤已安裝 Web SDK 擴充功能。</li><li>**Experience Platform Web SDK (alloy.js)：**&#x200B;在頁面上載入Web SDK資料庫(alloy.js)，並使用JSON裝載將資料傳送至Adobe的JavaScript實作。</li><li>**大量資料插入API：**<br/>&#x200B;使用資料插入API或大量資料插入API的實作。</li><li>**Experience Platform Mobile SDK：**<br/>&#x200B;使用Adobe Experience Platform Mobile SDK的實作。</li><li>**使用協力廠商標籤管理工具的AppMeasurement：**<br/>&#x200B;使用協力廠商標籤管理工具的實作。</li><li>**非Adobe Analytics產品：**<br/>&#x200B;為Adobe Analytics以外的產品(例如Google Analytics)收集資料的實作。 從非 Adobe Analytics 產品升級至 Customer Journey Analytics 時，選取此選項會停用升級指南中多個不適用的選項。 </li><li>**我不知道：**<br/>&#x200B;如果您不是管理實作的人員，您可以暫時選取此選項。</li></ul><p>如適用，請選取：<ul><li>**我們的實作目前使用Analytics來源連線器：**<br/> Analytics來源連線器可讓您輕鬆從Customer Journey Analytics取得價值，但需要您同時支付Adobe Analytics和Customer Journey Analytics的費用。 此指南可以協助您邁向獨立的 Web SDK 實作。</li></ul></p> | <ul><li>[瞭解您的Adobe Analytics實作及其對您升級至Customer Journey Analytics的影響](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md#understand-your-adobe-analytics-implementation-and-how-it-affects-your-upgrade-to-customer-journey-analytics)</li><li>[從Analytics來源聯結器轉換至Customer Journey Analytics的Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)</li></ul> |
   | 大部分 Adobe Analytics 功能均可在 Customer Journey Analytics 中取得。不過，在升級過程中需要考慮以下功能。請選取您計劃使用的任何項目。 | 請選取所有適合的項目：<ul><li>**Adobe Analytics的歷史資料：**</br>&#x200B;將您的Adobe Analytics歷史報表套裝資料匯入Adobe Experience Platform和Customer Journey Analytics。</li><li>**來自Adobe Analytics的元件和專案：**</br>&#x200B;來自Adobe Analytics的元件包括：專案（及其相關自由表格和視覺效果）、區段和計算量度。</li><li>**Activity Map覆蓋和連結追蹤：**</br>&#x200B;瀏覽器擴充功能可讓您在網站上將連結追蹤資料顯示為覆蓋。</li><li>**分類資料：**</br>&#x200B;將資料群組或分類為個別的維度。</li><li>**行銷管道：**</br>&#x200B;建立分類客戶如何到達您網站的規則。</li><li>**Data Warehouse：**</br>&#x200B;以試算表格式從Adobe Analytics匯出已處理的資料。</li><li>**資料摘要：**Customer Journey Analytics尚未提供資料摘要的確切替代專案。 不過，類似的功能可以透過如完整表格匯出、Platform資料集匯出、BI工具整合及報告API等功能來達成。</br></li><li>**串流媒體資料：**</br> Adobe Analytics和Customer Journey Analytics的附加元件，專門處理媒體的資料收集，例如音訊、視訊或串流內容。</li></ul> | <ul><li>[瞭解升級至Customer Journey Analytics時的Adobe Analytics功能支援](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)</li></ul> |
   | 大部分的新功能均可在 Customer Journey Analytics 中取得。不過，在升級過程中需要考慮以下功能。請選取您計劃使用的任何項目。 | 請選取所有適合的項目：<ul><li>**將收集的資料與其他來源的資料繫結（例如連絡中心資料）：**</br>（建議）將各種Web、行動及離線屬性的資料繫結，以建立客戶行為的單一整合檢視。 這種結合來自其他管道之分析資料的功能，是 Customer Journey Analytics 的主要使用案例。</li><li>**使用自訂維度拼接來自其他資料集的點選：**<br/>&#x200B;如果任何資料集不共用主要識別碼(例如Experience Cloud ID)，您仍然可以使用其他維度（例如登入使用者名稱或電子郵件地址）拼接該資料。</li><li>**與Adobe Journey Optimizer整合：**<br/>&#x200B;向客戶傳遞連線、情境式和個人化的體驗。</li><li>**與Adobe Real-Time CDP整合：**<br/>&#x200B;結合來自多個來源的設定檔資料，以根據使用者特徵產生對象和區段。</li><li>**與Adobe Target (A4T)整合：**<br/> Adobe建議針對個人化使用案例與Adobe Journey Optimizer整合。 與 Adobe Target 整合是可行的作法，但僅是短期的解決方案。</li><li>**與Adobe Audience Manager整合：**<br/> Adobe建議針對以受眾為基礎的使用案例，與Adobe Real-time CDP整合。 與 Audience Manager 整合是可行的作法，但僅是短期的解決方案。</li></ul> | [瞭解Customer Journey Analytics獨有的功能](/help/getting-started/cja-upgrade/cja-upgrade-customer-journey-analytics-features.md) |
   | 選取您計劃最終如何使用 Adobe Analytics 和 Customer Journey Analytics： | 選取一項： <ul><li>**我打算從Adobe Analytics完全移至Customer Journey Analytics：**<br/>（建議） Adobe建議您從Adobe Analytics完全轉換至Customer Journey Analytics。 在轉移期間，您應規劃同時使用 Adobe Analytics 和 Customer Journey Analytics，以便執行並列資料對照。資料經確認無誤後，即可停用 Adobe Analytics。</li><li>**我打算保留兩項Analytics產品：**<br/>（不建議）如果您選取此選項，您與Adobe的合約中會包含Adobe Analytics和Customer Journey Analytics，而這兩者可能會隨著時間推移而讓貴組織付出更高的代價。</li></ul> | [評估升級至Customer Journey Analytics後何時停用Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md) |
   | 選取您想要如何設定 Customer Journey Analytics 結構描述： | 選取一項： <ul><li>**我想要使用為我的組織量身打造的結構描述：**</br>（建議）自訂您的結構描述可讓您的組織僅追蹤您需要的內容，並避免因雜亂和不需要的欄位而造成的額外負荷。 此選項包括 Web SDK 新增的欄位群組和您的組織自訂的欄位群組。</li><li>**我想要使用預設的Adobe Analytics結構描述：**</br>（不建議） Adobe Analytics結構描述包含超過一千個欄位，這可能會導致結構描述雜亂而複雜。 您的組織將被迫繼續遵守 prop 和 eVar 的概念，而這是 Customer Journey Analytics 中未使用的舊版概念。與其他 Adobe Experience Platform 服務的整合更加困難。</li></ul> | [選擇您的Customer Journey Analytics結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) |
   | 選取您實作 Customer Journey Analytics 的偏好方式： | <ul><li>**手動實作(alloy.js)：**<br/>&#x200B;在網站的每個頁面上包含Web SDK資料庫(alloy.js)。</li><li>**標籤：**<br/>（建議）如果您尚未使用標籤，請在您的網站上安裝標籤載入器。 如果您已使用標記，則可以新增 Web SDK 擴充功能至您的標記屬性。此選項包括在 Adobe Experience Platform 資料收集和第三方標記管理系統中使用標記的實作。</li><li>**API：**<br/>&#x200B;使用資料收集API將資料直接傳送至資料流。 同時支援未驗證 (用戶端對伺服器) 和已驗證 (伺服器對伺服器) 類型。</li></ul> | [瞭解升級至Customer Journey Analytics時的Web SDK實作選項](/help/getting-started/cja-upgrade/cja-upgrade-websdk-implementation.md) |
   | （選用）選取替代升級方法 | <ul><li>**Soley使用Analytics來源聯結器：**<br/>（不建議）您可以將Analytics來源聯結器用作Customer Journey Analytics的唯一實作路徑。<p>此選項可快速將資料傳送至Customer Journey Analytics，以節省實作時間。 然而，這種作法有一些缺點，例如較高的延遲和未來難以脫離 Adobe Analytics。</p></li><li>**我想將我的AppMeasurement邏輯與Web SDK搭配使用：**<br/>&#x200B;不要透過XDM物件傳送資料，而是透過資料物件以AppMeasurement格式傳送您的所有變數。<p>此選項可讓您將您的AppMeasurement邏輯對應至XDM，而不是從頭開始填入XDM物件，以節省實作時間。 然而，這種作法會隨時間變得更加複雜，因為您將來新增的任何欄位都必須對應至資料流中的 XDM。</p></li><li>**我想要在不進行額外設定的情況下將我的資料層傳送到Adobe：**<br/>&#x200B;您可以透過資料物件將整個資料層傳送到Adobe，而不透過XDM物件傳送資料。<p>此選項可讓您將資料層對應至XDM，而不是從頭開始填入XDM物件，以節省實作時間。 然而，這種對應會帶來繁重的工作量，因為其中有大量 Adobe 無法快速理解的資料。此一選項也會隨時間變得更加複雜，因為您將來新增到資料中的任何欄位都必須對應至資料流中的 XDM。</p></li></ul> | <ul><li>[升級替代方案：僅使用Analytics來源聯結器升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)</li><li>[升級替代方案：將AppMeasurement資料收集與Experience Platform Web SDK和Customer Journey Analytics搭配使用](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)</li><li>[升級替代方案：將資料層傳送至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-data-layer.md)</li></ul> |

   與您的Adobe客戶團隊完成本升級指南後，系統會為您提供.csv檔案，檔案中包含問題、您的答案，以及動態產生的升級步驟，這些步驟最符合您現有的Adobe Analytics環境和Customer Journey Analytics的目標。

1. 請依照.csv檔案中產生的逐步指示，升級至Customer Journey Analytics。

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->
