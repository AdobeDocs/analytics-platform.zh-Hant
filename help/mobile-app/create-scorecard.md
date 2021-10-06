---
description: 如何建立Adobe Analytics控制面板計分卡
title: 建立計分卡
feature: Analytics Dashboards
role: User, Admin
source-git-commit: c41eeda10083ef6cc3d46b044f1c0052d08a575b
workflow-type: tm+mt
source-wordcount: '1323'
ht-degree: 56%

---


# 建立計分卡

以下資訊可為 Adobe Analytics 資料的組織者說明如何設定控制面板並將其對執行使用者呈現。首先，您可以檢視Adobe Analytics控制面板計分卡產生器影片：

>[!VIDEO](https://video.tv.adobe.com/v/34544)

Adobe Analytics計分卡以圖磚式版面配置呈現，為執行使用者顯示視覺化的關鍵資料，如下所示：

![計分卡範例](assets/intro_scorecard.png)

此計分卡的組織者可使用計分卡產生器，為執行消費者設定計分卡上顯示的圖磚。 您也可以設定點選圖磚後，詳細檢視或劃分可如何調整。 計分卡建立程式的介面如下：

![計分卡建立程式](assets/scorecard_builder.png)

若要建立計分卡，您必須執行下列操作：

1. 存取[!UICONTROL 「空白行動計分卡」]範本。
2. 使用資料設定計分卡並儲存。

## 存取[!UICONTROL 「空白行動計分卡」]範本

您可以建立新專案，或從「工具」功能表存取[!UICONTROL 空白行動計分卡]範本。

### 建立新專案

1. 開啟 Adobe Analytics，然後按一下&#x200B;**[!UICONTROL 「工作區」]**&#x200B;標籤。
1. 按一下「**[!UICONTROL 建立專案]**」，然後選取「**[!UICONTROL 空白行動計分卡]**」專案範本。
1. 按一下&#x200B;**[!UICONTROL 「建立」]**。

![計分卡範本](assets/new_template.png)

### 工具選單

1. 從&#x200B;**[!UICONTROL 工具]**&#x200B;功能表中，選取&#x200B;**[!UICONTROL Analytics控制面板（行動應用程式）]**。
1. 在後續畫面中，按一下「**[!UICONTROL 建立新計分卡]**」。

## 使用資料設定計分卡並儲存

實施計分卡範本：

1. 在右側邊欄的&#x200B;**[!UICONTROL 「屬性」]**&#x200B;下方，指定您要使用資料的&#x200B;**[!UICONTROL 專案報表套裝]**。

   ![選取報表套裝](assets/properties_save.png)

1. 若要為計分卡新增圖磚，請從左側面板拖曳量度，放置到顯示&#x200B;**[!UICONTROL 「將量度拖放至此」]**&#x200B;的區域。您也可以使用類似的工作流程，跨圖磚插入量度。

   ![新增圖磚](assets/build_list.png)


1. 您可以從每個圖磚存取顯示該量度其他資訊的詳細檢視畫面，例如前幾名相關維度的清單。

## 新增維度或量度

若要為量度新增相關維度，請從左側面板將維度拖曳至圖磚上。

例如，將適當的維度（如此範例中的&#x200B;**[!DNL Marketing Channel]**）拖曳至圖磚上，即可將其新增至&#x200B;**[!UICONTROL 獨特訪客]**&#x200B;量度。 Dimension劃分會顯示在磁貼特定&#x200B;**[!UICONTROL 屬性]**&#x200B;的[!UICONTROL 鑽取]（劃分）區段下。 每個圖磚可新增多個維度。

![新增維度](assets/layer_dimensions.png)

## 套用區段

若要將區段套用至個別圖磚，請從左側面板將區段直接拖曳至圖磚上。

如果要將區段套用至計分卡中的所有圖磚，請將圖磚放置在計分卡上。或者，您也可以在日期範圍下方的篩選功能表中選取區段，以套用區段。您可以比照 Adobe Analytics Workspace 中的相同方式，來[設定並套用計分卡的篩選器](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=zh-Hant)。

![建立篩選的區段](assets/segment_ui.png)

## 新增日期範圍

新增和移除日期範圍組合，該組合可在計分卡中從日期範圍下拉式清單中選取。

![新計分卡](assets/new_score_card.png)

每個新計分卡都始於 6 個以今日和昨日的資料為主日期範圍組合。您可以按一下 x 來移除不必要的日期範圍，也可以按一下鉛筆來編輯每個日期範圍組合。

![新計分卡 2](assets/new_score_card2.png)

若要建立或變更主要日期，使用下拉式選單並選擇可用的日期範圍，或將右側邊欄的日期組合拖放至下拉區。

![新計分卡 3](assets/new_score_card3.png)

若要建立比較日期，可以在下拉式選單中選擇方便的預設集以便進行共同時間比較。您還可以從右側邊欄拖放一個日期元件。

![新計分卡 4](assets/new_score_card4.png)

如果您想要的日期範圍還沒有建立，可以按一下日曆圖示建立一個新的。

![新計分卡 5](assets/new_score_card5.png)

這會帶您到日期範圍產生器，在其中可以建立和儲存新的日期範圍元件。

## 套用視覺效果

Analytics控制面板提供四個視覺效果，讓您能夠深入分析維度項目和量度。 變更圖磚[!UICONTROL 屬性]的[!UICONTROL 圖表類型]，以變更為不同的視覺效果。 只要選取正確的圖磚，然後變更圖表類型即可。

![磁貼屬性](assets/properties.png)

或者，按一下左側邊欄中的[!UICONTROL 視覺效果]圖示，然後將右側視覺效果拖放至圖磚：

![視覺效果](assets/vizs.png)

**[!UICONTROL 摘要數字]**

使用「摘要數字」視覺效果來強調專案中重要的大數字。

![摘要數字](assets/sparkline.png)

** Donutvisualization**

此視覺效果類似圓餅圖，以整體的部分或區段顯示資料。比較總計的百分比時，請使用環圈圖。 例如，假設您想了解哪些廣告平台對獨特訪客總數的貢獻：

![環形圖視覺效果](assets/donut-viz.png)

**線條視覺效果**

線條圖視覺效果使用線條圖表示量度，以顯示一段時間中值的變化。折線圖只可以在當做維度時使用。

![線條視覺效果](assets/line.png)


**[!UICONTROL 水準條形] 視覺效果**

此視覺效果顯示代表一或多個量度多個值的橫條。例如，若要輕鬆查看您的最上層產品，請使用[!UICONTROL 水準條]作為偏好的視覺效果。

![水準條](assets/horizontal.png)

**移除未 [!UICONTROL 指定]**

如果您想從資料中移除[!UICONTROL 未指定]維度項目，請執行下列動作：

1. 選擇正確的磁貼。
1. 在右側邊欄的&#x200B;**[!UICONTROL Drillins]**&#x200B;下，選取您要移除其&#x200B;**[!UICONTROL Unspecified]**&#x200B;項目之維度項目旁的右箭頭。

   ![未指定](assets/unspecified.png)

1. 按一下&#x200B;**[!UICONTROL Unspecified]**&#x200B;旁的圖示，從報表中移除未指定的資料。

## 查看和配置磁貼屬性

按一下計分卡產生器中的圖磚時，右側邊欄會顯示與該圖磚相關聯的屬性和特性。 在此邊欄中，您可以為該圖磚提供新的&#x200B;**[!UICONTROL 標題]**，或是透過指定元件來設定圖磚，而不必從左側邊欄拖放元件。

![「屬性」圖磚](assets/properties_tile.png)

按一下圖磚時，動態快顯視窗會顯示應用程式中執行使用者看到「鑽取（劃分）」檢視的方式。 如果沒有將任何維度套用至圖磚，劃分維度會是&#x200B;**小時**&#x200B;或&#x200B;**天數**，視預設日期範圍而定。

劃分會依其他量度和維度（例如在此零售範例中）逐字劃分量度和維度，借此精簡分析：

* 依廣告平台(AMO ID)劃分的獨特訪客量度
* 依產品類別劃分的瀏覽（零售）
* 依產品名稱劃分的總收入

![Breakdown_view](assets/break_view.png)

新增至圖磚的每個維度，都會顯示在應用程式詳細檢視的下拉式清單中。執行使用者可從下拉式清單中選擇選項。

## 移除元件

同樣地，若要移除套用至整個計分卡的元件，請在計分卡上按一下圖磚之外的任意位置，然後按一下將游標停留在元件上時顯示的 **x**，即可將其移除，如下方「**初次瀏覽**」區段所示：

![Remove_components](assets/new_remove.png)

## 為計分卡命名

若要為計分卡命名，請按一下畫面左上角的命名空間，並輸入新名稱。

![Naming_Scorecards](assets/new_name.png)

## 共用計分卡

若要與執行使用者共用計分卡：

1. 按一下&#x200B;**[!UICONTROL 「共用」]**&#x200B;功能表，然後選取&#x200B;**[!UICONTROL 「共用計分卡」]**。

1. 在&#x200B;**[!UICONTROL 「共用行動計分卡」]**&#x200B;表單中，依照以下說明填寫欄位：

   * 提供計分卡的名稱
   * 提供計分卡的說明
   * 新增相關標籤
   * 指定計分卡的收件者

1. 按一下&#x200B;**[!UICONTROL 「共用」]**。

![Share_Scorecards](assets/new_share.png)

共用計分卡後，收件者可在其Analytics控制面板上存取該計分卡。 如果您後續在計分卡建立程式中變更計分卡，共用的計分卡會自動更新。 到時，執行使用者在應用程式中重新整理計分卡後，就能看見變更。

如果是以新增新元件的方式更新計分卡，您可再次共用計分卡（並勾選&#x200B;**[!UICONTROL 共用內嵌元件]**&#x200B;選項），以確保您的執行使用者有權存取這些變更。