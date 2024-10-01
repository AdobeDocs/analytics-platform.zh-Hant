---
description: 瞭解如何在Workspace專案中使用流量視覺效果。
title: 如何設定流量視覺效果
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 37%

---

# 設定流量視覺效果

流量視覺效果可協助您瞭解源自網站或應用程式上特定轉換事件的歷程。 或導致特定轉換事件。 此視覺效果會透過您的維度（和維度專案）或量度追蹤路徑。

您可以設定感興趣的路徑的起點或終點。 或分析流經維度或維度專案的所有路徑。

![顯示[開頭為]、[包含]和[結尾為]欄位的[流量]設定畫面。](assets/new-flow.png)

## 使用

1. 新增![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;視覺效果。 請參閱[將視覺效果新增至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 使用以下選項之一，錨定您的流量視覺效果：

   * [!UICONTROL **開頭為**] (量度、維度或項目)，或
   * [!UICONTROL **包含**] (量度、維度或項目)，或
   * [!UICONTROL **結束於**] (量度、維度或項目)

   這些類別都會在熒幕中顯示為&#x200B;*拖放區域*。 您可以使用 3 種方式填入拖放區域：

   * 使用下拉式選單來選取量度或維度。
   * 從左側面板拖曳維度或量度。
   * 開始輸入維度或指標的名稱，然後在下拉式清單中出現時即可選取。

   >[!IMPORTANT]
   >
   >計算量度不能用於&#x200B;**[!UICONTROL 開頭為]**&#x200B;或&#x200B;**[!UICONTROL 結尾為]**&#x200B;欄位。

1. 如果您選擇量度，則還需要提供&#x200B;[!UICONTROL **路徑Dimension**]，以作為前往或來自您所選元件的路徑，如下所示。 預設為&#x200B;[!UICONTROL **「頁面」**]。

   ![流程組態](assets/flow-configure.png)

1. (選項) 選取「**[!UICONTROL 顯示進階設定]**」以設定以下任何選項：


   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 繞排標籤]** | 一般而言，系統會截斷「流量」元素的標籤以節省螢幕空間，但您可勾選此方塊以完整顯示標籤。預設 = 未勾選。 |
   | **[!UICONTROL 包含重複例項]** | 「流量」視覺效果是根據維度的例項而定。此設定可讓您選擇要包含或排除重複例項，例如頁面重新載入。 不過，無法從包含多值維度 (例如 listVars、listProps、s.product、銷售 eVars 等) 的「流量」視覺效果中移除重複項目。 <p>此選項預設為停用。</p> |
   | **[!UICONTROL 僅限於第一次/最後一次發生]** | 將路徑限製為以維度、專案或量度的第一次或最後一次發生次數開頭或結尾的路徑。 如需更詳細的說明，請參閱[僅限於第一次/最後一次發生](#example-scenario-for-limit-to-firstlast-occurrence)。 |
   | **[!UICONTROL 欄數]** | 流量圖中所需的欄數。您最多可以指定 5 個欄。 |
   | **[!UICONTROL 每欄展開的項目]** | 每欄中所需的項目數。您最多可以指定每欄展開 10 個項目。 |
   | **[!UICONTROL 流量容器]** | 您可以在&#x200B;**[!UICONTROL 工作階段]**&#x200B;和&#x200B;**[!UICONTROL 人員]**&#x200B;之間切換以分析路徑。 這些設定可協助您瞭解個人在個人層級的參與度（跨工作階段），或將分析限制在單一工作階段。 |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 欄數]**&#x200B;和&#x200B;**[!UICONTROL 每欄展開的項目]**&#x200B;組合可確定建立流量視覺效量所需的基本請求數。這些數字越高，呈現視覺效果所需的時間就越長。


1. 選取「**[!UICONTROL 建立]**」。


### 範例

假設您想要追蹤使用者在您網站上最受歡迎頁面之間所經過的路徑。

1. 建立上述的流量視覺效果。
1. 拖曳&#x200B;[!UICONTROL **頁面**]&#x200B;維度至「**[!UICONTROL 包含]**」欄位，然後選取「[!UICONTROL **建立**]」。
1. 流量視覺效果會建置，而檢視次數最多的頁面會顯示在視覺效果的中心。 您也會看見前導至該頁面的前幾頁（焦點節點的左側），以及前導至該頁面的前幾頁（焦點節點的右側）。
1. 分析流量中的資料，如[設定](#configure)中所述。


## 設定

流量組態的摘要會顯示在視覺效果的最上方。 圖表中的路徑會依照比例顯示。具有較多活動的路徑看起來比較寬。

![顯示以造訪結束的流量輸出範例、路徑維度：頁面，以及流量容器：訪客。](assets/flow-output.png)

若要深入研究資料，您有幾個選項：

* 流量圖是互動式的。將滑鼠移到圖表上方，可變更顯示的詳細資料。

* 選取圖表中的節點，會顯示該節點的詳細資料。再次選取節點以將其摺疊。

  ![顯示節點詳細資訊的互動流程圖範例。](assets/node-details.png)

* 您可以篩選欄以僅顯示某些結果，例如包含和排除、指定條件等。

* 選取左側或右側的![AddCircle](/help/assets/icons/AddCircle.svg)以展開欄。

* 若要自訂輸出，請使用[內容功能表](#context-menu)選項。

* 若要編輯流量或使用不同的選項重新建置流量，請選取組態摘要旁的![編輯](/help/assets/icons/Edit.svg)。

## 篩選器

當您將游標停留在欄上方時，會出現篩選器![篩選器](/help/assets/icons/Filter.svg)。 選取篩選器後，會出現與自由表格中相同的篩選器對話方塊。 請參閱[篩選與排序](freeform-table/../../freeform-table/filter-and-sort.md)。

* 使用&#x200B;**[!UICONTROL 顯示進階]**&#x200B;來設定進階設定，以包含或排除運運算元清單中的特定條件。 如需詳細資訊，請參閱[篩選和排序](../freeform-table/filter-and-sort.md)。
* 篩選欄之後，該特定欄會反映篩選結果。 藍色![篩選器](/help/assets/icons/FilterColored.svg)表示欄已篩選。  篩選器會減少欄以僅顯示篩選器中允許的專案。 或者，它會移除所有專案，但您想要在篩選器中移除的一個專案除外。
* 只要有資料流入其餘節點，所有下游和上游欄都會保持不變。
* 若要移除篩選器，請選取![篩選器](/help/assets/icons/Filter.svg)以開啟篩選器功能表。 移除套用的所有篩選器，然後選取「**[!UICONTROL 儲存]**」。流量應會回到其先前的未篩選狀態。

## 內容功能表

在流量視覺效果中的任何節點上使用內容功能表，並搭配下列選項：

| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 焦點放在這個節點]** | 將焦點變更至選取的節點。焦點節點會出現在流量圖的中央。 |
| **[!UICONTROL 重新開始]** | 將您帶回自由圖表產生器，讓您在那裡建立新的流量圖表。 |
| **[!UICONTROL 為此路徑建立篩選器]** | 建立篩選器。 此選取範圍會帶您進入篩選器產生器，您可在此設定新篩選器。 |
| **[!UICONTROL 劃分]** | 依據可用的「維度」、「量度」或「時間」來劃分節點。 |
| **[!UICONTROL 篩選資料行]** | 顯示的篩選選項與自由表格中提供的選項相同。 如需有關可用選項的詳細資訊，請參閱[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的「將簡單或進階篩選套用至表格」一節。 |
| **[!UICONTROL 排除專案]**&#x200B;或&#x200B;**[!UICONTROL 還原排除的專案]** | 從欄中移除特定節點，並自動將其建立為欄頂端的篩選器。若要還原排除的專案，請從內容功能表中選取&#x200B;**[!UICONTROL 還原排除的專案]**。 您也可以開啟欄頂端的篩選器，並移除包含剛剛排除的項目的方塊。 |
| **[!UICONTROL 趨勢]** | 建立節點的趨勢圖。 |
| **[!UICONTROL 顯示下一欄]** / **[!UICONTROL 顯示上一欄]** | 顯示視覺效果下一欄 (右邊) 或上一欄 (左邊)。 |
| **[!UICONTROL 隱藏欄]**n | 隱藏視覺效果的選取欄。 |
| **[!UICONTROL 展開整個欄]** | 展開該欄以顯示所有節點。依預設，只會顯示前五個節點。 |
| **[!UICONTROL 從選取專案建立對象]** | 根據選取的欄建立對象。 |
| **[!UICONTROL 摺疊整個欄]** | 隱藏該欄中的所有節點。 |

## 僅限於第一次/最後一次發生

使用此選項時，請記住：

* **[!UICONTROL 「僅限於第一次/最後一次發生」]**&#x200B;只會計算系列中的第一次/最後一次發生次數。**[!UICONTROL 「開頭為」]**&#x200B;或&#x200B;**[!UICONTROL 「結束於」]**&#x200B;條件的所有其他發生次數都會被捨棄。
* 如果與&#x200B;**[!UICONTROL 開頭為]**的流量一起使用，則僅包含符合開始條件的第一次發生次數。
在下列範例中，流程的每個步驟都包含**所有**&#x200B;的&#x200B;*加入購物車*&#x200B;和&#x200B;*產品主要類別*事件。
  ![沒有限制，第一個](assets/limitofffirst.png)

  在以下範例中，流程的每個步驟中只包括&#x200B;*加入購物車*&#x200B;和&#x200B;*產品主要類別*&#x200B;的&#x200B;**前**次。
  ![Lint，開始](assets/limitonfirst.png)
* 如果與&#x200B;**[!UICONTROL Ends with]**流量一起使用，則僅包含符合結束條件的最後一次發生次數。
在下列範例中，流程的每個步驟都包含*產品主要類別*&#x200B;的&#x200B;**所有**&#x200B;次發生次數和&#x200B;*加入購物車*。
  ![沒有限制，第一個](assets/limitofflast.png)

  在下列範例中，流程的每個步驟中只包括&#x200B;*產品主要類別*&#x200B;的&#x200B;**最後**&#x200B;次和&#x200B;*加入購物車*。
  ![Lint，開始](assets/limitonlast.png)
* 使用的系列因容器而異。如果使用&#x200B;**[!UICONTROL 人員]**&#x200B;容器，則事件系列為工作階段。 如果使用&#x200B;**[!UICONTROL 工作階段]**&#x200B;容器，則事件系列是所提供日期範圍內特定使用者的所有事件。
* 在&#x200B;**[!UICONTROL 開頭為]**&#x200B;或&#x200B;**[!UICONTROL 結尾為]**&#x200B;欄位中使用量度或Dimension專案時，可以在進階設定中設定&#x200B;**[!UICONTROL 僅限於第一次/最後一次發生]**&#x200B;選項。


>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

