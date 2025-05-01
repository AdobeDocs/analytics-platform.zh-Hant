---
title: 如何在Report Builder中篩選維度
description: 說明如何在適用於Customer Journey Analytics的Report Builder中使用篩選器維度
role: User
feature: Report Builder
type: Documentation
exl-id: 5730d5f3-de76-429f-81f5-ebe6b62a9480
solution: Customer Journey Analytics
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 33%

---


# 篩選器維度 

預設情況下，表格中的每個維度項目會傳回該維度的前 10 個項目。

若要變更每個維度會傳回的維度專案：

1. 在資料區塊中選取儲存格。

1. 在&#x200B;**[!UICONTROL 命令]**&#x200B;面板中選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料區塊]**。

1. 選取&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示&#x200B;**[!UICONTROL 維度]**&#x200B;索引標籤。

1. 選取資料表中元件名稱旁的![MoreSmall](/help/assets/icons/MoreSmall.svg)。

   ![省略符號圖示選項。](./assets/image27.png){zoomable="yes"}

1. 在快顯功能表中選取&#x200B;**[!UICONTROL 篩選維度]**&#x200B;以顯示&#x200B;**[!UICONTROL 篩選維度]**&#x200B;窗格。

1. 選取&#x200B;**最受歡迎**&#x200B;或&#x200B;**特定**&#x200B;作為&#x200B;**[!UICONTROL 型別]**。

   ![在[篩選器]維度窗格中選取的特定選項。](./assets/image28.png){zoomable="yes"}

1. 根據所選的[篩選器型別](#filter-type)選取適當的選項。

1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以新增篩選器。

1. Report Builder 會顯示通知，以確認新增的篩選器。

若要顯示已套用的篩選器，可將滑鼠游標停留在維度上。包含已套用篩選器的維度會在維度名稱旁顯示![篩選器](/help/assets/icons/Filter.svg)篩選器圖示。

## 變更篩選器和排序的順序

用來篩選及排序資料區塊的量度旁會出現![向上箭頭](/help/assets/icons/ArrowUp.svg)或![向下箭頭](/help/assets/icons/ArrowDown.svg)。 箭頭的方向會指出量度是以遞增或遞減順序排序。

若要變更排序順序：

- 選取量度旁的![向上鍵](/help/assets/icons/ArrowUp.svg)或![向下鍵](/help/assets/icons/ArrowDown.svg)以切換排序順序。

若要變更用於篩選和排序資料區塊的量度：

1. 將滑鼠游標停留在「表格產生器」中所需的量度元件上，即可顯示更多選項。 

2. 選取![向下箭頭](/help/assets/icons/ArrowDown.svg)作為偏好量度。

   ![資料表產生器和量度。](./assets/image30.png){zoomable="yes"}



## 篩選器類型

有兩種方式篩選維度專案： [最受歡迎](#most-popular)和[特定](#specific-filtering)

### **[!UICONTROL 最熱門]**

**[!UICONTROL 最受歡迎]**&#x200B;選項可讓您根據量度值動態篩選維度專案。 「最受歡迎」會根據量度值傳回排名最高的維度專案。 預設情況下，會出現前 10 個維度項目的清單，從加入資料區塊的第一個量度開始排序。

![最受歡迎的選項。](./assets/image29.png){zoomable="yes"}


#### 「頁面」和「列數」選項

利用&#x200B;**[!UICONTROL 頁面]**&#x200B;和&#x200B;**[!UICONTROL 列數]**&#x200B;欄位，將資料分割成循序群組或頁面。此功能可讓您將排名的列值而不是最高的值提取到您的報表中。 在提取超過50,000列上限的資料時，此外掛程式特別實用。

頁面的預設值為`1`，而列的預設值為`10`。 這些預設值表示每個頁面有10列資料。 頁面 1 會傳回前 10 個項目，而頁面 2 則傳回接下來的 10 個項目，以此類推。

以下表格列出了頁面和列數值以及結果輸出的範例。

| 頁面 | 列 | 輸出 |
|------|--------|----------------------|
| 1 | 10 | 前 10 個項目 |
| 2 | 10 | 項目 11 至 20 |
| 1 | 100 | 前 100 個項目 |
| 2 | 100 | 項目 101 至 200 |
| 2 | 50,000 | 項目 50,001 至 100,000 |

下表列出頁面和列的最小值和最大值。

|       | 最小值 | 最大值 |
|-------|---------------:|---------------:|
| 起始頁面 | 1 | 5千萬 |
| 列數 | 1 | 50,000 |


#### 包括「無值」

在Customer Journey Analytics中，某些維度會收集&#x200B;*沒有值*&#x200B;專案。 **[!UICONTROL 包含「沒有值」]**&#x200B;設定可讓您從報表中排除這些值。 例如，您可以根據產品 SKU 金鑰建立「產品名稱」之類的分類。如果特定產品SKU尚未以其特定「產品名稱」分類設定，其「產品名稱」值會設為&#x200B;*無值*。

預設會選取&#x200B;**[!UICONTROL 包含[沒有值]]**。 取消選取此選項，即可排除包含無值的輸入項。

#### 依「準則」篩選

您可根據是否符合所有準則或任何準則來篩選維度項目。

若要設定篩選條件，請執行下列動作：

1. 從運運算元下拉式選單中選取運運算元。 依預設，已選取&#x200B;**[!UICONTROL 包含片語]**

   ![運運算元清單。](./assets/image31.png){zoomable="yes"}

1. 輸入搜尋字詞。

1. 選取![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增列]**&#x200B;以確認選取範圍並新增另一個條件專案。

1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除條件專案。

您可包括最多 10 個準則項目。

### **[!UICONTROL 特定]**

**[!UICONTROL 特定]**&#x200B;選項可讓您為每個維度建立固定的維度專案清單。 使用&#x200B;**[!UICONTROL 特定]**&#x200B;篩選類型，即可指定包含您的篩選條件的精確維度項目。您可從清單或是儲存格範圍選取項目。

![特定選項和選取的專案。](./assets/image32.png){zoomable="yes"}

#### 從清單

1. 選取&#x200B;**[!UICONTROL 從清單]**&#x200B;選項，即可搜尋和選取維度項目。

   當您選取&#x200B;**從清單**&#x200B;選項時，**[!UICONTROL Dimension專案]**&#x200B;清單會填入維度專案，並依事件數量排序。

   ![從清單選項和可用專案。](./assets/image33.png){zoomable="yes"}

1. 在![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _新增專案_]**&#x200B;中輸入搜尋字詞，以搜尋清單。

1. 若要搜尋未包含在過去90天資料中的專案，請選取&#x200B;**[!UICONTROL 顯示過去6個月的專案]**&#x200B;以擴大搜尋。 在過去6個月的資料載入後，Report Builder會將連結更新為&#x200B;**[!UICONTROL 顯示過去18個月的專案]**。

1. 若要從&#x200B;**[!UICONTROL 選取的專案]**&#x200B;清單中刪除專案，請選取![CrossSize75](/help/assets/icons/CrossSize75.svg)。

1. 若要移動&#x200B;**[!UICONTROL 選取的專案]**&#x200B;清單中的專案，請拖放該專案或選取![MoreSmall](/help/assets/icons/MoreSmall.svg)以顯示內容功能表，並從移動選項中選取。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

Report Builder 會更新清單，以顯示您套用的特定篩選條件。

#### 從儲存格範圍

選取&#x200B;**從儲存格範圍**&#x200B;選項，以選擇包含要比對的維度專案清單的儲存格範圍。

![從儲存格範圍選項和欄位選取一個儲存格範圍。](./assets/image37.png){zoomable="yes"}

當您選取儲存格範圍時，請考量以下限制：

- 範圍必須至少包括一個儲存格。
- 範圍不能超過 50,000 個以上的儲存格。
- 範圍必須為單一連續的列或欄。

您的選取範圍可包含空白儲存格或是裡面的值和特定維度項目不相符的儲存格。


### 快速篩選維度

若要篩選目前未套用篩選器的維度：

1. 選取維度的![V形右側](/help/assets/icons/ChevronRight.svg)。 例如，**[!UICONTROL 互動管道]**。

1. 連按兩下要新增至篩選器的維度專案。 或者，選取一或多個維度專案，並將選取專案拖放至![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**&#x200B;區段。

   ![維度索引標籤和維度清單。](./assets/quickly-filter.png){zoomable="yes"}

