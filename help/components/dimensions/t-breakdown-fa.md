---
description: 在 Analysis Workspace 中劃分維度和維度項目。
keywords: Analysis Workspace
title: 劃分維度
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: b85ad91a80f277aaf35f1e3aa3366a46f6478215
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 58%

---

# 在工作區中劃分維度

您可以根據特定需求，以無限方式劃分資料；使用相關量度、維度、篩選器、時間表和其他分析劃分值來建立查詢。

1. 在[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中，從一或多個選取資料列的內容功能表中，選取&#x200B;**[!UICONTROL 劃分]** ![V形右側](/help/assets/icons/ChevronRight.svg)。

   ![顯示從選取專案建立警示的步驟結果。](assets/breakdown.png)

1. 從子功能表中選取&#x200B;**[!UICONTROL Dimension]**、**[!UICONTROL 量度]**、**[!UICONTROL 篩選器]**&#x200B;或&#x200B;**[!UICONTROL 資料範圍]**，然後選取專案。

您可以跨所選時段，依維度項目或客群篩選條件來劃分量度。您也可以更深入鑽研至更詳細的層級。

>[!NOTE]
>
>表格中顯示的劃分數目上限為 200。匯出劃分時，此限制會提高。

## 依位置劃分

依預設，劃分會固定至靜態列專案。 例如，想像您依「行銷管道」劃分前3個頁面維度專案（「首頁」、「搜尋結果」、「結帳」）。 接著，您離開專案，兩週後再回來。再次開啟專案時，前 3 個頁面已變更，現在「首頁」、「搜尋結果」和「結帳」是前 4 到 6 個頁面。您的「行銷管道」劃分預設仍會顯示在「首頁」、「搜尋結果」和「結帳」下方，即使它們現在位於第4到6列。

相反地，**依位置**&#x200B;劃分，一律劃分前3個專案，無論前3個專案是什麼。 請參考此範例，當您重新開啟專案時，行銷管道劃分會繫結至表格中的前3個頁面。 而非「首頁」、「搜尋結果」和「結帳」，它們現在位於第4-6列。 請參閱[資料列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)設定此設定的方式。



## 將歸因模型套用到資料劃分

表格中的任何劃分也可套用任何歸因模型。此歸因模型可與父欄相同或不同。舉例來說，您可以在「行銷管道」維度中分析線性訂單，但將「U 形訂單」套用至管道中的特定追蹤代碼。若要編輯套用到劃分的歸因模型，請將滑鼠移到劃分模型上，然後選取&#x200B;**[!UICONTROL 編輯]**。

![顯示劃分設定的訂單歸因比較](assets/breakdown-attribution.png)

這是將歸因模型套用至劃分或編輯劃分時的預期行為：

* 如果在沒有其他歸因時套用歸因，該歸因將套用於整個欄樹。

* 如果在套用了歸因後新增劃分，則將對新增的給定劃分使用預設值 (如果該維度具有預設值)。否則將使用父欄的劃分。某些維度具有預設配置。例如，「時間」維度和「反向連結」使用「同一次接觸」。「產品」維度使用「上次接觸」。其他維度沒有預設值，將使用父欄配置。

* 如果欄樹中已有歸因，則變更歸因只會影響正在編輯的歸因。

+++ 觀看說明維度和維度劃分的影片

Analysis Workspace中的Dimension

>[!VIDEO](https://video.tv.adobe.com/v/23971)

Dimension劃分

>[!VIDEO](https://video.tv.adobe.com/v/23969)

在 Analysis Workspace 中新增維度和量度至您的專案：

>[!VIDEO](https://video.tv.adobe.com/v/30606)

在自由格式表格中使用維度：

>[!VIDEO](https://video.tv.adobe.com/v/40179)

依位置的維度劃分：

>[!VIDEO](https://video.tv.adobe.com/v/24033)

{{videoaa}}

+++
