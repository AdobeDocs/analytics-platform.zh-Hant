---
description: 篩選器產生器提供畫布來拖放量度Dimension、篩選器和事件，以根據容器階層邏輯、規則和運算子來篩選訪客。 這個整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨造訪及頁面點擊的訪客屬性和動作。
title: 建立篩選器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '2054'
ht-degree: 37%

---

# 篩選產生器

此 [!UICONTROL 篩選產生器] 可讓您建立簡單或複雜的篩選器，以識別跨造訪和頁面點擊的訪客屬性和動作。 它提供畫布來拖放量度維度、事件或其他篩選器，以便根據階層邏輯、規則和運算子來篩選訪客。

如需如何建立僅套用至建立專案的快速篩選的相關資訊，請參閱 [快速篩選](/help/components/filters/quick-filters.md).

## 存取篩選產生器

您可以透過下列任一方式存取「篩選產生器」：

* **Analytics頂端導覽**:按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 元件]** > **[!UICONTROL 篩選器]**.
* **[!UICONTROL Analysis Workspace]**:在Analysis Workspace中開啟專案後，選取 **[!UICONTROL +元件]** > **[!UICONTROL 建立篩選]**.
* **[!UICONTROL Reports &amp; Analytics]**:按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 報表]**，開啟現有報表並按一下 **篩選** 圖示，然後按一下 **[!UICONTROL 新增]**.
* **[!UICONTROL Report Builder]**: [在Report Builder中新增或編輯篩選器](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=zh-Hant).

## 產生器條件概觀 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以新增規則定義和容器來定義篩選器。 (如需存取篩選產生器的相關資訊，請參閱 [存取篩選產生器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 標題]**:為篩選器命名。
1. **[!UICONTROL 說明]**:提供篩選器的說明。
1. **[!UICONTROL 標籤]**: [標籤篩選器](/help/components/filters/manage-filters.md) 您是透過選擇現有標籤清單中的標籤或建立新標籤來建立。
1. **[!UICONTROL 定義]**:這裡是你 [建立和設定篩選器](/help/components/filters/filters-overview.md)、新增規則、巢狀內嵌容器及排序容器。
1. **[!UICONTROL 顯示]**：(頂端容器選擇器)可讓您選取頂層 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 人員], [!UICONTROL 工作階段], [!UICONTROL 事件])。 預設的頂層容器是「事件」容器。
1. **[!UICONTROL 選項]**：(齒輪) 圖示

   * **[!UICONTROL +新增容器]**:可讓您新增新容器（在頂層容器下）至篩選器定義。
   * **[!UICONTROL 排除]**:可讓您透過排除一或多個維度、篩選器或量度來定義篩選器。

1. **[!UICONTROL 維度]**：從維度清單拖放過來的元件 (橘色側欄)。
1. **[!UICONTROL 運算子]**：您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**:您針對維度、篩選或量度所輸入或選取的值。
1. **[!UICONTROL 歸因模型]**:這些模型僅適用於維度，可決定要篩選的維度值。 Dimension模型在循序篩選器中特別實用。

   * **[!UICONTROL 重複]** (預設值)：包含維度的例項和持續值。
   * **[!UICONTROL 例項]**：包含維度的例項。
   * **[!UICONTROL 非重複例項]**：包含維度的唯一例項 (非重複)。這是在排除重複例項時套用於「流量」中的模型。

   ![](assets/attribution-models.jpg)

   **範例：eVar1 = A的事件篩選**

   | 範例 | A | A | A (持續) | B | A | C |
   |---|---|---|---|---|---|---|
   | 重複 | X | X | X | - | X | - |
   | 例項 | X | X | - | - | X | - |
   | 非重複的例項 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**：在容器或規則之間指派 [!UICONTROL AND/OR/THEN] 運算子。THEN運算子可讓您 [定義循序篩選器](/help/components/filters/filters-overview.md).
1. **[!UICONTROL 量度]**：(綠色側欄) 從「量度」清單拖放過來的量度。
1. **[!UICONTROL 比較]**&#x200B;運算子：可使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**:您針對維度、篩選或量度所輸入或選取的值。
1. **[!UICONTROL X]**:（刪除）可讓您刪除此部分的篩選器定義。
1. **[!UICONTROL Experience Cloud發佈]**:將Adobe Analytics篩選器發佈至Experience Cloud，可讓您在 [!DNL Audience Manager] 和其他激活通道。 [了解更多...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 受眾程式庫]**:Adobe的受眾服務可管理將訪客資料轉譯為受眾篩選器的過程。 因此，建立和管理對象類似於建立和使用篩選器，再加上可與Experience Cloud共用對象篩選器的能力。 [了解更多...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜尋]**:搜尋維度、篩選器或量度清單。
1. **[!UICONTROL 維度]**：(清單) 按一下標題可展開。
1. **[!UICONTROL 量度]**：按一下標題可展開。
1. **[!UICONTROL 篩選器]**:按一下標題可展開。
1. **[!UICONTROL 資料檢視選取器]**:可讓您選取要將此篩選器儲存於其下的報表套裝。 您仍可在所有資料檢視中使用篩選器。
1. **[!UICONTROL 篩選器預覽]**:可讓您預覽關鍵量度，以查看您是否具備有效的篩選條件以及篩選的範圍。 代表套用此篩選時，您可以看到的資料集劃分。 顯示3個同心圓和一個清單，以顯示符合的數目和百分比 [!UICONTROL 事件], [!UICONTROL 人員]，和 [!UICONTROL 工作階段] ，針對資料集執行篩選。 在您建立或變更篩選器定義後，此圖表會立即更新。
1. **[!UICONTROL 產品相容性]**:提供Adobe Analytics產品的清單(Analysis Workspace、 [!UICONTROL Reports &amp; Analytics],Data Warehouse)，而您建立的篩選器相容。 大多數篩選器與所有產品相容。 不過，並非所有運算子和維度均與所有 Analytics 產品相容，特別是 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html)。在您變更篩選器定義後，此圖表會立即更新。
1. **[!UICONTROL 儲存]** 或 **[!UICONTROL 取消]**:儲存或取消篩選。 按一下 **[!UICONTROL 儲存]**，您會前往「篩選器管理器」，您可於其中管理篩選器。

內嵌日期範圍的篩選器在Analysis Workspace和 [!UICONTROL Reports &amp; Analytics]:在工作區中，包含內嵌日期範圍的篩選器會覆寫面板日期範圍。 相反， [!UICONTROL Reports &amp; Analytics] 提供報表日期範圍與篩選器內嵌日期範圍的交集。

## 建立篩選器 {#build-filters}

1. 只需將Dimension、篩選或量度事件從左窗格拖曳至 [!UICONTROL 定義] 欄位。

   ![](assets/drag_n_drop_dimension.png)

1. 從下拉式選單中設定[運算子](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hant)。
1. 針對選取的項目輸入或選取值。
1. 必要時使用 **[!UICONTROL And]**、**[!UICONTROL Or]** 或 **[!UICONTROL Then]** 規則新增額外的限制。
1. 放置容器並設定規則後，請在右上方的驗證圖表中查看篩選結果。 驗證器會指出與您所建立篩選器相符之頁面檢視、造訪和不重複訪客的百分比和絕對數量。
1. 在&#x200B;**[!UICONTROL 「標記」]**&#x200B;底下，選取現有標記或建立新標記即可[標記](/help/components/filters/manage-filters.md)容器。
1. 按一下 **[!UICONTROL 儲存]** 來儲存篩選器。

   您會被帶至 [篩選器管理器](/help/components/filters/manage-filters.md)，您可在此透過多種方式標籤、共用及管理篩選器。

## 新增容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[建立容器的架構](/help/components/filters/filters-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下 **[!UICONTROL 選項>新增容器]**.

   新 [!UICONTROL **事件**] 容器開啟時沒有 [!UICONTROL **事件**] （頁面檢視）已識別。

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 從左窗格拖曳Dimension、篩選或事件至容器。
1. 繼續從定義上方的頂層「**[!UICONTROL 選項]**」>「**[!UICONTROL 新增容器]**」按鈕新增容器，或從容器內新增容器以巢狀內嵌邏輯。

   **或**

   選取一或多個規則，然後按一下「**[!UICONTROL 選項]**」>「**[!UICONTROL 從選項新增容器]**」。這會將您的選項轉變成個別容器。

## 使用日期範圍 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以建立包含滾動日期範圍的篩選器，以回答與持續性促銷活動或事件有關的問題。

例如，您可以輕鬆建立包含「過去60天內購買過商品的所有人」的篩選器。

您可以建立「工作階段」容器，並在其中新增 [!UICONTROL 最近60天] 時間範圍和量度 [!UICONTROL 訂購大於或等於1]，並搭配AND運算子。

以下是在篩選器中使用滾動日期範圍的影片：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆疊篩選器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

堆疊篩選器的運作方式是使用&#39;and&#39;運算子結合每個篩選器中的准則，然後套用結合後的准則。 您可以直接在工作區專案中或在篩選器產生器中完成此操作。

例如，將「行動電話使用者」篩選器與「美國地理位置」篩選器堆疊，只會傳回美國行動電話使用者的資料。

請將這些篩選器想像成可納入篩選器程式庫的組建區塊或模組，供使用者視需要使用。 如此，您就可大幅減少所需的篩選器數量。 例如，假設您有40個篩選器：

* 20 個代表不同國家/地區的行動電話使用者 (US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等等)
* 20 個代表不同國家/地區的平板電腦使用者 (US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等等)

透過使用篩選器堆疊，您可以將篩選器計數減少至22個，並視需要堆疊。 您需要建立下列篩選器：

* 行動使用者一個篩選器
* 平板電腦使用者一個篩選器
* 20個不同地理位置的篩選器

>[!NOTE]
>
>將兩個篩選器堆疊在一起時，預設會使用AND陳述式加以連結。 無法將其變更為 OR 陳述式。

1. 前往篩選器產生器。

1. 提供篩選器的標題和說明。

1. 按一下 **[!UICONTROL 顯示篩選器]** 以在左側導覽中開啟篩選器清單。

1. 拖曳您要堆疊的篩選器至篩選器定義畫布。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

## 篩選範本 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

篩選範本是針對常見的篩選使用案例而提供，例如「首次造訪」或「來自行動裝置的造訪」。 它們可在工作區專案中和篩選器產生器中，做為新篩選器的建置區塊。

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
   <td colname="col2">檢視已新增項目至購物車但並未訂購任何項目的訪客的相關資料。在篩選定義中，容器為造訪。 此循序篩選的規則為 <p> 購物車新增非空值 </p> <p>Then </p> <p>訂購等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 首次瀏覽次數 </td> 
   <td colname="col2">檢視最多僅造訪過 1 次的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>瀏覽次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非購買者 </td> 
   <td colname="col2">檢視未參與訂購事件的訪客的相關資料。在篩選器定義中，容器為訪客。 此篩選器使用排除邏輯。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非單一頁面瀏覽 (非彈回) </td> 
   <td colname="col2">檢視瀏覽超過一次的訪客的相關資料。在篩選器定義中，容器為訪客。 此篩選器使用排除邏輯。 規則是 <p>單次存取非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付費搜尋 </td> 
   <td colname="col2">檢視來自付費搜尋的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>付費搜尋等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 購買者 </td> 
   <td colname="col2">檢視參與訂購事件的訪客的相關資料。在篩選器定義中，容器為訪客。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回訪 </td> 
   <td colname="col2">檢視已瀏覽至少一次的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>瀏覽次數大於 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 單頁造訪次數 </td> 
   <td colname="col2"> 檢視您看到單一頁面值之瀏覽中的資料，即使您可能在該次瀏覽期間提交多個頁面檢視亦同。篩選器中會包含含有退出連結事件的單頁造訪次數。 在篩選定義中，容器為造訪。 規則是 <p>單頁造訪次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檢視未加到購物車的產品 </td> 
   <td colname="col2">檢視查看了產品但並未加任何項目到購物車的訪客的相關資料。在篩選定義中，容器為造訪。 此循序篩選的規則為 <p>產品檢視非空值 </p> <p>Then </p> <p> 購物車新增等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自促銷活動的瀏覽次數 </td> 
   <td colname="col2">檢視由促銷活動引薦過來的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>追蹤代碼非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視使用行動裝置的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>行動裝置非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自免費搜尋的瀏覽次數 </td> 
   <td colname="col2">檢視不是來自付費搜尋的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>付費搜尋等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自非行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視非使用行動裝置的訪客的相關資料。在篩選定義中，容器為造訪。 此篩選器使用排除邏輯。 規則是 <p>行動裝置類型等於行動電話 </p> <p>或 </p> <p>行動裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自手機的瀏覽次數 </td> 
   <td colname="col2">檢視使用手機的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>裝置類型等於行動電話。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自搜尋引擎的瀏覽次數 </td> 
   <td colname="col2">檢視由搜尋引擎引薦過來的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>反向連結類型等於搜尋引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自社交網站的瀏覽次數 </td> 
   <td colname="col2">檢視社交網站參照的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>反向連結類型等於社交網路. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自平板電腦的瀏覽次數 </td> 
   <td colname="col2">檢視使用平板電腦的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有訪客 ID Cookie 的瀏覽次數 </td> 
   <td colname="col2">檢視到您網站 (需要永久性 Cookie) 的訪客的相關資料。在篩選定義中，容器為造訪。 規則是 <p>永久性 Cookie 等於 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>