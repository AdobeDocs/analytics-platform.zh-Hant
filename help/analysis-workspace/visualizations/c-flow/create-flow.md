---
description: 瞭解如何在Analysis Workspace中設定流量視覺效果
title: 設定流量視覺效果
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1759'
ht-degree: 79%

---

# 設定流量視覺效果 {#configure-a-flow-visualization}

>[!CONTEXTUALHELP]
>id="workspace_flow_startswith"
>title="開始於"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_flow_contains"
>title="包含"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_flow_endswith"
>title="終止於"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_flow_pathingdimension"
>title="路徑分析維度"
>abstract="選取一個維度，以用作前往或離開您選取之元件的路徑。"

>[!CONTEXTUALHELP]
>id="workspace_flow_container"
>title="流量容器"
>abstract="選取用於顯示路徑分析 (數量) 的容器。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_disabled"
>title="包括重複項目 (已停用)"
>abstract="無法從包括多值維度的「流量」視覺效果中移除重複項目。"

>[!CONTEXTUALHELP]
>id="workspace_flow_include_repeats_default"
>title="包括重複項目"
>abstract="「流量」視覺效果是根據維度的例項而定。此設定提供您要包括或排除重複執行個體的選項，例如：頁面重新載入次數。"

>[!CONTEXTUALHELP]
>id="workspace_flow_limit_occurrence"
>title="僅限於第一次/最後一次發生次數"
>abstract="結果僅限為第一個/最後一個接觸點是進入/退出時的路徑。"

>[!CONTEXTUALHELP]
>id="workspace_flow_numberofcolumns"
>title="欄數"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_flow_itemsexpandedpercolumn"
>title="每欄展開的項目"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_flow_resettoupdate"
>title="重設以更新"
>abstract="此欄位僅可在初始建置時設定。若要更新此欄位，請選取「**[!UICONTROL 重設]**」以建置新的「流量」視覺效果。"


流量視覺效果可協助您瞭解源自網站或應用程式上特定轉換事件的歷程。 或導致特定轉換事件。 此視覺效果會透過您的維度（和維度專案）或量度追蹤路徑。

您可以設定感興趣的路徑的起點或終點。 或分析流經維度或維度專案的所有路徑。

![顯示[開頭為]、[包含]和[結尾為]欄位的[流量]設定畫面。](assets/new-flow.png)

## 使用

1. 新增 ![GraphPathing](/help/assets/icons/GraphPathing.svg) **[!UICONTROL 流量]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 使用以下選項之一，錨定您的流量視覺效果：

   * [!UICONTROL **開頭為**] (量度、維度或項目)，或
   * [!UICONTROL **包含**] (量度、維度或項目)，或
   * [!UICONTROL **結束於**] (量度、維度或項目)

   這些類別皆會顯示為螢幕上的&#x200B;*放置區*。您可以使用 3 種方式填入拖放區域：

   * 使用下拉式選單來選取量度或維度。
   * 從左側面板拖曳維度或量度。
   * 開始輸入維度或量度的名稱，然後在其出現在下拉式選單中時選取它。

   >[!IMPORTANT]
   >
   >計算量度不可在&#x200B;**[!UICONTROL 開頭為]**&#x200B;或&#x200B;**[!UICONTROL 結束於]**&#x200B;的欄位中使用。

1. 如果您選擇一個量度，您還需要提供一個&#x200B;[!UICONTROL **路徑分析維度**]，以用於通往或來自選取元件的路徑，如此處所示。此預設為&#x200B;[!UICONTROL **「頁面」**]。

   ![流量設定](assets/flow-configure.png)

1. (可選) 請選取「**[!UICONTROL 顯示進階設定]**」，以設定下列任何選項：


   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 繞排標籤]** | 一般而言，系統會截斷「流量」元素的標籤以節省螢幕空間，但您可勾選此方塊以完整顯示標籤。預設 = 未勾選。 |
   | **[!UICONTROL 包含重複例項]** | 「流量」視覺效果是根據維度的例項而定。此設定提供您要包括或排除重複例項的選項，例如頁面重新載入次數。不過，無法從包括多值維度 (例如 listVars、listProps、s.product、銷售 eVars 等) 的「流量」視覺效果中移除重複項目。 <p>此選項預設為停用。</p> |
   | **[!UICONTROL 僅限於第一次/最後一次發生次數]** | 將路徑限制為維度、項目/或量度開始或結束於第一次或最後一次發生次數的路徑。請參閱[僅限第一次/最後一次發生次數](#example-scenario-for-limit-to-firstlast-occurrence)，以了解更多詳細的解釋。 |
   | **[!UICONTROL 欄數]** | 流量圖中所需的欄數。您最多可以指定 5 個欄。 |
   | **[!UICONTROL 每欄展開的項目]** | 每欄中所需的項目數。您最多可以指定每欄展開 10 個項目。 |
   | **[!UICONTROL 流量容器]** | 您可以切換&#x200B;**[!UICONTROL 全域帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 商機]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 購買群組]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 工作階段]**&#x200B;和&#x200B;**[!UICONTROL 人員]**&#x200B;以分析路徑。 這些設定可協助您瞭解特定容器層級（跨工作階段）的參與情形，或將分析限制在單一工作階段。 |

   >[!IMPORTANT]
   >
   >**[!UICONTROL 欄數]**&#x200B;和&#x200B;**[!UICONTROL 每欄展開的項目]**&#x200B;組合可確定建立流量視覺效量所需的基本請求數。這些數字越高，呈現視覺效果所需的時間就越長。


1. 選取「**[!UICONTROL 建置]**」。


### 範例

假設您想要追蹤使用者往返您網站上最受歡迎頁面的路徑。

1. 依上所述建立流量視覺效果。
1. 拖曳&#x200B;[!UICONTROL **頁面**]&#x200B;維度至「**[!UICONTROL 包含]**」欄位，然後選取「[!UICONTROL **建置**]」。
1. 使用檢視次數最多的頁面 (可在視覺效果中央的焦點節點內看到) 建置流量視覺效果。您也可以看到會引導至該頁面的上層頁面 (位於焦點節點的左側) 以及引導出該頁面的上層頁面 (位於焦點節點的右側)。
1. 如[設定](#configure)所述，在流量分析資料。


## 設定

流量設定的摘要會顯示在視覺效果的頂端。圖表中的路徑成比例。 活動較多的路徑看起來較厚。

![流量輸出範例顯示結束於造訪數、路徑分析維度：頁面和流量容器：訪客。](assets/flow-output.png)

若要深入研究資料，您有幾個選項：

* 流程圖為互動式。 將滑鼠移到圖表上可變更顯示的詳細資料。

* 當您在圖表中選取節點時，會顯示該節點的詳細資料。 再次選取節點，以將其摺疊。

  在流量視覺效果中保持多個節點展開會影響報表時間。 一般而言，在特定時間內不應持續擴充超過10個節點。

  ![顯示節點詳細資訊的範例互動式流量圖。](assets/node-details.png)

* 您可以篩選欄以僅顯示特定結果，例如包括和排除、指定條件等。

* 請選取左側或右側的「![AddCircle](/help/assets/icons/AddCircle.svg)」以展開一欄。

* 若要自訂輸出，請使用[內容選單](#context-menu)選項。

* 若要使用不同選項編輯流量或重建，請選取設定摘要旁的「![編輯](/help/assets/icons/Edit.svg)」。

## 篩選器

將滑鼠游標停留在欄上方時，會出現一個篩選器![Filter](/help/assets/icons/Filter.svg)。選取篩選器，您會獲得與在自由格式表格中相同的篩選器對話框。請參閱[篩選和排序](freeform-table/../../freeform-table/filter-and-sort.md)。

* 使用「**[!UICONTROL 顯示進階]**」以設定進階設定來使用運算子清單包括或排除特定條件。請參閱[篩選和排序](../freeform-table/filter-and-sort.md)，以了解更多詳細資訊。
* 您篩選某一欄後，該特定欄會反映此篩選結果。藍色![篩選器](/help/assets/icons/FilterColored.svg)表示已篩選該欄。篩選器可以減少欄，僅顯示篩選器中允許的項目。或者移除所有項目，篩選器中您所需的一個項目除外。
* 只要有資料流入剩餘節點，所有下游和上游欄均保持不變。
* 若要移除篩選器，請選取「![篩選器](/help/assets/icons/Filter.svg)」以開啟篩選器選單。移除套用的所有篩選器，然後選取「**[!UICONTROL 儲存]**」。流量應會回到其先前的未篩選狀態。

## 內容選單

使用流量視覺效果中任意節點上的內容選單，其中包含下列選項：

| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 焦點放在這個節點]** | 將焦點變更為選取的節點。 焦點節點會顯示在「流量」圖表的中心。 |
| **[!UICONTROL 重新開始]** | 將您帶回自由格式圖表產生器，您可以在那裡建置新的流量圖。 |
| **[!UICONTROL 為此路徑建立區段]** | 建立區段。 此選取範圍會帶您進入區段產生器，您可在此設定新區段。 |
| **[!UICONTROL 劃分]** | 依據可用的「維度」、「量度」或「時間」來劃分節點。 |
| **[!UICONTROL 篩選欄]** | 出現如同在自由格式表格中可用的相同篩選器選項。請參閱[篩選和排序表格](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)中的「套用簡易或進階篩選器置表格」，了解有關可用選項的更多資訊。 |
| **[!UICONTROL 排除項目]**&#x200B;或&#x200B;**[!UICONTROL 還原排除項目]** | 從欄中移除特定節點，並自動將其建立為欄頂端的篩選器。若要還原排除項目，請從內容選單選取「**[!UICONTROL 還原排除項目]**」。您也可以開啟欄頂端的區段，並移除包含您剛剛排除的專案的Pillbox。 |
| **[!UICONTROL 趨勢]** | 建立節點的趨勢圖。 |
| **[!UICONTROL 顯示下一欄]**/**[!UICONTROL 顯示上一欄]** | 顯示視覺效果下一欄 (右邊) 或上一欄 (左邊)。 |
| **[!UICONTROL 隱藏資料行]**n | 隱藏視覺效果的選取欄。 |
| **[!UICONTROL 展開整個欄]** | 展開欄以顯示所有節點。 依預設，只會顯示前五個節點。 |
| **[!UICONTROL 從選取項目中建立客群]** | 根據選取欄建立客群。 |
| **[!UICONTROL 摺疊整個欄]** | 隱藏該欄中的所有節點。 |

## 僅限於第一次/最後一次發生次數

使用此選項時，請記住：

* **[!UICONTROL 「僅限於第一次/最後一次發生」]**&#x200B;只會計算系列中的第一次/最後一次發生次數。**[!UICONTROL 「開頭為」]**&#x200B;或&#x200B;**[!UICONTROL 「結束於」]**&#x200B;條件的所有其他發生次數都會被捨棄。
* 如果與&#x200B;**[!UICONTROL 開頭為]**&#x200B;流量搭配使用，則僅包括符合開始條件的第一次發生次數。在下列範例中，**全部***新增至購物車* 的發生次數和&#x200B;*產品主類別*流量中的每個步驟均包括在內。
  ![無限制，第一](assets/limitofffirst.png)

  在下列範例中，僅&#x200B;**第一次***新增至購物車* 的發生次數和&#x200B;*產品主類別*流量中的每個步驟均包括在內。
  ![Lint，開始](assets/limitonfirst.png)
* 如果與&#x200B;**[!UICONTROL 結束於]**&#x200B;流量搭配使用，則僅包括符合結束條件的最後一次發生次數。在下列範例中，**全部***產品主類別* 的發生次數和&#x200B;*新增至購物車*流量中的每個步驟均包括在內。
  ![無限制，第一](assets/limitofflast.png)

  在下列範例中，僅&#x200B;**最後一次***產品主類別* 的發生次數和&#x200B;*新增至購物車*流量中的每個步驟均包括在內。
  ![Lint，開始](assets/limitonlast.png)
* 使用的系列因容器而異。如果您使用&#x200B;**[!UICONTROL 工作階段]**&#x200B;容器，則事件系列僅限於一個工作階段。  如果您使用任何其他容器(例如，**[!UICONTROL Person]**、**[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}或&#x200B;**[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"})，則事件系列會以指定的容器為基礎，並可能跨越多個工作階段。
* 在&#x200B;**[!UICONTROL 開始於]**&#x200B;或&#x200B;**[!UICONTROL 結束於]**&#x200B;欄位中使用量度或維度項目時，可以在進階設定中設定&#x200B;**[!UICONTROL 僅限於第一次/最後一次發生次數]**&#x200B;選項。


>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺化內容選單](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

