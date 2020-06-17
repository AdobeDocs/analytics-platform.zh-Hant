---
description: 「快速洞察」是適用於新工作區使用者的工具，可引導他們建立資料表格和視覺化
title: 快速洞察面板
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 6%

---


# 快速洞察面板

>[!NOTE] 您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL 「快速洞察]** 」面板目前測試有限。 [更多詳情](https://docs.adobe.com/content/help/zh-Hant/analytics/landing/an-releases.html)

[!UICONTROL 「快速深入分析」]為 [!UICONTROL Analysis Workspace] 的非分析師和新使用者提供指引，瞭解如何快速輕鬆回答業務問題。對於想要快速回答簡單問題而不需要自行建立表格的進階使用者而言，它也是絕佳的工具。

當您第一次使用此分析工作區時 ，可能會想知道哪些視覺化最有用、哪些維度和量度可能有助於洞察、拖放項目的位置、建立區段的位置等。

為協助您，並根據您公司在 [!UICONTROL Analysis Workspace中的資料元件使用情況，]Quick Insights  運用演算法，提供您公司使用的最熱門維度、量度、區段和日期範圍。 事實上，您會在下拉式清單中看到標籤為 [!UICONTROL Popul] （熱門）的維度、量度和區段，如下所示：

![](assets/popular-tag.png)

[!UICONTROL 快速洞察] ，協助您

* 在分析工作區中正確建立資料表格及隨附 [!UICONTROL 的視覺化]。
* 瞭解分析工作區的基本元件和部分的術語 [!UICONTROL 和辭彙]。
* 在自由表格中輕鬆進行維度的簡單劃分、新增多個量度或比較 [!UICONTROL 區段]。
* 變更或試用各種視覺化類型，以快速且直覺式的方式尋找分析的尋找工具。

## 基本關鍵術語

以下是您需要熟悉的一些基本辭彙。 每個資料表格包含2個或多個您用來述說資料故事的建置區塊（元件）。

| 構件（元件） | 定義 |
|---|---|
| [!UICONTROL 維度] | 維度是量度資料的說明或特性，可在專案中檢視、劃分和比較。 它們是非數值和日期，可劃分為維度項目。 例如，「瀏覽器」或「頁面」是維度。 |
| [!UICONTROL 維度項目] | 維度項目是維度的個別值。 例如，瀏覽器維度的維度項目為「Chrome」、「Firefox」、「Edge」等。 |
| [!UICONTROL 量度] | 量度是有關訪客活動的量化資訊，例如瀏覽次數、點進、重新載入、平均逗留時間、件數、訂購、收入等。 |
| [!UICONTROL 視覺效果] | Workspace offers [a number of visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to build visual representations of your data, such as bar charts, donut charts, histograms, line charts, maps, scatterplots, and others. |
| [!UICONTROL 維度劃分] | 維度劃分是依其他維度來劃分維度的一種方式。 在我們的範例中，您可以依行動裝置來劃分美國各州，以取得每個州的行動裝置瀏覽次數，或依行動裝置類型、地區、內部促銷活動等來劃分行動裝置。 |
| [!UICONTROL 區段] | 區段可讓您根據特性或網站互動來識別訪客的子集。 例如，您可以根據屬 [!UICONTROL 性] ，建立訪客區段： 瀏覽器類型、裝置、瀏覽次數、國家、性別或根據互動： 促銷活動、關鍵字搜尋、搜尋引擎，或根據退出點和登入點： 來自Facebook、已定義登陸頁面、反向連結網域或自訂變數的訪客： 表單欄位、定義的類別、客戶ID。 |

## 快速洞察入門

1. 使用您所提供的認證登入Adobe Analytics。
1. 前往「工 [!UICONTROL 作區] 」，按一下「 **[!UICONTROL 建立新專案]** 」，然後按一 **[!UICONTROL 下「快速分析」]**。 (您也可以從左側導軌的「面板 **** 」選單存取此面板。)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. 當您第一次開始時，請進行簡短的教學課程，教導您一些「快速洞察」面 [!UICONTROL 板的基本概念] 。 或者，按一下「略過 **[!UICONTROL 教學課程」]**。
1. 選擇您的構建塊（也稱為元件）: 維度（橘色）、量度（綠色）、區段（藍色）或日期範圍（紫色）您必須為要自動建立的表格至少選擇一個維度和一個量度。

   ![](assets/qibuilder2.png)

   您有三種選擇構造塊的方法：
   * 從左側導軌拖放。
   * 如果您知道您要尋找的是： 開始輸入 [!UICONTROL 內容] ,「快速洞察」將為您填空。
   * 按一下下拉式清單並搜尋清單。

1. 當您新增至少一個維度和一個量度時，將會為您建立下列項目：

   * 自由表格，其上方為垂直維度（此處為美國州）和水準度量（此處為瀏覽）。 查看下表：

   ![](assets/qibuilder3.png)

   * 隨附的視覺化，在此例中為長 [條圖](/help/analysis-workspace/visualizations/bar.md)。 產生的視覺化是根據您新增至表格的資料類型。 任何以時間為基礎的資料(例如 [!UICONTROL 每日] /月的瀏覽次數 [!UICONTROL )都預設為] 折線圖。 任何非時間型資料(例如每個裝 [!UICONTROL 置的][!UICONTROL 瀏覽次數])都預設為 [!UICONTROL 長條圖] 。 您可以按一下視覺化類型旁的下拉箭頭，以變更視覺化類型。


1. （可選）按一下維度旁的>向右箭頭，以深入檢視維度項目。

1. 嘗試新增一些更精良的功能，如下面「更多提示」中所述。

1. 按一下「專案>儲 **[!UICONTROL 存」以儲存專案]**。

## 更多秘訣

「快速洞察」產生器中會出現其 [!UICONTROL 他有用的提示]，其中一些提示會視您最後的動作而定。

* 首先，完成更多 **[!UICONTROL 提示教學課程]** : 透過說明(?)存取它 圖示，位於「快 [!UICONTROL 速洞察] 」標題旁。 本教學課程在您建立專案後24小時內顯示，專案至少包含一個維度和一個度量。

   ![](assets/qibuilder4.png)

* **劃分依據**: 您最多可針對維度使用3個層級的劃分，以深入探討您真正需要的資料。

   ![](assets/qibuilder5.png)

* **新增更多量度**: 您最多可以使用AND運算子新增2個量度至表格。

   ![](assets/qibuilder6.png)

* **新增更多區段**: 您最多可以使用AND或OR運算子來新增多達2個區段。 查看新增「行動使用者」或「忠誠訪客」時表格的變更。 它們彼此相鄰，位於量度上方。 如果您新增「行動使用者」和「忠誠訪客」，您會同時看到這兩個區段的結果，而且這些結果會堆疊在表格中。

   ![](assets/qibuilder7.png)

## 已知限制

如果您嘗試直接在表格中編輯，會導致「快速 [!UICONTROL 洞察] 」面板不同步。 您可以按一下面板右上 [!UICONTROL 方的「重新同步產生器]**** 」，將其還原為先前的「快速分析」設定。

![](assets/qibuilder9.png)

在直接將任何內容新增至表格之前，您會收到警告：

![](assets/qibuilder8.png)

否則，直接建立會使表格現在像傳統的自由表格一樣運作，而沒有新使用者的實用功能。

