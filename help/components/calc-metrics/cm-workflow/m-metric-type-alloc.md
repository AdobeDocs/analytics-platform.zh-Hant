---
description: 了解
title: 量度類型和歸因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 7f3412dc852ccae1ad5e122c200da5567ba89e87
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 37%

---

# 量度類型和歸因

選取量度旁的齒輪圖示，即可指定量度類型和歸因模式。

## 量度類型

若要在建立計算量度時指定量度型別：

1. 選取您要選取其型別的量度旁的齒輪圖示。

   ![](assets/cm_type_alloc.png)

1. 從下列選項中選擇：

   | 量度類型 | 定義 |
   |---|---|
   | 標準 | 這些量度就是在標準 [!DNL Analytics] 報表中使用的量度。如果某個公式由單一標準量度組成，則其顯示的資料將與其非計算量度相對應公式一樣。標準量度適合用來建立每個行項目專屬的計算量度。例如， [訂購] / [工作階段] 會採用該特定條列專案的訂單，然後除以該特定條列專案的工作階段數。 |
   | 全部總計 | 在每個行專案中使用報告期間的總計。 如果公式包含單一「總量」量度，它會在每個行專案上顯示相同的「總量」數字。 「總量」量度適合用來建立計算量度，以便與網站總計資料進行比較。 例如， [訂購] / [工作階段總數] 顯示網站上所有工作階段的訂單比例，而不只是特定條列專案的工作階段。 |

## 歸因

如需Customer Journey Analytics中歸因的相關資訊，請參閱 [歸因元件設定](/help/data-views/component-settings/attribution.md).
