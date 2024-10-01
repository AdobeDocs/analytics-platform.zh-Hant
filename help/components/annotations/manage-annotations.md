---
title: 管理註解
description: 如何在 Workspace 中管理註解。
feature: Components
exl-id: 12f2cc2f-477c-4f16-afdd-b0db84725b32
role: User
source-git-commit: 19d2130f4fae736a8553c1a3dd573706d4fb8083
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 6%

---

# 管理註解

您可以從中央[!UICONTROL 註解]管理介面共用、篩選、標籤、核准、複製、刪除註解以及將註解標示為我的最愛。 若要管理註解：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 註解]**。


>[!NOTE]
>
>您在特定Workspace專案中建立的註解不會顯示在[!UICONTROL 註解]管理員中，除非您讓註解可供所有專案使用。
>

## 註解管理員

註解管理員有下列介面元素：

![註解介面](assets/annotations-manager.png)

### 註解清單

註解清單➊會顯示您擁有的所有註解、已設定至您所有專案範圍的註解，以及已與您共用的註解。 此清單包含下列欄：

| 欄 | 說明 |
| --- | --- | 
| ![星形大綱](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)註釋。 |
| **[!UICONTROL 標題和說明]** | 在註解產生器中提供。若要編輯標題和說明，請選取標題連結 — 開啟[註解產生器](/help/components/annotations/create-annotations.md#annotation-builder)。 共用註解以![共用](/help/assets/icons/ShareLight.svg)表示。 |
| **[!UICONTROL 資料視圖]** | 套用此註解的資料檢視。 |
| **[!UICONTROL 所有者]** | 附註的擁有者。 身為使用者，您只會看見自己擁有的註解或與您共用的註解。 |
| **[!UICONTROL 套用的日期範圍]** | 套用此註解的日期或日期範圍。 |
| **[!UICONTROL 標記]** | 此註解的標籤。 |
| **[!UICONTROL 共用對象]** | 您與之共用註解的個人或群組。 選取以開啟&#x200B;**[!UICONTROL 共用元件]**&#x200B;對話方塊。 |
| **[!UICONTROL 修改日期]** | 顯示上次修改註解的日期和時間。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定您要顯示哪些欄。

### 動作列

您可以使用動作列對註解進➋行動作。 動作列包含下列動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]** | 使用[Annotation Builder](create-annotations.md#annotation-builder)新增另一個附註。 |
| ![搜尋](/help/assets/icons/Search.svg) [!UICONTROL *依標題搜尋*] | 當清單中未選取註解時，請使用此搜尋欄位搜尋註解。 |
| ![標籤](/help/assets/icons/Label.svg) **[!UICONTROL 標籤]** | 標籤選取的註解。 在&#x200B;**[!UICONTROL 標籤元件]**&#x200B;對話方塊中，選取或取消選取所選註解的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選註解的標籤。 |
| ![共用](/help/assets/icons/ShareLight.svg) **[!UICONTROL 共用]** | 共用選取的註解。 在&#x200B;**[!UICONTROL 共用元件]**&#x200B;對話方塊中，您可以![搜尋](/help/assets/icons/Search.svg) *搜尋個人或群組*，也可以選取&#x200B;**[!UICONTROL 組織]**&#x200B;或&#x200B;**[!UICONTROL 群組]**。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選註解的共用詳細資料。 如需詳細資訊，請參閱[共用註解](#share-annotations)。 |
| ![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]** | 刪除選取的註解。 系統會提示您進行確認。 |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名單一選取的註解。 選取後，您可以重新命名註釋內嵌。 |
| ![副本](/help/assets/icons/Copy.svg) **[!UICONTROL 副本]** | 複製選取的註解。 新註解會以相同名稱和字尾建立（複製） |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出至CSV]** | 將註解匯出至`Annotations List.csv`檔案。 |

### 作用中的篩選器列

篩選列➌會顯示作用中的篩選（如果有的話）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選器。 如果指定了多個篩選器，您可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有篩選器。

### 篩選器面板

您可以使用&#x200B;**[!UICONTROL 篩選器]**&#x200B;左側面板來篩選註➍解。 篩選器面板會顯示篩選器的型別以及遵循該篩選器的註釋數量。 選取![篩選器](/help/assets/icons/Filter.svg)以切換篩選器面板的顯示。

若要篩選篩選清單：

1. 選取![篩選器](/help/assets/icons/Filter.svg)以開啟「篩選器」面板。 如果您需要更多空間以儲存篩選器清單，可以再選取![篩選器](/help/assets/icons/Filter.svg)以關閉面板。
1. 您可以使用任何可用的[篩選區段](#filter-sections)來篩選附註。

   >[!INFO]
   >
   >*專案*&#x200B;參考[註解清單](manage-annotations.md#annotations-list)中顯示的註解專案。
   > 

#### 篩選區段

{{tagfiltersection}}
{{dataviewfiltersection}}
{{ownerfiltersection}}
{{daterangefiltersection}}
{{otherfiltersfiltersection}}


[註解清單](manage-annotations.md#annotations-list)會根據您的篩選器設定自動更新。 您可以在[作用中的篩選器列](manage-annotations.md#active-filter-bar)中看到已設定的篩選器。


## 編輯註解

編輯註解有兩個方法：

* 在Workspace專案中使用[元件資訊](/help/components/use-components-in-workspace.md#component-info)圖示。

* 在[[!UICONTROL 註解]清單](#annotations-list)中，選取註解的標題。

您使用[註解產生器](/help/components/annotations/create-annotations.md#annotation-builder)來編輯註解。

## 共用註解

共用註解或使用與您共用的註解時，以下是適用的：

* 您與其他使用者共用的專案中僅限專案的註解會針對這些使用者顯示。 使用者無法編輯或刪除這些僅限專案的註解。
* 如果您儲存註解並直接和使用者共用註解，則該使用者只有在具有管理員許可權的情況下才能編輯和刪除註解。

* 如果專案與您共用，則該專案中建立的註解只會顯示在該專案中。 如果註解直接與您共用，該註解會顯示在可以顯示該註解的所有專案中。

## 註解和時區

所有註解都使用時間戳記建立，但沒有小時或時區資訊。 在報表時間，會使用為面板設定的資料檢視的時區。
