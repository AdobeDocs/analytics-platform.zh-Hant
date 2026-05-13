---
description: 瞭解如何在Analysis Workspace中劃分維度和維度專案。
keywords: Analysis Workspace
title: 劃分維度
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
TQID: https://experienceleague.adobe.com/GTRg4PodKPvehRu0CwAq8QTMUmoOtY2qIU1kHzmwHRI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 615
ht-degree: 57%

---

# 劃分維度

您可以在Analysis Workspace中以不限數量的方式根據特定需求劃分資料；使用相關量度、維度、區段、時間表和其他分析劃分值來建立查詢。

1. 在[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中，從一或多個選取資料列的內容功能表中，選取&#x200B;**[!UICONTROL 劃分]** ![V形右側](/help/assets/icons/ChevronRight.svg)。

   ![顯示從選取專案建立警示的步驟結果。](assets/breakdown.png)

1. 從子功能表中選取&#x200B;**[!UICONTROL 維度]**、**[!UICONTROL 量度]**、**[!UICONTROL 區段]**&#x200B;或&#x200B;**[!UICONTROL 日期範圍]**，然後選取專案。 或只是在&#x200B;**[!UICONTROL *搜尋&#x200B;*]**&#x200B;欄位中搜尋元件。

您可以跨所選時段，依維度項目或客群細分群體來劃分量度。 您也可以更深入鑽研至更詳細的層級。

>[!NOTE]
>
>表格中顯示的劃分數目上限為 400。 匯出劃分時，此限制會提高。

## 依位置劃分

依預設，劃分會固定至靜態列專案。 例如，想像您根據行銷管道劃分前 3 個頁面維度項目 (「首頁」、「搜尋結果」、「結帳」)。 接著，您離開專案，兩週後再回來。 再次開啟專案時，前 3 個頁面已變更，現在「首頁」、「搜尋結果」和「結帳」是前 4 到 6 個頁面。 即使它們目前位於第 4 至 6 列，您的行銷管道劃分根據預設仍會顯示在「首頁」、「搜尋結果」和「結帳」中。

相反地，**依位置**&#x200B;劃分，一律劃分前3個專案，無論前3個專案是什麼。 請參考範例，當您重啟專案時，行銷管道劃分將與表格中的前 3 頁面相連結。 而不是目前位於第 4 至 6 列的首頁、搜尋結果和結帳。 請參閱[資料列設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)設定此設定的方式。

## 將歸因模型套用到資料劃分

表格中的任何劃分也可套用任何歸因模型。 此歸因模型可與父欄相同或不同。 舉例來說，您可以在「行銷管道」維度中分析線性訂單，但將「U 形訂單」套用至管道中的特定追蹤代碼。 若要編輯套用到劃分的歸因模型，請將滑鼠移到劃分模型上，然後選取&#x200B;**[!UICONTROL 編輯]**。

![顯示劃分設定的訂單歸因比較](assets/breakdown-attribution.png)

這是將歸因模型套用至劃分或編輯劃分時的預期行為：

* 如果在沒有其他歸因時套用歸因，該歸因將套用於整個欄樹。

* 如果在套用了歸因後新增劃分，則將對新增的給定劃分使用預設值 (如果該維度具有預設值)。 否則將使用父欄的劃分。 某些維度具有預設配置。 例如，「時間」維度和「反向連結」使用「同一次接觸」。 「產品」維度使用「上次接觸」。 其他維度沒有預設值，將使用父欄配置。

* 如果欄樹中已有歸因，則變更歸因只會影響正在編輯的歸因。

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace中的Dimension](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Dimension劃分](https://video.tv.adobe.com/v/23969?quality=12&learn=on){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [新增維度和量度](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [在自由格式表格中使用維度](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [依位置劃分的Dimension](https://video.tv.adobe.com/v/24033){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]



