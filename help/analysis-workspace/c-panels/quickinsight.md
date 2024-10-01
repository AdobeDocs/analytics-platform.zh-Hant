---
description: 「快速深入分析」是適用於新 Workspace 使用者的工具，可引導他們建立資料表格和視覺效果
title: 快速深入分析面板
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 24%

---

# 快速深入分析面板 {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_quickinsights_button"
>title="快速深入分析"
>abstract="建立面板以快速建立自由格式表格和隨附的視覺效果，從而更快速地分析和發掘深入分析。"

<!-- markdownlint-enable MD034 -->


[!UICONTROL 快速深入分析]為 [!UICONTROL Analysis Workspace] 的非分析師和新使用者提供指引，瞭解如何快速輕鬆回答業務問題。對於想要快速解答簡單的問題而無須自行建立表格的進階使用者，這也是絕佳的工具。

第一次使用此[!UICONTROL Analysis Workspace]時，您可能會想：

* 哪些視覺效果最有用，
* 哪些維度和量度可能有助於深入分析，
* 拖放專案的位置，
* 建立篩選器的位置，
* 及更多內容。

為協助您解決這些問題，[!UICONTROL 快速深入分析]會運用演演算法，提供貴公司最常使用的維度、量度、篩選器和日期範圍。 此演演算法是根據您公司在[!UICONTROL Analysis Workspace]中使用資料元件的情形。 實際上，您會在下拉式清單中看到標示為[!UICONTROL POPULAR]的維度、量度和篩選器，如下所示：

![「快速深入分析」面板。](assets/popular-tag.png)

[!UICONTROL 快速深入分析]可協助您

* 在 [!UICONTROL Analysis Workspace] 中適當建立資料表格及隨附的視覺效果。
* 瞭解 [!UICONTROL Analysis Workspace] 的基本元件和部件所適用的術語和辭彙。
* 在[!UICONTROL 自由形式表格]中輕鬆進行維度的簡單劃分、新增多個量度或比較篩選器。
* 變更或試用各種視覺效果類型，以快速且直覺地找出您的分析適用的尋找工具。

## 基本關鍵術語

以下是您需要熟悉的一些基本術語。 每個資料表格都包含2個或更多組成要素（元件），讓您用來建構自己的資料故事。

| 組成要素 (元件) | 定義 |
|---|---|
| **[!UICONTROL 維度]** | 維度是量度資料的描述或特性，您可以在專案中加以檢視、劃分及比較。這是可劃分為維度項目的非數值和日期。例如，*瀏覽器*&#x200B;或&#x200B;*頁面*&#x200B;是維度。 |
| **[!UICONTROL 維度項目]** | 維度項目是維度的個別值。例如，瀏覽器維度的維度專案為&#x200B;*Chrome*、*Firefox*、*Edge*&#x200B;或其他。 |
| [!UICONTROL 量度] | 度量是有關人員活動的量化資訊，例如瀏覽次數、點進、重新載入、平均逗留時間、件數、訂購、收入等。 |
| **[!UICONTROL 視覺效果]** | Workspace提供[許多視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)，以建立資料的視覺化表示法。 例如長條圖、環圈圖、直方圖、折線圖、地圖、散點圖等。 |
| **[!UICONTROL 維度劃分]** | 維度劃分是以其他維度來劃分維度的方式。 例如，您可以依行動裝置劃分美國各州，以取得各州的行動裝置造訪次數。 或者，您也可以依行動裝置型別、地區、內部促銷活動等劃分行動裝置。 |
| **[!UICONTROL 篩選器]** | 篩選器可讓您根據特性或網站互動來識別人員的子集。 例如，您可以根據以下條件建立[!UICONTROL 人員]篩選器 <li>屬性：瀏覽器型別、裝置、造訪次數、國家/地區、性別或</li><li>互動：促銷活動、關鍵字搜尋、搜尋引擎或</li><li>退出點和登入點：來自Facebook、已定義的登陸頁面、反向連結網域或是</li><li> 自訂變數：表單欄位、定義的類別、客戶ID。 |

## 使用

若要使用&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板。 如需如何建立面板的詳細資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 第一次使用&#x200B;**[!UICONTROL 快速深入分析]**&#x200B;面板時，您可能會想要進行簡短的[!UICONTROL 簡介教學課程]，以教導您一些基本知識。 選取「快速深入分析」面板標題旁的![說明大綱](/help/assets/icons/HelpOutline.svg)，並從快顯視窗中選取&#x200B;**[!UICONTROL 介紹教學課程]**。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。


### 面板輸入

選取您的建置區塊：

* **[!UICONTROL 分析]** — 指定維度（橘色）
* **[!UICONTROL by]** — 指定量度（綠色）
* **[!UICONTROL 篩選依據]** — 指定篩選器（藍色）
* **[!UICONTROL on]** — 指定資料範圍（紫色）。

您必須至少選取一個維度和一個量度，視覺效果才能正常運作。



您可以透過三種方式指定組成要素：

* 從左側面板拖放元件。
* 開始輸入其中一個建置區塊欄位。 找到輸入時，建置區塊欄位會自動填入可能的值。
* 指定建置區塊下拉式清單（例如&#x200B;**[!UICONTROL Analyze]**&#x200B;中的`Country`），並搜尋可能值的清單（使用![ChevronRight](/help/assets/icons/ChevronRight.svg)）以取得您要使用的值（例如&#x200B;**[!UICONTROL 國家/地區代碼]**）。

選取&#x200B;**[!UICONTROL 清除]**&#x200B;以清除所有輸入欄位。


### 面板輸出

1. 當您已新增至少一個維度和一個量度時，就能看到結果。

   ![自由形式表格，垂直顯示維度，水平顯示量度。](assets/quick-insights-output.png)

   * 自由表格，內含維度（國家/地區代碼）和量度（工作階段），依過去12個月的網頁工作階段篩選。

   * 隨附的視覺效果，在此案例中為[長條圖](/help/analysis-workspace/visualizations/bar.md)。產生的視覺效果會以您新增至表格的資料類型為基礎。任何以時間為基礎的資料（例如，每日/月的[!UICONTROL 工作階段]）都會預設為[!UICONTROL 折線]圖表。 任何非時間型資料（例如，每個[!UICONTROL 裝置]的[!UICONTROL 工作階段]）預設為[!UICONTROL 橫條]圖表。 您可以按一下視覺效果類型旁的下拉箭頭，以變更視覺效果類型。

1. 嘗試新增一些更精細的功能，如下所述[更多提示](#more-tips)

1. 您可能會想要使用&#x200B;**[!UICONTROL 專案>儲存]**&#x200B;來儲存專案。

## 更多秘訣

[!UICONTROL 快速深入分析產生器]中會出現其他有用的提示，其中一些提示取決於您最後的動作。

* 首先，您可能會想要完成&#x200B;**[!UICONTROL 更多提示]**&#x200B;教學課程。 本教學課程會在您建立專案的24小時後顯示，其中至少包含一個維度和一個量度。 選取「快速深入分析」面板標題旁的![說明大綱](/help/assets/icons/HelpOutline.svg)，然後從快顯視窗中選取&#x200B;**[!UICONTROL 更多提示]**。

  ![選取「說明」圖示後，會顯示「快速深入分析」面板通知。](assets/qibuilder4.png)

* 您可以分析多個維度和量度、合併或比較篩選器，以及指定資料範圍：

  ![快速深入分析產生器結果](assets/qibuilder-result.png)

   * **[!UICONTROL 分析]**&#x200B;維度&#x200B;**[!UICONTROL 劃分依據]**：您最多可對維度使用3個層級的劃分，以深入鑽研您真正需要的資料。 請參閱➊、➋和➌。

   * **[!UICONTROL 由]**&#x200B;新增更多量度：您最多可以再新增2個量度。 請參閱➍和➎。

   * **[!UICONTROL 篩選依據]**：您最多可以再新增2個篩選器。 例如，新增Bookings作為篩選器，並將該篩選器與您比較的「經常預約者」和「首次傳單」篩選器合併。 請參閱➏、➐和➑。

   * 開啟：您可以指定資料範圍。 請參閱➒。

## 已知限制

如果您嘗試直接在表格中進行編輯，[!UICONTROL 快速深入分析]面板可能會不同步。 選取面板右上角的&#x200B;**[!UICONTROL 重新同步產生器]**，將其還原為先前的[!UICONTROL 快速深入分析]設定。

直接將任何專案新增至表格前，您會收到警告：

![「重新同步產生器」選項警告。](assets/qibuilder-outofsync.png)

否則，直接建立會導致表格如傳統自由表格般運作，而沒有可協助新使用者的功能。


>[!MORELIKETHIS]
>
>[建立面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>