---
description: 您可以在Analysis Workspace中從接觸點建立篩選器、將篩選器新增為接觸點，以及跨各種篩選器比較關鍵工作流程。
keywords: 流失和篩選器；流失分析中的篩選器；比較流失的篩選器
title: 在流失分析中套用篩選器
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 15%

---

# 在流失分析中套用篩選器

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[深入了解...](/help/getting-started/cja-aa.md)

您可以在Analysis Workspace中從接觸點建立篩選器、將篩選器新增為接觸點，以及跨各種篩選器比較關鍵工作流程。

>[!IMPORTANT]
>
>在流失分析中當作查核點使用的篩選器，其所用容器的層級必須低於流失視覺效果的整體設定。 若使用訪客內容流失，當作查核點使用的篩選器必須為造訪或點擊型篩選器。 使用造訪內容流失時，當作查核點使用的篩選器必須是點擊型篩選器。 如果使用無效的組合，流失率會計為 100%。我們已新增警告至「流失」視覺效果，當您新增不相容的篩選器作為接觸點時，將會顯示此警告。 某些無效的篩選器容器組合會導致無效的流失圖表，例如：

* 使用以訪客為基礎的篩選器，作為訪客內容流失視覺效果內的接觸點
* 使用以訪客為基礎的篩選器，作為造訪內容流失視覺效果內的接觸點
* 使用造訪型篩選器作為造訪內容流失視覺效果內的接觸點

## 從接觸點建立篩選 {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 從您特別感興趣的特定接觸點建立篩選器，此篩選器可能適合套用至其他報表。 若要這麼做，請以滑鼠右鍵按一下接觸點並選取&#x200B;**[!UICONTROL 從接觸點建立篩選器]**。

   ![](assets/segment-from-touchpoint.png)

   篩選器產生器隨即開啟，預先填入符合您選取接觸點的預先建立循序篩選器：

   ![](assets/segment-builder.png)

1. 為篩選器提供標題和說明並儲存。

   您現在可以在任何您想要的專案中使用此篩選器。

## 將篩選器新增為接觸點 {#section_17611C1A07444BE891DC21EE8FC03EFC}

如果您想查看美國使用者（舉例來說）的趨勢以及如何影響流失，只需將美國使用者篩選器拖曳至流失中：

![](assets/segment-touchpoint.png)

或者，將美國使用者篩選器拖曳至其他查核點，即可建立AND接觸點。

## 比較流失中的篩選器 {#section_E0B761A69B1545908B52E05379277B56}

您可以在「流失」視覺效果中比較不限數量的篩選器。

1. 從左側的[!UICONTROL Filter]邊欄選取您要比較的篩選器。 在範例中，我們選取了2個篩選器：美國使用者和非美國使用者。
1. 將它們拖曳至頂端的「篩選」拖放區域。

   ![](assets/segment-drop.png)

1. 選用：您可將「所有造訪」保留作為預設容器，也可將其刪除。

   ![](assets/seg-compare.png)

1. 您現在可以比較這兩個篩選器的流失，例如其中一個篩選器的績效優於另一個篩選器，或其他分析。
