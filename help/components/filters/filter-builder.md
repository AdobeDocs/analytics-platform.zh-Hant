---
description: 篩選器產生器提供的畫布可用來拖放量度Dimension、篩選器和事件，以便根據容器階層邏輯、規則和運運算元來篩選人員。 此整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨造訪和事件的人員屬性和動作。
title: 建立篩選器
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: e97f206e2c2f00d32e7e06d56fcc84819fe329c6
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 24%

---

# 篩選產生器

此 [!UICONTROL 篩選產生器] 可讓您建立簡單或複雜的篩選器，用於識別跨造訪和事件的人員屬性和動作。 它提供畫布來拖放量度維度、事件或其他篩選器，以便根據階層邏輯、規則和運運算元來篩選人員。

如需有關如何建立僅套用至建立篩選之專案的快速篩選的資訊，請參閱 [快速篩選](/help/components/filters/quick-filters.md).

## 存取篩選產生器

您可以透過下列任何方式存取篩選產生器：

* **頂端導覽**：按一下 **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 元件]** > **[!UICONTROL 篩選器]**.
* **[!UICONTROL Analysis Workspace]**：在Analysis Workspace中開啟專案後，選取 **[!UICONTROL +元件]** > **[!UICONTROL 建立篩選器]**.
* **[!UICONTROL Report Builder]**： [在Report Builder中使用篩選器](/help/report-builder/work-with-filters.md).

## 產生器條件概觀 {#section_F61C4268A5974C788629399ADE1E6E7C}

您可以新增規則定義和容器以定義篩選器。 (如需有關存取篩選產生器的資訊，請參閱 [存取篩選產生器](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

| UI 元素 | 說明 |
| --- | --- |
| **[!UICONTROL 標題]** | 為篩選器命名 |
| **[!UICONTROL 說明]** | 提供篩選的詳細說明。 |
| **[!UICONTROL 標記]** | [標籤篩選器](/help/components/filters/manage-filters.md) 您是從現有標籤清單中挑選標籤或建立新標籤來建立。 |
| **[!UICONTROL 定義]** | 這裡是您 [建立及設定篩選器](/help/components/filters/filters-overview.md)，新增規則，以及巢狀內嵌和排序容器。 |
| **[!UICONTROL 包括]** | (頂層容器選擇器.) 讓您選取頂層 [容器](/help/components/filters/filters-overview.md) ( [!UICONTROL 個人]， [!UICONTROL 工作階段]， [!UICONTROL 事件])。 預設的頂層容器為「事件」容器。 |
| **[!UICONTROL 選項]** | （齒輪）圖示 | <ul><li>**[!UICONTROL +新增容器]**：可讓您新增容器（在頂層容器下）至篩選定義。</li><li>**[!UICONTROL 排除]**：可讓您透過排除一或多個維度、篩選器或量度來定義篩選器。</li></ul> |
| **[!UICONTROL 維度]** | 從「Dimension」清單拖放過來的元件（橘色側欄）。 |
| **[!UICONTROL 運算子]** | 您可以使用選取的運算子來比較和限制值。（等於、不等於、包含、包含全部等） |
| **[!UICONTROL 值]** | 您針對維度、篩選器或量度所輸入或選取的值。 |
| **[!UICONTROL 歸因模型]** | 這些模型僅適用於維度，可決定要篩選的維度值。 Dimension模型在循序篩選中特別有用。<ul><li>**[!UICONTROL 重複]** (預設值)：包含維度的例項和持續值。</li><li>**[!UICONTROL 例項]**：包含維度的例項。</li><li>**[!UICONTROL 非重複例項]**：包含維度的唯一例項 (非重複)。這是在排除重複例項時套用於「流量」中的模型。</li></ul>如需範例，請參閱下方的「歸因模型」一節。 |
| **[!UICONTROL And/Or/Then]** | 指派容器或規則之間的 [!UICONTROL AND/OR/THEN] 運算子。THEN 運算子可讓您 [定義循序篩選器](/help/components/filters/filters-overview.md). |
| **[!UICONTROL 量度]** | （綠色側欄）從量度清單拖放過來的量度。 |
| **[!UICONTROL X]** | （刪除）可用來刪除這個部分的篩選定義。 |
| **[!UICONTROL 透過篩選器建立對象]** | 從篩選器建立受眾時，可讓您與Adobe Experience Platform共用篩選器以供啟用。 [了解更多...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL 搜尋元件]** | 搜尋維度、篩選器或量度清單。 |
| **[!UICONTROL 維度]** | （清單）可包含在篩選器中的維度清單。 按一下標題以展開。 |
| **[!UICONTROL 量度]** | 您可以納入篩選器中的量度清單。 按一下標題以展開。 |
| **[!UICONTROL 篩選條件]** | 可包含在篩選器中的現有篩選器清單。 按一下標題以展開。 |
| **[!UICONTROL 資料檢視選擇器]** | 可讓您選取要將此篩選器儲存哪個報表套裝底下。 您仍可在所有資料檢視中使用該篩選器。 |
| **[!UICONTROL 篩選器預覽]** | 可讓您預覽關鍵量度，以檢視您是否具備有效的篩選器以及篩選器的廣度。 代表資料集的劃分，您可以預期資料集將會顯示您是否套用此篩選器。 顯示3個同心圓和一個清單，用以顯示相符專案的數目和百分比 [!UICONTROL 人員]， [!UICONTROL 工作階段]、和 [!UICONTROL 報表執行] 用於針對資料集執行的篩選。<p>此圖表會在您建立或變更篩選器定義後立即更新。 |
| **[!UICONTROL 儲存]**&#x200B;或&#x200B;**[!UICONTROL 取消]** | 儲存或取消篩選器。 按一下 **[!UICONTROL 儲存]**，系統就會將您帶至「篩選器管理器」，讓您管理篩選器。 |

## 建立篩選器 {#build-filters}

1. 只要將Dimension、篩選器或量度事件從左窗格拖曳至 [!UICONTROL 定義] 欄位。

   ![](assets/drag_n_drop_dimension.png)

1. 從下拉式選單中設定[運算子](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=zh-Hant)。
1. 針對選取的項目輸入或選取值。
1. 必要時使用 **[!UICONTROL And]**、**[!UICONTROL Or]** 或 **[!UICONTROL Then]** 規則新增額外的限制。
1. 放置容器並設定規則後，可在右上角的驗證圖表中檢視篩選結果。 驗證器會指出與您建立之篩選器相符之頁面檢視、造訪次數和不重複人員的百分比與絕對數量。
1. 在&#x200B;**[!UICONTROL 「標記」]**&#x200B;底下，選取現有標記或建立新標記即可[標記](/help/components/filters/manage-filters.md)容器。
1. 按一下 **[!UICONTROL 儲存]** 以儲存篩選。

   您被帶到 [篩選器管理器](/help/components/filters/manage-filters.md)，您可在此透過多種方式標籤、共用及管理您的篩選器。

## 新增容器 {#containers}

您可以[建立容器的架構](/help/components/filters/filters-overview.md)，然後在當中放置邏輯規則和運算子。

1. 按一下 **[!UICONTROL 「選項>新增容器」]**.

   新 [!UICONTROL **事件**] 容器開啟，但不包含 [!UICONTROL **事件**] （頁面檢視）已識別。

   ![](assets/new_container.png)

1. 視需要變更容器類型。
1. 從左窗格將Dimension、篩選器或事件拖曳至容器。
1. 繼續從定義上方的頂層「**[!UICONTROL 選項]**」>「**[!UICONTROL 新增容器]**」按鈕新增容器，或從容器內新增容器以巢狀內嵌邏輯。

   **或**

   選取一或多個規則，然後按一下「**[!UICONTROL 選項]**」>「**[!UICONTROL 從選項新增容器]**」。這會將您的選項轉變成個別容器。

## 使用日期範圍 {#date-ranges}

您可以建立包含滾動日期範圍的篩選器，以回答與持續性促銷活動或事件有關的問題。

例如，您可以輕鬆建立包含「過去60天內購買過一次的人」的篩選器。

您可以建立工作階段容器，並在其中新增 [!UICONTROL 過去60天] 時間範圍和量度 [!UICONTROL 訂單大於或等於1]，且使用AND運運算元。

以下是有關在篩選器中使用滾動式日期範圍的影片：

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## 堆疊篩選器 {#stack}

棧疊篩選器的運作方式是使用&#39;and&#39;運運算元結合每個篩選器中的准則，然後套用結合後的准則。 您可以直接在Workspace專案中或在篩選產生器中完成此作業。

例如，棧疊「行動電話使用者」篩選器和「美國地理」篩選器只會傳回美國行動電話使用者的資料。

您可以將這些篩選器視為建置區塊或模組，您可將其納入篩選器庫中，讓使用者自行選擇使用。 如此一來，您就可以大幅減少所需的篩選器數量。 例如，假設您有40個篩選器：

* 20 個代表不同國家/地區的行動電話使用者 (US_mobile、Germany_mobile、France_mobile、Brazil_mobile 等等)
* 20 個代表不同國家/地區的平板電腦使用者 (US_tablet、Germany_tablet、France_tablet、Brazil_tablet 等等)

透過使用篩選器棧疊，您可以將篩選器數量減少到22個，然後視需要棧疊。 您需要建立下列篩選器：

* 適用於行動使用者的單一篩選器
* 平板電腦使用者適用一個篩選器
* 適用於不同地理區域的20個篩選器

>[!NOTE]
>
>將兩個篩選器棧疊在一起時，預設會使用AND陳述式加以連結。 無法將其變更為 OR 陳述式。

1. 前往篩選產生器。

1. 提供篩選的標題和說明。

1. 按一下 **[!UICONTROL 顯示篩選器]** 以在左側導覽中開啟篩選器清單。

1. 將您要棧疊的篩選器拖曳至篩選器定義畫布。

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

## 歸因模型 {#attribution}

![](assets/attribution-models.jpg)

**範例：eVar1 = A的事件篩選器**

| 範例 | A | A | A (持續) | B | A | C |
|---|---|---|---|---|---|---|
| 重複 | X | X | X | - | X | - |
| 例項 | X | X | - | - | X | - |
| 非重複的例項 | X | - | - | - | X | - |