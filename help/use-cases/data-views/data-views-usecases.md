---
title: Customer Journey Analytics 的資料檢視使用案例
description: 多個使用案例顯示 Customer Journey Analytics 中資料檢視的彈性和功能
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 629935d66b0f2c5731806a68cc2fcda5fb11fc9a
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 33%

---

# 資料檢視使用案例

這些使用案例說明了資料檢視在Customer Journey Analytics中的彈性和功能。

## 使用繫結維度量度

如需詳細資訊，請參閱[使用繫結維度量度](binding-dimensions-metrics.md)使用案例。

## 使用摘要資料

如需詳細資訊，請參閱[使用摘要資料](summary-data.md)使用案例。

## BI 擴充功能使用案例

請參閱[BI擴充功能使用案例](bi-extension-usecases.md)，瞭解如何使用Customer Journey AnalyticsBI擴充功能完成許多使用案例。

## 從字串結構欄位建立量度 {#string}

例如，在建立資料檢視時，您可以從字串「[!UICONTROL 頁面標題]」結構描述欄位建立[!UICONTROL 訂單]量度。



1. 在「**[!UICONTROL 元件]**」標籤上，將「**[!UICONTROL 頁面標題]**」拖曳至「[!UICONTROL 包含的元件]」下的「**[!UICONTROL Metrics]**」區段。
1. 反白標示您剛才拖曳的量度，並將其重新命名為&#x200B;**[!UICONTROL 元件設定]**&#x200B;中的`Orders`
1. 開啟&#x200B;**[!UICONTROL 包含/排除值]**&#x200B;區段並指定下列專案：
   1. 啟用&#x200B;**[!UICONTROL 設定包含排除值]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;中選取&#x200B;**[!UICONTROL 如果所有條件都符合]**。
   1. 指定`confirmation`。 此page_title文字表示此頁面與下訂單有關。 在檢閱符合這些條件的所有頁面標題後，每個執行個體都會計算`1`。 此結果是新量度（而非計算量度）。具有包含/排除值的量度可用於任何其他量度的任何地方。 它適用於 Attribution IQ、篩選器，以及您可使用標準量度的其他任何地方。

   ![Dimension至量度](../assets/string-to-metric.gif){width=100%}
1. 您可以進一步指定此量度的歸因模型，例如 「[!UICONTROL 上次接觸]」，並具有「[!UICONTROL 工作階段]」的 [!UICONTROL 「回顧」視窗]。您也可以從相同欄位建立另一個[!UICONTROL 訂單]量度，並指定不同的歸因模型。 例如[!UICONTROL 首次接觸]，以及不同的[!UICONTROL 回顧期間]，例如[!UICONTROL 30天]。

另一個範例是使用人員ID維度當做量度，以判斷貴公司有多少人員ID。

## 將整數作為維度使用 {#integers}

過去，整數會自動被視為Customer Journey Analytics中的量度。 現在，數字 (包括 Adobe Analytics 的自訂事件) 可被視為維度。其範例如下：



1. 將&#x200B;**[!UICONTROL 持續時間]**&#x200B;整數拖曳至[!UICONTROL 包含的元件]下的&#x200B;**[!UICONTROL Dimension]**&#x200B;區段：
1. 您現在可以新增「**[!UICONTROL 值分組]**」，在報告中以分組方式呈現此維度。若未進行分組，此維度的每個例項都會顯示為Workspace報告中的條列專案。
   ![整數至維度](../assets/integer-to-dimension.gif){width=100%}


## 在流量圖表中使用數值維度作為量度 {#numeric}

您可以使用數值維度，將量度放入您的[!UICONTROL 流量]視覺效果中。

1. 在「資料檢視[元件](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview)」標籤上，將「行銷管道」]結構欄位拖曳至「[!UICONTROL 包含的元件]」下的「[!UICONTROL 量度]」區域。[!UICONTROL 
2. 在工作區報表中，此流量顯示流入[!UICONTROL 訂單]的[!UICONTROL 行銷管道]:

![行銷管道流量從電子郵件到結束/訂單。](../assets/flow.png)

## 執行子事件篩選 {#sub-event}

此功能特別適用於以陣列為基礎的欄位。 包含/排除功能可讓您在子事件層級進行篩選，而內建在篩選產生器中的篩選（區段）只會提供您事件層級的篩選。 因此，您可以使用資料檢視中的包含/排除來執行子事件篩選，然後在事件層級參照篩選中的新量度/維度。

例如，使用資料檢視中的包含/排除功能，僅聚焦於產生的銷售額超過$50美元的產品。 因此，如果您的訂單包括$50的產品購買和$25的產品購買，則包含/排除功能會移除$25的產品購買，而非整個訂單。

1. 在「資料檢視[元件](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview)」標籤上，將&#x200B;**[!UICONTROL 收入]**&#x200B;結構欄位拖曳至[!UICONTROL 包含的元件]下的&#x200B;**[!UICONTROL 量度]**&#x200B;區域。
1. 選取量度並在右側設定下列項目：
a.在**[!UICONTROL Format]**&#x200B;下，選擇&#x200B;**[!UICONTROL Currency]**。
b.在**[!UICONTROL 貨幣]**&#x200B;下，選取&#x200B;**[!UICONTROL USD]**。
c.在**[!UICONTROL 包含/排除值]**&#x200B;下，選取&#x200B;**[!UICONTROL 設定包含/排除值]**旁的核取方塊。
d.在**[!UICONTROL Match]**&#x200B;下，選擇&#x200B;**[!UICONTROL 如果所有條件都滿足]**。
e.在**[!UICONTROL 條件]**&#x200B;下，選擇&#x200B;**[!UICONTROL 大於或等於]**。
f.指定`50`作為值。

這些新設定可讓您檢視僅限高收入的資料，並篩選掉低於 $50 美元的所有資料。

## 使用[!UICONTROL 無值選項]設定 {#no-value}

貴公司可能已花了一些時間來訓練您的使用者，以期望報表中的維度會是「未指定」。 資料檢視中維度的預設值為「沒有值」。 不過，您可以為每個維度指定無值的報告方式。 請參閱維度元件的「沒有值」選項。

![沒有值選項](../assets/no-value-options.gif){width=100%}


## 使用不同的歸因設定建立多個量度 {#attribution}

使用右上方的&#x200B;**[!UICONTROL 複製]**&#x200B;功能，建立具有不同歸因設定的許多總收入量度，例如&#x200B;**[!UICONTROL 首次接觸]**、**[!UICONTROL 上次接觸]**&#x200B;和&#x200B;**[!UICONTROL 演演算法]**。

別忘了重新命名每個量度以反映差異，例如`Total Revenue (Algorithmic)`

![重複不同歸因設定的量度](../assets/duplicate-metric-for-attribution.gif){width=100%}

有關其他資料檢視設定的詳細資訊，請參閱「[建立資料檢視](/help/data-views/create-dataview.md)」。有關資料檢視的概念性概觀，請參閱「[資料檢視概觀](/help/data-views/data-views.md)」。

## 新工作階段和回訪工作階段報告 {#new-repeat}

您可以判斷工作階段確實是使用者的首次工作階段還是回訪工作階段。 根據您為此資料檢視定義的報表回溯期及13個月的回溯期。 例如，此報告可讓您判斷以下問題：

* 您的訂單中有多少百分比來自新工作階段或回訪工作階段？

* 對於指定的行銷管道或特定行銷活動，您是針對首次使用者還是回訪使用者？這項選擇如何影響轉換率？

有一個維度和兩個指標能協助此報告：

* [工作階段型別](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference) — 此維度有兩個值： [!UICONTROL 新的]和[!UICONTROL 回訪]。 [!UICONTROL 新]條列專案包含已確定為個人定義的首次工作階段的工作階段中的所有行為（亦即針對此維度的量度）。 所有其他資料都會包含在[!UICONTROL 回訪]條列項目中 (假設所有資料都屬於一個工作階段)。如果量度不屬於任何工作階段，則將屬於此維度的「不適用」貯體。

* [首次工作階段](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference)。 首次工作階段量度定義為個人在報告時段內定義的首次工作階段。

* [回訪工作階段](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-reference)回訪工作階段量度是非個人首次工作階段的工作階段數量。—>

若要存取元件：

1. 前往資料檢視編輯器。
1. 選取&#x200B;**[!UICONTROL 元件]**&#x200B;標籤，然後從左側邊欄選取&#x200B;**[!UICONTROL 標準元件]**。
1. 將&#x200B;**[!UICONTROL 工作階段型別]**、**[!UICONTROL 首次工作階段]**&#x200B;和&#x200B;**[!UICONTROL 傳回工作階段]**&#x200B;元件拖曳到您的資料檢視中。

新工作階段幾乎總是會準確報告。 唯一例外情況如下：

* 首次工作階段發生在 13 個月的回溯期之前。 <br/>已忽略此工作階段。

* 工作階段同時橫跨回溯期和報告時段時。 <br/>例如，您在2022年6月1日至6月15日期間執行報告。 回顧期間將為從2021年5月1日到2022年5月31日。 如果工作階段在2022年5月30日開始並在2022年6月1日結束，則該工作階段包含在回顧視窗中。 而報告時段中的所有工作階段都會計為傳回工作階段。

## 使用日期和日期-時間功能 {#date}

Adobe Experience Platform 中的結構描述包含「[!UICONTROL 日期]」和「[!UICONTROL 日期-時間]」欄位。Customer Journey Analytics資料檢視現在支援這些欄位。 將這些欄位做為維度拖曳至資料檢視時，您可以指定其[格式](/help/data-views/component-settings/format.md)。 此格式設定決定欄位如何在報告中顯示。例如：

* 就日期格式而言，如果您選取格式為&#x200B;**[!UICONTROL 月、日、年]**&#x200B;的&#x200B;**[!UICONTROL 日]**，報告的範例輸出可能會是這樣：August 23, 2022。

* 就日期-時間格式而言，如果您選取格式為&#x200B;**[!UICONTROL 時:分]**&#x200B;的&#x200B;**[!UICONTROL 當日的分鐘]**，您的輸出可能會是這樣：20:20。

支援1900年1月1日之後的日期（1970年1月1日除外）和2000年1月1日之後的日期時間值00:00:00。

### 日期和日期-時間使用案例

* 日期：旅行社收集旅程的出發日期，作為資料中的欄位。 公司想要有一份報告，對所有已收集的出發日期比較[!UICONTROL 一週中的第幾天]，以瞭解哪一天最受歡迎。 而公司想要對[!UICONTROL 月份]做同樣的事情。

* 日期 — 時間：零售公司收集店內銷售點(POS)每次購買的時間。 在指定的月份內，公司想要依每天[!UICONTROL 小時]瞭解最繁忙的購物期間。

>[!MORELIKETHIS]
>
>[格式元件設定中的日期和日期時間](/help/data-views/component-settings/format.md)
>

