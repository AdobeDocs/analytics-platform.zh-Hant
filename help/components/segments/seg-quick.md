---
description: 在適用於 Customer Journey Analytics 的 Analysis Workspace 中使用快速區段
title: 快速區段
feature: Workspace Basics, Filters, Segments
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 91%

---

# 快速區段

快速區段可讓您快速探索 Workspace 專案內的資料，而無需在[區段產生器](/help/components/segments/seg-create.md)中建立區段。



>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的快速區段](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"}示範影片。

>[!ENDSHADEBOX]


當您想要使用快速區段時，請注意：

* 快速區段是直接在 Workspace 專案中所建立。因此，快速區段僅適用於您建立快速區段所在的 Workspace 專案。您 Workspace 專案中的快速區段不適用於其他專案，也不能供其他使用者共用。
* 您只能指定三個條件作為快速區段的一部分。
* 快速區段不支援巢狀容器或序列條件。
* 您可以在共用 Workspace 專案中編輯快速區段。因此，其他使用者可以編輯您已供這些使用者共用的 Workspace 專案快速區段。

## 建立

快速區段適用於面板。您可以為 Workspace 專案中的每個面板建立一個或多個快速區段。Analysis Workspace 中的任何使用者都可以建立快速區段。

若要建立快速區段：

* 選取面板最上方的「![SegmentAdd](/help/assets/icons/FilterAdd.svg)」。<br/>然後，直接在[快速區段產生器](#quick-segment-builder)中編輯區段。
* 將元件從元件面板拖曳到面板標題中的區段放置區。放下後，將滑鼠停留在區段上並選取「![編輯](/help/assets/icons/Edit.svg)」，即可在[快速區段產生器](#quick-segment-builder)中編輯區段。

使用拖放動作來建立快速區段時，請注意：

* 並非所有元件類型都受支援。計算量度不受支援，僅有建置區段的維度和量度受支援。
* 對於維度和量度元件，[快速區段產生器](#quick-segment-builder)會自動建立 `exists` 條件。例如，如果您拖放 `City`，則 `City exists` 條件就會建立。
* 對於維度值，[快速區段產生器](#quick-segment-builder)會自動建立 `equals` 條件。例如，如果您從 `City` 維度拖放 `amsterdam`，則 `City equals amsterdam` 條件就會建立。
* 如果您拖放 `unspecified` 或 `none`，[快速區段產生器](#quick-segment-builder)會自動建立一個 `does not exist` 條件。

您建立的快速區段會出現在面板頂部。快速區段左邊有一個淺藍色長條。當使用[快速區段產生器](#quick-segment-builder)，而快速區段處於編輯模式時，快速區段的背景為淺藍色。

您在面板中建立的快速區段結果將套用 (使用 AND 邏輯) 至面板的所有視覺效果。


## 管理

若要管理快速區段，請將滑鼠停留在特定的&#x200B;**[!UICONTROL 快速區段]**&#x200B;上。

* 選取「![編輯](/help/assets/icons/Edit.svg)」，開啟[快速區段產生器](#quick-segment-builder)，編輯快速區段。
* 選取「![InfoOutline](/help/assets/icons/InfoOutline.svg)」，開啟快顯視窗。快顯視窗會顯示關於區段的資訊。您可以選取&#x200B;**[!UICONTROL 「設為可用於所有專案，並新增至您的元件清單」]** 新增區段至元件面板中的 ![Segment](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;元件清單。您會看到「**[!UICONTROL 儲存快速區段]**」對話框，提示您為區段指定名稱。選取「**[!UICONTROL 儲存]**」以繼續。您的[!UICONTROL 快速區段]會變成&#x200B;**[!UICONTROL 區段]**。您無法再使用[快速區段產生器](#quick-segment-builder)編輯該區段。相對地，您必須使用[區段產生器](seg-builder.md)，以一般區段來編輯該區段。

## 快速區段產生器

請參閱下面的快速區段產生器範例。在範例中，開啟產生器以快速產生標題為 `Call Reason = Order Change AND Online Orders is greater than or equal 1` 的區段。上方的兩個快速區段均適用於「[!UICONTROL 平均訂購值儀表板]」面板及其中所有視覺效果，例如「[!UICONTROL 每個國家/地區的平均訂購值]」自由格式表格。

![快速區段產生器](assets/quick-filter-builder.png)

快速區段產生器由以下區域和按鈕組成。

### 標題區域

標題區域會確定快速區段的名稱、類型和範圍。此區域還會以視覺效果顯示快速區段的結果。

| 元素 | 說明 |
|---|---|
| **[!UICONTROL 名稱]** | 該名稱是從快速區段定義自動衍生。 |
| **[!UICONTROL 人員]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![警報](/help/assets/icons/Alert.svg) | 預覽快速區段所得的資料。透過長條圖和百分比可以了解整體資料中有多少是快速區段結果的一部分。紅色![警報](/help/assets/icons/Alert.svg)表示快速區段未回傳資料。 |
| **[!UICONTROL 包括]**<br/>**[!UICONTROL 排除]** | 從下拉式清單![V形](/help/assets/icons/ChevronDown.svg)中選取是否要從面板中的資料包含或排除快速區段的結果。 |
| **[!UICONTROL 事件]**<br/>**[!UICONTROL 工作階段]**<br/>**[!UICONTROL 人員]** | 從下拉式功能表中選取![V形向下鍵](/help/assets/icons/ChevronDown.svg)快速區段的範圍。 |

### 條件區域

條件區域可指定條件 (最多三個)。對於每個條件，您可以指定以下內容：

| 元素 | 說明 |
|---|---|
| **[!UICONTROL 維度]**<br/>**[!UICONTROL 量度]**<br/>**[!UICONTROL 日期範圍]** | 從下拉式功能表選取![V形](/help/assets/icons/ChevronDown.svg)您要指定維度、量度或日期範圍的條件。 |
| **[!UICONTROL *元件&#x200B;*]** | 條件的元件欄位。你可以&#x200B;[!UICONTROL *輸入以新增*]&#x200B;元件、從清單中選取元件，或者，您可以從元件面板中拖放一個元件。您只能將類似的元件放置在條件的元件欄位上。例如，您只能根據維度條件從元件面板中放置維度元件。<br/>您也可以透過拖放動作來取代現有元件。<br/>選取 ![CrossSize75](/help/assets/icons/CrossSize75.svg)，從元件欄位刪除該元件。 |
| **[!UICONTROL *運算子&#x200B;*]** | 元件的運算子。如需詳細資訊，請參閱「[運算子](seg-operators.md)」。僅適用於維度和量度。 |
| **[!UICONTROL *值&#x200B;*]** | 條件的值。根據所選的運算子，可以從清單中選取值或輸入一個值。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 選取並從快速區段中刪除一個條件。 |

### 按鈕

| 按鈕 | 說明 |
|---|---|
| **[!UICONTROL AND]**<br/>**[!UICONTROL OR]** | 只有在您定義多個條件時才適用。從下拉式功能表![條件之間的V形](/help/assets/icons/ChevronDown.svg)中選取。 這項選擇會確定快速區段的布林邏輯。當有三個條件時，你不能混合使用邏輯。布林邏輯可以是 **[!UICONTROL AND]** 或 **[!UICONTROL OR]**。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 新增另一個條件至您的快速區段。只有在您為快速區段定義一個或兩個條件時，此按鈕才適用。 |
| **[!UICONTROL 套用]** | 套用變更至快速區段。 |
| **[!UICONTROL 開啟產生器]** | 系統會出現提示，請您確認：**[!UICONTROL 你確定嗎？]**&#x200B;對話框。如果您選取「**[!UICONTROL 確定」]**，您再也無法在後者編輯您的區段：[快速區段產生器](#quick-segment-builder) 您的快速區段已重新命名為&#x200B;**[!UICONTROL 區段]**，且現在左邊有一個深藍色的細條。<br/>一般[區段產生器](seg-builder.md)會開啟，並有「**[!UICONTROL 讓此區段適用於您的所有專案並將其新增至您的元件清單中]**」選項。 <ul><li>如果您選取此選項並選取&#x200B;**[!UICONTROL 套用]**，區段會新增至元件面板中的![區段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;元件清單。</li><li>如果您未選取此選項並選取「**[!UICONTROL 套用]**」，該區段仍然是僅限 Workspace 專案的區段。</li></ul> |
| **[!UICONTROL 取消]** | 選取並取消建立或編輯快速區段。 |

## 快速區段與區段

快速區段即如其名所示。您可以快速建立和編輯快速區段，並立即在面板中查看效果。

與快速區段相比，區段確實具有以下優點。

* 區段可建立為適於您所有的 Workspace 專案
* 區段支援使用巢狀和階層式[容器](seg-builder.md#containers)和序列（使用[循序區段](seg-sequential-build.md)）的更多複雜性。


