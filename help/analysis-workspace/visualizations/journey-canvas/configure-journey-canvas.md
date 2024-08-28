---
description: 設定歷程畫布視覺效果
title: 歷程畫布
feature: Visualizations
role: User
hide: true
hidefromtoc: true
source-git-commit: e06793a0ce73fa8d6aa9b798209bfc044e696931
workflow-type: tm+mt
source-wordcount: '4087'
ht-degree: 1%

---

# 設定歷程畫布視覺效果

Journey Canvas視覺效果可讓您分析和深入瞭解您提供給使用者和客戶的歷程。

## 歷程畫布概述

檢視[歷程畫布總覽](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)以進一步瞭解歷程畫布，包括：

* 主要功能

* 可能的深入分析

* 歷程畫布和流失之間的差異

* 有關分析Journey Optimizer歷程的詳細資訊

* 及更多內容

## 開始建立歷程畫布視覺效果

1. 新增空白面板至您的專案，選取左側邊欄中的&#x200B;[!UICONTROL **視覺效果**]&#x200B;圖示，然後將&#x200B;[!UICONTROL **歷程畫布**]&#x200B;視覺效果拖曳至面板。

   或

   以[視覺效果概述](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)的[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)區段中所述的任何方式新增「歷程畫布」視覺效果。

1. 指定下列基本資訊：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **主要量度**] | 主要量度會影響Journey Canvas視覺效果的下列方面：  <ul><li>定義人們如何移動歷程。</li><li>每個節點上顯示的總數。<p>例如，如果人員是主要量度，則每個節點會顯示到達歷程中該節點的人員數量。</p></li><li>每個節點上顯示的百分比。 （建立視覺效果後，您可以選擇顯示總數百分比或起始節點）。</li><p>例如，如果人員是主要量度，則每個節點會顯示到達歷程中該節點的使用者百分比（總數的百分比或起始節點的百分比）。</p></li><li>將維度新增至視覺效果時，會根據主要量度新增視覺效果的前3個節點。</li></ul> |
   | [!UICONTROL **次要量度**] | 次要量度為選用。 選取其中一個時，主要量度下方的每個節點會顯示下列資訊： <ul><li>總數<p>例如，如果階段作業是次要量度，則每個節點會顯示到達歷程中該節點的工作階段數量。</p></li><li>百分比（建立視覺效果後，您可以選擇顯示總數百分比或起始節點百分比）。</li><p>例如，如果階段作業是次要量度，則每個節點會顯示到達歷程中該節點的工作階段百分比（總數的百分比或起始節點的百分比）。</p></li></ul> |
   | [!UICONTROL **Journey Optimizer歷程**]<!-- name? --> | 選取您要用作Journey Canvas中分析基礎的Journey Optimizer歷程。 (或者，如果您想要在Analysis Workspace中建立分析的空白畫布，可將此選項保留空白。)</p> <p>當您在Journey Canvas中分析Journey Optimizer歷程時，該歷程的顯示順序、順序和結構與Journey Optimizer中相同。 如需詳細資訊，請參閱[歷程畫布總覽](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)中的[分析Journey Optimizer歷程](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys)。</p><p>**注意**：只有在您新增視覺效果的Journey Optimizer面板中選取的資料檢視中偵測到Analysis Workspace資料時，才會顯示此選項。 如需有關變更Analysis Workspace中面板上的資料檢視的資訊，請參閱[Analysis Workspace概觀](/help/analysis-workspace/home.md)。</p> |

1. （選擇性）選取「[!UICONTROL **顯示進階設定**]」，然後指定下列資訊：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **歷程畫布容器**] | 選擇您想要在整個歷程中著重處理的容器。 您選擇的容器會決定視覺效果中顯示的統計資料。 （如果您的容器名稱與下方顯示的預設名稱不同，則這些名稱會在您的資料檢視中自訂。）<ul><li>**工作階段：**&#x200B;將視覺效果的統計資料限制在指定人員的單一已定義工作階段內。 這表示每個節點上顯示的數字和百分比（根據主要和次要量度），必須發生在每個人的單一工作階段中。</li><li>**人員：**&#x200B;允許視覺效果的統計資料跨越指定人員的多個工作階段。 這表示每個節點上顯示的數字和百分比（根據主要和次要量度）可發生在任意數量的工作階段中，只要這些工作階段屬於同一個使用者。 這是預設設定。</li></ul> |

1. 選取「[!UICONTROL **建立**]」。

   如果您有Journey Optimizer且已選取Journey Optimizer歷程，則該歷程會以與Journey Optimizer相同的順序、序列和結構顯示。

   <!-- add screen shot -->

   如果您沒有Journey Optimizer或未選取Journey Optimizer歷程，則會顯示空白畫布，讓您開始填入歷程。

   <!-- add screen shot -->

1. 無論您是從空白畫布建立新的分析，還是要分析Journey Optimizer歷程，都可以依照[設定歷程畫布視覺效果](#begin-building-a-journey-canvas-visualization)中所述來設定歷程。


## 設定歷程畫布視覺效果

您必須[開始建立Journey Canvas視覺效果](#begin-building-a-journey-canvas-visualization)，才能依照下列章節所述進行設定。

### 設定設定

1. 在Analysis Workspace中，開啟現有的Journey Canvas視覺效果，或[開始建立新的視覺效果](#begin-building-a-journey-canvas-visualization)。

1. 設定下列任一項在視覺效果上方顯示的設定：

   | 設定 | 函數 |
   |---------|----------|
   | [!UICONTROL **節點型別**] | 可讓您設定哪些節點型別會顯示在視覺效果中。 若要隱藏視覺效果中的節點型別，請選取節點型別旁的(x)，或從下拉式選單中取消選取。 若要顯示隱藏的節點型別，請從下拉式選單中選取它。 <p>根據視覺效果的內容，可能的節點型別包括：</p><ul><li>[!UICONTROL **讀取區段**]</li><li>[!UICONTROL **結束**]</li><li>[!UICONTROL **維度**]</li><li>[!UICONTROL **量度**]</li></ul><p>**注意**：使用此欄位時，請考慮下列事項：</p><ul><li>只有在您新增視覺效果的Analysis Workspace面板中選取的資料檢視中偵測到Journey Optimizer資料時，才會顯示此選項。 如需有關變更Analysis Workspace中面板上的資料檢視的資訊，請參閱[Analysis Workspace概觀](/help/analysis-workspace/home.md)。</li><li>在歷程畫布中修改Journey Optimizer歷程後，此選項將不再可用。 如需詳細資訊，請參閱[在歷程畫布中修改歷程後的視覺差異](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p> |
   | [!UICONTROL **百分比值**] | 從下列選項中選擇： <ul><li>總數的&#x200B;[!UICONTROL **百分比**]：面板日期範圍內包含在資料檢視中的所有人員的百分比。</li><li>[!UICONTROL **開始節點的百分比**]：開始節點中包含之所有人員的百分比。<p>此選項僅在您有單一起始節點時可用。 如果您有多個開始節點，則會隱藏節點。</p></li></ul> |
   | [!UICONTROL **箭頭設定**] | 從下列選項中選擇：<ul><li>[!UICONTROL **無**]： </li><li>[!UICONTROL **條件**]： </li><li>[!UICONTROL **所有標籤**]： </li></ul><p>**注意**：只有在您新增視覺效果的Journey Optimizer面板中選取的資料檢視中偵測到Analysis Workspace資料時，才會顯示此選項。 如需有關變更Analysis Workspace中面板上的資料檢視的資訊，請參閱[Analysis Workspace概觀](/help/analysis-workspace/home.md)。</p> |
   | [!UICONTROL **顯示流失**] | 顯示每個節點的流失資料，顯示在指定節點離開歷程的人數及百分比。 |

1. 繼續[新增節點](#add-a-node)。

### 新增節點

Journey Canvas視覺效果中的節點代表使用者歷程的事件或動作。 您可以將Workspace元件從左側邊欄拖曳至畫布，藉此建立節點。

若要將節點新增至Journey Canvas視覺效果：

1. 在Analysis Workspace中，開啟現有的Journey Canvas視覺效果，或[開始建立新的視覺效果](#begin-building-a-journey-canvas-visualization)。

1. 從左側邊欄將量度、維度、維度專案、篩選器或日期範圍拖曳至畫布上。 不支援計算量度。 此外，不支援任何以[摘要資料集](/help/data-views/summary-data.md)為基礎的量度或維度。

   您可以按住Shift鍵或按住Command鍵(在Mac上)或Ctrl鍵（在Windows上），在左側邊欄中選取多個元件。

   視覺效果會根據元件型別和您放置位置的畫布區域更新如下：

   | 元件類型 | 放置元件 | 新增節點後視覺效果更新 |
   |---------|----------|----------|
   | 量度 | 畫布的空白區域 | 節點會在元件放置的位置顯示，且不會與任何現有節點連線。 |
   | 量度 | 現有節點 | 元件會自動與現有節點結合。 （如需詳細資訊，請參閱[結合節點](#combine-nodes)。）</p> |
   | 量度 | 2個現有節點之間的箭頭 | 節點會顯示在兩個現有節點之間，元件會放置於這兩個現有節點中，且會連線至這兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p> |
   | 維度 | 畫布的空白區域 | 系統會針對放置元件的前3個維度專案建立3個節點，且不會與任何現有節點連線。 (**注意：**&#x200B;如果只顯示1或2個節點，表示只有1或2個維度專案可以使用資料。 如果沒有顯示節點，表示資料不可用於任何維度專案。 在此情況下，請嘗試將其新增至歷程的不同點、調整視覺效果的日期範圍，或選擇不同的維度。)<p>按住Shift鍵，將維度拖放至畫布上，以新增為具有3個維度專案的單一節點。</p><p></p> |
   | 維度 | 現有節點 | 劃分會自動套用至顯示前5個維度專案的節點。<!--what happens if you hold Shift?--> |
   | 維度 | 連線2個現有節點的箭頭 | 系統會為第一個節點（最終到達第二個節點的人員/工作階段）之後第一個事件之後的前3個維度專案建立3個節點。 節點會顯示在兩個現有節點之間，其中元件已卸除，且每個節點都連線到兩個現有節點。 (**注意：**&#x200B;如果只顯示1或2個節點，表示只有1或2個維度專案可以使用資料。 如果沒有顯示節點，表示資料不可用於任何維度專案。 在此情況下，請嘗試將其新增至歷程的不同點、調整視覺效果的日期範圍，或選擇不同的維度。)<p>按住Shift鍵，將維度拖放至畫布上，以新增為具有3個維度專案的單一節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p> |
   | 維度項目 | 畫布的空白區域 | 節點會在元件放置的位置顯示，且不會與任何現有節點連線。 |
   | 維度項目 | 現有節點 | 元件會自動與現有節點結合。 |
   | 維度項目 | 連線2個現有節點的箭頭 | 節點會顯示在兩個現有節點之間，元件會放置於這兩個現有節點中，且會連線至這兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p> |
   | 篩選器 | 畫布的空白區域 | 節點會顯示在元件中斷與任何其他節點連線的位置。<p>節點上顯示的數字和百分比包含主要量度的總計，這些量度是按照您選取的篩選條件進行篩選。</p> <p>例如，如果選取「人物」作為歷程的主要量度，則將「今天」篩選條件新增至畫布的空白區域，會顯示今天有事件的所有人物。</p> |
   | 篩選器 | 現有節點 | 將篩選器套用至現有節點。 |
   | 篩選器 | 連線2個節點的箭頭 | 節點會顯示在兩個現有節點之間，元件會放置於這兩個現有節點中，且會連線至這兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p><p>將篩選器套用至路徑上放置元件的位置。</p> |
   | 日期範圍 | 畫布的空白區域 | 節點會在元件放置的位置顯示，且不會與任何其他節點連線。<p>節點上顯示的數字和百分比包含主要量度的總計，且以您選取的日期範圍篩選。</p> <p>例如，如果選擇「人員」作為歷程的主要量度，則將「本月」的日期範圍新增至畫布的空白區域，會顯示所有在當月發生事件的人員。</p> |
   | 日期範圍 | 現有節點 | 將日期範圍套用至現有節點。 |
   | 日期範圍 | 連線2個節點的箭頭 | 節點會顯示在兩個現有節點之間，元件會放置於這兩個現有節點中，且會連線至這兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p><p>將日期範圍套用至路徑上放置元件的點。</p> |
   | 多個元件 | 畫布的空白區域 | **如果沒有任何元件是維度：**<p>每個元件會顯示為個別的節點，元件會放置於此處，且不會與任何現有節點連線。</p><p>按住Shift鍵，將元件拖放到畫布上，將其新增為合併節點。 </p><p>**如果您要新增的任何元件是維度：**</p><p>每個元件會顯示為個別的節點，元件會放置於此處，且不會與任何現有節點連線。</p><p>一次只能新增一個維度，並且會為放置元件的前3個維度專案建立3個節點。</p><p>按住Shift鍵，將元件拖放到畫布上，將其新增為合併節點。 前3個維度專案會與每個節點結合。 （如需詳細資訊，請參閱[結合節點](#combine-nodes)。）</p> |
   | 多個元件 | 現有節點 | 所有元件都會與現有節點結合。<p>如果您新增的任何元件是維度，則排名前3的維度專案會與節點結合。</p> <p>一次只能新增一個維度。</p> |
   | 多個元件 | 連線2個現有節點的箭頭 | **如果沒有任何元件是維度：**<p>每個元件會顯示為個別的節點，放置元件後，每個節點都會連線至兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p><p>按住Shift鍵，將元件拖放到畫布上，將其新增為合併節點。 （元件必須屬於相同型別，才能合併成單一節點。） （如需詳細資訊，請參閱[結合節點](#combine-nodes)。）</p><p>**如果您要新增的任何元件是維度：**</p><p>每個元件會顯示為個別的節點，放置元件後，每個節點都會連線至兩個現有節點。</p><p>一次只能新增一個維度，並為第一個節點（最終到達第二個節點的人員/工作階段）之後的第一個事件之後的維度前3個專案建立3個節點。 每個節點都連線到兩個現有節點。 （如需詳細資訊，請參閱[連線節點](#connect-nodes)。）</p><p>按住Shift鍵，將元件拖放到畫布上，將其新增為合併節點。 前3個維度專案會與每個節點結合，每個節點會連線至兩個現有節點。 （如需詳細資訊，請參閱[結合節點](#combine-nodes)。）</p> |

   節點會顯示為矩形方塊，內含下列資訊：

   * 元件名稱

   * 元件型別（例如量度或維度）

   * 主要量度統計資料（總計和百分比）

   * 次要量度統計資料（總計和百分比）

1. 重複此程式以繼續新增節點來建置您的歷程。

1. 繼續自訂歷程，如下節所述。 您可以連線節點、重新命名節點、套用劃分、建立對象、新增時間限制等。

### 根據現有節點新增排名最前的節點

您可以根據畫布上已存在的節點，自動新增排名最前的節點。

此選項適用於畫布上的下列物件：

* 個別節點

* 節點之間的箭頭

#### 在現有節點之後新增頂端節點

您可以選取節點，並在歷程中新增該節點之後的前3個節點。

1. 以滑鼠右鍵按一下您要新增歷程中在其後面排名前3的節點的節點。

   此節點在歷程中無法擁有任何離開的現有節點。

1. 選取&#x200B;[!UICONTROL **在此節點**]&#x200B;之後新增頂端節點。

   接著會新增歷程中此節點之後的前3個節點，每個節點都會連線至您選取做為個別分支的節點。

#### 在現有節點之前新增頂端節點

您可以新增在歷程中現有節點之前的前3個節點。

1. 以滑鼠右鍵按一下您要新增歷程中前3個節點的節點。

   此節點在歷程中不能有任何現有節點進入其中。

1. 選取&#x200B;[!UICONTROL **在此節點**]&#x200B;之前新增頂端節點。

   接著會新增歷程中位於此節點之前的前3個節點，每個節點都會連線至您選取做為個別分支的節點。

#### 在現有節點之間新增頂端節點

您可以新增介於2個現有節點之間的前3個節點：

1. 以滑鼠右鍵按一下您要新增歷程中前3個節點的2個節點之間的箭頭。

1. 選取&#x200B;[!UICONTROL **新增最上層節點**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   前3個節點會新增至2個現有節點之間，每個節點都會以個別分支的方式連線。

### 重新排列節點

Journey Canvas中的歷程由彈性的節點和箭頭圖表組成，代表事件、維度專案和篩選器的任何組合。

您可以在畫布上拖曳節點，以重新排列歷程的事件和條件。 如同您所做的，資料會據此更新。

### 合併節點

Journey Canvas中的組合節點是使用者歷程（節點）中的單一點，其中包含2個或多個透過邏輯連結在一起的元件。

#### 建立合併的節點

您可以執行下列任一項作業，在Journey Canvas中建立合併節點：

* 從左側邊欄，將單一元件拖曳至畫布上的節點。

* 從左側邊欄，同時拖曳多個元件至畫布上的節點。

* 從左側邊欄中，同時拖曳多個元件至畫布的空白區域，同時按住Shift鍵。

* 在畫布上，選取您要合併的節點，用滑鼠右鍵按一下其中一個選取的節點，然後選取&#x200B;**合併**。<!--Is there a limit on how many you can combine? -->

#### 合併節點時的邏輯

合併節點時套用至節點的邏輯會根據您要合併的元件型別而有所不同，如下所示：

>[!TIP]
>
>您可以用滑鼠右鍵按一下節點，然後選取&#x200B;[!UICONTROL **從節點**]&#x200B;建立篩選器，以檢視合併節點的邏輯。 此邏輯會顯示在&#x200B;[!UICONTROL **定義**]&#x200B;區段中。


| 要組合的元件型別 | 使用的邏輯（運運算元） |
|---------|----------|
| 度量+度量 | 已使用OR連結 |
| Dimension+Dimension | 已使用OR連結 |
| 篩選+篩選 | 使用AND聯結 |
| Dimension+量度、日期範圍或篩選 | 使用AND聯結 |
| 日期範圍+量度、篩選器或Dimension | 使用AND聯結 |
| 篩選+量度、日期範圍或Dimension | 使用AND聯結 |

### 連線節點

您可以連線畫布上已存在的節點，也可以在將節點新增至畫布時連線節點。

#### 連線現有節點

Journey Canvas中節點之間的箭頭會決定歷程中的事件順序。

若要連線Journey Canvas中的節點：

1. 在畫布上，暫留在您要連線至其他節點的歷程式列中排在第一位的節點上。

   所選節點的兩側會出現4個藍色點。

1. 將4個藍點中的任何一個拖曳至您要連線之節點的4個側邊中的任何一個。

   會出現一個箭頭，連線這2個節點。 箭頭會指出使用者在歷程中移動的方向。

#### 新增節點時連線節點

將節點新增至畫布時，您可以將其置於兩個連線的節點之間。 節點會新增至2個現有節點之間的歷程流量中。

如需詳細資訊，請參閱[新增節點](#add-a-node)。

### 變更節點或箭頭的顏色

您可以變更畫布上節點或箭頭的顏色。

變更顏色的選項適用於畫布上的下列物件：

* 個別節點

* 節點之間的箭頭

若要變更節點或箭頭的顏色：

1. 以滑鼠右鍵按一下您要變更其顏色的節點或箭頭。

1. 選取&#x200B;[!UICONTROL **變更顏色**]。<!--make sure "color" isn't capitalized. It is in the req doc-->

1. 選取所需的顏色。

   下列色彩可供使用： <!--look into this interaction and color list-->

### 重新命名節點或箭頭

將元件拖曳至「歷程」畫布視覺效果時，會建立與元件名稱同名的節點。 您可以重新命名節點，以更符合節點代表的歷程步驟。

重新命名的選項適用於畫布上的下列物件：

* 個別節點

* 節點之間的箭頭

若要重新命名節點，請執行下列動作：

1. 以滑鼠右鍵按一下要重新命名的節點。

1. 選取&#x200B;[!UICONTROL **重新命名**]。

1. 指定新名稱，然後按Enter。<!--is that right?-->

### 套用劃分

畫布上的下列物件可使用將劃分套用至資料的選項：

* 個別節點

* 多個節點

* 節點之間的箭頭

* 節點之間的多個箭頭

### 將劃分套用至一或多個節點或箭頭

1. 選取一或多個要套用劃分的節點，然後以滑鼠右鍵按一下其中一個選取的節點。

   或

   在2個要套用劃分的節點之間選取一或多個箭頭，然後以滑鼠右鍵按一下其中一個選取的箭頭。

1. 選取&#x200B;[!UICONTROL **劃分**]。

### 將劃分套用至個別節點

您可以從左側邊欄將維度拖曳至畫布上您要套用劃分的節點。

如需詳細資訊，請參閱[新增節點](#add-a-node)。

### 建立客群

建立對象的選項適用於畫布上的下列物件：

* 個別節點

* 多個節點

* 節點之間的箭頭

* 節點之間的多個箭頭

若要建立對象：

1. 選取一或多個要建立對象的節點，然後以滑鼠右鍵按一下其中一個選取的節點。

   或

   在2個要建立受眾的節點之間選取一或多個箭頭，然後以滑鼠右鍵按一下其中一個選取的箭頭。

1. 選取&#x200B;[!UICONTROL **建立對象**]。

1. 繼續建立和發佈對象，如[建立和發佈對象](/help/components/audiences/publish.md)中所述。

### 檢視趨勢資料

您可以在Journey Canvas中的線圖檢視物件的趨勢資料。 &lt;！—，其中包含一些預先建立的異常偵測資料（這是「流失」中的定義）>

趨勢選項可用於畫布上的下列物件：

* 個別節點

* 多個節點

* 節點之間的箭頭

* 節點之間的多個箭頭

若要檢視趨勢資料：

1. 選取您要檢視趨勢資料的一或多個節點，然後以滑鼠右鍵按一下其中一個選取的節點。

   或

   在2個您要檢視趨勢資料的節點之間選取一或多個箭頭，然後以滑鼠右鍵按一下其中一個選取的箭頭。

1. 選取&#x200B;[!UICONTROL **趨勢**]。

### 複製節點

複製選項適用於畫布上的下列物件：

* 多個節點

若要複製節點：

1. 選取多個要複製的節點。

1. 以滑鼠右鍵按一下其中一個選取的節點，然後選取&#x200B;[!UICONTROL **複製**]。


### 在節點之間新增時間限制

您可以在節點之間設定時間限制。 當時間限制已設定時，如果人員依照定義的歷程移動，但花在節點之間分配的時間較長，則被視為已離開歷程。

新增時間限制的選項適用於畫布上的下列物件：

* 節點之間的箭頭

若要新增時間限制：

1. 以滑鼠右鍵按兩節點之間的箭頭，然後選取&#x200B;[!UICONTROL **新增時間限制**]。

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

-->

### 根據節點或箭頭建立篩選器

您可以根據歷程中的節點或箭頭來建立新的篩選器。 建立篩選器後，您就可以在Analysis Workspace的任何地方使用此篩選器。

從歷程畫布建立的篩選器使用[循序篩選](/help/components/filters/seg-sequential-build.md)。 這表示篩選器會使用THEN運運算元，將人們流經的事件（即歷程）順序連結在一起，連至選取的節點或箭頭。 符合所選節點或箭頭的所有事件都會納入篩選器中。

如果您根據具有多個路徑的節點建立篩選器，則所有路徑都會納入篩選器中。 使用OR運運算元聯結個別路徑。

若要建立篩選器：

1. 在畫布上，以滑鼠右鍵按一下要用來建立篩選的節點或箭頭。

1. 選取&#x200B;[!UICONTROL **從節點**]&#x200B;建立篩選器，或&#x200B;[!UICONTROL **從箭頭**]&#x200B;建立篩選器。

   篩選產生器隨即顯示。 在&#x200B;[!UICONTROL **定義**]&#x200B;區段中，篩選定義是根據您選取的節點或箭頭及其在歷程中的內容建立的。

1. 指定篩選的標題，並進行任何其他變更。 如需建立篩選的詳細資訊，請參閱[篩選產生器](/help/components/filters/filter-builder.md)。

1. 選取&#x200B;[!UICONTROL **儲存**]&#x200B;以儲存篩選。

### 刪除節點

您可以在歷程中一次刪除一或多個節點。 當您刪除歷程中2個節點之間連線的節點時，剩餘2個節點會直接連線。

若要刪除Journey Canvas中的節點：

1. 選取一或多個要刪除的節點，然後以滑鼠右鍵按一下其中一個選取的節點。

1. 選取「[!UICONTROL **刪除**]」。

### 刪除節點之間的箭頭

您可以在歷程中一次刪除一或多個箭頭。 當您刪除2個節點之間的箭頭時，這些節點將不再連線。 如果箭頭是較長路徑的一部分，則路徑會中斷連線。

若要刪除Journey Canvas中節點之間的箭頭：

1. 在2個要刪除的節點之間選取一或多個箭頭，然後以滑鼠右鍵按一下其中一個選取的箭頭。

1. 選取「[!UICONTROL **刪除**]」。


<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |

   -->


## 從Journey Optimizer開啟歷程


在Journey Optimizer中，開啟您要在Journey Canvas中分析的歷程。

1. 選取&#x200B;[!UICONTROL **在CJA**]&#x200B;中分析。<!-- ?? -->

