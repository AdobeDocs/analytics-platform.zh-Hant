---
title: 內容分析報表
description: 如何報告內容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: b4325135ec05737a75027ded70e96f599eb0220c
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Content Analytics報表概觀

{{release-limited-testing}}

您可在[Analysis Workspace](/help/analysis-workspace/home.md)中報告、執行分析並深入瞭解Content Analytics。 有特定的Workspace [範本](#template)可供使用，因此您可以立即存取預先填入的Workspace專案，其中包含相關的內容深入分析。

若要從草稿開始報告內容分析：

1. [建立新的](/help/analysis-workspace/build-workspace-project/create-projects.md)或[在Workspace中開啟現有的](/help/analysis-workspace/build-workspace-project/open-projects.md)專案。
1. 請確定您[為Content Analytics報表選取資料檢視](/help/analysis-workspace/c-panels/panels.md#data-view)。 Content Analytics報表僅適用於[已針對Content Analytics設定](/help/content-analytics/config/configuration.md)的資料檢視。
1. 將![表格](/help/assets/icons/Table.svg) [自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)視覺效果拖曳到畫布上。
1. 使用[特定的Content Analytics元件](components.md)和其他一般[元件](/help/components/overview.md) （如篩選器、日期範圍、註解）來建置您的內容分析深入分析。

## 縮圖

系統會根據您在專案中使用的Content Analytics特定維度，顯示資產和維度的縮圖。

![Content Analytics縮圖](../assets/aca-thumbnails.png)

依預設，系統會顯示相關Content Analytics維度的縮圖。 若要設定Content Analytics維度的縮圖顯示：

* 將游標暫留在Content Analytics維度的標題列上。 例如，**[!UICONTROL 資產名稱]**&#x200B;或&#x200B;**[!UICONTROL 體驗識別碼]**。
* 選取![設定](/help/assets/icons/Setting.svg)。
* 在&#x200B;**[!UICONTROL 列設定]**&#x200B;快顯視窗中，在&#x200B;**[!UICONTROL 設定]**&#x200B;下，核取或取消核取&#x200B;**[!UICONTROL 顯示縮圖]**。


## 預覽

對於顯示縮圖的Content Analytics維度列，您可以開啟預覽快顯視窗。

若要開啟具有下列詳細資訊的預覽：

* 選取![資訊大綱](/help/assets/icons/InfoOutline.svg)。 您會看到下列詳細資料。

  | 體驗預覽 | 資產預覽 |
  |---|---|
  | ![內容分析體驗預覽](../assets/aca-experience-preview.png) | ![Content Analytics資產預覽](../assets/aca-asset-preview.png) |
  | 維度名稱（例如，**[!UICONTROL 體驗ID]）** | 資產維度的名稱（例如，**[!UICONTROL 資產識別碼]）** |
  | **[!UICONTROL 曝光次數（所有時間）]**：體驗的曝光次數。 | **[!UICONTROL 曝光次數（所有時間）]**：資產的曝光次數。 |
  | **[!UICONTROL Assets]**：此體驗包含的資產數目。 <br/>選取![劃分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 劃分]**&#x200B;以檢查資產。 | **[!UICONTROL 體驗]**：此資產顯示所在的體驗數目。 <br/>選取![劃分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 劃分]**&#x200B;以檢查資產。 |
  | **[!UICONTROL 第一印象]**：體驗的第一印象日期。 | **[!UICONTROL 第一印象]**：資產第一印象的日期。 |
  | **[!UICONTROL 最近曝光]**：體驗最近曝光的日期。 | **[!UICONTROL 最近曝光次數]**：資產最近曝光的日期。 |
  | **[!UICONTROL 體驗屬性]**：體驗的[屬性](/help/content-analytics/report/components.md#experience-attributes)。 | **[!UICONTROL 資產屬性]**：資產的[屬性](/help/content-analytics/report/components.md#asset-attributes)。 |


## 範本

內容分析[範本](/help/analysis-workspace/templates/use-templates.md)可協助您瞭解哪些內容和內容屬性表現最佳。 範本是[Web channel and Engagement使用案例](/help/analysis-workspace/templates/use-templates.md#web-engagement)的一部分，詳細說明您的內容在精細層次的執行方式。 您可以檢視個別資產或特定屬性的效能。

根據您學到的內容，您可能會執行許多操作。 就像在首頁上促銷高效能資產、個人化特定區段的內容以包含高效能屬性，或輪換已開始陳舊的內容。

若要使用範本：

1. 從主功能表選取&#x200B;**[!UICONTROL Workspace]**。
1. 確保您已選取為Content Analytics設定的資料檢視。
1. 搜尋或使用篩選器(**[!UICONTROL 頻道]**&#x200B;的&#x200B;**[!UICONTROL 網頁]**&#x200B;和[!UICONTROL 使用案例]**的**4}參與&#x200B;]**)來尋找及選取**[!UICONTROL &#x200B;內容分析&#x200B;]**範本。**[!UICONTROL 
1. 選取&#x200B;**[!UICONTROL 使用範本]**。
1. 在&#x200B;**[!UICONTROL 設定範本]**&#x200B;對話方塊中，從&#x200B;**[!UICONTROL 選取轉換量度]**&#x200B;對話方塊中選取量度。 例如，**[!UICONTROL 資產CTR]**。
1. 選取&#x200B;**[!UICONTROL 繼續]**。

**[!UICONTROL Content Analytics概觀]**&#x200B;專案會在[Analysis Workspace](/help/analysis-workspace/home.md)中開啟。 專案包含四個[面板](/help/analysis-workspace/c-panels/panels.md)，每個面板提供[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)和[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)，以回答特定問題：

* **哪些內容表現最好？**
此面板可協助您瞭解哪些體驗以及這些體驗中的哪些資產可促進參與和轉換。 體驗是完整網頁，於特定時間擷取。 一個體驗可以同時包含文字和多個個別影像資產。 資產是個別影像。

  此面板包含下列視覺效果：

   * **體驗**。

     >[!NOTE]
     >
     >只有在您的Content Analytics設定中有[包含體驗](/help/content-analytics/config/guided.md#experience-capture-and-definition)時，才會顯示這些視覺效果。
     > 

      * **體驗CTR**： [摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)視覺效果，顯示體驗CTR。
      * **排名在前的轉換體驗**： [橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果，根據選取的轉換量度顯示排名在前的轉換體驗。
      * **表現最佳的體驗**：表現最佳的體驗的[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （包括[縮圖](#thumbnails)和[預覽](#previews)）。

   * **資產**

      * **資產CTR**
顯示Asset CTR的[摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)視覺效果。
      * **排名在前的轉換資產**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據選取的轉換量度顯示排名最前的轉換資產。
      * **績效最佳的資產**
表現最出色的資產的[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （包括[縮圖](#thumbnails)和[預覽](#previews)）。
      * **Assets — 檢視與轉換。**
[散佈圖](/help/analysis-workspace/visualizations/scatterplot.md)視覺效果，可顯示資產檢視與資產轉換的散佈圖。

* **哪些資產屬性會影響轉換？**
Content Analytics使用AI和GenAI自動指派每個資產中繼資料，例如主題、場景、前景顏色等。 屬性是AI指派的中繼資料標籤，說明資產或體驗中的內容。 例如： <code>前景色彩：紅色</code> 是自動指派的屬性。 視覺效果可協助您識別哪些資產屬性對轉換的貢獻最大。

  此面板包含下列視覺效果：

   * **最常轉換的資產屬性**
[橫條](/help/analysis-workspace/visualizations/horizontal-bar.md)會根據選取的轉換量度顯示最上層轉換資產屬性。
   * **最常轉換的資產屬性與前30天的比較**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據所選的轉換量度，顯示相較於之前30天排名最前的轉換資產屬性。
   * **最常轉換的資產屬性資料**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名最前的轉換屬性。 選取表格中的列以更新「屬性趨勢」視覺效果。
   * **屬性趨勢**
顯示所選最上層轉換資產屬性之屬性趨勢的[線](/help/analysis-workspace/visualizations/line.md)視覺效果。
   * **資產前景色彩**
範例[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)比較單一資產屬性類別（前景色彩）中專案的效能。 您可以使用其他資產屬性類別維度來取代此資產屬性。

* **哪些體驗屬性對轉換有貢獻？**

  >[!NOTE]
  >
  >只有當您在Content Analytics設定中包含[體驗](/help/content-analytics/config/guided.md#experience-capture-and-definition)時，此面板才會顯示。
  > 

  資產屬性著重於影像的視覺品質，而體驗屬性則著重於頁面的文字。 下列視覺效果可讓您探索哪些體驗屬性對轉換有貢獻。 這些屬性也會使用AI和GenAI模型自動指派。

  此面板包含下列視覺效果：

   * **最上層轉換體驗屬性**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據選取的轉換量度顯示排名最前的轉換體驗屬性。
   * **排名在前的轉換體驗屬性與前30天的比較**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據所選的轉換量度，顯示相較於前30天排名最前的轉換體驗屬性。
   * **排名在前的轉換體驗屬性資料**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名最前的轉換體驗。 在表格中選取一列以更新線條視覺效果。
   * **行**
顯示所選最上層轉換體驗屬性趨勢的[線](/help/analysis-workspace/visualizations/line.md)視覺效果。
   * **體驗關鍵字**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名在前的體驗關鍵字。

* **資產出現在我的網站上的什麼位置？**
由自由表格組成的面板，可詳細說明網站上檢視次數最多的資產顯示位置。

  面板由一個視覺效果組成：

   * **檢視次數最多的資產會顯示在何處？**
您可以依尺寸劃分任何資產，協助您更清楚瞭解該影像出現的位置。

     在範例[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （包括[縮圖](#thumbnails)和[預覽](#previews)）中，使用了&#x200B;**[!UICONTROL 資產感知識別碼]**，而非[!UICONTROL 資產識別碼]。 有時候，網站上可能會出現完全相同的影像，並使用不同的影像URL。 [!UICONTROL 資產感知ID]屬性有助於將這些重複專案群組在單一ID下。

     因為資產可以在頁面上變更，每個資產都會依&#x200B;**[!UICONTROL 體驗ID]**&#x200B;劃分，以識別資產顯示在該頁面的哪個版本。 您可以使用其他有助於您瞭解網站上資產位置的維度來取代[!UICONTROL 體驗ID]。 例如，[!UICONTROL 頁面名稱]、[!UICONTROL 頁面URL]或[!UICONTROL 網站區段]。

     您也可以將[!UICONTROL 資產感知識別碼]與[!UICONTROL 資產識別碼]交換，以取得參照特定影像URL的記錄。


>[!MORELIKETHIS]
>
>[Content Analytics元件](components.md)
>[使用範本](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
