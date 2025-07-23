---
description: 使用地圖視覺效果，在地理地圖視覺效果上繪製資料。
title: 地圖
feature: Visualizations
role: User, Admin
hide: true
hidefromtoc: true
exl-id: 6656b34a-ae1e-4f9f-9c6d-13c54e49625c
source-git-commit: f0ef310f120e278685893308315902e32c54e35e
workflow-type: tm+mt
source-wordcount: '2385'
ht-degree: 13%

---

# 地圖 {#map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="地圖"
>abstract="此視覺效果是透過將量度覆蓋在地圖上來表示量度。這相當實用，可辨識和不同地理區域之間的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="泡泡圖"
>abstract="使用泡泡圖繪製事件。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="熱度圖"
>abstract="使用熱度圖繪圖事件。"

<!-- markdownlint-enable MD034 -->


{{release-limited-testing}}

>[!BEGINSHADEBOX]

_本文會在_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中記錄地圖視覺效果。_<br/>_檢視此文章的[ ](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/map-visualization)AdobeAnalytics_ ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg)版本的&#x200B;_**地圖**。_

>[!ENDSHADEBOX]

Analysis Workspace中的![全域](/help/assets/icons/Globe.svg) **[!UICONTROL 地圖]**&#x200B;視覺效果可讓您建立任何量度（包括計算量度）的視覺效果地圖。 它適合用於識別及比較不同地理區域的量度資料。

## 先決條件

### 在資料檢視中新增內容標籤

在Customer Journey Analytics資料檢視設定中，管理員可以將[內容標籤](/help/data-views/component-settings/overview.md)新增至維度或量度，而Customer Journey Analytics服務（例如[!UICONTROL 地圖]視覺效果）可針對其目的使用這些標籤。

#### 地圖視覺效果所需的內容標籤

地圖視覺效果需要內容標籤才能運作。 如果沒有下列內容標籤，地圖視覺效果就無法運作，因為沒有經緯度資料可以使用。

* [!UICONTROL 地理：緯度]
* [!UICONTROL 地理：經度]

若要新增這些內容標籤：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料檢視]**。

1. 在「資料檢視」頁面上，選取包含您要在地圖視覺效果中分析之資料的資料檢視。

1. 選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，然後選取包含經度資料的維度。

1. 在右側邊欄的&#x200B;**[!UICONTROL 元件設定]**&#x200B;區段中，在&#x200B;**[!UICONTROL 內容標籤]**&#x200B;欄位中，開始輸入`Longitude`，然後從下拉式功能表中選取它。

   ![經緯度內容標籤](assets/map-context-labels-lat-long.png)

1. 重複此程式，將&#x200B;**[!UICONTROL Latitude]**&#x200B;內容標籤新增至包含Latitude資料的維度。

1. 選取「**[!UICONTROL 儲存並繼續]** > **[!UICONTROL 儲存並完成]**」。

#### 地理範本的必要內容標籤

Adobe提供數個[預先建立的範本](/help/analysis-workspace/templates/use-templates.md#web-audience)，這些範本使用地圖視覺效果。 為了使用每個範本，您必須將對應的內容標籤新增到資料檢視中的維度。

以下是範本和所需的內容標籤。 如果沒有這些標籤，範本就無法運作，因為沒有地理資料可使用。

| 範本名稱 | 必要內容標籤 |
|---------|----------|
| 地理國家 | [!UICONTROL 地理：地理國家] |
| 地理區域 | [!UICONTROL 地理：地理區域] |
| 地理城市 | [!UICONTROL 地理：地理城市] |
| 地理美國各州 | [!UICONTROL 地理：地理狀態] |
| Geo US DMA | [!UICONTROL 地理：地理Dma] |

若要新增這些內容標籤：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料檢視]**。

1. 在「資料檢視」頁面上，選取包含您要使用預建範本（使用地圖視覺效果）分析之資料的資料檢視。 在此資料檢視中，您會挑選五個維度，一個包含國家/地區資料、一個包含城市資料、一個包含州資料，以及一個包含DMA資料。 然後，您會以對應的內容標籤來標示這些維度。

1. 選取&#x200B;**[!UICONTROL 元件]**&#x200B;標籤，然後選取包含國家/地區資料的維度。

1. 在右側邊欄的&#x200B;**[!UICONTROL 元件設定]**&#x200B;區段中，在&#x200B;**[!UICONTROL 內容標籤]**&#x200B;欄位中，開始輸入`Geo Country`，然後從下拉式功能表中選取它。

   ![範本內容標籤](assets/map-context-labels-templates.png)

1. 重複此程式，將&#x200B;**[!UICONTROL 地理：地理區域]**、**[!UICONTROL 地理：地理城市]**、**[!UICONTROL 地理：地理狀態]**&#x200B;和&#x200B;**[!UICONTROL 地理：Dma]**&#x200B;內容標籤新增至包含對應資料的每個維度。

1. 選取「**[!UICONTROL 儲存並繼續]** > **[!UICONTROL 儲存並完成]**」。

### 圖形驅動程式必須支援WebGL轉譯

地圖視覺效果使用WebGL顯示圖形。 如果您的圖形驅動程式不支援WebGL轉譯，您可能需要更新驅動程式。

## Customer Journey Analytics與Adobe Analytics中的地圖視覺效果

Customer Journey Analytics中的地圖視覺效果與Adobe Analytics中的地圖視覺效果有以下不同：

| 功能 | Customer Journey Analytics | Adobe Analytics |
|---------|----------|---------|
| 資料來源 | 使用資料檢視中任何可用的區段作為資料來源。 | 提供下列選項： <ul><li>行動裝置緯度/經度</li><li>地理Dimension<br/>代表有關訪客位置（根據訪客的IP位址）的地理細分資料。 </li></ul> |
| 精確度 | 對於具有極高精確度的資料集，您可以在資料檢視中設定維度，以顯示最多5位小數。 這可讓地圖視覺效果在單一米內精確顯示。 <p>如需詳細資訊，請參閱[設定維度的精確位置](#configure-precise-locations-for-dimensions)。</p> | 資料對於[!UICONTROL 國家]、[!UICONTROL 地區]和[!UICONTROL 城市]層級而言是準確的。 （不會移至DMA或郵遞區號層級。） |
| 從選取專案建立區段 | 根據您在地圖視覺效果中選擇的特定區域建立區段。 <p>如需詳細資訊，請參閱[從地圖視覺效果建立區段](#create-a-segment-from-the-map-visualization)。</p> | 根據一般地圖視覺效果中報告的資料建立區段。 |
| 從選取專案建立對象 | 根據您在地圖視覺效果中選擇的特定區域建立對象。 <p>如需詳細資訊，請參閱[從地圖視覺效果建立對象](#create-an-audience-from-the-map-visualization)。 | 無法從地圖視覺效果建立對象。 |
| 從選取專案建立趨勢 | 根據您在地圖視覺效果中選擇的特定區域，建立趨勢線圖視覺效果。 <p>如需詳細資訊，請參閱[從地圖視覺效果建立趨勢線圖](#create-a-trended-line-chart-from-the-map-visualization)。<!-- is this correct? --> | 無法從地圖視覺效果建立趨勢。 |
| 從選取專案新增劃分 | 劃分您在地圖視覺效果中選取之特定區域中的特定維度專案、量度、區段或日期範圍。 <p>如需詳細資訊，請參閱[從地圖視覺效果新增劃分](#add-a-breakdown-from-the-map-visualization)。 | 無法從地圖視覺效果新增劃分。 |

## 開始建構地圖視覺效果 {#begin-building-map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_panel"
>title="設定地圖視覺效果"
>abstract="選擇作為地圖視覺效果基礎的量度或計算量度。如果您想聚焦於資料的特定子集，也可以新增一個片段。<p>您可以在視覺效果呈現後隨時更新此資訊。</p>"

<!-- markdownlint-enable MD034 -->

1. 選取左側邊欄中的&#x200B;[!UICONTROL **視覺效果**]&#x200B;圖示，然後將&#x200B;**[!UICONTROL 地圖]**&#x200B;視覺效果![地圖](/help/assets/icons/Globe.svg)拖曳至包含自由表格的面板。

   或

   以[視覺效果概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)的[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)區段中所述的任何方式新增地圖視覺效果。

   ![地圖設定](assets/map-configuration.png){width="50%"}

1. 指定下列基本資訊以設定地圖視覺效果：

   * **[!UICONTROL 新增量度]**：在量度下拉式清單中，選取量度或計算量度。 （您也可以從左側邊欄拖曳量度。）

     >[!IMPORTANT]
     >
     >如果您選擇的量度已套用[歸因](/help/data-views/component-settings/attribution.md#attribution-models)，則相同的歸因會套用至地圖視覺效果目前檢視區中的經緯度配對。
     >

     <!-- Only choose metrics that use Last Touch as the [attribution model](/help/data-views/component-settings/attribution.md#attribution-models) (this is the default attribution model for all metrics). Choosing a metric that has an attribution model other than Last Touch results in inaccurate map data, because attribution is applied to the latitude and longitude pairs. -->

   * **[!UICONTROL 新增區段]**： （選擇性）在區段下拉式清單中，選取區段。 或從區段清單中拖曳區段。

   在視覺效果建立後，您可以選取視覺效果標題中的編輯圖示![編輯](/help/assets/icons/Edit.svg)，更新此資訊。

1. 請選取「**[!UICONTROL 建置]**」。

   產生附泡泡圖的世界地圖視覺效果。

   ![](assets/map-visualization.png)

1. 繼續[檢視地圖視覺效果](#view-a-map-visualization)和[設定視覺效果設定](#configure-visualization-settings)。

## 檢視地圖視覺效果

1. 如果您尚未建立地圖視覺效果，請依照[開始建立地圖視覺效果](#begin-building-a-map-visualization)中的說明建立地圖視覺效果。

1. 在Analysis Workspace的地圖視覺效果中，執行下列任一項作業：

   * **放大**：您可以透過下列任何方式放大地圖，以放大特定區域：

      * 用滑鼠按兩下地圖。

      * 在觸控板上使用滑鼠滾輪或類似的動作。

      * 在地圖視覺效果上選取加號圖示![放大圖示](assets/map-zoomin-icon.png)。

     地圖會相應縮放。 系統會自動根據縮放層級更新所需的維度（國家/地區>州/省>城市）。

   * **縮小**：您可以透過下列任何方式縮小地圖，檢視較大的區域：

      * 按住Shift鍵，並以滑鼠連按兩下地圖。

      * 在觸控板上使用滑鼠滾輪或類似的動作。

      * 在地圖視覺效果上選取減號圖示![縮小圖示](assets/map-zoomout-icon.png)。

     地圖會相應縮放。 系統會自動根據縮放層級更新所需的維度（國家/地區>州/省>城市）。

   * **旋轉**：您可以在拖曳地圖時按住[!UICONTROL Ctrl]鍵，以二維或三維方式旋轉地圖。

     若要將地圖重設為原始的北對齊，請選取指南針圖示![指南針圖示](assets/map-compass-icon.png)。

   * **選取工具**：您可以選取地圖區域來[建立區段](#create-a-segment-from-the-map-visualization)、[建立趨勢](#create-a-trended-line-chart-from-the-map-visualization)或[新增劃分](#add-a-breakdown-from-the-map-visualization)。

     按一下選取工具![對應選取範圍圖示](assets/map-selection-icon.png)，然後拖曳滑鼠以選取所要的區域。

   * **比較**：您可以並排放置兩個或兩個以上相同專案中的地圖視覺效果。

   * **顯示比較期間（例如逐年比較）**：

      * 顯示負數。

        舉例來說，如果您繪製的是逐年比較量度，則地圖可以在紐約上顯示 -33％。

      * 對於&#x200B;*百分比*&#x200B;類型的量度，叢集會一併平均此百分比。

      * 綠色和紅色色彩配置表示正值和負值。

   * **其他視覺效果設定**：選取視覺效果標題中的「設定」圖示![設定](/help/assets/icons/Setting.svg)，以檢視地圖視覺效果的其他設定。 如需詳細資訊，請參閱[設定視覺效果設定](#configure-visualization-settings)。

1. **儲存**&#x200B;專案，以儲存所有地圖設定 (座標、縮放、旋轉)。
1. （可選）您可以從左側欄拖曳位置維度和量度，填入視覺效果下方的自由表格。

## 設定視覺效果設定

若要設定地圖視覺效果的設定：

1. 在Analysis Workspace中，開啟現有的地圖視覺效果，或[開始建立新的視覺效果](#begin-building-a-map-visualization)。

1. 將滑鼠懸停在地圖視覺效果上，然後選取視覺效果標題中的「設定」圖示![設定](/help/assets/icons/Setting.svg)。

   提供下列選項：

   | 區域 | 設定 | 說明 |
   | --- |--- |--- |
   | **[!UICONTROL 地圖類型]** | | |
   | | **[!UICONTROL 泡泡圖]** | 使用泡泡圖繪圖事件。泡泡圖是多變數圖表，散點圖和等比區域圖的混合體。此檢視為預設。 |
   | | **[!UICONTROL 熱度圖]** | 使用熱度圖繪圖事件。熱度圖是以圖形來顯示資料，並以顏色來代表對照表中所包含的個別值。 |
   | **[!UICONTROL 樣式]** | | |
   | | **[!UICONTROL 色彩主題]** | 顯示熱度圖和泡泡圖的顏色主題。您可以選擇珊瑚色、紅色、綠色或藍色。此預設為珊瑚色。 |
   | | **[!UICONTROL 地圖樣式]** | 您可以從基本、街道、明亮、淺色、深色和衛星中進行選擇。 |
   | | **[!UICONTROL 叢集半徑]** | 將指定像素數內的資料點分組在一起。預設值為 50。<p>只有在選取&#x200B;**[!UICONTROL 泡泡]**&#x200B;做為&#x200B;**[!UICONTROL 對應型別]**&#x200B;時，才能使用此選項。</p> |
   | | **[!UICONTROL 自訂最大值]** | 可讓您變更地圖最大值的臨界值。 調整此值會調整泡泡或熱度圖值（顏色和大小）相對於您設定的自訂最大值的比例。 |
   | | **[!UICONTROL 顯示註解]** | 顯示為此視覺效果所做的註解。 |
   | | **[!UICONTROL 隱藏標題]** | 隱藏視覺效果的標題。 |

## 設定維度的精確位置

如果您的自訂資料集精確度很高，您可以設定地圖視覺效果，以便在單一儀表內達到位置精確度。

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料檢視]**。

1. 選取資料檢視，其中包含您要設定以使用更精確位置的維度。

1. 在資料檢視中，選取「**[!UICONTROL 元件]**」索引標籤。

1. 選取您要設定的維度。

1. 設定維度的精確度等級：

   1. 在您要設定的維度仍然選取的情況下，展開右側邊欄中的&#x200B;**[!UICONTROL 格式]**&#x200B;區段。

      已選取格式區段展開的![維度專案](assets/map-dimension-format.png)

   1. 在&#x200B;**[!UICONTROL 小數位數]**&#x200B;欄位中，變更小數位數以反映所需的精確度等級：

      * **0：**&#x200B;地圖視覺效果中的大區域或國家層級精確。 在Workspace報表中顯示0個小數位數。

      * **1：**&#x200B;精確到地圖視覺效果中的地區或大城市等級。  在Workspace報表中顯示1個小數位數。

      * **2：**&#x200B;地圖視覺效果中的城鎮或郵遞區號層級精確。 在Workspace報表中顯示2個小數位數。

        這是預設選取範圍。

      * **3：**&#x200B;精確到地圖視覺效果中的非常小城鎮或街坊層級。 在Workspace報表中顯示3個小數位數。

      * **4：**&#x200B;精確到地圖視覺效果中的特定地塊或建築物等級。 在Workspace報表中顯示4個小數位數。

      * **5：**&#x200B;地圖視覺效果精確到單公尺。 在Workspace報表中顯示5個小數位數。

1. 選取「**[!UICONTROL 儲存並繼續]** > **[!UICONTROL 儲存並完成]**」。

## 從地圖視覺效果建立區段 {#map-create-segment}

您可以根據您在地圖視覺效果中選取的特定區域建立區段。 當您根據選取的區域建立區段時，任何位於選取範圍經緯度內的資料都會納入區段中。

若要從地圖視覺效果建立區段：

1. 縮放或平移至地圖中包含您要用於區段之資料的區域。

1. 進行下列一項：

   * **若要從地圖目前顯示的所有專案建立區段：**&#x200B;在地圖上的任何位置按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 從目前的檢視建立區段]**。

   * **若要為地圖更具體的區域建立區段：**&#x200B;按一下選取工具![地圖選取範圍圖示](assets/map-selection-icon.png)，拖曳滑鼠以選取想要的區域，然後選取&#x200B;**[!UICONTROL 從選取範圍建立區段]**。

1. 使用區段產生器來定義新區段。 如需詳細資訊，請參閱[區段產生器](/help/components/segments/seg-builder.md)。

## 從地圖視覺效果建立對象

您可以根據您在地圖視覺效果中選擇的特定區域建立對象。

若要從地圖視覺效果建立對象：

1. 縮放或平移至地圖上包含您想用於對象之資料的區域。

1. 進行下列一項：

   * **若要從地圖目前顯示的所有專案建立對象：**&#x200B;在地圖上的任何位置按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 從目前的檢視建立對象]**。

   * **若要針對地圖中更具體的區域建立對象：**&#x200B;按一下選取工具![地圖選取範圍圖示](assets/map-selection-icon.png)，拖曳滑鼠以選取想要的區域，然後選取&#x200B;**[!UICONTROL 從選取範圍建立對象]**。

1. 使用對象產生器來定義新對象。 如需詳細資訊，請參閱[建立和發佈對象](/help/components/audiences/publish.md#audience-builder)中的[對象產生器](/help/components/audiences/publish.md)

## 從地圖視覺效果建立趨勢線圖

您可以在地圖視覺效果中，針對特定區域選取的資料，建立趨勢線圖視覺效果。

若要從地圖視覺效果建立趨勢線圖：

1. 縮放或平移至包含您要用於趨勢線圖之資料的地圖區域。

1. 進行下列一項：

   * **若要從目前地圖中顯示的所有專案建立趨勢線圖：**&#x200B;在地圖上的任何位置按一下滑鼠右鍵，然後從目前檢視中選取&#x200B;**[!UICONTROL 趨勢]**。

   * **若要針對地圖中更具體的區域建立趨勢線圖：**&#x200B;按一下選取工具![地圖選取圖示](assets/map-selection-icon.png)，拖曳滑鼠以選取想要的區域，然後選取&#x200B;**[!UICONTROL 趨勢]**。

   已建置包含趨勢線的線條視覺效果。 如需此視覺效果的詳細資訊，請參閱[線條](/help/analysis-workspace/visualizations/line.md)。

<!--

Can you do this?

## Add a breakdown from the map visualization

You can break down a specific dimension item, metric, segment, or date range for the data within a designated area that you select in the map visualization.

To add a breakdown from the map visualization:

1. (Optional) Zoom in on the specific area of the map that contains the data where you want to add the breakdown.

1. Click the selection tool ![map selection icon](assets/map-selection-icon.png), then drag your mouse to select the desired area.

1. Select **[!UICONTROL Add breakdown]**. 

-->

<!--

Can you do this?

## Export the map visualization as a PDF

To export the map visualization in PDF format:

1. how...

-->

