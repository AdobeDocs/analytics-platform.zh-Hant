---
description: 計算量度產生器提供的畫布可用來拖放維度、量度、篩選器和函數，讓您根據容器階層邏輯、規則和運算子來建立自訂量度。此整合性開發工具可讓您建立並儲存簡單的計算量度或複雜的進階計算量度。
title: 建置計算量度
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '1526'
ht-degree: 11%

---

# 建置計算量度 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="產品相容性"
>abstract="指出可以在 Customer Journey Analytics 的何處使用此計算量度，例如在 Analysis Workspace、Report Builder 等。一些計算量度不能用於實驗。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="在實驗中使用計算量度"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="變更外部 ID 可能會影響計算量度在外部來源 (例如商業智慧工具) 中的顯示方式"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 計算量度產生器]**&#x200B;對話方塊可用來建立新的計算量度或編輯現有的計算量度。 此對話方塊的標題為&#x200B;**[!UICONTROL 新增計算量度]**&#x200B;或&#x200B;**[!UICONTROL 編輯從[[!UICONTROL 計算量度]管理員](/help/components/calc-metrics/cm-workflow/cm-manager.md)建立或管理的量度的計算量度]**。

>[!BEGINTABS]

>[!TAB 計算量度產生器]

![顯示下一節中說明的欄位和選項的計算量度詳細資料視窗。](assets/calculated-metric-builder.png)

>[!TAB 建立或編輯計算量度]

![顯示下一節中說明的欄位和選項的計算量度詳細資料視窗。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 指定以下詳細資料 (![Required](/help/assets/icons/Required.svg) 是必要的)：

   | 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料釋圖]** | 您可以選取計算量度的資料檢視。  根據所選的資料檢視，您定義的計算量度可用於Workspace專案中。 |
   | **[!UICONTROL 僅限專案的量度]** | 資訊方塊，說明量度僅會顯示在建立該量度的專案中，且不會將該量度新增至您的元件清單中。 啟用&#x200B;**[!UICONTROL 讓此量度可用於您的所有專案，並將其新增至您的元件清單]**&#x200B;以變更該設定。 只有當您在Workspace中使用&#x200B;**[!UICONTROL 從選取範圍建立量度]**&#x200B;建立量度，並已選取函式（例如&#x200B;**[!UICONTROL 平均值]**&#x200B;或&#x200B;**[!UICONTROL 中位數]**）時，才會看到此資訊方塊。 稍後再使用[元件資訊](/help/components/use-components-in-workspace.md#component-info)來編輯該已建立的量度。 |
   | **[!UICONTROL 標題]**![Required](/help/assets/icons/Required.svg) | 為計算量度命名，例如`Conversion Rate`。 |
   | **[!UICONTROL 外部ID]** ![必要](/help/assets/icons/Required.svg) | 使用外部BI工具和BI擴充功能時計算量度的名稱。 除非您覆寫值，否則值會自動定義為`undefined_xxx`。 |
   | **[!UICONTROL 說明]** | 提供篩選的說明，例如，`Calculated metric to define the conversion rate.`。不需要說明計算量度的公式，因為公式已可在[!UICONTROL 摘要]中自動使用。 |
   | **[!UICONTROL 格式]** | 選取計算量度的格式：您可以選取介於&#x200B;**[!UICONTROL 小數]**、**[!UICONTROL 時間]**、**[!UICONTROL 百分比]**&#x200B;和&#x200B;**[!UICONTROL 貨幣]**&#x200B;之間。 |
   | **[!UICONTROL 小數位數]** | 指定所選格式的小數位數。 僅當選取的格式為小數、貨幣和百分比時啟用。 |
   | **[!UICONTROL 顯示上升趨勢的方式]** | 指定計算量度的上升趨勢顯示為▲ **[!UICONTROL 好（綠色）]**&#x200B;或▼ **[!UICONTROL 壞（紅色）]**。 |
   | **[!UICONTROL 貨幣]** | 指定計算量度的貨幣。 只有當選取的格式為貨幣時才會啟用。 |
   | **[!UICONTROL 標記]** | 透過建立或套用一個或多個標籤來組織計算量度。 開始輸入內容以尋找您可以選取的現有標記。或按&#x200B;**[!UICONTROL ENTER]**&#x200B;以新增標籤。 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標記。 |
   | **[!UICONTROL 預覽]** | 預覽涵蓋過去90天，可讓您評估量度定義是否正確。 |
   | **[!UICONTROL 摘要]** | 顯示計算量度定義的摘要。 <br/>例如： ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 訂單總數]** ![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段]**。 |
   | **[!UICONTROL 定義]** ![必要](/help/assets/icons/Required.svg) | 使用[定義產生器](#definition-builder)定義您的篩選器。 |

1. 若要驗證您的計算量度定義是否正確，請使用持續更新的計算量度結果&#x200B;**[!UICONTROL 預覽]**。 **[!UICONTROL 預覽]**&#x200B;涵蓋過去90天，並持續評估您計算量度的定義。

   **[!UICONTROL 產品相容性]**&#x200B;指出計算量度是否可用於實驗。 可能的值包括：
   * **[!UICONTROL Customer Journey Analytics中的所有位置]**：計算量度可在所有Customer Journey Analytics中使用。
   * **[!UICONTROL Customer Journey Analytics中的所有位置（實驗除外）]**：計算度量可用於所有Customer Journey Analytics，實驗面板除外。

1. 選取：
   * **[!UICONTROL 儲存]**&#x200B;以儲存計算量度。
   * **[!UICONTROL 另存新檔]**&#x200B;以儲存計算量度的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消您對計算量度所做的任何變更，或取消建立新的計算量度。


## 定義產生器

您可以使用「定義產生器」拖放維度、量度、篩選器和函式，根據容器階層邏輯、規則和運運算元建立自訂量度。 在該建構中，您可以使用標準量度、Adobe定義的量度、計算量度、篩選器、維度和函式。 所有這些元件都可從計算量度產生器的元件面板使用。 此外，您可以在定義中使用運運算元和容器。

![建立計算量度](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

只有量度在&#x200B;**[!UICONTROL 定義]**&#x200B;區域中定義為單一元件。 所有其他元件均定義為容器、包裝量度或其他容器。 如需詳細資訊，請參閱[容器](#containers)。

### 量度

若要新增量度：

* 將![事件](/help/assets/icons/Event.svg) **[!UICONTROL 量度]**&#x200B;元件從元件面板拖放到&#x200B;**[!UICONTROL 將量度、維度、維度專案、篩選器和/或函式拖放到這裡]**。 您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定元件。

當您使用計算量度做為定義的一部分時，計算量度會展開。

若要修改量度：

1. 在&#x200B;**[!UICONTROL 定義]**&#x200B;區域中的量度元件中選取![設定](/help/assets/icons/Setting.svg)。
1. 在快顯對話方塊中，您可以定義量度型別和歸因模型。 檢視[量度型別和歸因](m-metric-type-alloc.md)。

若要刪除量度：

* 在量度中選取![關閉](/help/assets/icons/Close.svg)。

### 運算子

運運算元可讓您指定元件或容器之間的運運算元。 運運算元會自動顯示於

* 容器中的兩個或多個量度，
* 容器中的兩個或多個容器，
* 容器中的一或多個量度和一或多個容器。

您可以選擇︰

| 符號 | 運算子 |
|:---:|---|
| ![除](/help/assets/icons/Divide.svg) | 除（預設） |
| ![關閉](/help/assets/icons/Close.svg) | 乘 |
| ![移除](/help/assets/icons/Remove.svg) | 減 |
| ![新增](/help/assets/icons/Add.svg) | 新增 |

### 靜態數字

您可以將靜態數字新增至計算量度定義。 若要新增靜態數字：

* 從容器中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**。
* 選取&#x200B;**[!UICONTROL 靜態數字]**。 靜態數字容器隨即顯示。
* 選取&#x200B;[!UICONTROL *按一下以新增值*]&#x200B;並輸入值。


### 容器

您可以將維度、篩選器和函式新增為計算量度定義的容器。 您也可以新增一般容器。 容器的功能類似數學運算式，用以決定運算順序。容器內的任何專案都會在下一個元件或容器之前處理。


#### 篩選器容器

您使用篩選容器的概念來建立[篩選的量度](metrics-with-segments.md)。 您可以使用篩選器來建構篩選器容器，或使用從維度建立的篩選器來建構篩選器容器。

* 若要從維度新增篩選器容器：

   1. 將![Dimension](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimension]**&#x200B;元件從元件面板拖放到&#x200B;**[!UICONTROL 將量度、維度、維度專案、篩選器和/或函式拖放到這裡]**。 您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定元件。
   1. 在&#x200B;**[!UICONTROL 從Dimension]**&#x200B;快顯視窗建立篩選器，定義篩選條件。 從運運算元清單中選取，然後選取值或輸入值。 例如，**[!UICONTROL Month]** **[!UICONTROL 等於]** ![V形](/help/assets/icons/ChevronDown.svg) `Sep 2024`。
   1. 選取&#x200B;**[!UICONTROL 完成]**。 篩選器容器已新增至&#x200B;**[!UICONTROL 定義]**。


* 若要從篩選器新增篩選器容器，您可以使用：

   * 將![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 篩選器]**&#x200B;元件從元件面板拖放到&#x200B;**[!UICONTROL 將量度、維度、維度專案、篩選器和/或函式拖放到這裡]**。 您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定篩選器。
使用篩選的名稱，自動將篩選容器新增至**[!UICONTROL 定義]**。

   * 將![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL 篩選器]**&#x200B;元件從元件面板拖放至一般容器。 容器已修改為篩選器容器。

   * 從容器中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**：

      1. 選取&#x200B;**[!UICONTROL 篩選器]**。 篩選器容器已新增至&#x200B;**[!UICONTROL 定義]**。
      1. 在新篩選器容器中，從&#x200B;[!UICONTROL *選取……*]&#x200B;下拉式選單中選取篩選器。

  >[!TIP]
  >
  >您可以新增多個篩選器至容器。

  容器中的篩選器是以篩選器元件命名。 例如，![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 網頁工作階段]**。 選取![資訊大綱](/help/assets/icons/InfoOutline.svg)以顯示包含篩選器詳細資訊的快顯視窗。 在快顯視窗中，選取![編輯](/help/assets/icons/Edit.svg)以編輯篩選器定義。

若要從容器中移除篩選器：

* 選取篩選器名稱旁的![關閉](/help/assets/icons/Close.svg)。

如需詳細資訊和範例，請參閱[篩選的量度](metrics-with-segments.md)。

#### 函式容器

若要新增函式容器，您可以使用：

* 拖放：

   1. 將![函式](/help/assets/icons/Effect.svg) **[!UICONTROL 函式]**&#x200B;元件從元件面板拖放到&#x200B;**[!UICONTROL 將量度、維度、維度專案、篩選器和/或函式拖放到這裡]**。 您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定功能。
   1. 自動使用函式的名稱將函式容器新增至&#x200B;**[!UICONTROL 定義]**。

* 從容器中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**：

   1. 選取&#x200B;**[!UICONTROL 函式]**。
   1. 在容器中，從&#x200B;[!UICONTROL *選取……*]&#x200B;下拉式功能表中選取一個函式。

函式容器會以函式元件命名。 例如，![函式](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度）]**。 選取![資訊大綱](/help/assets/icons/InfoOutline.svg)以顯示包含函式詳細資訊的快顯視窗。 選取&#x200B;**[!UICONTROL 深入瞭解]**&#x200B;以取得函式的詳細資訊。

請參閱[使用函式](cm-using-functions.md)，以取得有關如何使用函式以及哪些函式可用來建立計算量度的詳細資訊。


#### 通用容器

若要新增一般容器：

* 從容器中選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**
* 選取&#x200B;**[!UICONTROL 容器]**。 新的空白泛型容器已新增至&#x200B;**[!UICONTROL 定義]**。 您可以使用一般容器，在計算量度的定義中巢狀內嵌或建立階層。


#### 刪除容器

若要刪除容器，請選取容器層級的![關閉](/help/assets/icons/Close.svg)。

>[!MORELIKETHIS]
>
>[使用函數](cm-using-functions.md)
>[篩選器](/help/components/filters/filters-overview.md)
>

