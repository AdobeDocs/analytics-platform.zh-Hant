---
title: Customer Journey Analytics中資料檢視的使用案例
description: 多種使用案例，可顯示資料檢視在Customer Journey Analytics中的彈性和功能
translation-type: tm+mt
source-git-commit: b99e108e9f6dd1c27c6ebb9b443f995beb71bdbd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 資料檢視使用案例

>[!IMPORTANT]
>
>此功能將於2021年4月22日正式推出。

這些使用案例顯示資料檢視在Customer Journey Analytics中的彈性和功能。

## 從pageTitle（字串）結構欄位建立「訂購」量度

例如，在建立資料檢視時，您可以從字串[!UICONTROL pageTitle]結構欄位建立[!UICONTROL Orders]量度。 以下是步驟：

1. 在「元件」標籤上，將[!UICONTROL pageTitle]拖曳至[!UICONTROL Included Components]下的[!UICONTROL Metrics]區段。
   ![](assets/use-case1a.png)
1. 現在，在右側的[!UICONTROL 元件設定]下反白標示您剛拖曳的量度，並將其重新命名：
   ![](assets/orders.png)
1. 開啟右側的[!UICONTROL 包含／排除值]對話方塊，並指定下列項目：
   ![](assets/orders2.png)

   「確認」短語表示這是訂單。 在檢閱符合這些標準的所有頁面標題後，每個例項都會計為&quot;1&quot;。 結果是新量度（而非計算量度）。 包含／排除值的量度可用於任何其他量度皆可使用。 它適用於Attribution IQ、篩選器，以及您可使用標準量度的其他任何地方。
1. 您可以進一步指定此量度的歸因模型，例如[!UICONTROL 上次接觸]，並具有[!UICONTROL Session]的[!UICONTROL 回顧視窗]。
您也可以從相同欄位建立另一個[!UICONTROL Orders]量度，並為其指定不同的歸因模型，例如[!UICONTROL First Touch]，以及不同的[!UICONTROL  Lookback window]，例如[!UICONTROL 30天]。

## 將整數用作維

在舊版中，整數會自動視為CJA中的量度。 現在，數字(包括來自Adobe Analytics的自訂事件)可視為維度。 其範例如下：

1. 將[!UICONTROL call_length_min]整數拖曳至[!UICONTROL Included Components]下的[!UICONTROL Dimension]區段：

   ![](assets/integers.png)

1. 您現在可以新增[!UICONTROL 值分組]，在報表中以分組方式呈現此維度。 （若未進行分段，此維度的每個例項都會顯示為「工作區」報表中的行項目。）

   ![](assets/bucketing.png)

有關其他資料視圖設定的詳細資訊，請參閱[建立資料視圖](/help/data-views/create-dataview2.md)。
有關資料視圖的概念性概述，請參閱[資料視圖概述](/help/data-views/data-views.md)。