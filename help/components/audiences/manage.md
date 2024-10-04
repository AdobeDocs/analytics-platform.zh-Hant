---
title: 瞭解如何管理在Customer Journey Analytics中建立的對象
description: 了解如何在 Customer Journey Analytics 中管理客群
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
feature: Audiences
role: User
source-git-commit: 8676497c9341e3ff74d1b82ca79bc1e73caf514f
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 20%

---

# 管理客群

可以使用&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 對象]**&#x200B;在Customer Journey Analytics中管理對象。

管理先前建立的對象可讓您：

* 為自動客群重新整理/更新進行&#x200B;**排程或取消排程**。 排程的最長到期時間為 1 年。
* 在客群更新排程快過期時，**續訂該排程。**。系統處理即將過期客群的方法與即將過期的排程報告相似，管理員會在排程過期前的一個月收到電子郵件。
* 檢視&#x200B;**重新整理間隔**&#x200B;和上次更新對象的時間&#x200B;****
* 深入瞭解從Customer Journey Analytics產生對象&#x200B;**所花費的**&#x200B;時間。 以及讓對象出現在即時客戶平台以供啟動所需的時間。
* 檢視Customer Journey Analytics中的對象是否正由Real-time Customer Platform **主動使用**。 或（理想情況下）任何消耗Customer Journey Analytics所建立對象的Experience Platform應用程式。

如果您有[對象檢視](/help/technotes/access-control.md#user-level-access)存取權，則可以檢視對象。 如果您有[對象建立](/help/technotes/access-control.md#user-level-access)存取權，您可以編輯和刪除對象。 [對象清單](#audiences-list)會顯示對象。

## 對象清單

「對象」清單會顯➊示下列專案欄：

| 欄 | 說明 |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 選取一或多個對象時，「對象」介面的底部會出現一個藍色動作列。 如需詳細資訊，請參閱[動作](#actions)。 |
| **[!UICONTROL 標題和說明]** | 您在建立對象時輸入的標題和說明。 |
| **[!UICONTROL 資料檢視]** | 建立此客群的資料檢視。 |
| **[!UICONTROL 客群規模]** | 此客群的總人數。 |
| **[!UICONTROL 所有者]** | 對象的所有者 — 建立對象的人。 |
| **[!UICONTROL 重新整理頻率]** | 建立對象時設定的重新整理間隔。 |
| **[!UICONTROL 標記]** | 套用到此客群的任何標記。 |
| **[!UICONTROL 發佈狀態]** | 可以顯示![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 就緒]**、![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 進行中]**&#x200B;或![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 錯誤]**。 |
| **[!UICONTROL 上次重新整理時間]** | 上次重新整理對象的時間戳記。 |
| **[!UICONTROL 上次修改日期]** | 上次編輯或修改對象的時間戳記。 |

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)來設定要顯示哪些欄。 使用![搜尋](/help/assets/icons/Search.svg)來搜尋對象。

若要編輯對象：

1. 選取對象標題。 使用&#x200B;**[!UICONTROL 編輯對象專案]**&#x200B;對話方塊來更新對象。 如需詳細資訊，請參閱[對象產生器](publish.md#audience-builder)。

1. 選取&#x200B;**[!UICONTROL 重新發佈]**&#x200B;以重新發佈對象。


## 動作

以下是「排程專案管理員」中的常見動作。 您可以從快顯功能表中選取動作：

| 圖示 | 動作 | 說明 |
|:---:|---|---|
| ![標籤](/help/assets/icons/Labels.svg) | **[!UICONTROL 標記]** | 標籤選取的對象。 在&#x200B;**[!UICONTROL 更新標籤： *對象名稱&#x200B;*]**對話方塊中，從下拉式選單中選取標籤，或輸入一或多個新標籤。 選取**[!UICONTROL 儲存&#x200B;]**以儲存。 |
| ![刪除](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除選取的對象。 |
| ![編輯](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名選取的對象。 使用&#x200B;**[!UICONTROL 重新命名： *對象名稱&#x200B;*]**對話方塊來重新命名對象，並選取**[!UICONTROL 儲存&#x200B;]**以儲存。 |

選取一或多個排程專案時，可從藍色動作列執行下列動作。

| 圖示 | 動作 | 說明 |
|:---:|---|---|
| ![關閉](/help/assets/icons/Close.svg) | 已選取&#x200B;**[!UICONTROL *x *]** | 選取「 」以取消選取您選取的對象。 |
| ![刪除](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除選取的對象。 |
| ![檔案CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出至 CSV]** | 將選取的對象匯出至名為`audiences.csv`的檔案。 |

## 篩選器

您可以使用篩選器面板來篩選[對象清單](#audiences-list)➋。 若要顯示或隱藏篩選器面板，請使用![篩選器](/help/assets/icons/Filter.svg)。

「濾鏡」面板由下列區段組成。

### 資料視圖

| 資料視圖 | 說明 |
|---|---|
| ![擁有者](/help/components/audiences/assets/audiences-filter-dataviews.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;區段可讓您篩選資料檢視。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg)來搜尋要用來篩選的資料檢視。</li><li>您可以選取多個資料檢視。</li></ul> |

### 擁有者

| 所有者 | 說明 |
|---|---|
| ![擁有者](/help/components/audiences/assets/audiences-filter-owner.png){width="300"} | **[!UICONTROL 所有者]**&#x200B;區段可讓您依所有者篩選。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg)來搜尋要用來篩選的所有者。</li><li>您可以選取多個擁有者。 </li></ul> |

## 重新整理頻率

| 重新整理頻率 | 說明 |
|---|---|
| ![重新整理頻率](/help/components/audiences/assets/audiences-filter-refreshfrequency.png){width="300"} | **[!UICONTROL 重新整理頻率]**&#x200B;區段可讓您篩選重新整理頻率。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg)來搜尋要用來篩選的重新整理頻率。</li><li>只有為[對象清單](#audiences-list)中的對象<br/>定義的重新整理頻率才會顯示為可用選項。</li></ul> |


### 標記

| 標記 | 說明 |
|---|---|
| ![標記](/help/components/audiences/assets/audiences-filter-tags.png){width="300"} | **[!UICONTROL 標籤]**&#x200B;區段可讓您依標籤篩選。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg)來搜尋要用來篩選的標籤。 |
