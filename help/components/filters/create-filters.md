---
title: 建立篩選器
description: 瞭解建立篩選器的使用者介面。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# 建立篩選器

篩選器產生器提供的畫布可拖放量度、維度、篩選器和事件，以便根據容器階層邏輯、規則和運算子來篩選訪客。這個整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨造訪及頁面點擊的訪客屬性和動作。

您可以將任何元件類型（維度、維度項目、事件、量度、區段、區段範本、日期範圍）拖放至面板頂端的篩選拖放區，以建立立即篩選。

元件類型會自動轉換為濾鏡。 Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

請記住：

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* 對於完整維度和事件，分析工作區會建立「存在」點擊篩選。 例子：「點撃 eVar1 存在的位置」或「點撃 event1 存在的位置」。
* 如果「未指定」或「無」在篩選拖放區域中拖放，則會自動轉換為「不存在」篩選，以便正確處理。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>以此方式建立的篩選器是專案內部的。

您可以依照下列步驟，選擇將這些篩選設為公用（全域）:

1. 將滑鼠指標暫留在拖放區的篩選器上，然後按一下「i」圖示。
1. 在顯示的資訊面板中，按一下&#x200B;**[!UICONTROL 「設為公用」]**。

   ![](assets/segment-info.png)

## 套用濾鏡的其他方法

套用篩選器至專案還有其他幾種方法：

| 動作 | 說明 |
|--- |--- |
| 從選取範圍建立篩選 | 建立內嵌篩選。 選取行，以滑鼠右鍵按一下選取範圍，然後建立內嵌篩選。 此篩選器僅適用於已開啟的專案，不會儲存為CJA篩選器。 1. 選取所需的列。2. 以滑鼠右鍵按一下選取項目。3. Click *Create filter from selection*. |
| 元件>新增篩選 | 顯示篩選產生器。 See [Filter Builder](https://docs.adobe.com/content/help/zh-Hant/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| 「共用 > 共用專案」或「共用 > 組織專案資料」 | In [Curate and Share](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| 將篩選器用作維度 | 影片：[在 Analysis Workspace 中使用區段作為維度](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
