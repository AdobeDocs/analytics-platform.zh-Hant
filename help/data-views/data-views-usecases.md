---
title: Customer Journey Analytics 的資料檢視使用案例
description: 多個使用案例顯示 Customer Journey Analytics 中資料檢視的彈性和功能
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 11171eb6e079adbf41e0abc798a54a5749492eac
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 69%

---

# 資料檢視使用案例

這些使用案例顯示了 Customer Journey Analytics 中資料檢視的靈活性和強大威力。

## 1. 從字串結構描述欄位建立量度 {#string}

例如，在建立資料檢視時，您可以從字串「[!UICONTROL pageTitle]」結構欄位建立「[!UICONTROL 訂單]」量度。步驟如下：

1. 在「元件」索引標籤上，將「[!UICONTROL pageTitle]」拖曳至「[!UICONTROL 已包含元件]」下的「[!UICONTROL 量度]」區段。
   ![](assets/use-case1a.png)
1. 現在，在右側的「[!UICONTROL 元件設定] 」下反白標示您剛才拖曳的量度，並將其重新命名：
   ![](assets/orders.png)
1. 開啟右側的「[!UICONTROL 包含/排除值]」對話框，並指定下列項目：
   ![](assets/orders2.png)

   「確認」短語表示這是訂單。在檢閱符合這些標準的所有頁面標題後，每個例項都會計為「1」。此結果是新量度 (而非計算量度)。具有包含/排除值的量度可用於任何其他量度也可使用的地方。它適用於 Attribution IQ、篩選器，以及您可使用標準量度的其他任何地方。
1. 您可以進一步指定此量度的歸因模型，例如 「[!UICONTROL 上次接觸]」，並具有「[!UICONTROL 工作階段]」的 [!UICONTROL 「回顧」視窗]。您也可以從相同欄位建立另一個「[!UICONTROL 訂單]」量度，並為其指定不同的歸因模型，例如「[!UICONTROL 上次接觸]」，以及不同的[!UICONTROL 「回顧」視窗]，例如「[!UICONTROL 30天]」。

另一個範例為使用訪客 ID 維度當做量度，以判斷貴公司有多少訪客 ID。

## 2. 將整數當做維度使用 {#integers}

先前，整數會自動被視為 CJA 中的量度。現在，數字 (包括 Adobe Analytics 的自訂事件) 可被視為維度。其範例如下：

1. 將「[!UICONTROL call_length_min]」整數拖曳至「[!UICONTROL 已包含元件]」下的「[!UICONTROL 維度]」區段：

   ![](assets/integers.png)

1. 您現在可以新增「[!UICONTROL 值分組]」，在報告中以分組方式呈現此維度。(若未進行分組，此維度的每個例項都會顯示為 Workspace 報告中的條列項目。)

   ![](assets/bucketing.png)

## 3. 在流程圖表中使用數值維度當做「量度」 {#numeric}

您可以使用數值維度，將您的「量度」放入[!UICONTROL 流程]視覺效果中。

1. 在「資料檢視[元件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings)」標籤上，將「行銷管道」]結構欄位拖曳至「[!UICONTROL 包含的元件]」下的「[!UICONTROL 量度]」區域。[!UICONTROL 
2. 在工作區報表中，此流量顯示流入[!UICONTROL 訂單]的[!UICONTROL 行銷管道]:

![](assets/flow.png)

## 4. 執行子事件篩選 {#sub-event}

此功能特別適用於以陣列為基礎的欄位。 包含/排除功能可讓您在子事件層級執行篩選，而內建在篩選產生器中的篩選 (區段) 只會提供您事件層級的篩選。 因此，您可以在資料檢視中使用包含/排除來執行子事件篩選，然後在事件層級參照篩選中的新量度/維度。

例如，在資料檢視中使用包含/排除功能，僅聚焦於產生的銷售額超過 50 美元的商品。 所以，如果您的訂單包含價值 50 美元的商品及價值 25 美元的商品，我們只會移除 25 美元的商品，而不是整筆訂單。

1. 在「資料檢視[元件](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings)」標籤上，將[!UICONTROL 收入]結構欄位拖曳至[!UICONTROL 包含的元件]下的[!UICONTROL 量度]區域。
1. 選取量度並在右側設定下列項目：
a.在[!UICONTROL Format]下，選擇[!UICONTROL Currency]。
b.在[!UICONTROL Currency]下，選擇USD。
c.在[!UICONTROL 包含/排除值]下，選取[!UICONTROL 設定包含/排除值]旁的核取方塊。
d.在[!UICONTROL Match]下，選擇[!UICONTROL 如果所有條件都滿足]。
e.在[!UICONTROL 條件]下，選擇[!UICONTROL 大於或等於]。
f. 指定「50」當做值。

這些新設定可讓您檢視僅限高收入的資料，並篩選掉低於 $50 美元的所有資料。

## 5. 利用「[!UICONTROL 無值選項]」設定 {#no-value}

貴公司可能已花了一些時間來訓練您的使用者，以期望報表中出現「未指定」。 資料檢視中的預設值為「沒有值」。 您現在可以在資料檢視 UI 中[將「沒有值」重新命名為「未指定」](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-no-value-options-settings)。

另一個範例為會籍計劃註冊的維度。 在此情況下，您可以將「沒有值」重新命名為「沒有會籍計劃註冊」。

## 6. 使用不同[!UICONTROL 歸因]設定建立多個量度 {#attribution}

使用右上方的「[!UICONTROL 複製]」功能時，可建立具有不同歸因設定的許多收入量度，像是[!UICONTROL 首次接觸]、[!UICONTROL 上次接觸]和[!UICONTROL 演算法]。

別忘了重新命名每個量度來反映差異，例如「演算法收入」：

![](assets/algo-revenue.png)

有關其他資料檢視設定的詳細資訊，請參閱「[建立資料檢視](/help/data-views/create-dataview.md)」。有關資料檢視的概念性概觀，請參閱「[資料檢視概觀](/help/data-views/data-views.md)」。

## 7。新會話與重複會話報告 {#new-repeat}

>[!NOTE]
>
>此功能目前正在進行有限測試。

您可以根據為此資料視圖定義的報告窗口和13個月的回望窗口來確定某個會話是否確實是用戶的第一個會話。 此報告允許您確定，例如：

* 新會話與重複會話的訂單佔您的訂單的百分比是多少？

* 對於給定的市場營銷渠道或特定的市場活動，您是針對首次使用者還是返回用戶？ 這些選擇如何影響轉換率？

三個構成部分促進了此報告：

* 1維： [會話類型](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional)  — 此維有兩個值：1) [!UICONTROL 新建] 和2) [!UICONTROL 返回]。 的 [!UICONTROL 新建] 行項目包括已確定為人員定義的第一個會話的會話中的所有行為（即針對此維的度量）。 其他所有內容都包含在 [!UICONTROL 返回] 行項目（假定所有內容都屬於會話）。 如果度量不是任何會話的一部分，則它們會落入此維的「不適用」儲存段。

* 2個指標： [新會話，返回會話](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional)。 新會話定義為報告窗口內人員定義的第一個會話。 返回會話是不是個人第一次會話的會話數。

要訪問這些元件：

1. 進入資料視圖編輯器。
1. 按一下 **[!UICONTROL 元件]** > **[!UICONTROL 可選標準元件]** 按鈕。
1. 將它們拖到資料視圖中。

九成五至九成機會，新會期的報導會準確無誤。 唯一的例外是：

* 在13個月回望窗口之前發生第一個會話時。 將忽略此會話。

* 當會話同時跨越回望窗口和報告窗口時。 比方說你在2022年6月1日到6月15日發佈報告。 回望窗口將涵蓋2021年5月1日至2022年5月31日。 如果會話將於2022年5月30日開始，於2022年6月1日結束，因為該會話包含在回望窗口中，則報告窗口中的所有會話都被計算為返回會話。

