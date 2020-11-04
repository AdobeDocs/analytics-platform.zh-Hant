---
description: 了解 Analysis Workspace 中的視覺效果和視覺效果設定。
keywords: Analysis Workspace
title: 視覺效果概述
translation-type: tm+mt
source-git-commit: 1759bbf965e6b8d07e5a25867b73c3242dc49005
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 95%

---


# 視覺效果概述

工作區提供許多視覺效果，可產生資料的視覺化表示法，例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。每個視覺效果都有各自的設定可供您管理。按一下視覺效果名稱，取得更詳細的資訊。

教學影片： [分析工作區中的視覺化類型](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/visualization-types.html) (2:57)

| 視覺效果名稱 | 說明 |
| --- | --- |
| [區域](/help/analysis-workspace/visualizations/area.md) | 就像線條圖，但線下有彩色區域。 有多個量度且以要視覺化方式表示多個量度之間交會的區域時，可使用區域圖。 |
| [長條圖](/help/analysis-workspace/visualizations/bar.md) | 顯示代表一或多個量度多個值的垂直長條。 |
| [項目圖表](/help/analysis-workspace/visualizations/bullet-graph.md) | 顯示您感興趣的值與其他效能範圍 (目標) 相比較或進行測量的結果。 |
| [同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 同類群組是指一段指定時間內，共享相同特徵的一組人。例如當您想知道一個同類群組與某個品牌的互動關係時，就很適合使用同類群組分析。您可輕易看出趨勢中的變化，然後據以做出回應。 |
| [環形圖](/help/analysis-workspace/visualizations/donut.md) | 此視覺效果類似圓餅圖，以整體的部分或區段顯示資料。 |
| [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | 流失報表可顯示在一系列預先定義的連續頁面中，訪客在哪個位置離開 (流失) 和繼續通過 (流過)。 |
| [流量](/help/analysis-workspace/visualizations/c-flow/flow.md) | 顯示客戶使用您網站和應用程式的路徑。 |
| [自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | 自由表格不僅僅是資料表格，也是互動式視覺效果。 |
| [色階分佈圖](/help/analysis-workspace/visualizations/histogram.md) | 色階分佈圖類似於長條圖，但前者將數字分組為範圍 (貯體)。 |
| [橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | 顯示代表一或多個量度多個值的橫條。 |
| [折線圖](/help/analysis-workspace/visualizations/line.md) | 使用線條呈現量度，顯示一段時間內值的變化。僅可在使用時間當作維度時，才使用折線圖。 |
| [散點圖](/help/analysis-workspace/visualizations/scatterplot.md) | 顯示維度項目與最多三個量度之間的關係。 |
| [摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md) | 此視覺效果會根據選取的儲存格顯示總計和摘要。 |
| [摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md) | 此視覺效果會根據選取的儲存格相互比較儲存格。 |
| [文字](/help/analysis-workspace/visualizations/text.md) | 可讓您將使用者定義文字新增至「工作區」。 |
| [樹狀圖](/help/analysis-workspace/visualizations/treemap.md) | 以一組巢狀矩形顯示階層式 (樹狀結構) 資料。 |
| [Venn](/help/analysis-workspace/visualizations/venn.md) | 可讓您拖曳至最多 3 個區段 (從「元件」) 及一個量度來建立文氏圖表。 |

## 視覺效果面板 {#section_DC07F032FBEF4046A40F7B95C28DA018}

若要顯示「視覺化」面板，請按一下 **[!UICONTROL 視覺化]** 在左邊欄上。

![步驟結果](assets/visualizations.png)

如果您有使用 Adobe Analytics，則會對大部分的視覺效果類型 (例如面積圖、長條圖、環圈圖和折線圖) 都很熟悉。不過，Analysis Workspace 還提供視覺效果設定，以及許多具有互動功能的新或獨特的視覺效果類型。

## 視覺效果設定 {#section_D3BB5042A92245D8BF6BCF072C66624B}

若要存取「[!UICONTROL 視覺效果設定]」，請將視覺效果拖曳至「[!UICONTROL 自由面板]」，接著按一下「[!UICONTROL 視覺效果設定]」齒輪圖示。

>[!IMPORTANT]
>
>系統會顯示哪些視覺效果設定，需依視覺效果而定。並非所有設定均可套用至所有視覺效果。此外，部分進階設定&#x200B;**僅**&#x200B;針對特定視覺效果顯示，例如[「色階分布圖」設定](/help/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477)。

![](assets/visualization_settings.png)

| 設定 | 說明 |
| --- | --- |
| 百分比 | 以百分比顯示值。 |
| 100% 堆疊 | 針對堆疊區域圖/堆疊長條圖/堆疊橫條圖的設定可讓圖表以「100% 堆疊」的視覺效果方式呈現。範例： ![](assets/stacked_100_percent.png) |
| 可見圖例 | 可讓您隱藏「摘要編號/摘要變更」視覺效果的篩選器詳細資料文字。 |
| 項目數上限 | 可讓您限制視覺效果顯示的項目數。 |
| 將 Y 軸固定於零 | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |
| 標準化 | 強制量度為相同比例。 |
| 顯示雙軸 | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。 |
| 顯示異常 | 強化線性圖和自由表格，以顯示資料異常。 |

## 「建立視覺效果」圖示{#section_9C11D9DEDC42413AA53E69A71A509DFC}

如果您不確定要挑選哪個視覺效果，請按一下任何表格列中的&#x200B;**[!UICONTROL 「建立視覺效果」]**&#x200B;圖示。當您在表格列上暫留時，會顯示這個圖示。按一下它會提示 Analysis Workspace 教育性猜測哪個視覺效果最適合您的資料。例如，如果您選取最多 3 個區段，則會建立 Venn 圖表。如果大於 3 個區段，則會建立長條圖。若為其他類型的資料，則會建立線性圖等等。

![](assets/create-visual.png)

## 右鍵視覺效果/面板功能表 {#section_05B7914D4C9E443F97E2BFFDEC70240C}

在視覺效果或面板標頭旁按一下滑鼠右鍵，可存取與圖表內容相關的設定。您可存取下列部分或全部的設定：

![](assets/right-click_menu.png)

| 設定 | 說明 |
| --- | --- |
| 插入複製的視覺效果/面板 | 讓您將複製的元素貼到 (「插入」) 專案內的其他位置或其他專案中。 |
| 複製視覺效果/面板 | 讓您按一下滑鼠右鍵複製視覺效果或面板。 |
| 複製視覺效果/面板 | 完全複製目前的視覺效果，接著可供進行修改。 |
| 摺疊所有面板 | 摺疊所有專案面板。 |
| 摺疊面板中的所有視覺效果 | 摺疊專案面板中的所有視覺效果。 |
| 展開所有面板 | 展開所有專案面板。 |
| 展開面板中的所有視覺效果 | 展開專案面板中的所有視覺效果。 |
| 編輯描述 | 新增 (或編輯) 視覺效果/面板的文字描述。此描述會顯示在「專案 > 專案資訊和設定」中。 |
| 取得面板連結 | 讓您可將使用者直接導向專案中的特定面板。 |
| 取得視覺效果連結 | 讓您複製並共用此連結以便直接將其他項目傳送至此視覺效果。使用者必須登入。 |
| 重新開始 | (適用於流量、Venn、色階分佈圖) 刪除目前視覺效果的設定，並開啟一個新面板，讓您在其中重新設定。 |

## 編輯圖例標籤 {#section_94F1988CB4B9434BA1D9C6034062C3DE}

您可以重新命名視覺效果圖例 (「流失」、「區域圖」、「堆疊區域圖」、「長條圖」、「堆疊長條圖」、「環形圖」、「色階分布圖」、「橫條圖」、「堆疊橫條圖」、「折線圖」、「散佈圖」和「Venn 圖表」) 中的數列名稱，有助於讓視覺效果更簡單明瞭。

編輯圖例&#x200B;**不**&#x200B;適用於：「樹狀圖」、「項目」、「摘要變更或數字」、「文字」、「自由格式」、「色階分布圖」、「同類群組」或「流量」視覺效果。

以在折線途中編輯圖例標籤為例說明，

1. 以滑鼠右鍵按一下圖例標籤。
1. 按一下&#x200B;**[!UICONTROL 「編輯標籤」]**。

   ![](assets/edit-label.png)

1. 輸入新的標籤文字。
1. 按下 **[!UICONTROL Enter]** 以儲存。

以下是此主題的[影片連結](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html)。
