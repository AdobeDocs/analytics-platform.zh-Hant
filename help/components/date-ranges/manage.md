---
title: 管理日期範圍
description: 在 Analysis Workspace 中共用、重新命名或刪除日期範圍。
feature: Calendar
exl-id: 694758c4-d740-4fd7-9fb0-3ff7f6b25a3d
role: User
source-git-commit: 19d2130f4fae736a8553c1a3dd573706d4fb8083
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 9%

---

# 管理日期範圍


您可以從中央的[!UICONTROL 日期範圍]管理介面共用、篩選、標籤、核准、複製、共用和刪除日期範圍，以及將日期範圍標示為我的最愛。 若要管理日期範圍：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 日期範圍]**。


## 日期範圍管理器

日期範圍管理器有下列介面元素：

![日期範圍介面](assets/date-ranges-manager.png)

### 日期範圍清單

日期範圍清單➊會顯示所有日期範圍。 此清單包含下列欄：

| 欄 | 說明 |
| --- | --- | 
| ![星形大綱](/help/assets/icons/StarOutline.svg) | 選取以偏好![星形](/help/assets/icons/Star.svg)或取消偏好![星形大綱](/help/assets/icons/StarOutline.svg)日期範圍。 |
| **[!UICONTROL 標題和說明]** | 若要編輯標題和說明，請選取標題連結，以開啟[日期範圍產生器](/help/components/date-ranges/create.md#date-range-builder)。 |
| **[!UICONTROL 所有者]** | 日期範圍的所有者。 |
| **[!UICONTROL 標記]** | 此日期範圍的標籤。 |
| **[!UICONTROL 共用對象]** | 您與之共用日期範圍的個人或群組。 選取以開啟&#x200B;**[!UICONTROL 共用日期範圍]**&#x200B;對話方塊。 |
| **[!UICONTROL 修改日期]** | 顯示上次修改日期範圍的日期和時間。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定您要顯示哪些欄。

### 動作列

您可以使用動作列對日期範圍進➋行動作。 動作列包含下列動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | 使用[日期範圍產生器](create.md#date-range-builder)新增另一個日期範圍。 |
| ![搜尋](/help/assets/icons/Search.svg) [!UICONTROL *依標題搜尋*] | 當清單中未選取日期範圍時，請使用此搜尋欄位來搜尋日期範圍。 |
| ![標籤](/help/assets/icons/Label.svg) **[!UICONTROL 標籤]** | 標籤選取的日期範圍。 在&#x200B;**[!UICONTROL 標籤日期範圍]**&#x200B;對話方塊中，選取或取消選取所選日期範圍的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選日期範圍的標籤。 |
| ![共用](/help/assets/icons/ShareLight.svg) **[!UICONTROL 共用]** | 共用選取的日期範圍。 在&#x200B;**[!UICONTROL 共用日期範圍]**&#x200B;對話方塊中，您可以![搜尋](/help/assets/icons/Search.svg) *搜尋個人或群組*，也可以選取&#x200B;**[!UICONTROL 組織]**&#x200B;或&#x200B;**[!UICONTROL 群組]**。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選日期範圍的共用詳細資料。 |
| ![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]** | 刪除所選的日期範圍。 系統會提示您進行確認。 |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名單一選取的日期範圍。 選取後，您可以重新命名內嵌日期範圍。 |
| ![核取記號Circle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 核准]** | 核准所選的日期範圍。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 複製所選的日期範圍。 新日期範圍會以相同名稱和尾碼建立（複製） |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出至CSV]** | 將選取的日期範圍匯出至`Date ranges List.csv`檔案。 |

### 作用中的篩選器列

篩選列➌會顯示作用中的篩選（如果有的話）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選器。 如果指定了多個篩選器，請使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有篩選器。

### 篩選器面板

您可以使用&#x200B;**[!UICONTROL 篩選器]**&#x200B;左側面板來篩選日期范➍圍。 篩選器面板會顯示篩選器的型別和遵循該篩選器的日期範圍數。 選取![篩選器](/help/assets/icons/Filter.svg)以切換篩選器面板的顯示。

若要篩選篩選清單：

1. 選取![篩選器](/help/assets/icons/Filter.svg)以開啟「篩選器」面板。 如果您需要更多空間以儲存篩選器清單，可以再選取![篩選器](/help/assets/icons/Filter.svg)以關閉面板。
1. 您可以使用任何可用的[篩選區段](#filter-sections)來篩選日期範圍。

   >[!INFO]
   >
   >*專案*&#x200B;參考[日期範圍清單](#date-ranges-list)中顯示的日期範圍專案。
   > 

#### 篩選區段

{{tagfiltersection}}
{{ownerfiltersection}}
{{otherfiltersfiltersection}}


[日期範圍清單](#date-ranges-list)會根據您的篩選器設定自動更新。 您可以在[作用中的篩選器列](#active-filter-bar)中看到已設定的篩選器。


## 編輯日期範圍

編輯日期範圍有兩個方法：

* 在Workspace專案中使用[元件資訊](/help/components/use-components-in-workspace.md#component-info)圖示。

* 在[[!UICONTROL 日期範圍]清單](#date-ranges-list)中，選取日期範圍的標題。

您使用[日期範圍產生器](/help/components/date-ranges/create.md#date-range-builder)來編輯日期範圍。




使用日期範圍管理器來共用、重新命名或刪除日期範圍。 若要存取日期管理器：

1. 使用您的 AdobeID 憑證登入 [analytics.adobe.com](https://analytics.adobe.com)。
1. 導覽至[!UICONTROL 元件] > [!UICONTROL 日期範圍]。


<!--

## Interface

![Date Ranges with Example range highlighted.](../assets/date-range-ui.png)

The date range manager includes the following options:

* **Add**: Create a new date range. See [create a date range](create.md) for more information.
* **Search by title**: Search for a date range by title. Results are filtered based on text entered here.
* **Filter**: Filter date ranges using the left column. You can filter by custom tag, owner, created by you, your favorites, approved, or shared with you. You can also search for desired filters.
* **Favorite**: Click the ![star](../assets/star.png) icon next to a date range to add it to your favorites.
* **Customize columns**: Click the ![columns](../assets/columns.png) icon to show or hide columns in the date range manager.

Click the checkbox next to one or more date ranges for more options.

* **Tag**: Apply a tag to all selected date ranges. Tags help you organize date ranges, and let you filter them using the left column.
* **Share**: Share a date range to other Experience Cloud users. If you are a product administrator, you can also share to the entire organization or groups. Date ranges that are shared to other users in your organization include a ![shared](../assets/shared.png) icon next to the title.
* **Delete**: Permanently delete the selected date range(s).
* **Rename**: If a single date range is selected, you can change its title.
* **Approve**: If you are a product admin, you can add a stamp of approval to a date range. Approved date ranges inform users in your organization that they are 'official', differentiating them from date ranges created by other users in your organization. Approved date ranges include a ![approved](../assets/approved.png) icon next to the title.
* **Unapprove**: If you are a product admin and select a date range that is already approved, you can unapprove it.
* **Copy**: Create a copy of the selected date range(s). Copying date ranges appends `(Copy)` to the end of the title of the newly copied date range(s).
* **Export to CSV**: Exports all selected date ranges into a CSV file. Columns in the resulting CSV file include all visible columns in the date range manager.
-->