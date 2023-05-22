---
description: 篩選器生成器提供一個畫布以拖放度量Dimension、篩選器和事件，以根據容器層次結構邏輯、規則和運算子篩選訪問者。 此整合開發工具使您能夠構建和保存簡單或複雜的過濾器，以識別訪問和事件中的訪問者屬性和操作。
title: 建立篩選器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 36%

---

# 篩選器生成器

的 [!UICONTROL 篩選器生成器] 允許您構建簡單或複雜的篩選器，以識別訪問和事件之間的訪問者屬性和操作。 它提供了一個畫布來拖放度量維、事件或其他篩選器，以便根據層次邏輯、規則和運算子篩選訪問者。

有關如何建立僅應用於建立這些篩選器的項目的快速篩選器的資訊，請參見 [快速篩選器](/help/components/filters/quick-filters.md)。

## 訪問篩選器生成器

可以通過以下任何方式訪問篩選器生成器：

* **分析頂部導航**:按一下 **[!UICONTROL 分析]** > **[!UICONTROL 元件]** > **[!UICONTROL 篩選器]**。
* **[!UICONTROL Analysis Workspace]**:在Analysis Workspace開啟項目時，選擇 **[!UICONTROL +元件]** > **[!UICONTROL 建立篩選器]**。
* **[!UICONTROL 報告和分析]**:按一下 **[!UICONTROL 分析]** > **[!UICONTROL 報告]**，開啟現有報告，然後按一下 **篩選** 表徵圖，然後按一下 **[!UICONTROL 添加]**。
* **[!UICONTROL Report Builder]**: [在Report Builder中添加或編輯篩選器](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=zh-Hant)。

## 生成器條件概述 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以添加規則定義和容器來定義篩選器。 (有關訪問篩選器生成器的資訊，請參見 [訪問篩選器生成器](#access-the-filter-builder)。)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL 標題]**:命名篩選器。
1. **[!UICONTROL 說明]**:提供篩選器的說明。
1. **[!UICONTROL 標籤]**: [標籤篩選器](/help/components/filters/manage-filters.md) 您是通過從現有標籤清單中選取或建立新標籤來建立的。
1. **[!UICONTROL 定義]**:這裡是你 [生成和配置篩選器](/help/components/filters/filters-overview.md)、添加規則，以及嵌套和序列容器。
1. **[!UICONTROL 顯示]**：(頂端容器選擇器)用於選擇頂級 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 人員]。 [!UICONTROL 會話]。 [!UICONTROL 事件])。 預設的頂級容器是事件容器。
1. **[!UICONTROL 選項]**：(齒輪) 圖示

   * **[!UICONTROL +添加容器]**:用於向篩選器定義中添加新容器（位於頂級容器下方）。
   * **[!UICONTROL 排除]**:用於通過排除一個或多個維、篩選器或度量來定義篩選器。

1. **[!UICONTROL 維度]**：從維度清單拖放過來的元件 (橘色側欄)。
1. **[!UICONTROL 運算子]**：您可以使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**:您為維、篩選器或度量輸入或選擇的值。
1. **[!UICONTROL 歸因模型]**:這些模型僅可用於維，確定要篩選的維中的值。 Dimension模型在順序濾波器中尤其有用。

   * **[!UICONTROL 重複]** (預設值)：包含維度的例項和持續值。
   * **[!UICONTROL 例項]**：包含維度的例項。
   * **[!UICONTROL 非重複例項]**：包含維度的唯一例項 (非重複)。這是在排除重複例項時套用於「流量」中的模型。

   ![](assets/attribution-models.jpg)

   **示例：事件篩選器，其中eVar1 = A**

   | 範例 | A | A | A (持續) | B | A | C |
   |---|---|---|---|---|---|---|
   | 重複 | X | X | X | - | X | - |
   | 例項 | X | X | - | - | X | - |
   | 非重複的例項 | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**：在容器或規則之間指派 [!UICONTROL AND/OR/THEN] 運算子。THEN運算子允許您 [定義順序篩選器](/help/components/filters/filters-overview.md)。
1. **[!UICONTROL 量度]**：(綠色側欄) 從「量度」清單拖放過來的量度。
1. **[!UICONTROL 比較]**&#x200B;運算子：可使用選取的運算子來比較和限制值。
1. **[!UICONTROL 值]**:您為維、篩選器或度量輸入或選擇的值。
1. **[!UICONTROL X]**:（刪除）用於刪除篩選器定義的此部分。
1. **[!UICONTROL Experience Cloud發佈]**:將Adobe Analytics篩選器發佈到Experience Cloud中，您可以使用篩選器在 [!DNL Audience Manager] 和其他激活通道。 [了解更多...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL 受眾庫]**:Adobe的受眾服務管理訪問者資料到受眾過濾器的轉換。 因此，建立和管理受眾與建立和使用過濾器類似，並增加了將受眾過濾器共用到Experience Cloud的能力。 [了解更多...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL 搜索]**:搜索維、篩選器或度量的清單。
1. **[!UICONTROL 維度]**：(清單) 按一下標題可展開。
1. **[!UICONTROL 量度]**：按一下標題可展開。
1. **[!UICONTROL 篩選器]**:按一下要展開的標題。
1. **[!UICONTROL 資料視圖選擇器]**:用於選擇此篩選器將保存在的報表套件。 您仍然可以在所有資料視圖中使用篩選器。
1. **[!UICONTROL 篩選器預覽]**:用於預覽關鍵度量，以查看是否具有有效篩選器以及篩選器的範圍。 表示如果應用此篩選器，您將會看到的資料集的細分。 顯示3個同心圓和一個清單，以顯示匹配項的數量和百分比 [!UICONTROL 事件]。 [!UICONTROL 人員], [!UICONTROL 會話] 用於針對資料集運行的篩選器。 建立或更改篩選器定義後，此圖表會立即更新。
1. **[!UICONTROL 產品相容性]**:提供Adobe Analytics產品清單(Analysis Workspace, [!UICONTROL 報告和分析]、Data Warehouse)，您建立的篩選器與其相容。 大多數篩選器與所有產品相容。 不過，並非所有運算子和維度均與所有 Analytics 產品相容，特別是 [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html)。在對篩選器定義進行更改後，此圖表會立即更新。
1. **[!UICONTROL 保存]** 或 **[!UICONTROL 取消]**:保存或取消篩選器。 按一下後 **[!UICONTROL 保存]**，您將被帶到「過濾器管理器」(Filter Manager)，在該管理器中可以管理過濾器。

具有嵌入日期範圍的篩選器在Analysis Workspace和 [!UICONTROL 報告和分析]:在Workspace中，具有嵌入日期範圍的篩選器將覆蓋面板日期範圍。 相反， [!UICONTROL 報告和分析] 為您提供報告日期範圍與篩選器的嵌入日期範圍的交集。

## 建立篩選器 {#build-filters}

1. 只需將Dimension、篩選器或度量事件從左窗格拖到 [!UICONTROL 定義] 的子菜單。

   ![](assets/drag_n_drop_dimension.png)

1. 從下拉式選單中設定[運算子](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hant)。
1. 針對選取的項目輸入或選取值。
1. 必要時使用 **[!UICONTROL And]**、**[!UICONTROL Or]** 或 **[!UICONTROL Then]** 規則新增額外的限制。
1. 放置容器並設定規則後，請參閱右上角驗證圖表中篩選器的結果。 驗證程式指示與您建立的篩選器匹配的頁面視圖、訪問和唯一訪問者的百分比和絕對數。
1. 在&#x200B;**[!UICONTROL 「標記」]**&#x200B;底下，選取現有標記或建立新標記即可[標記](/help/components/filters/manage-filters.md)容器。
1. 按一下 **[!UICONTROL 保存]** 按鈕。

   您被帶到 [篩選器管理器](/help/components/filters/manage-filters.md)，您可以通過多種方式標籤、共用和管理篩選器。

## 新增容器 {#section_1C38F15703B44474B0718CEF06639EFD}

您可以[建立容器的架構](/help/components/filters/filters-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下 **[!UICONTROL 「選項」>「添加容器」]**。

   新 [!UICONTROL **事件**] 容器在沒有 [!UICONTROL **事件**] （頁面視圖）已標識。

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 將Dimension、過濾器或事件從左窗格拖到容器。
1. 繼續從定義上方的頂層「**[!UICONTROL 選項]**」>「**[!UICONTROL 新增容器]**」按鈕新增容器，或從容器內新增容器以巢狀內嵌邏輯。

   **或**

   選取一或多個規則，然後按一下「**[!UICONTROL 選項]**」>「**[!UICONTROL 從選項新增容器]**」。這會將您的選項轉變成個別容器。

## 使用日期範圍 {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

您可以構建包含累計日期範圍的篩選器，以回答有關當前市場活動或事件的問題。

例如，您可以輕鬆構建一個包含「過去60天內購買過產品的所有人」的篩選器。

建立會話容器，並在其中添加 [!UICONTROL 最後六十天] 時間範圍和度量 [!UICONTROL 訂單大於或等於1]，使用AND運算子。

以下是在篩選器中使用滾動日期範圍的視頻：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆疊篩選器 {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

堆疊過濾器通過使用「和」運算子將每個過濾器中的標準組合，然後應用組合的標準來工作。 可以直接在Workspace項目中或在篩選器生成器中完成此操作。

例如，堆疊「手機用戶」過濾器和「美國地理」過濾器將只返回美國行動電話用戶的資料。

將這些篩選器視為可以包含在篩選器庫中的構建塊或模組，以便用戶根據自己的需要使用。 這樣，您就可以大大減少所需的篩選器數量。 例如，假定您有40個篩選器：

* 20 個代表不同國家/地區的行動電話使用者 (US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等等)
* 20 個代表不同國家/地區的平板電腦使用者 (US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等等)

通過使用篩選器堆疊，您可以將篩選器計數減少到22，並根據需要堆疊。 您需要建立以下篩選器：

* 移動用戶的一個過濾器
* 平板電腦用戶的一個過濾器
* 20個不同地理的過濾器

>[!NOTE]
>
>堆疊兩個篩選器時，預設情況下它們由AND語句聯接。 無法將其變更為 OR 陳述式。

1. 轉到篩選器生成器。

1. 提供篩選器的標題和說明。

1. 按一下 **[!UICONTROL 顯示篩選器]** 的子菜單。

1. 將要堆疊的濾鏡拖到濾鏡定義畫布。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

## 篩選器模板 {#concept_5098446CC78D441E93B8E4D1D1EA6558}

為常用過濾器使用案例，例如「首次訪問」或「移動設備的維護者」提供過濾器模板。 它們可在Workspace項目和篩選器生成器中用作新篩選器的構建塊。

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
   <td colname="col2">檢視已新增項目至購物車但並未訂購任何項目的訪客的相關資料。在篩選器定義中，容器為訪問。 此順序篩選器的規則是 <p> 購物車新增非空值 </p> <p>Then </p> <p>訂購等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 首次瀏覽次數 </td> 
   <td colname="col2">檢視最多僅造訪過 1 次的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>瀏覽次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非購買者 </td> 
   <td colname="col2">檢視未參與訂購事件的訪客的相關資料。在「過濾器定義」中，容器為訪問者。 此篩選器使用排除邏輯。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非單一頁面瀏覽 (非彈回) </td> 
   <td colname="col2">檢視瀏覽超過一次的訪客的相關資料。在「過濾器定義」中，容器為訪問者。 此篩選器使用排除邏輯。 規則是 <p>單次存取非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 付費搜尋 </td> 
   <td colname="col2">檢視來自付費搜尋的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>付費搜尋等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 購買者 </td> 
   <td colname="col2">檢視參與訂購事件的訪客的相關資料。在「過濾器定義」中，容器為訪問者。 規則是 <p>訂購非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 回訪 </td> 
   <td colname="col2">檢視已瀏覽至少一次的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>瀏覽次數大於 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 單頁造訪次數 </td> 
   <td colname="col2"> 檢視您看到單一頁面值之瀏覽中的資料，即使您可能在該次瀏覽期間提交多個頁面檢視亦同。過濾器中包含帶退出連結事件的單頁訪問。 在篩選器定義中，容器為訪問。 規則是 <p>單頁造訪次數等於 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檢視未加到購物車的產品 </td> 
   <td colname="col2">檢視查看了產品但並未加任何項目到購物車的訪客的相關資料。在篩選器定義中，容器為訪問。 此順序篩選器的規則是 <p>產品檢視非空值 </p> <p>Then </p> <p> 購物車新增等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自促銷活動的瀏覽次數 </td> 
   <td colname="col2">檢視由促銷活動引薦過來的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>追蹤代碼非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視使用行動裝置的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>行動裝置非空值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自免費搜尋的瀏覽次數 </td> 
   <td colname="col2">檢視不是來自付費搜尋的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>付費搜尋等於 0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自非行動裝置的瀏覽次數 </td> 
   <td colname="col2">檢視非使用行動裝置的訪客的相關資料。在篩選器定義中，容器為訪問。 此篩選器使用排除邏輯。 規則是 <p>行動裝置類型等於行動電話 </p> <p>或 </p> <p>行動裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自手機的瀏覽次數 </td> 
   <td colname="col2">檢視使用手機的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>裝置類型等於行動電話。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自搜尋引擎的瀏覽次數 </td> 
   <td colname="col2">檢視由搜尋引擎引薦過來的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>反向連結類型等於搜尋引擎。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自社交網站的瀏覽次數 </td> 
   <td colname="col2">檢視社交網站參照的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>反向連結類型等於社交網路. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來自平板電腦的瀏覽次數 </td> 
   <td colname="col2">檢視使用平板電腦的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>裝置類型等於平板電腦。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有訪客 ID Cookie 的瀏覽次數 </td> 
   <td colname="col2">檢視到您網站 (需要永久性 Cookie) 的訪客的相關資料。在篩選器定義中，容器為訪問。 規則是 <p>永久性 Cookie 等於 1。 </p> </td> 
  </tr> 
 </tbody> 
</table>