---
title: 管理篩選
description: 瞭解如何管理Customer Journey Analytics中的篩選器
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 97b831d7eee477ee7ef0bf8ae65e6a415d243464
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 4%

---

# 管理篩選


您可以從中央的[!UICONTROL 篩選器]管理介面[共用](filters-share.md)、[篩選器](filters-filter.md)、[標籤](filters-tag.md)、[核准](filters-approve.md)、重新命名、[複製](filters-copy.md)、刪除、匯出篩選器並將篩選器標示為[我的最愛](filters-favorite.md)。 若要管理篩選器：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 篩選器]**。


>[!NOTE]
>
>您在特定Workspace專案中建立的快速篩選不會出現在[!UICONTROL 篩選器]管理員中，除非您讓此篩選器可用於您的所有專案。
>

## 篩選器管理器

「篩選器」管理員具有下列介面元素：

![篩選器介面](assets/filters-manager.png)

### 篩選器清單

篩選器清單會顯➊示您擁有的所有篩選器、已設定至您所有專案的篩選器，以及已與您共用的篩選器。 此清單包含下列欄：

| 欄 | 說明 |
| --- | --- | 
| ![星形大綱](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)篩選器。 檢視[將篩選器標示為我的最愛](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL 標題和說明]** | 若要編輯篩選器，請選取標題連結，這會開啟[篩選器產生器](filter-builder.md)。 共用篩選器以![共用](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 資料視圖]** | 套用此篩選器的資料檢視。 |
| **[!UICONTROL 所有者]** | 篩選的擁有者。 身為使用者，您只會看見自己擁有的篩選器或與您共用的註解。 |
| **[!UICONTROL 標記]** | 此篩選的標籤。 |
| **[!UICONTROL 共用對象]** | 您與之共用篩選器的個人或群組數。 選取以開啟&#x200B;**[!UICONTROL 共用元件]**&#x200B;對話方塊。 如需詳細資訊，請參閱[共用篩選器](filters-share.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改篩選器的日期和時間。 |
| **[!UICONTROL 用於]** | 顯示目前使用篩選器的位置，以及在每個區域使用篩選器的次數。 <p>例如，如果篩選器用於40個專案和2個警示，則此欄的值顯示為&#x200B;[!UICONTROL **42個元件**]。</p> <p>選取此欄中的值，以檢視使用篩選器的位置劃分(例如，[!UICONTROL **專案(40)**]、[!UICONTROL **行動計分卡(2)**])。 此外，您也可以檢視使用篩選器的專案清單。 例如，檢視使用它們的專案清單，選取&#x200B;[!UICONTROL **專案(40)**]&#x200B;連結。</p><p>下列各區顯示在該區中使用的篩選器例項數目：</p>  <ul><li>[!UICONTROL **專案**]<p>包含已在篩選產生器](/help/components/filters/filter-builder.md#)中建立[且可用於所有專案的篩選器。</p></li><li>[!UICONTROL **臨時元件**]<p>包含[建立為快速篩選](/help/components/filters/quick-filters.md)的篩選器，且僅可在單一專案中使用。</p></li><li>[!UICONTROL **已排程的專案**]</li><li>[!UICONTROL **行動計分卡**]</li><li>[!UICONTROL **註解**]</li><li>[!UICONTROL **計算量度**]</li><li>[!UICONTROL **Report Builder**]<p>選取此選項可下載包含下列資料欄的CSV檔案：</p><ul><li>Report Builder名稱</li><li>上次存取</li><li>上次存取IMS使用者ID</li><li>上次存取的使用者名稱</li></ul></li></ul><p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件的使用位置以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊僅供系統管理員使用。</li><li>預設不會顯示&#x200B;**]資料行中使用的[!UICONTROL **。 使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)設定此資料行的顯示。</li><li>此資訊不包括來自API或Data Warehouse的使用情況。</li><li>如果此欄中沒有指定元件的資料，但元件有&#x200B;[!UICONTROL **上次使用日期**]，表示元件可能用於分析而未儲存。</li><li>使用情況資訊從 2023 年 9 月開始提供。</li></ul><p>您可以搭配此資訊使用[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)，協助您追蹤並更清楚瞭解組織中如何使用元件。</p> |
| **[!UICONTROL 上次使用]** | 上次使用篩選器的時間。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定您要顯示哪些欄。

### 動作列

您可以使用動作列對篩選器進➋行動作。 動作列包含下列動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | 使用[篩選器產生器](filter-builder.md)新增另一個篩選器。 |
| ![搜尋](/help/assets/icons/Search.svg) [!UICONTROL *依標題搜尋*] | 當清單中未選取篩選器時，請使用此搜尋欄位搜尋篩選器。 |
| ![標籤](/help/assets/icons/Label.svg) **[!UICONTROL 標籤]** | 標籤選取的篩選器。 在&#x200B;**[!UICONTROL 標籤篩選器]**&#x200B;對話方塊中，選取或取消選取所選篩選器的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選篩選器的標籤。 如需詳細資訊，請參閱[標籤篩選器](/help/components/filters/filters-tag.md)。 |
| ![共用](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共用]** | 共用選取的篩選器。 在&#x200B;**[!UICONTROL 共用篩選器]**&#x200B;對話方塊中，您可以![搜尋](/help/assets/icons/Search.svg) *搜尋個人或群組*，也可以選取&#x200B;**[!UICONTROL 組織]**&#x200B;或&#x200B;**[!UICONTROL 群組]**。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選篩選器的共用詳細資料。 如需詳細資訊，請參閱[共用篩選器](filters-share.md)。 |
| ![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]** | 刪除選取的篩選器。 系統會提示您進行確認。 |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名單一選取的篩選器。 選取後，您可以重新命名內嵌篩選器。 |
| ![核取記號Circle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 核准]** | 核准所選的篩選器。 如需詳細資訊，請參閱[核准篩選器](filters-approve.md)。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 複製選取的篩選器。 已建立具有相同名稱和尾碼`(Copy)`的新篩選器。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出至CSV]** | 將篩選器匯出至`Filters List.csv`檔案。 |

### 作用中的篩選器列

篩選器列會顯➌示從篩選器面板套用至篩選器清單（如果有的話）的作用中篩選器。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選器。 如果指定了多個篩選器，您可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有篩選器。

### 篩選器面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選篩選器清單。 篩選器面板會顯示篩選器的型別，以及遵循特定篩選器的篩選器數目。 選取![篩選器](/help/assets/icons/Filter.svg)以切換篩選器面板的顯示。

如需詳細資訊，請參閱[篩選篩選清單](filters-filter.md)。
