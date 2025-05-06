---
title: 搭配Customer Journey Analytics使用量子量度熱度圖
description: 使用Quantum量度熱度圖資料，更能瞭解頁面層級的參與度，並根據消費者行為最佳化頁面。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 1%

---

# 搭配Customer Journey Analytics使用量子量度熱度圖

將Quantum量度熱度對應連結至CJA資料，可讓您更瞭解頁面層級的參與，並根據消費者行為將頁面最佳化。 Workspace可用來了解消費者使用者流程，以及了解消費者在不同頁面間遵循哪些路徑。 然後，您可以按一下超連結的頁面URL，以視覺化熱度圖形式呈現使用者如何與內容互動。 將Quantum Metric Heatmapping連結至CJA，您現在可以將頁面層級的互動與業務結果建立關聯，將您的分析提升到新的境界。

此表格會傳回該區段中的所有工作階段，您可以按一下其中的任何工作階段，進一步探索QM。  若要進一步瞭解Quantum量度工作階段重播，請前往https://www.quantummetric.com/platform/session-replay

## 先決條件

您必須有權使用Quantum Metric的&#x200B;**UX Ops**&#x200B;封裝，才能存取Quantum Metric的熱度圖功能。

## 步驟1：在Analysis Workspace中設定連結

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取現有專案，或建立專案。
1. 建立[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 將頁面URL維度拖曳至Workspace畫布。
1. 以滑鼠右鍵按一下維度資料行標題，然後選取&#x200B;**[!UICONTROL 為所有維度專案建立超連結]**。
1. 選取&#x200B;**[!UICONTROL 建立自訂URL]**。
1. 貼上下列URL結構：

   ```
   $value?qm-visible=true
   ```

1. 按一下「**[!UICONTROL 建立]**」。
1. 測試其中一個連結，以檢視它是否在URL中開啟且檢視量子量度副檔名。 這些連結會在新標籤中開啟，讓您的Workspace專案保持開啟狀態。

![熱度圖](assets/heatmap.png)

## 步驟2：按一下Customer Journey Analytics中的連結以檢視熱度圖

找到您要探索熱度對映的頁面後，您可以將其套用至所需的面板。 此表格會傳回URL，讓您瀏覽熱度圖、捲動深度，以及使用量度互動的關鍵區域。 如需詳細資訊，請參閱[Quantum量度熱度圖產品概述](https://www.quantummetric.com/platform/interaction-heatmaps)。 您也可以連絡您的Quantum Metric客戶支援代表，或透過[Quantum Metric客戶請求入口網站](https://community.quantummetric.com/s/public-support-page)提交請求。
