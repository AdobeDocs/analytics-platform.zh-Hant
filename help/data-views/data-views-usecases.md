---
title: Customer Journey Analytics 的資料檢視使用案例
description: 多個使用案例顯示 Customer Journey Analytics 中資料檢視的彈性和功能
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
translation-type: tm+mt
source-git-commit: 37c667b9c3f85e781c79a6595648be63c686649b
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 100%

---

# 資料檢視使用案例

這些使用案例顯示 Customer Journey Analytics 中資料檢視的彈性和功能。

## 從 pageTitle (字串) 結構欄位建立「訂單」量度

例如，在建立資料檢視時，您可以從字串「[!UICONTROL pageTitle]」結構欄位建立「[!UICONTROL 訂單]」量度。步驟如下：

1. 在「元件」索引標籤上，將「[!UICONTROL pageTitle]」拖曳至「[!UICONTROL 已包含元件]」下的「[!UICONTROL 量度]」區段。
   ![](assets/use-case1a.png)
1. 現在，在右側的「[!UICONTROL 元件設定] 」下反白標示您剛才拖曳的量度，並將其重新命名：
   ![](assets/orders.png)
1. 開啟右側的「[!UICONTROL 包含/排除值]」對話框，並指定下列項目：
   ![](assets/orders2.png)

   「確認」短語表示這是訂單。在檢閱符合這些標準的所有頁面標題後，每個例項都會計為「1」。此結果是新量度 (而非計算量度)。具有包含/排除值的量度可用於任何其他量度也可使用的地方。它適用於 Attribution IQ、篩選器，以及您可使用標準量度的其他任何地方。
1. 您可以進一步指定此量度的歸因模型，例如 「[!UICONTROL 上次接觸]」，並具有「[!UICONTROL 工作階段]」的 [!UICONTROL 「回顧」視窗]。您也可以從相同欄位建立另一個「[!UICONTROL 訂單]」量度，並為其指定不同的歸因模型，例如「[!UICONTROL 上次接觸]」，以及不同的[!UICONTROL 「回顧」視窗]，例如「[!UICONTROL 30天]」。

## 將整數作為維度使用

先前，整數會自動被視為 CJA 中的量度。現在，數字 (包括 Adobe Analytics 的自訂事件) 可被視為維度。其範例如下：

1. 將「[!UICONTROL call_length_min]」整數拖曳至「[!UICONTROL 已包含元件]」下的「[!UICONTROL 維度]」區段：

   ![](assets/integers.png)

1. 您現在可以新增「[!UICONTROL 值分組]」，在報告中以分組方式呈現此維度。(若未進行分組，此維度的每個例項都會顯示為 Workspace 報告中的條列項目。)

   ![](assets/bucketing.png)

有關其他資料檢視設定的詳細資訊，請參閱「[建立資料檢視](/help/data-views/create-dataview.md)」。有關資料檢視的概念性概觀，請參閱「[資料檢視概觀](/help/data-views/data-views.md)」。
