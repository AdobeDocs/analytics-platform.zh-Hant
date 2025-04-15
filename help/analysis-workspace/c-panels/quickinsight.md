---
description: 「快速深入分析」是適用於新 Workspace 使用者的工具，可引導他們建立資料表格和視覺效果
title: 快速深入分析面板
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 94%

---

# 快速深入分析面板 {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="快速深入分析"
>abstract="建立一個面板來快速建置自由格式表格和伴隨的視覺化描繪，加快分析及揭露深入分析的速度。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_ 中的「快速深入分析」面板。<br/>_請參閱本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 版本的[快速深入分析面板](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/panels/quickinsight)。_

>[!ENDSHADEBOX]


[!UICONTROL 快速深入分析]為 [!UICONTROL Analysis Workspace] 的非分析師和新使用者提供指引，瞭解如何快速輕鬆回答業務問題。對於想要快速解答簡單的問題而無須自行建立表格的進階使用者，這也是絕佳的工具。

當您首次使用 [!UICONTROL Analysis Workspace]，您可能想知道：

* 哪些視覺化呈現最有用、
* 哪些維度和量度可能有助於深入分析、
* 拖放項目的位置、
* 建立區段的位置，
* 及更多內容。

為了解答這些問題，[!UICONTROL 快速深入分析]利用演算法為您提供貴公司所使用的最熱門維度、量度、區段和日期範圍。此演算法是根據您自己的公司在 [!UICONTROL Analysis Workspace] 的資料元件使用情況。實際上，您會在下拉式清單中看到標示為[!UICONTROL POPULAR]的維度、量度和區段，如下所示：

![「快速深入分析」面板。](assets/popular-tag.png)

[!UICONTROL 快速深入分析]可協助您

* 在 [!UICONTROL Analysis Workspace] 中適當建立資料表格及隨附的視覺效果。
* 瞭解 [!UICONTROL Analysis Workspace] 的基本元件和部件所適用的術語和辭彙。
* 在[!UICONTROL 自由表格]中輕鬆進行維度的簡單劃分、新增多個量度或比較區段。
* 變更或試用各種視覺效果類型，以快速且直覺地找出您的分析適用的尋找工具。

## 基本關鍵術語

以下是您需要熟悉的一些基本術語。每個資料表格都包含 2 個以上建置要素 (元件)，讓您用來說明自己的資料故事。

| 組成要素 (元件) | 定義 |
|---|---|
| **[!UICONTROL 維度]** | 維度是量度資料的描述或特性，您可以在專案中加以檢視、劃分及比較。這是可劃分為維度項目的非數值和日期。例如，*瀏覽器*&#x200B;或&#x200B;*頁面*&#x200B;是維度。 |
| **[!UICONTROL 維度項目]** | 維度項目是維度的個別值。例如，瀏覽器維度的維度項目為 *Chrome*、*Firefox*、*Edge*&#x200B;等。 |
| [!UICONTROL 量度] | 量度是有關人員活動的量化資訊，例如瀏覽次數、點進、重新載入、平均逗留時間、件數、訂購、收入等。 |
| **[!UICONTROL 視覺化呈現]** | Workspace 提供[一些視覺化呈現](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)，方便您建置資料的視覺呈現方式。例如長條圖、環形圖、直方圖、折線圖、地圖、散佈圖等。 |
| **[!UICONTROL 維度劃分]** | 維度劃分是用其他維度來劃分某個維度。例如，您可以將「依行動裝置劃分美國各州」劃分為每個州的行動裝置造訪次數。或者，您可以依行動裝置類型、區域、內部促銷活動等來劃分行動裝置。 |
| **[!UICONTROL 篩選]** | 篩選讓您根據特性或網站互動來識別人員子集。例如，您可以根據以下專案建立[!UICONTROL 人員]區段 <li>屬性：瀏覽器類型、裝置、造訪次數、國家/地區、性別；或</li><li>互動：促銷活動、關鍵字搜尋、搜尋引擎；或</li><li>進入和退出：訪客來自 Facebook、已定義的登陸頁面、反向連結網域；或</li><li> 自訂變數：表單欄位、已定義的類別、客戶 ID。 |

## 使用

若要使用&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板：

1. 建立一個&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板。有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 首次使用&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板時，您可能要完成簡短的[!UICONTROL 入門教學課程]，以了解一些基本概念。選取「快速深入分析」面板標題旁的![HelpOutline](/help/assets/icons/HelpOutline.svg)，然後從快顯視窗中選取&#x200B;**[!UICONTROL 入門教學課程]**。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。


### 面板輸入

選取您的建置要素：

* **[!UICONTROL 分析]**  - 指定維度 (橘色)
* **[!UICONTROL 依據]**  - 指定量度 (綠色)
* **[!UICONTROL 區段依據]** — 指定區段（藍色）
* **[!UICONTROL 在]** - 指定日期範圍 (紫色)。

您必須至少選取一個維度和一個量度才能使視覺化呈現正常運作。



您可以透過三種方式指定建置要素：

* 從左側面板拖放元件。
* 開始在建置要素欄位之一中輸入內容。找到輸入後，建置要素欄位會自動填入可能的值。
* 指定建置要素的下拉式清單 (例如在&#x200B;**[!UICONTROL 分析]**&#x200B;中的 `Country`)，並搜尋可能值的清單 (使用![箭號向右](/help/assets/icons/ChevronRight.svg)) 找出您要使用的值 (例如，**[!UICONTROL 國家/地區代碼]**)。

選取&#x200B;**[!UICONTROL 清除]**&#x200B;以清除所有輸入欄位。


### 面板輸出

1. 當您已新增至少一個維度和一個量度後，就可以看到結果。

   ![自由格式表格依垂直方向顯示維度並依水平方向顯示量度。](assets/quick-insights-output.png)

   * 自由表格，內含維度（國家/地區代碼）和量度（工作階段），依過去12個月的網頁工作階段分段。

   * 隨附的視覺效果，在此案例中為[長條圖](/help/analysis-workspace/visualizations/bar.md)。產生的視覺效果會以您新增至表格的資料類型為基礎。任何以時間為基礎的資料 (例如，每日/月的[!UICONTROL 工作階段])，預設以[!UICONTROL 折線圖]呈現。任何非基於時間的資料 (例如[!UICONTROL 工作階段]，依每個[!UICONTROL 裝置]) 都會預設以[!UICONTROL 條形]圖呈現。您可以按一下視覺化呈現類型旁的下拉箭頭，以變更視覺化呈現類型。

1. 嘗試新增一些更精細的功能，如以下[更多秘訣](#more-tips)所述

1. 您可能想要使用&#x200B;**[!UICONTROL 專案 > 儲存]**&#x200B;來儲存專案。

## 更多秘訣

[!UICONTROL 快速深入分析產生器]會出現其他有用的提示，其中部分取決於您最後的動作。

* 首先，您可能要完成&#x200B;**[!UICONTROL 更多秘訣]**&#x200B;教學課程。本教學課程會在您建立專案的 24 小時後顯示，其中至少包含一個維度和一個量度。選取「快速深入分析」面板標題旁的![HelpOutline](/help/assets/icons/HelpOutline.svg)，然後從快顯視窗中選取&#x200B;**[!UICONTROL 更多秘訣]**。

  ![The Quick Insights Panel notification displayed after you select the Help icon.](assets/qibuilder4.png)

* 您可以分析多個維度和量度、結合或比較區段，以及指定日期範圍：

  ![Quick Insights Builder Result](assets/qibuilder-result.png)

   * **[!UICONTROL 分析]**&#x200B;維度&#x200B;**[!UICONTROL 劃分依據]**：最多可將維度劃分為 3 個層級，以深入研究您真正需要的資料。請參閱➊、➋和➌。

   * 新增更多量度&#x200B;**[!UICONTROL 依據]**：您最多可以再增加 2 個量度。請參閱➍和➎。

   * **[!UICONTROL 區段依據]**：您最多可以再新增2個區段。 例如，新增「預訂」作為區段，並結合您所比較的「預訂常客」和「首次搭機者」區段。請參閱➏、➐和➑。

   * 在：您可以指定日期範圍。請參閱➒。

## 已知限制

如果您嘗試直接在表格中進行編輯，[!UICONTROL 快速深入分析]面板會無法同步。選取面板右上方的[!UICONTROL 重新同步產生器]，將其還原為先前的&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;設定。

直接在表格中新增任何項目之前，您會收到警告：

![The Resync Builder option warning.](assets/qibuilder-outofsync.png)

否則，直接建立表格會使其與傳統自由格式表格運作模式相同，沒有可協助新使用者的功能。


>[!MORELIKETHIS]
>
>[建立面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>