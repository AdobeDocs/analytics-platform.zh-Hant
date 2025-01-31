---
description: 在適用於 Customer Journey Analytics 的 Analysis Workspace 中使用快速篩選
title: 快速篩選
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 2%

---

# 快速篩選

快速篩選可讓您快速探索Workspace專案中的資料，而不需要在[篩選產生器](/help/components/filters/create-filters.md)中建立篩選。



>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace中的快速區段](https://video.tv.adobe.com/v/341466/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


當您想要使用快速篩選器時，請注意：

* 快速篩選會直接在Workspace專案中建立。 因此，快速篩選僅適用於您建立快速篩選的Workspace專案。 您的Workspace專案中的快速篩選器無法用於其他專案，且無法與其他使用者共用。
* 您只能指定三個條件作為快速篩選的一部分。
* 快速篩選器不支援巢狀容器或循序條件。
* 您可以在共用的Workspace專案中編輯快速篩選。 因此，其他使用者可以在您與這些使用者共用的Workspace專案中編輯快速篩選。

## 建立

快速篩選器適用於面板。 您可以為Workspace專案中的每個面板建立一或多個快速篩選器。 Analysis Workspace中的任何使用者都可以建立快速篩選。

若要建立快速篩選：

* 選取面板頂端的![篩選新增](/help/assets/icons/FilterAdd.svg)。 <br/>然後，直接在[快速篩選產生器](#quick-filter-builder)中編輯篩選。
* 將元件從元件面板拖曳至面板標題中的篩選器拖放區域。 捨棄後，將滑鼠懸停在篩選器上，並選取![編輯](/help/assets/icons/Edit.svg)以在[快速篩選產生器](#quick-filter-builder)中編輯篩選器。

使用拖放功能建立快速篩選時，請注意：

* 並非所有元件型別都受支援。 計算量度不受支援，僅支援您可從中建立篩選器的維度和量度。
* 對於維度和量度元件，[快速篩選產生器](#quick-filter-builder)會自動建立`exists`條件。 例如，若您拖放`City`，則會建立條件`City exists`。
* 對於維度值，[快速篩選產生器](#quick-filter-builder)會自動建立`equals`條件。 例如，如果您從`City`維度拖放`amsterdam`，則會建立條件`City equals amsterdam`。
* 如果您拖放`unspecified`或`none`，[快速篩選產生器](#quick-filter-builder)會自動建立`does not exist`條件。

您建立的快速篩選會出現在面板頂端。 快速濾鏡的左邊欄是淺藍色的。 當使用[快速篩選產生器](#quick-filter-builder)的快速篩選處於編輯模式時，快速篩選的背景為淡藍色。

您在面板中建立的快速篩選結果，會套用（使用AND邏輯）至面板中的所有視覺效果。


## 管理

若要管理快速篩選，請將游標移至特定的&#x200B;**[!UICONTROL 快速篩選]**&#x200B;上。

* 選取![編輯](/help/assets/icons/Edit.svg)以開啟[快速篩選產生器](#quick-filter-builder)並編輯快速篩選。
* 選取![資訊大綱](/help/assets/icons/InfoOutline.svg)以開啟快顯視窗。 快顯視窗會顯示篩選的相關資訊。 您可以選取&#x200B;**[!UICONTROL 使其可用於所有專案並新增至您的元件清單]**&#x200B;若要將篩選器新增至元件面板中的![篩選器](/help/assets/icons/Segmentation.svg) **[!UICONTROL 篩選器]**&#x200B;元件清單。 您會看到&#x200B;**[!UICONTROL 儲存快速篩選]**&#x200B;對話方塊，提示您指定篩選的名稱。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以繼續。 您的[!UICONTROL 快速篩選器]會變成&#x200B;**[!UICONTROL 篩選器]**。 您無法再使用[快速篩選產生器](#quick-filter-builder)編輯篩選。 您必須改用[篩選產生器](filter-builder.md)，將篩選編輯為一般篩選。

## 快速篩選產生器

如需快速篩選產生器的範例，請參閱下文。 在此範例中，會開啟產生器以供標題為`Call Reason = Order Change AND Online Orders is greater than or equal 1`的快速篩選。 上方的兩個快速篩選器皆適用於[!UICONTROL 平均訂購值儀表板]面板及其中的所有視覺效果，例如[!UICONTROL 每個國家/地區的平均訂購值]自由表格。

![快速篩選產生器](assets/quick-filter-builder.png)

快速篩選產生器包含下列區域和按鈕。

### 頁首區域

標題區域決定快速篩選的名稱、型別和範圍。 它也會顯示快速篩選結果的視覺效果。

| 元素 | 說明 |
|---|---|
| **[!UICONTROL 名稱]** | 名稱會自動衍生自快速篩選定義。 |
| **[!UICONTROL 人員]** <br/>![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) ![警報](/help/assets/icons/Alert.svg) | 預覽快速篩選所產生資料的視覺效果。 長條圖和百分比可提供快速篩選結果中整體資料組成部分的分析。 紅色![警報](/help/assets/icons/Alert.svg)表示快速篩選器未傳回資料。 |
| **[!UICONTROL 包含]**<br/>**[!UICONTROL 排除]** | 從下拉式清單![ChevronDown](/help/assets/icons/ChevronDown.svg)中選取是否要從面板中的資料包含或排除快速篩選的結果。 |
| **[!UICONTROL 事件]**<br/>**[!UICONTROL 工作階段]**<br/>**[!UICONTROL 人員]** | 從下拉式清單中選取![V形](/help/assets/icons/ChevronDown.svg)快速篩選的範圍。 |

### 條件區域

條件區域會指定條件（最多三個）。 您可以針對每個條件指定下列專案：

| 元素 | 說明 |
|---|---|
| **[!UICONTROL Dimension]**<br/>**[!UICONTROL 量度]**<br/>**[!UICONTROL 日期範圍]** | 從下拉式清單![ChevronDown](/help/assets/icons/ChevronDown.svg)中選取您要指定維度、量度或日期範圍的條件。 |
| **[!UICONTROL *元件&#x200B;*]** | 條件的元件欄位。 您可以&#x200B;[!UICONTROL *輸入以新增*]&#x200B;元件、從清單中選取元件，或是從元件面板拖放元件。 您只能在條件的元件欄位上拖放類似的元件。 例如，您只能將維度元件從維度條件上的元件面板中拖放。 <br/>您也可以拖放以取代現有元件。<br/>選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從元件欄位中刪除元件。 |
| **[!UICONTROL *運運算元&#x200B;*]** | 元件的運運算元。 如需詳細資訊，請參閱[運運算元](operators.md)。 僅適用於維度和量度。 |
| **[!UICONTROL *值&#x200B;*]** | 條件的值。 根據選取的運運算元，可以從清單中選取值或輸入值。 |
| ![CrossSize75](/help/assets/icons/CrossSize75.svg) | 選取以從快速篩選刪除條件。 |

### 按鈕

| 按鈕 | 說明 |
|---|---|
| **[!UICONTROL 和]**<br/>**[!UICONTROL 或]** | 僅當您定義多個條件時可用。 從條件之間的下拉式清單中選取![V形](/help/assets/icons/ChevronDown.svg)。 選取範圍會決定快速篩選的布林值邏輯。 有三個條件時無法混合邏輯。 布林邏輯為&#x200B;**[!UICONTROL AND]**&#x200B;或&#x200B;**[!UICONTROL OR]**。 |
| ![AddCircle](/help/assets/icons/AddCircle.svg) | 將另一個條件新增至您的快速篩選。 只有當您為快速篩選定義一或兩個條件時，才能使用此按鈕。 |
| **[!UICONTROL 套用]** | 將變更套用至快速篩選。 |
| **[!UICONTROL 開啟產生器]** | 系統會提示您使用&#x200B;**[!UICONTROL 進行確認。確定嗎？]**&#x200B;對話方塊。 如果您選取「**[!UICONTROL 確定]**」，您將無法在「[快速篩選產生器](#quick-filter-builder)」中修改您的篩選。您的快速篩選已重新命名為「**[!UICONTROL 篩選]**」，現在左邊有一個較暗的藍色細條。<br/>一般[篩選產生器](filter-builder.md)會開啟，其中包含&#x200B;**[!UICONTROL 讓此篩選可用於您的所有專案，並將其新增至您的元件清單]**&#x200B;的選項。 <ul><li>如果您選取此選項並選取&#x200B;**[!UICONTROL 套用]**，則篩選器會新增至元件面板中的![篩選器](/help/assets/icons/Segmentation.svg) **[!UICONTROL 篩選器]**&#x200B;元件清單。</li><li>如果您未選取此選項並選取&#x200B;**[!UICONTROL 套用]**，則篩選器會維持為僅限Workspace專案的篩選器。</li></ul> |
| **[!UICONTROL 取消]** | 選取以取消建立或編輯快速篩選。 |

## 快速篩選與篩選

快速篩選器正是其命名方式。 您可以快速內嵌及編輯快速篩選，並立即在面板中檢視效果。

和快速篩選相比，篩選具有以下優點。

* 篩選器可在您的所有Workspace專案中使用
* 篩選器可支援使用巢狀和階層式容器及序列（使用序列篩選器）來增加複雜性。


