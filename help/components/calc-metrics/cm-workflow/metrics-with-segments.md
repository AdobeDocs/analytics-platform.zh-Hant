---
description: 篩選個別量度可讓您在同一份報表中比較量度。
title: 篩選量度
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# 篩選量度

在[計算量度產生器](cm-build-metrics.md#definition-builder)中，您可以在量度定義中套用篩選器。 如果您想要在分析中將量度用於資料的子集，套用篩選器會很有幫助。

>[!NOTE]
>
>已透過[篩選產生器](/help/components/filters/filter-builder.md)更新篩選定義。 如果您變更篩選器，則篩選器會在任何使用篩選器的地方自動更新，包括該篩選器是否為計算量度定義的一部分。
>

您想要比較和您的品牌互動的德國人員與德國以外人員的量度。 因此，您可以回答以下問題：

1. 有多少德國和國際人士造訪您最受歡迎的[頁面](#popular-pages)。
1. 本月[總計](#totals)有多少德國和國際人士與您的品牌進行線上互動。
1. 造訪過您熱門頁面的德國人和海外人士的[百分比](#percentages)為何？

請參閱下列各節，說明篩選量度如何協助您回答這些問題。 在適當的情況下，會參考更詳細的檔案。

## 受歡迎頁面

1. [從名為`German people`的Workspace專案建立計算量度](cm-workflow.md)。
1. 在[計算量度產生器](cm-build-metrics.md)中，[建立標題為`Germany`的篩選器](/help/components/filters/filter-builder.md)，此篩選器使用您CRM資料中的CRM國家/地區欄位來判斷人員的來源。

   >[!TIP]
   >
   >在計算量度產生器中，您可以使用「元件」面板直接建立篩選器。
   >   

   您的篩選器可能如下所示。

   ![篩選器德國](assets/filter-germany.png)

1. 返回計算量度產生器，使用篩選器更新計算量度。

   ![計算量度Germany](assets/calculated-metric-germany.png)

針對計算量度的國際版本重複上述步驟。

1. 從您的Workspace專案中建立標題為`International people`的計算量度。
1. 在計算量度產生器中，建立標題為`Not Germany`的篩選器，使用您CRM資料中的CRM國家/地區欄位來判斷人員的來源。

   您的篩選器應該看起來像。

   ![篩選器德國](assets/filter-not-germany.png)

1. 返回計算量度產生器，使用篩選器更新計算量度。

   ![計算量度Germany](assets/calculated-metric-notgermany.png)


1. 在Analysis Workspace中建立專案，在那裡您可以檢視德國和國際人士造訪的頁面。

   ![Workspace自由格式表格視覺效果顯示德國人員與國際人員](assets/workspace-german-vs-international.png)


## 總計

1. 根據總計建立兩個新篩選器。 開啟先前建立的每個篩選器、重新命名篩選器、將&#x200B;**[!UICONTROL 人員]**&#x200B;的&#x200B;**[!UICONTROL 量度型別]**&#x200B;設定為&#x200B;**[!UICONTROL 總計]**，並使用&#x200B;**[!UICONTROL 另存新檔]**&#x200B;以新名稱儲存篩選器。 例如：

   德國的![總計量度](assets/calculated-metric-germany-total.png)

1. 新增自由表格視覺效果至您的Workspace專案，顯示當月的總頁數。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際人員總數](assets/workspace-german-vs-international-totals.png)


## 百分比

1. 建立兩個新計算量度，用於根據您先前建立的計算量度計算百分比。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際總人員百分比](assets/calculated-metric-germany-total-percentage.png)


1. 更新您的Workspace專案。

   ![Workspace自由格式表格視覺效果顯示德文人員與國際人員總數](assets/workspace-german-vs-international-totals-percentage.png)


+++ 以下影片會說明如何將篩選的計算量度作為無實作量度。

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

{{videoaa}}

+++
