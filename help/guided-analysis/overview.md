---
title: 引導式分析概觀
description: 一種在 Customer Journey Analytics 中分析資料的方法，可讓產品團隊快速獲得高品質的深入分析。
keywords: Product Analytics
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 1e7d61f05a8351a1bd9e4d289c9d31906676f909
workflow-type: tm+mt
source-wordcount: '1806'
ht-degree: 47%

---

# 引導式分析概觀

引導式分析可讓從行銷到產品再到分析師的使用者透過建置在 Customer Journey Analytics 跨管道資料上的引導式工作流程，自行取得有關客戶歷程的高品質資料和深入分析。與 Analysis Workspace 和行動計分卡類似，引導式分析使用來自[資料視圖](/help/data-views/data-views.md)的資料，透過[連線](../connections/overview.md)參考 Adobe Experience Platform 中的資料。多種在引導式分析中建立的報告可以無縫轉移到 Analysis Workspace 以進行其他研究。

可以使用以下引導式分析：

| 圖示 | 分析 | 說明 |
| :----:|--- | --- |
| ![人員群組](/help/assets/icons/PeopleGroup.svg) | [積極成長](types/active-growth.md) | 識別哪些使用者是新的、保留的、回訪的或非活躍的。 |
| ![轉換趨勢](/help/assets/icons/ConversionTrends.svg) | [轉換趨勢](types/conversion-trends.md) | 追蹤一段時間內的轉換率變化。 |
| ![參與度圖](/help/assets/icons/EngagementGraph.svg) | [參與度](types/engagement.md) | 了解功能參與的廣度與深度。 |
| ![首次使用](/help/assets/icons/FirstUse.svg) | [首次使用影響](types/first-use-impact.md) | 測量功能首次使用對關鍵指標的影響。 |
| ![長條圖](/help/assets/icons/Histogram.svg) | [頻率](types/frequency.md) | 依照使用頻率來測量參與度。 |
| ![轉換漏斗](/help/assets/icons/ConversionFunnel.svg) | [漏斗](types/funnel.md) | 比較步驟之間的轉換率。 |
| ![淨成長](/help/assets/icons/NetGrowth.svg) | [淨增長](types/net-growth.md) | 您正在獲得還是失去使用者? |
| ![發行](/help/assets/icons/Release.svg) | [發行影響](types/release-impact.md) | 比較發行前和發行後同期的績效。 |
| ![保留](/help/assets/icons/Retention.svg) | [保留](types/retention.md) | 測量使用者持續的回訪習慣。 |
| ![時間軸](/help/assets/icons/Timeline.svg) | [時間軸](types/timeline.md) | 探索工作階段活動的模式。 |
| ![趨勢圖](/help/assets/icons/GraphTrend.svg) | [趨勢](types/trends.md) | 測量使用者在一段時間內的參與度。 |



## 存取權

您可以從Customer Journey Analytics首頁存取引導式分析。

1. 從首頁中選取&#x200B;**[!UICONTROL 引導式分析]**，即可直接前往[趨勢分析](types/trends.md)。

   ![登陸頁面圖磚](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 選取&#x200B;**[!UICONTROL 新建]**&#x200B;可查看不同的視圖選項，並選擇不同的分析起始點。

   ![建立強制回應視窗](assets/create-new-modal.png){style="border:1px solid gray"}

您也可以從Analysis Workspace專案存取引導式分析。

1. 從首頁中選取&#x200B;**[!UICONTROL 空白專案]**&#x200B;以建立一個空的 Workspace 專案。

   ![建立空白專案](assets/blank-project.png){style="border:1px solid gray"}

1. 選取左側邊欄中的![引導式分析](/help/assets/icons/GuidedAnalysis.svg)「**[!UICONTROL 引導式分析]**」。

   ![Workspace 左側邊欄](assets/workspace-left-rail.png){style="border:1px solid gray"}

1. 將任何新的分析拖曳到Workspace畫布上，然後選取「**[!UICONTROL 建立]**」以產生所需的分析（例如： **[!UICONTROL 建立趨勢]**）。 您也可以從&#x200B;**[!UICONTROL 已儲存]**&#x200B;區段下將現有分析拖曳至 Workspace 版面上。

   ![建立面板](assets/create-guided-analysis-panel.gif)

## 介面

引導式分析的介面會遵循問答格式。 在查詢邊欄中形成您的問題，然後透過寫入的深入分析、圖表和表格獲得答案。然後您可以透過分析和視覺效果設定來詢問下一個問題。

引導式分析會使用以下 UI 元素：

| 介面預覽 | UI 元素 | 說明 |
| --- | --- | --- |
| ![查詢邊欄](assets/query-rail.png){style="border:1px solid gray"} | **[!UICONTROL 查詢邊欄]** | 選取組成分析的所需元件（事件、屬性和區段），以設定您的&#x200B;*問題*。 以下選項適用於所有分析，其他設定則適用於每個檢視。 <ul><li>**檢視**：從選項中選取，以切換至新的分析。 您的查詢選取範圍會維持在新分析的允許限制內。</li><li>**事件**：您要測量的事件。每個分析都會對可設定的事件數實施不同的限制。  事件有時標示為&#x200B;**[!UICONTROL 開始和傳回事件]**、**[!UICONTROL 步驟]**&#x200B;或&#x200B;**[!UICONTROL 索引鍵]**。 在分析中使用1， 2， ...<br/>選取![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增事件]**&#x200B;以新增事件。</li><li>**[!UICONTROL 因素]**：如果可用，可讓您指定因素，例如自第一次事件以來的日期和第一次事件。</li><li>**計為**：您要套用至所選事件的計數方法。 從下拉式選單中選取。</li><li>**區段**：您要測量的區段。每個分析都會對可設定的區段數實施不同的限制。 使用A、B、...在分析中識別區段<br/>選取![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增區段]**&#x200B;以新增區段。</li><li>**[!UICONTROL 劃分]**：如果可用，則您要套用至分析的劃分。</li></ul>在某些設定上，有其他設定可供使用。<ul><li>**篩選器**：使用![篩選器](assets/filter.png)依特定維度縮小事件或區段的範圍。 選取維度後，標準篩選條件 (例如「**[!UICONTROL 等於]**」、「**[!UICONTROL 包含]**」或「**[!UICONTROL 結尾為]**」) 和前 1000 個維度值都可用。<br/>選取![篩選器](/help/assets/icons/Filter.svg)以新增其他篩選器。<br/>選取![移除](/help/assets/icons/Remove.svg)以移除篩選器。</li><li>**更多動作**：使用![更多](/help/assets/icons/More.svg)來選取動作，例如<ul><li>![重新命名](/help/assets/icons/Rename.svg) **[!UICONTROL 重新命名]**：重新命名事件或區段。</li><li>![複製](/help/assets/icons/Duplicate.svg) **[!UICONTROL 複製]**：複製事件或區段。</li><li>![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 移除]**：移除事件、區段或劃分。</li><li>![編輯區段](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯區段]**：若要在[篩選產生器](/help/components/filters/filter-builder.md)中編輯區段。</li><li>![星號](/help/assets/icons/Star.svg) **[!UICONTROL 新增至我的最愛]**：新增區段至[篩選器管理員](/help/components/filters/manage-filters.md)中的我的最愛篩選器清單。</li><li>![SaveAsFloppy](/help/assets/icons/SaveAsFloppy.svg) **[!UICONTROL 另存新檔]**：將區段另存為新元件。 在&#x200B;**[!UICONTROL 將區段儲存至元件]**&#x200B;對話方塊中，您可以指定區段名稱和說明。 您可以選取![星形外框](/help/assets/icons/StarOutline.svg)，將新區段標示為我的最愛。 選取&#x200B;**[!UICONTROL 儲存]**，將區段儲存為新篩選器。</li><li>![連結](/help/assets/icons/Link.svg) **[!UICONTROL 連結開始和傳回事件]**。：在[保留](types/retention.md)分析中連結開始和傳回事件。</li><li>![取消連結](/help/assets/icons/Unlink.svg) **[!UICONTROL 取消連結開始和傳回事件]**：在[保留](types/retention.md)分析中取消連結開始和傳回事件。</li></ul></li></ul> |
| ![圖表](assets/chart.png){style="border:1px solid gray"} | **[!UICONTROL 圖表]** | 根據查詢邊欄和設定的輸入內容傳回的資料視覺效果。您看到的視覺效果取決於圖表上方的視圖和設定。該圖表也包括： <ul><li>**工具提示**：將滑鼠停留在任何圖表資料點上，可顯示包含更多資訊的工具提示。</li><li>**圖例**：將滑鼠停留在圖表圖例系列上，可檢視可用的定義、聚焦於該系列，以及暫時隱藏其他系列。在圖例中選取序列以隱藏該序列。</li><li>**註解**：適用的[註解](../components/annotations/overview.md)會顯示在視覺效果和圖例之間。它會以註解設定的顏色顯示為 ![註解圖示](assets/annotation.png) 圖示。分析顯示一段時間的資料時，將![註解圖示](assets/annotation.png)圖示放在設定的日期或日期範圍下。 不會隨時間顯示資料的分析會在圖表的右下角顯示![註解圖示](assets/annotation.png)圖示。</li><li>**選取動作**：選取任何資料點，以公開下一個可用的動作。 選項包括&#x200B;**儲存區段**。</li></ul> |
| ![表格](assets/table.png){style="border:1px solid gray"} | **[!UICONTROL 表格]** | 根據查詢邊欄和設定的輸入內容傳回之資料的表格表示。表格中的列使用事件(1， 2， ...)和區段識別碼(A， B， ...)作為參考。 表格中的欄取決於圖表上方的分析。 此表格也包含每一列的下列專案： <ul><li>**選取動作**：切換![顯示隱藏圖示](assets/hide-in-chart.png)以隱藏或公開某一列的圖表序列。 選取![更多](/help/assets/icons/More.svg)以取得其他動作。 選項包括&#x200B;**儲存區段**。</li></ul> |
| ![視覺效果設定](assets/visualization-settings.png){style="border:1px solid gray"} | **[!UICONTROL 視覺效果設定]** | 圖表上方的選項可讓您提出下一個問題，以及自訂圖表和表格傳回資料的方式。以下選項適用於所有分析，其他設定則適用於每個分析。 <ul><li>![GraphTrend](/help/assets/icons/GraphTrend.svg) **圖表設定**：微調圖表和表格顯示的內容。 可用選項取決於所選分析。</li><li>![圖層](/help/assets/icons/Layer.svg) **覆蓋設定**：新增覆蓋。 可用選項取決於所選分析。</li><li>![貯體](/help/assets/icons/Bucket.svg) **[!UICONTROL 貯體設定]**：自動貯體或套用自訂貯體設定至資料。 可用選項取決於所選分析。<li>![DataCorrelated](/help/assets/icons/DataCorrelated.svg) **[!UICONTROL 比較設定]**：比較資料與特定日期範圍。 可用選項取決於所選分析。</li><li>![腳步](/help/assets/icons/Footsteps.svg) **[!UICONTROL 顯示設定]**：選取如何顯示資料。 可用選項取決於所選分析。<li>![行事曆](/help/assets/icons/Calendar.svg) **日期範圍**：可讓您決定分析日期範圍的行事曆選擇器。 您也可以選取趨勢分析的間隔，例如每日、每週或每月。</li><li>![LightBulb](/help/assets/icons/LightBulb.svg) **Insights**：根據您檢視的分析產生內容深入分析。 這些分析見解是為目前的分析提供觀察結果。如果有多個分析見解，您可以使用右側的箭頭查看。您可以使用右上角的燈泡圖示切換此方框的可見度。</li></ul> |
| ![選單](assets/menu.png){style="border:1px solid gray"} | 引導式分析專案中可用的&#x200B;**[!UICONTROL 功能表]**<br/> | 引導式分析專案右上角的命令，可為您的分析提供總體動作。<ul><li>![資料](/help/assets/icons/Data.svg) ***資料檢視的名稱***：變更分析使用的資料檢視。 您變更資料視圖時，查詢邊欄中的可用元件也會變更。</li><li>![連結](/help/assets/icons/Link.svg) **複製連結**：將分析連結複製到剪貼簿。 共用之前，系統會提示您先儲存。</li><li>**共用**：會開啟共用強制回應視窗，其中包含用來共用給個別使用者或群組的更多選項。您可以讓其他使用者共用分析內容，或產生讓任何人共用的連結。</li><li>**儲存**：儲存分析。如果您要儲存新的分析，**[!UICONTROL 儲存分析]**&#x200B;對話方塊就會顯示，要求名稱和說明。 儲存後，**[!UICONTROL 分析已儲存]**&#x200B;對話方塊可讓您共用分析。</li></ul>選取![更多](/help/assets/icons/More.svg)以取得更多動作，例如：<ul><li>**另存新檔**：將該分析與目前分析分開儲存，從而建立副本。畫面會顯示要求新名稱和說明的對話方塊。</li><li>**匯出至Workspace**：在Analysis Workspace中重新建立目前的引導式分析查詢。 Workspace 專案會以新標籤建立，藉此防止在引導式分析中使用時發生中斷。它是分析的副本，在開啟後不會與原始分析保持同步。 當您想要將資料移交分析團隊或深入瞭解分析所允許的資料時，請使用此命令。</li><li>**將圖表複製到剪貼簿**：將圖表圖形複製到剪貼簿，以貼到其他應用程式。 查詢邊欄和表格不會包含在圖形中。</li><li>**下載 PNG**：將圖表圖形下載為 `.png`。查詢邊欄和表格不會包含在圖形中。</li><li>**下載 CSV**：將表格資料下載為 `.csv`。查詢邊欄和圖表不會包含在檔案中。</li></ul> |
| ![功能表視覺效果](assets/menu-visualization.png){style="border:1px solid gray"} | **功能表**<br/>&#x200B;可在Analysis Workspace的引導式分析視覺效果中使用。 | Analysis Workspace中引導式分析視覺效果中的命令。<ul><li>![GraphScatter](/help/assets/icons/GraphScatter.svg) **[!UICONTROL 圖表]**：只顯示分析圖表。</li><li>![資料表](/help/assets/icons/Table.svg) **[!UICONTROL 資料表]**：只顯示分析的資料表。</li><li>![TableAndChart](/help/assets/icons/TableAndChart.svg) **[!UICONTROL 全部]**：顯示分析的圖表和表格。</li><li>![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**：編輯分析的設定</li><li>![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL *日期範圍&#x200B;*]**：設定分析的日期範圍。</li></ul> |


## 佈建

引導式分析會以下列方式納入 Customer Journey Analytics 套件中：

| 套件 | 可用分析 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics 附加元件] | 積極成長、轉換趨勢、頻率、漏斗、淨成長、保留、趨勢 |
| [!UICONTROL Customer Journey Analytics Foundation] | 趨勢 |
| [!UICONTROL Customer Journey Analytics Select] | 基礎視圖 + 積極成長、轉換趨勢、頻率、漏斗、淨成長、保留 |
| [!UICONTROL Customer Journey Analytics Prime] | 選取視圖 + 參與度、首次使用影響、發行影響、時間軸 |
| [!UICONTROL Customer Journey Analytics Ultimate] | Prime 視圖 |

{style="table-layout:auto"}

產品設定檔管理員可新增或移除Adobe Admin Console中引導式分析的存取權。

1. 登入 [Adobe Admin Console](https://adminconsole.adobe.com)。
1. 在產品清單中選取「**[!UICONTROL Customer Journey Analytics]**」。
1. 為您要編輯的權限選取所需的產品設定檔。
1. 選取「**[!UICONTROL 權限]**」標籤，然後按一下「**[!UICONTROL 編輯]**」(在「[!UICONTROL 報告工具]」下方)。
1. 選取「**[!UICONTROL 引導式分析存取權]**」(在[!UICONTROL 可用權限項目]清單中) 旁邊的![AddCircle](/help/assets/icons/AddCircle.svg)，將其新增至[!UICONTROL 包含的權限項目]清單中。
1. 選取「**[!UICONTROL 儲存]**」。

如需詳細資訊，請參閱[使用者層級存取](/help/technotes/access-control.md#user-level-access)。

>[!TIP]
>
>部分管理員偏好為 Customer Journey Analytics 的新使用者啟用引導式分析，並停用 Analysis Workspace。一旦這些使用者熟悉該產品和您的組織資料，您就可以啟用對 Analysis Workspace 的存取權。
