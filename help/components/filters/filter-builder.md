---
description: 篩選器產生器提供的畫布可拖放量度Dimension、篩選器和事件，以便根據容器階層邏輯、規則和運運算元來篩選人員。 此整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨造訪和事件的個人屬性和動作。
title: 建立篩選器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 28%

---

# 篩選產生器

此 [!UICONTROL 篩選產生器] 可讓您建立簡單或複雜的篩選器，用於識別跨造訪和事件的個人屬性和動作。 它提供畫布來拖放量度維度、事件或其他篩選器，以便根據階層邏輯、規則和運運算元來篩選人員。

如需如何建立僅套用至建立篩選條件之專案的快速篩選條件的相關資訊，請參閱 [快速篩選](/help/components/filters/quick-filters.md).

## 存取篩選產生器

您可以透過下列任何方式存取「篩選產生器」：

* **Analytics頂端導覽**：按一下 **[!UICONTROL 分析]** > **[!UICONTROL 元件]** > **[!UICONTROL 篩選器]**.
* **[!UICONTROL Analysis Workspace]**：在Analysis Workspace中開啟專案後，選取 **[!UICONTROL +元件]** > **[!UICONTROL 建立篩選器]**.
* **[!UICONTROL Reports &amp; Analytics]**：按一下 **[!UICONTROL 分析]** > **[!UICONTROL 報表]**，開啟現有報表並按一下 **篩選** 圖示並按一下「 」 **[!UICONTROL 新增]**.
* **[!UICONTROL Report Builder]**： [在Report Builder中新增或編輯篩選器](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=zh-Hant).

## 產生器條件概觀 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以新增規則定義和容器來定義篩選器。 (如需有關存取篩選產生器的資訊，請參閱 [存取篩選產生器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 標題]**：為篩選器命名。
1. **[!UICONTROL 說明]**：提供篩選的說明。
1. **[!UICONTROL 標籤]**： [標籤篩選器](/help/components/filters/manage-filters.md) 您是從現有標籤清單中挑選標籤或建立新標籤來建立。
1. **[!UICONTROL 定義]**：這裡是您 [建置和設定篩選器](/help/components/filters/filters-overview.md)，新增規則、巢狀內嵌及排序容器。
1. **[!UICONTROL 顯示]**：(頂端容器選擇器)可讓您選取頂層 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 個人]， [!UICONTROL 工作階段]， [!UICONTROL 事件])。 預設的頂層容器為「事件」容器。
1. **[!UICONTROL 選項]**：(齒輪) 圖示

   * **[!UICONTROL +新增容器]**：可讓您新增容器（在頂層容器下）至篩選定義。
   * **[!UICONTROL 排除]**：可讓您透過排除一或多個維度、篩選器或量度來定義篩選器。

1. **[!UICONTROL 維度]**：從維度清單拖放過來的元件 (橘色側欄)。
1. **[!UICONTROL 運算子]**：您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**：您針對維度、篩選器或量度所輸入或選取的值。
1. **[!UICONTROL 歸因模型]**：這些模型僅適用於維度，可決定要篩選的維度值。 Dimension模型在循序篩選器中特別有用。

   * **[!UICONTROL 重複]** (預設值)：包含維度的例項和持續值。
   * **[!UICONTROL 例項]**：包含維度的例項。
   * **[!UICONTROL 非重複例項]**：包含維度的唯一例項 (非重複)。這是在排除重複例項時套用於「流量」中的模型。

   ![](assets/attribution-models.jpg)

   **範例：eVar1 = A的事件篩選器**

   | 範例 | A | A | A (持續) | B | A | C |
   |---|---|---|---|---|---|---|
   | 重複 | X | X | X | - | X | - |
   | 例項 | X | X | - | - | X | - |
   | 非重複的例項 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**：在容器或規則之間指派 [!UICONTROL AND/OR/THEN] 運算子。THEN運運算元可讓您 [定義循序篩選器](/help/components/filters/filters-overview.md).
1. **[!UICONTROL 量度]**：(綠色側欄) 從「量度」清單拖放過來的量度。
1. **[!UICONTROL 比較]**&#x200B;運算子：可使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**：您針對維度、篩選器或量度所輸入或選取的值。
1. **[!UICONTROL X]**：（刪除）可用來刪除這部分篩選定義。
1. **[!UICONTROL Experience Cloud發佈]**：將Adobe Analytics篩選器發佈至Experience Cloud，可讓您在中的行銷活動使用該篩選器 [!DNL Audience Manager] 和其他啟用管道中的。 [了解更多...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 對象庫]**：Adobe的受眾服務可管理將個人資料轉譯為受眾篩選器的作業。 因此，建立和管理對象類似於建立和使用篩選器，再加上可與Experience Cloud共用對象篩選器的功能。 [了解更多...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜尋]**：搜尋維度、篩選器或量度清單。
1. **[!UICONTROL 維度]**：(清單) 按一下標題可展開。
1. **[!UICONTROL 量度]**：按一下標題可展開。
1. **[!UICONTROL 篩選器]**：按一下標題可展開。
1. **[!UICONTROL 資料檢視選擇器]**：可讓您選取要將此篩選器儲存哪個報表套裝底下。 您仍可在所有資料檢視中使用該篩選器。
1. **[!UICONTROL 篩選器預覽]**：可讓您預覽關鍵量度，以檢視您是否具備有效的篩選器以及篩選器的作用範圍。 代表資料集的劃分，您可預期資料集將會顯示您是否套用此篩選器。 顯示3個同心圓和一個清單，用以顯示相符專案的數目和百分比 [!UICONTROL 事件]， [!UICONTROL 個人]、和 [!UICONTROL 工作階段] 用於針對資料集執行的篩選。 此圖表會在您建立或變更篩選定義後立即更新。
1. **[!UICONTROL 產品相容性]**：提供哪些Adobe Analytics產品(Analysis Workspace、 [!UICONTROL Reports &amp; Analytics]，Data Warehouse)，與您建立的篩選器相容。 大部分篩選器都與所有產品相容。 不過，並非所有運算子和維度均與所有 Analytics 產品相容，特別是 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html)。在您變更篩選器定義後，此圖表會立即更新。
1. **[!UICONTROL 儲存]** 或 **[!UICONTROL 取消]**：儲存或取消篩選器。 按一下 **[!UICONTROL 儲存]**，系統就會將您帶至「篩選器管理器」，讓您管理篩選器。

包含內嵌日期範圍的篩選器在Analysis Workspace中的運作方式持續與 [!UICONTROL Reports &amp; Analytics]：在工作區中，包含內嵌日期範圍的篩選器會覆寫面板日期範圍。 對比之下， [!UICONTROL Reports &amp; Analytics] 會提供報表日期範圍與篩選器內嵌日期範圍的交集。

## 建立篩選器 {#build-filters}

1. 只需將Dimension、篩選器或量度事件從左窗格拖曳至 [!UICONTROL 定義] 欄位。

   ![](assets/drag_n_drop_dimension.png)

1. 從下拉式選單中設定[運算子](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hant)。
1. 針對選取的項目輸入或選取值。
1. 必要時使用 **[!UICONTROL And]**、**[!UICONTROL Or]** 或 **[!UICONTROL Then]** 規則新增額外的限制。
1. 放置容器並設定規則後，可在右上角的驗證圖表中檢視篩選結果。 驗證器會指出符合您建立之篩選器的頁面檢視、造訪次數和不重複人員所佔百分比和絕對數量。
1. 在&#x200B;**[!UICONTROL 「標記」]**&#x200B;底下，選取現有標記或建立新標記即可[標記](/help/components/filters/manage-filters.md)容器。
1. 按一下 **[!UICONTROL 儲存]** 以儲存篩選。

   您會被帶到 [篩選器管理器](/help/components/filters/manage-filters.md)，您可在此透過多種方式標籤、共用及管理您的篩選器。

## 新增容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[建立容器的架構](/help/components/filters/filters-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下 **[!UICONTROL 選項>新增容器]**.

   新 [!UICONTROL **事件**] 容器開啟，但不包含 [!UICONTROL **事件**] （頁面檢視）已識別。

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 將Dimension、篩選器或事件從左窗格拖曳至容器。
1. 繼續從定義上方的頂層「**[!UICONTROL 選項]**」>「**[!UICONTROL 新增容器]**」按鈕新增容器，或從容器內新增容器以巢狀內嵌邏輯。

   **或**

   選取一或多個規則，然後按一下「**[!UICONTROL 選項]**」>「**[!UICONTROL 從選項新增容器]**」。這會將您的選項轉變成個別容器。

## 使用日期範圍 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以建立包含滾動日期範圍的篩選器，以回答與持續性促銷活動或事件有關的問題。

例如，您可以輕鬆建立包含「過去60天內購買過一次的人」的篩選器。

您可以建立工作階段容器，並在其中新增 [!UICONTROL 過去60天] 時間範圍和量度 [!UICONTROL 訂單大於或等於1]，且使用AND運運算元。

以下是有關在篩選中使用滾動式日期範圍的影片：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆疊篩選器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

棧疊篩選的運作方式是使用&#39;and&#39;運運算元結合每個篩選中的條件，然後套用結合的條件。 您可以直接在Workspace專案中或在篩選產生器中完成此作業。

例如，棧疊「行動電話使用者」篩選器和「美國地理」篩選器只會傳回美國行動電話使用者的資料。

將這些篩選器視為建置區塊或模組，您可將其納入篩選器程式庫中，讓使用者在他們認為合適的時候使用。 如此一來，您就可以大幅減少所需的篩選器數量。 例如，假設您有40個篩選器：

* 20 個代表不同國家/地區的行動電話使用者 (US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等等)
* 20 個代表不同國家/地區的平板電腦使用者 (US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等等)

透過使用篩選棧疊，您可以將篩選計數減少到22個，並視需要加以棧疊。 您需要建立下列篩選器：

* 適用於行動使用者的單一篩選器
* 平板電腦使用者適用一個篩選器
* 適用於不同地理位置的20個篩選器

>[!NOTE]
>
>將兩個篩選器棧疊在一起時，預設會使用AND陳述式加以連結。 無法將其變更為 OR 陳述式。

1. 前往篩選產生器。

1. 提供篩選的標題和說明。

1. 按一下 **[!UICONTROL 顯示篩選器]** 以在左側導覽中開啟篩選器清單。

1. 將您要棧疊的篩選器拖曳至篩選器定義畫布。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

## 篩選範本 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

篩選範本是針對常見的篩選使用案例而提供的，例如「首次造訪」或「來自行動裝置的造訪」。 它們可在Workspace專案中和篩選器產生器中作為新篩選器的建置組塊。

範本會以 Adobe 的「A」標誌表示。以下列出範本的範例：

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 範本名稱 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 放棄購物車 </td> 
   <td colname="col2">檢視將專案新增至購物車但未訂購任何專案的人員的資料。 在「篩選器定義」中，容器為「造訪」。 此循序篩選器的規則為 <p> 購物車新增非空值 </p> <p>Then </p> <p>訂購等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 首次瀏覽次數 </td> 
   <td colname="col2">檢視最多造訪過一[1]次之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>瀏覽次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非購買者 </td> 
   <td colname="col2">檢視未參與訂單事件之人員的資料。 在篩選定義中，容器為「訪客」。 此篩選器使用排除邏輯。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非單一頁面瀏覽 (非彈回) </td> 
   <td colname="col2">檢視造訪過多次之人員的資料。 在篩選定義中，容器為「訪客」。 此篩選器使用排除邏輯。 規則是 <p>單次存取非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付費搜尋 </td> 
   <td colname="col2">檢視來自付費搜尋之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>付費搜尋等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 購買者 </td> 
   <td colname="col2">檢視已參與訂單事件之人員的資料。 在篩選定義中，容器為「訪客」。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回訪 </td> 
   <td colname="col2">檢視至少造訪過一次之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>瀏覽次數大於 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 單頁造訪次數 </td> 
   <td colname="col2"> 檢視您看到單一頁面值之瀏覽中的資料，即使您可能在該次瀏覽期間提交多個頁面檢視亦同。包含退出連結事件的單頁造訪次數會納入篩選器中。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>單頁造訪次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檢視未加到購物車的產品 </td> 
   <td colname="col2">檢視已檢視產品但沒有購物車新增之人員的資料。 在「篩選器定義」中，容器為「造訪」。 此循序篩選器的規則為 <p>產品檢視非空值 </p> <p>Then </p> <p> 購物車新增等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自促銷活動的瀏覽次數 </td> 
   <td colname="col2">檢視行銷活動引薦之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>追蹤代碼非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視使用行動裝置之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>行動裝置非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自免費搜尋的瀏覽次數 </td> 
   <td colname="col2">檢視非來自付費搜尋之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>付費搜尋等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自非行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視未使用行動裝置之人員的資料。 在「篩選器定義」中，容器為「造訪」。 此篩選器使用排除邏輯。 規則是 <p>行動裝置類型等於行動電話 </p> <p>或 </p> <p>行動裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自手機的瀏覽次數 </td> 
   <td colname="col2">檢視使用電話之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>裝置類型等於行動電話。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自搜尋引擎的瀏覽次數 </td> 
   <td colname="col2">檢視搜尋引擎所引薦人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>反向連結類型等於搜尋引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自社交網站的瀏覽次數 </td> 
   <td colname="col2">檢視由社交網站引薦之人員的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>反向連結類型等於社交網路. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自平板電腦的瀏覽次數 </td> 
   <td colname="col2">檢視使用平板電腦的使用者資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有訪客 ID Cookie 的瀏覽次數 </td> 
   <td colname="col2">在需要永久性Cookie的地方，檢視從人員到您網站的資料。 在「篩選器定義」中，容器為「造訪」。 規則是 <p>永久性 Cookie 等於 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>