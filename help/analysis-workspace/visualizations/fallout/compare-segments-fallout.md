---
description: 您可以從接觸點建立區段、新增區段作為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: 在流失分析中套用區段
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 23%

---


# 在流失分析中套用篩選器

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

您可以從觸點建立篩選器、新增區段作為觸點，以及比較分析工作區中各種篩選器的關鍵工作流程。

>[!IMPORTANT]
>
>「流失」中用作查核點的篩選器，必須使用低於「流失」視覺化整體內容的容器。 使用訪客內容流失時，用作查核點的篩選必須是瀏覽或點擊型篩選。 使用瀏覽內容流失時，用作查核點的篩選器必須是點擊型區段。 如果使用無效的組合，流失率會計為 100%。我們已新增警告至「流失」視覺化，當您新增不相容的篩選器作為觸點時，將會顯示此警告。 某些無效的篩選容器組合會導致無效的流失圖，例如：

* 在訪客內容流失視覺化內使用訪客型篩選作為觸點
* 在瀏覽內容流失視覺化中使用訪客型篩選作為觸點
* 在瀏覽內容流失視覺化中使用瀏覽型篩選作為觸點

## 從接觸點{#section_915E8FBF35CD4F34828F860C1CCC2272}建立篩選

1. 從您特別感興趣的特定觸點建立篩選器，並套用至其他報表時可能會很有用。 若要這麼做，請以滑鼠右鍵按一下接觸點，然後選取「從接觸點建立篩選」**[!UICONTROL 。]**

   ![](assets/segment-from-touchpoint.png)

   「篩選產生器」隨即開啟，並預先填入符合您選取之觸點的預建循序篩選：

   ![](assets/segment-builder.png)

1. 為篩選器提供標題和說明並儲存。

   您現在可以在任何您想要的專案中使用此篩選。

## 新增濾鏡作為接觸點{#section_17611C1A07444BE891DC21EE8FC03EFC}

例如，如果您想瞭解您的美國使用者如何趨勢化及影響流失，只需將美國使用者篩選拖曳至流失中：

![](assets/segment-touchpoint.png)

或者，您也可以將美國使用者篩選拖曳至另一個查核點，以建立AND觸點。

## 比較流失{#section_E0B761A69B1545908B52E05379277B56}中的篩選器

您可以比較「流失」視覺化中不限數量的篩選器。

1. 從左側的[!UICONTROL Filter]邊欄中，選取您要比較的區段。 在我們的範例中，已選取 2 個區段：美國使用者和非美國使用者。
1. 將它們拖曳至頂端的「篩選」拖放區域。

   ![](assets/segment-drop.png)

1. 選用：您可將「所有造訪」保留作為預設容器，也可將其刪除。

   ![](assets/seg-compare.png)

1. 您現在可以比較兩個篩選器的流失，例如一個篩選器的效能優於另一個篩選器，或其他分析。
