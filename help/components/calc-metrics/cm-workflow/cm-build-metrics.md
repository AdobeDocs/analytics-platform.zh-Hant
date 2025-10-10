---
description: 了解計算量度產生器提供的畫布可用來拖放維度、量度、區段及函數，以根據容器階層邏輯、規則及運算子來建立自訂量度。
title: 建立量度
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1613'
ht-degree: 100%

---

# 建置計算量度 {#build-metrics}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="產品相容性"
>abstract="指出可以在 Customer Journey Analytics 的何處使用此計算量度，例如在 Analysis Workspace、Report Builder 等。一些計算量度不能用於實驗。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="在實驗中使用計算量度"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="變更外部 ID 可能會影響計算量度在外部來源 (例如商業智慧工具) 中的顯示方式"

Customer Journey Analytics 提供的畫布可用來拖放維度、量度、區段及函數，根據容器階層邏輯、規則及運算子來建立自訂量度。此整合性開發工具可讓您建置並儲存簡單或複雜的計算量度。

您可以使用計算量度產生器來建立或編輯計算量度。用這個方式建立的計算量度會出現在元件清單中，而且之後可用於整個組織的專案。或者，您也可以快速建立僅供建立量度之專案使用的計算量度，如[量度](/help/components/apply-create-metrics.md)的[建立單一專案的計算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)中所述。

[建立計算量度](cm-workflow.md)說明可用來建立新計算量度的不同選項。

## 計算量度產生器的區域

 **[!UICONTROL 計算量度產生器]**&#x200B;對話框用於建立新註解或編輯現有的計算量度。對於您從[[!UICONTROL 計算量度]管理員](/help/components/calc-metrics/cm-workflow/cm-manager.md)建立或管理的量度，此對話框標題為&#x200B;**[!UICONTROL 新計算量度]**&#x200B;或&#x200B;**[!UICONTROL 編輯計算量度]**。

>[!BEGINTABS]

>[!TAB 計算量度產生器]

![計算量度詳細資料視窗，顯示下一節說明的欄位和選項。](assets/calculated-metric-builder.png)

>[!TAB 建立或編輯計算量度]

![計算量度詳細資料視窗，顯示下一節說明的欄位和選項。](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. 指定以下詳細資料 (![Required](/help/assets/icons/Required.svg) 是必要的)：

   | 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料檢視]** | 您可以選取計算量度的資料檢視。根據選取的資料檢視，您定義的計算量度可在 Workspace 專案中使用。 |
   | **[!UICONTROL 僅限專案的量度]** | 如[為單一專案建立計算量度](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)所述，當您編輯為單一專案所建立的計算量度時，此對話框頂部會出現一個資訊框。 <p>如果您希望將此計算量度套用至所有專案，請選取以下選項： **[!UICONTROL 讓此量度適用於您的所有專案並將其新增至您的元件清單中]**。</p> |
   | **[!UICONTROL 標題]**![必填](/help/assets/icons/Required.svg) | 命名計算量度，例如 `Conversion Rate`。 |
   | **[!UICONTROL 外部 ID]** ![必填](/help/assets/icons/Required.svg) | 使用外部 BI 工具和 BI 擴充功能時的計算量度名稱。除非您覆寫該值，否則該值會自動定義為 `undefined_xxx` 。 |
   | **[!UICONTROL 說明]** | 提供區段說明，例如 `Calculated metric to define the conversion rate.` 不必說明計算量度的公式，因為公式已自動提供在[!UICONTROL 摘要]中。 |
   | **[!UICONTROL 格式]** | 選取計算量度的格式：您可以在&#x200B;**[!UICONTROL 十進位]**、 **[!UICONTROL 時間]**、 **[!UICONTROL 百分比]**&#x200B;和&#x200B;**[!UICONTROL 貨幣]**&#x200B;之間選取。 |
   | **[!UICONTROL 小數位數]** | 指定所選格式的小數位數。只有在選取的格式為十進制、貨幣和百分比時才啟用。 |
   | **[!UICONTROL 顯示上升趨勢的方式]** | 指定計算量度的上升趨勢是否顯示為 ▲ **[!UICONTROL 良好 (綠色)]** 或 ▼ **[!UICONTROL 不良 (紅色)]**。 |
   | **[!UICONTROL 貨幣]** | 指定計算量度的貨幣。只有在選取的格式為貨幣時才啟用。 |
   | **[!UICONTROL 標記]** | 透過建立或套用一個或多個標記來安排計算量度。開始輸入內容以尋找您可以選取的現有標記。或按一下 **[!UICONTROL ENTER]** 以新增新標記。選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標記。 |
   | **[!UICONTROL 預覽]** | 預覽涵蓋過去 90 天的情況，並且是衡量您是否正確定義量度的方法。 |
   | **[!UICONTROL 摘要]** | 顯示計算量度定義的摘要。<br/>例如：  ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 總訂單]** ![劃分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段]**。 |
   | **[!UICONTROL 定義]** ![必填](/help/assets/icons/Required.svg) | 使用[定義產生器](#definition-builder)來定義區段。 |

1. 若要驗證您的計算量度定義是否正確，請使用不斷更新的計算指標結果&#x200B;**[!UICONTROL 預覽]** 。 **[!UICONTROL 預覽]**&#x200B;涵蓋過去 90 天的情況，並持續評估計算量度的定義。

   **[!UICONTROL 產品相容性]**&#x200B;表示計算量度是否可用於實驗。可能的值包括：
   * **[!UICONTROL 在 Customer Journey Analytics 中各處]**：計算量度可用於整個 Customer Journey Analytics。
   * **[!UICONTROL 在 Customer Journey Analytics 中各處 (不包括實驗)]**：計算量度可用於除實驗面板之外的所有 Customer Journey Analytics 部分。

1. 選取：
   * **[!UICONTROL 儲存]**&#x200B;以儲存計算量度。
   * **[!UICONTROL 另存新檔]**&#x200B;以儲存計算量度副本。
   * **[!UICONTROL 取消]**&#x200B;以取消您對計算量度所做的任何變更，或取消新計算量度的建立。


## 定義產生器

您使用定義產生器來拖放維度、量度、區段和函數，讓您根據容器階層邏輯、規則和運算子來建立自訂量度。在該構造中，您可以使用標準量度、Adobe 定義的量度、計算量度、區段、維度和函數。計算量度產生器中的元件面板都提供所有這些元件。此外，您還可以在定義中使用運算子和容器。

![建立計算量度](/help/components/calc-metrics/cm-workflow/assets/create-calculated-metric.gif)

在&#x200B;**[!UICONTROL 定義]**&#x200B;區域中，只有量度會被定義為單一元件。所有其他元件都被定義為容器、封裝量度或其他容器。如需詳細資訊，請參閱[容器](#containers)。

### 量度

若要新增量度：

* 將 ![Events](/help/assets/icons/Event.svg) **[!UICONTROL 量度]**&#x200B;元件從元件面板拖放至&#x200B;**[!UICONTROL 將量度、維度、維度項目、區段和/或函數拖放到這裡]**。您可以使用元件列中的「![搜尋](/help/assets/icons/Search.svg)」來搜尋特定元件。

當您使用計算量度作為定義的一部分時，計算量度將會擴展。

若要修改量度：

1. 在&#x200B;**[!UICONTROL 定義]**&#x200B;區域中，選取量度元件中的 ![設定](/help/assets/icons/Setting.svg)。
1. 在快顯對話框中，您可以定義量度類型和歸因模型。請參閱「[量度類型和歸因](m-metric-type-alloc.md)」。

若要刪除量度：

* 選取量度中的 ![關閉](/help/assets/icons/Close.svg)。

### 運算子

運算子可讓您指定元件或容器之間的運算子。運算子會自動出現在二者之間：

* 容器中的兩個或多個量度、
* 容器中的兩個或多個容器、
* 容器中的一個或多個量度以及一個或多個容器。

您可以選擇：

| 符號 | 運算子 |
|:---:|---|
| ![除](/help/assets/icons/Divide.svg) | 除 (預設) |
| ![關閉](/help/assets/icons/Close.svg) | 乘 |
| ![移除](/help/assets/icons/Remove.svg) | 減 |
| ![新增](/help/assets/icons/Add.svg) | 新增 |

### 靜態數字

您可以將靜態數字新增至計算量度定義。若要新增靜態數字：

* 從容器內部選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]**。
* 選取「**[!UICONTROL 靜態數字]**」。出現靜態數字容器。
* 選取「[!UICONTROL *按一下以新增值*]」，並輸入一個值。


### 容器

您可以將維度、區段和函數做為容器，以新增至計算量度定義。您也可以新增通用容器。容器的功能類似數學運算式，用以決定運算順序。容器內的一切都會在下一個元件或容器之前獲得處理。


#### 區段容器

您可以使用區段容器的概念來建立[已劃分的量度](metrics-with-segments.md)。您可以使用區段，或使用從維度建立的區段來建構區段容器。

* 若要從維度新增區段容器：

   1. 將 ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL 維度]**&#x200B;元件從元件面板拖放至&#x200B;**[!UICONTROL 將量度、維度、維度項目、區段和/或函數拖放到這裡]**。您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定元件。
   1. 在&#x200B;**[!UICONTROL 「從維度中建立區段」]**&#x200B;快顯視窗中，定義區段的條件。從運算子清單中選取，並選取一個值或輸入一個值。例如， **[!UICONTROL 月]** **[!UICONTROL 等於]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`。
   1. 選取「**[!UICONTROL 完成]**」。將區段容器加入&#x200B;**[!UICONTROL 定義]**&#x200B;中。


* 若要從區段新增區段容器，您可以使用：

   * 將 ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;元件從元件面板拖放至&#x200B;**[!UICONTROL 將量度、維度、維度項目、區段和/或函數拖放到這裡]**。您可以使用元件列中的![搜尋](/help/assets/icons/Search.svg)來搜尋特定區段。使用區段名稱將區段容器自動加入&#x200B;**[!UICONTROL 定義]**&#x200B;中。

   * 將 ![分段](/help/assets/icons/Segmentation.svg)**[!UICONTROL 「區段」]**&#x200B;元件從元件面板拖放到通用容器中。該容器被修改為區段容器。

   * 從容器內部選取 ![AddCircle](/help/assets/icons/AddCircle.svg)**[!UICONTROL 「新增」]**：

      1. 選取&#x200B;**[!UICONTROL 「區段」]**。區段容器就會新增至&#x200B;**[!UICONTROL 「定義」]**。
      1. 在新的區段容器中，從&#x200B;[!UICONTROL *「選取...」*]&#x200B;下拉式選單中選取區段。

  >[!TIP]
  >
  >您可以新增多個區段至一個容器中。

  容器中的區段是以區段元件所命名。例如， ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL 網頁工作階段]**。選取 ![InfoOutline](/help/assets/icons/InfoOutline.svg)，顯示出含有區段詳細資訊的快顯視窗。在快顯視窗中，選取「![編輯](/help/assets/icons/Edit.svg)」以編輯區段定義。

若要從容器中移除區段：

* 選取區段名稱旁的「![關閉](/help/assets/icons/Close.svg)」。

請參閱[分段量度](metrics-with-segments.md)以了解更多詳細資料和範例。

#### 函數容器

若要新增函數容器，您可以使用：

* 拖放：

   1. 將 ![Function](/help/assets/icons/Effect.svg) **[!UICONTROL 函數]**&#x200B;元件從元件面板拖放至&#x200B;**[!UICONTROL 將量度、維度、維度項目、區段和/或函數拖放到這裡]**。您可以使用元件列中的「![搜尋](/help/assets/icons/Search.svg)」來搜尋特定函數。
   1. 使用函數名稱將函數容器自動加入「**[!UICONTROL 定義]**」中。

* 從容器內部選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]**：

   1. 選取「**[!UICONTROL 函數]**」。
   1. 在容器中，從&#x200B;[!UICONTROL *「選取...」*]&#x200B;下拉式選單中選取一個函數。

函數容器以函數元件命名。例如， ![函數](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根 (量度)]**。選取 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 來顯示含有函數詳細資訊的快顯視窗。選取「**[!UICONTROL 了解更多]**」，了解更多有關該函數。

請參閱「[使用函數](cm-using-functions.md)，了解如何使用函數以及可使用哪些函數來建立計算量度的詳情。


#### 通用容器

若要新增通用容器：

* 從容器內部選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]**
* 選取「**[!UICONTROL 容器]**」。將一個空置的新通用容器加入「**[!UICONTROL 定義]**」中。您可以使用通用容器在計算量度的定義中嵌套或建立層次結構。


#### 刪除容器

若要刪除容器，請從容器層級選取 ![關閉](/help/assets/icons/Close.svg) 。

>[!MORELIKETHIS]
>
>[使用函數](cm-using-functions.md)
>>[區段](/help/components/segments/seg-overview.md)
>
