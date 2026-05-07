---
title: Content Analytics報告
description: 瞭解如何使用自由表格、長條圖和散佈圖等視覺效果報告Content Analytics。
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: 21bf687f3cff101ee1b3e4be3d870de270f82e89
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 47%

---

# Content Analytics 報告概觀

您在[Analysis Workspace](/help/analysis-workspace/home.md)中報告、執行分析並取得[!DNL Content Analytics]的深入分析。 特定的 Workspace [範本](#template) 已可使用，讓您可以立即存取預先填入相關內容洞察的 Workspace 專案。

若要從頭開始建立您自己的Content Analytics報表，請遵循下列步驟：

1. 在Workspace中建立[新專案](/help/analysis-workspace/build-workspace-project/create-projects.md)或開啟[現有專案](/help/analysis-workspace/build-workspace-project/open-projects.md)。
1. 請務必為 Content Analytics 報告[選取一個資料視圖](/help/analysis-workspace/c-panels/panels.md#data-view)。 Content Analytics 報告僅適用於針對 Content Analytics [設定](/help/content-analytics/config/configuration.md)的資料視圖。
1. 將![表格](/help/assets/icons/Table.svg) [自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)視覺效果拖曳至畫布上。
1. 使用[特定的 Content Analytics 元件](components.md)及其他通用[元件](/help/components/overview.md) (例如區段、日期範圍、註解)，建置您的 Content Analytics 洞察。
1. 使用其他[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)來增強您的專案。


## 縮圖

根據您在專案中使用的Content Analytics特定維度，縮圖會顯示在下列視覺效果中：

### 自由格式表格

![Content Analytics 縮圖](../assets/aca-thumbnails.png)

依預設，縮圖會顯示在[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中。 若要設定 Content Analytics 維度的縮圖顯示：

* 將滑鼠停留在 Content Analytics 維度的標題列上。 例如，「**[!UICONTROL 資產 ID]**」或「**[!UICONTROL 體驗 ID]**」。
* 選取![設定](/help/assets/icons/Setting.svg)。
* 在「**[!UICONTROL 列設定]**」快顯視窗中，在「**[!UICONTROL 設定]**」下方，勾選或取消勾選「**[!UICONTROL 顯示縮圖]**」。


### 橫條圖（棧疊）和水準橫條圖（棧疊）

{{release-limited-testing-section}}

![長條圖的Content Analytics縮圖](/help/content-analytics/assets/aca-bar-thumbnail.png)


縮圖會作為圖例的一部分顯示在垂直軸或水平軸上。 當您將滑鼠游標停留在[橫條圖（棧疊）](/help/analysis-workspace/visualizations/bar.md)和[水準橫條圖（棧疊）](/help/analysis-workspace/visualizations/horizontal-bar.md)中的橫條圖上時，也會顯示縮圖。


### 散佈圖

{{release-limited-testing-section}}

![散佈的Content Analytics縮圖](/help/content-analytics/assets/aca-scatter-thumbnail.png)

當您將游標移至[散佈圖](/help/analysis-workspace/visualizations/scatterplot.md)中的資料點上時，會顯示縮圖。

## 預覽

>[!AVAILABILITY]
>
>本節所述的長條圖和散佈圖視覺效果位於有限測試中，可能無法在您的環境中使用。 當功能正式可用時，會移除此附註。 有關 Customer Journey Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。
>

您可以開啟預覽快顯視窗。 若要這麼做：

* 在[自由格式表格](#freeform-table)中選取![資訊大綱](/help/assets/icons/InfoOutline.svg)。
* 選取[橫條圖](#bar-and-horizontal-bar)或[水準橫條圖](#bar-and-horizontal-bar)視覺效果中的特定橫條圖，或[散佈圖](#scatter)視覺效果中的資料點。


您會看到以下詳細資訊。

| 體驗預覽 | 資產預覽 |
|---|---|
| ![Content Analytics 體驗預覽](../assets/aca-experience-preview.png) | ![Content Analytics 資產預覽](../assets/aca-asset-preview.png) |
| 維度的名稱 (例如「**[!UICONTROL 體驗 ID]」)** | 資產維度的名稱 (例如「**[!UICONTROL 資產 ID]」)** |
| **[!UICONTROL 印象 (所有時間)]**：體驗的印象。 | **[!UICONTROL 印象 (所有時間)]**：資產的印象次數。 |
| **[!UICONTROL 資產]**：此體驗包含的資產數量。 <br/>選取「![劃分](/help/assets/icons/Breakdown.svg)」「**[!UICONTROL 劃分]**」以檢查資產。 | **[!UICONTROL 體驗]**：顯示此資產的體驗次數。 <br/>選取「![劃分](/help/assets/icons/Breakdown.svg)」「**[!UICONTROL 劃分]**」以檢查資產。 |
| **[!UICONTROL 第一印象]**：對體驗的第一印象日期。 | **[!UICONTROL 第一印象]**：對資產的第一印象日期。 |
| **[!UICONTROL 最近曝光]**：體驗最近曝光的日期。 | **[!UICONTROL 最近的印象]**：對資產的最近印象日期。 |
| **[!UICONTROL 體驗屬性]**：體驗的 [屬性](/help/content-analytics/report/components.md#experience-attributes)。 | **[!UICONTROL 資產屬性]**：資產的 [屬性](/help/content-analytics/report/components.md#asset-attributes)。 |


## 範本

Content Analytics [範本](/help/analysis-workspace/templates/use-templates.md)可協助您瞭解哪些內容和內容屬性表現最佳。 此範本是 [Web 管道和參與度使用案例](/help/analysis-workspace/templates/use-templates.md#web-engagement)的一部分，詳細說明您的內容在精細度的表現情況。 您可以查看個別資產或特定屬性的效能。

您可以根據所學到的內容展現才華。 例如在首頁推廣高效能資產、針對特定區段將內容個人化以納入高效能屬性，或者淘汰已開始過時的內容。

若要使用範本：

1. 從主選單中選取「**[!UICONTROL Workspace]**」。
1. 確訂您選取了針對 Content Analytics 設定的資料視圖。
1. 搜尋或使用區段 (針對&#x200B;**[!UICONTROL 管道]**&#x200B;需使用&#x200B;**[!UICONTROL 網頁]**&#x200B;以及針對&#x200B;**[!UICONTROL 使用案例]**&#x200B;需使用&#x200B;**[!UICONTROL 參與]**) 來尋找及選取 **[!UICONTROL Content analytics]** 範本。
1. 選取&#x200B;**[!UICONTROL 使用範本]**。
1. 在「**[!UICONTROL 設定您的範本]**」對話框中，從「**[!UICONTROL 選取轉換量度]**」對話框選取一個量度。 例如「**[!UICONTROL 資產點按率]**」。
1. 選取「**[!UICONTROL 繼續]**」。

**[!UICONTROL Content Analytics 概觀]**&#x200B;專案會在 [Analysis Workspace](/help/analysis-workspace/home.md) 中開啟。 專案包含四個[面板](/help/analysis-workspace/c-panels/panels.md)，每個面板提供[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)和[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)以回答特定問題。 您可以使用&#x200B;**[!UICONTROL 內容管道]**&#x200B;劃分為[劃分](/help/analysis-workspace/c-panels/panels.md#break-down-a-panel)您感興趣的內容管道面板： **[!UICONTROL 網頁]**&#x200B;或&#x200B;**[!UICONTROL 行動裝置]**。

四個面板為：

* **哪些內容表現最佳?**
此面板可識別哪些體驗和資產可促進參與和轉換。 體驗是指在特定時間擷取的完整網頁，或行動應用程式內定義的文字、資產和行動號召組合。

   * **體驗**。

     >[!NOTE]
     >
     >只有在您將系統設定為[在您的Content Analytics設定中包含體驗](/help/content-analytics/config/guided.md#experience-capture-and-definition)時，這些視覺效果才會顯示在您的範本中。
     > 

      * **體驗CTR**：顯示Experience CTR的[摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)視覺效果。
      * **轉換率最高的體驗**：[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果顯示根據所選取轉換量度的最高轉換率體驗。
      * **表現最佳的體驗**：表現最佳的體驗的[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （包括[縮圖](#thumbnails)和[預覽](#previews)）。

   * **資產**

      * **資產CTR**
顯示資產CTR的[摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)視覺效果。
      * **排名在前的轉換資產**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據選取的轉換量度顯示排名最前的轉換資產。
      * **績效最佳的資產**
表現最出色的資產的[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) （包括[縮圖](#thumbnails)和[預覽](#previews)）。
Assets — 檢視次數與轉換次數的比較。
[散佈圖](/help/analysis-workspace/visualizations/scatterplot.md)視覺效果，可顯示資產檢視與資產轉換的散佈圖。

* **哪些資產屬性有助於轉換?**
Content Analytics使用AI和GenAI來自動將中繼資料和屬性（例如主體、場景和前景顏色）指派給每個資產。

   * **最常轉換的資產屬性**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)會根據選取的轉換量度顯示排名最前的轉換資產屬性。
   * **最常轉換的資產屬性與前30天的比較**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果會根據所選的轉換量度，顯示相較於之前30天排名最前的轉換資產屬性。
   * **排名在前的轉換資產屬性資料**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名最前的轉換屬性。 選取表格中的一列來更新屬性趨勢視覺效果。
   * **屬性趨勢**
顯示所選最上層轉換資產屬性之屬性趨勢的[線](/help/analysis-workspace/visualizations/line.md)視覺效果。
   * **資產前景色彩**
範例[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)比較單一資產屬性類別（前景色彩）中專案的效能。 您可以用其他資產屬性類別維度取代此資產屬性。

* **哪些體驗屬性有助於轉換？**

  >[!NOTE]
  >
  >此面板僅在 Content Analytics 設定中[包含體驗](/help/content-analytics/config/guided.md#experience-capture-and-definition)時顯示。
  > 

  資產屬性著重於影像的視覺特性，而體驗屬性則著重於頁面中的文字。 以下的視覺化圖表可以讓您探索哪些體驗屬性有助於轉換。 這些屬性也使用 AI 和 GenAI 模型自動指派。

  面板由以下視覺效果組成：

   * **排名在前的轉換體驗屬性**
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果可依據選取的轉換量度顯示排名最前的轉換體驗屬性。
相較於前30天轉換體驗屬性的排名最前
[橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md)視覺效果會根據所選的轉換量度，顯示相較於之前30天排名最前的轉換體驗屬性。
   * **排名在前的轉換體驗屬性資料**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名最前的轉換體驗。 選取表格中的一列來更新線條圖視覺效果。
   * **行**
顯示所選最上層轉換體驗屬性趨勢的[線](/help/analysis-workspace/visualizations/line.md)視覺效果。
   * **體驗關鍵字**
[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)會根據選取的轉換量度顯示排名在前的體驗關鍵字。

* **資產會出現在我網站上的什麼地方?**
此自由表格詳細說明您檢視次數最多的資產出現的位置。 使用此分析來識別高效能頁面，並最佳化資產放置。

   * **檢視次數最多的資產出現在哪裡?**
您可以依尺寸劃分任何資產，協助您更清楚瞭解該影像出現的位置。

     在範例[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (包括[縮圖](#thumbnails)和[預覽](#previews))，使用「**[!UICONTROL 資產感知 ID]**」而非「[!UICONTROL 資產 Id]」。 完全相同的影像有時可能會透過不同的影像 URL 重複出現在您的網站上。 [!UICONTROL 資產感知 ID] 屬性有助於將這些重複項目分組到單一 ID 之下。

     因為資產可以在頁面上變更，所以系統會依據&#x200B;**[!UICONTROL 體驗ID]**&#x200B;劃分每個資產，以識別資產出現的頁面版本。 您可以用其他維度取代[!UICONTROL 體驗 Id]，以協助您了解資產在您網站上的位置。 例如「[!UICONTROL 頁面名稱]」、「[!UICONTROL 頁面 URL]」或「[!UICONTROL 網站區段]」。

     您也可以用[!UICONTROL 資產感知 ID] 交換[!UICONTROL 資產 ID]，以取得參照特定影像 URL 的位置記錄。


>[!MORELIKETHIS]
>
>[Content Analytics元件](components.md)
>[使用範本](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
