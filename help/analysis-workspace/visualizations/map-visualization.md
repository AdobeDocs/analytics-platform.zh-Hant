---
description: 'null'
title: 地圖
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 100%

---


# 地圖

## 概述 {#section_19F740FAF08D47B1AF1EF239A74FC75C}

Analysis Workspace 中的地圖視覺效果

* 可讓您建立任何量度 (包括計算量度) 的視覺化地圖。
* 相當實用，可辨識和比較不同地理區域之間的量度資料。
* 可支援 2 項資料來源：行動裝置使用的經緯度、或網頁使用的地理維度。
* 支援 PDF 匯出。
* 針對圖形顯示使用 WebGL。如果您的顯示卡驅動程式不支援 WebGL 轉譯，您可能需要更新驅動程式。

## 建立地圖視覺效果 {#section_61BBFA3A7BFD48DA8D305A69D9416299}

1. 從視覺效果清單中，將&#x200B;**[!UICONTROL 「地圖」]**&#x200B;拖曳至自由面板:

   ![](assets/map-viz1.png)

1. 從量度清單拖曳量度 (包括計算量度)。
1. 指定您要提取的資料來源。(只有當您已為行動應用程式資料啟用「位置追蹤」時，才會顯示此對話方塊。)

<table id="table_CD54B433464B4282A7524FB187016C47"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>行動裝置緯度/經度</b> </p> </td> 
   <td colname="col2"> <p>此選項代表行動應用程式資料。 </p> <p>只有當您在<span class="ignoretag"><span class="uicontrol">「Analytics</span> &gt; <span class="uicontrol">管理</span> &gt; <span class="uicontrol">報表套裝</span> &gt; <span class="uicontrol">&lt;選取報表套裝&gt;</span> &gt; <span class="uicontrol">編輯設定</span> &gt; <span class="uicontrol">行動管理</span> &gt; <span class="uicontrol">啟用位置追蹤」</span></span>為您的報表套裝啟用此選項時，才會顯示此選項。 </p> <p>這是預設設定 (如果已啟用位置追蹤)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>地理維度</b> </p> </td> 
   <td colname="col2"> <p>此選項代表有關訪客位置的地域劃分資料 (根據訪客 IP 位址)。此資料可轉換為國家、地區和城市。請注意，此資料不會深入至 DMA 或郵遞區號的層級。 </p> <p>幾乎所有報表套裝都會啟用這個維度。如果您尚未啟用，請聯絡 Adobe 客戶服務，以啟用地理報表。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下&#x200B;**[!UICONTROL 「建立」]**。

   您看到的第一張檢視會是「世界視圖」以及與此類似的泡泡圖地圖。

   ![](assets/bubble-world-view.png)

1. 您現在可以

   * 按兩下地圖或使用捲動滾輪來&#x200B;**放大**&#x200B;此地圖，以放大顯示某些區域。地圖會根據游標的位置來縮放顯示。透過縮放互動，所需的維度 (國家/地區 > 州/省 > 城市) 也會根據縮放等級自動更新。
   * 以並排方式&#x200B;**比較**&#x200B;同一個專案中的兩個或多個地圖視覺效果。
   * **顯示比較期間(例如，逐年比較)**：

      * 顯示負數：舉例來說，如果您繪製的是逐年比較量度，則地圖可以在紐約上顯示 -33％。
      * 對於類型為「百分比」的量度，叢集會一併平均分配百分比。
      * 綠/紅色彩配置：正值/負值
   * 按住 [!UICONTROL Ctrl] 鍵並移動地圖，以&#x200B;**旋轉** 2D 或 3D 地圖。

   * 使用下述[設定](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E)，**切換**&#x200B;至不同的檢視 (例如熱度圖)。請注意，泡泡圖檢視是預設設定。


1. **儲存**&#x200B;專案，以儲存所有地圖設定 (座標、縮放、旋轉)。
1. 您可從左側欄拖曳位置維度和量度，填入視覺效果下方的自由表格：

   ![](assets/location-dimensions.png)

## 地圖視覺效果設定 {#section_5F89C620A6AA42BC8E0955478B3A427E}

地圖中有 2 組設定：

右上角的&#x200B;**扳手圖示**&#x200B;可顯示初始對話方塊，您可以在此變更量度和資料來源：

![](assets/map-wrench.png)

按一下&#x200B;**齒輪圖示**&#x200B;則會顯示以下這些視覺效果設定：

| 設定 | 說明 |
|--- |--- |
| 泡泡圖 | 使用泡泡圖繪圖事件。泡泡圖是多變數圖表，散點圖和等比區域圖的混合體。這是預設檢視。 |
| 熱度圖 | 使用熱度圖繪圖事件。熱度圖是以圖形來顯示資料，並以顏色來代表對照表中所包含的個別值。 |
| 樣式：顏色主題 | 顯示熱度圖和泡泡圖的顏色主題。您可以選擇珊瑚色、紅色、綠色或藍色。預設為珊瑚色。 |
| 樣式：地圖樣式 | 您可以選擇基本、街道、明亮、淺色、深色和衛星。 |
| 叢集半徑 | 將指定像素數內的資料點分組在一起。預設為 50。 |
| 自訂最大值 | 可用於變更地圖最大值的臨界值。調整此數值可以調整泡泡圖/熱度圖的值 (顏色和大小) 相對於自訂最大值的比例。 |
