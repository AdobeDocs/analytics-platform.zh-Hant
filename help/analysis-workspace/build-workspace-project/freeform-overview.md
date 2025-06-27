---
description: 瞭解如何在Analysis Workspace中使用專案。 使用專案管理員管理（建立、刪除、移動、共用、核准、釘選、複製和標籤）專案。
keywords: Analysis Workspace
title: 專案概觀
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 93%

---

# 專案概觀

Workspace 專案可讓您合併面板、視覺效果和元件，以進行分析並與貴組織的任何人共用。在開始第一個專案之前，請先了解如何存取、瀏覽及管理您的專案。

若要存取 Customer Journey Analytics 中的專案，請選取「**[!UICONTROL Workspace]**」。**[!UICONTROL 專案]**&#x200B;管理員會列出您擁有的所有專案或與您共用的專案。含有專案清單的專案管理員也是 Customer Journey Analytics 的預設登陸頁面，除非您在「偏好設定」中另有設定。

![專案登陸頁會顯示專案清單。](assets/projects.png)


## 標題區域

您可以從標題區域➊中建立專案、建立資料夾、編輯偏好設定，以及顯示或隱藏具有其他圖磚的面板。

* 若要顯示或隱藏左側面板以便您在「**[!UICONTROL 專案]**」和「**[!UICONTROL 了解]**」之間選取，您可選取「![邊欄](/help/assets/icons/Rail.svg)」。
* 標題會顯示專案，還可選擇新增至您已選取資料夾的路徑。例如，[!UICONTROL 專案] > **[!UICONTROL 公司資料夾]**。您可以選取個別子資料夾部分，以直接前往特定資料夾。
* 若要顯示 [**[!UICONTROL 空白專案]**](create-projects.md)， [**[!UICONTROL 空白行動計分卡]**](/help/mobile-app/create-scorecard.md)， [**[!UICONTROL 引導式分析]**](/help/guided-analysis/overview.md)， **[!UICONTROL 開啟文件]** 和 **[!UICONTROL 開啟發行說明]**&#x200B;的圖磚，選取 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 「顯示更多」]**。若要隱藏有圖磚的區域，請選取 ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 「顯示較少」]**。
* 根據您的選取來顯示 (使用[顯示選擇器](#show-selector))，您可以編輯偏好設定並對&#x200B;**[!UICONTROL 專案]**&#x200B;中目前可見到的資料夾執行動作：

  | 動作 | 說明 |
  |---|---|
  | **[!UICONTROL 建立專案]** | 選取以[建立新專案](create-projects.md)。 |
  | **[!UICONTROL 建立資料夾]** | 選取以[建立新專案](workspace-folders/create-folders.md)。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 編輯偏好設定]** | [編輯偏好設定](/help/analysis-workspace/user-preferences.md)適用於您所有的專案。當階層連結導致空間有限時，此動作是「![更多](/help/assets/icons/More.svg)」子選單中的一部分。 |
  | **[!UICONTROL 新增專案]** | 選取以[新增專案](workspace-folders/add-projects.md)至目的資料夾。當階層連結導致空間有限時，此動作是「![更多](/help/assets/icons/More.svg)」子選單中的一部分。 |
  | **[!UICONTROL 重新命名資料夾]** | [重新命名](workspace-folders/manage-folders.md#rename-folders)目前資料夾。 |
  | **[!UICONTROL 移動資料夾]** | [移動](workspace-folders/manage-folders.md#move-folders)目前資料夾。 |
  | **[!UICONTROL 刪除資料夾]** | [刪除](workspace-folders/manage-folders.md#delete-folders)目前資料夾。 |




## 專案清單


專案清單➋會顯示您所擁有以及已經與您共用的所有專案。 清單有以下欄位：

| 欄 | 說明 |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 當選取一個或多個專案時，專案介面底部會出現一個藍色操作欄。如需詳細資訊，請參閱「[動作](#actions)」。 |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以將專案設為我的最愛 ![Star](/help/assets/icons/Star.svg) 或取消我的最愛 ![StarOutline](/help/assets/icons/StarOutline.svg)。 |
| **[!UICONTROL 標題和說明]** | 若要編輯專案，請選取標題連結，即會開啟 [Workspace 專案](/help/analysis-workspace/home.md)。與您共用的專案會以「![共用](/help/assets/icons/ShareAlt.svg)」來表示。選取 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 以顯示快顯選單，其中含有專案的更多詳細資訊。選取「![更多](/help/assets/icons/More.svg)」以開啟含有動作的內容選單。如需詳細資訊，請參閱「[動作](#actions)」。 |
| **[!UICONTROL 類型]** | Workspace 專案、![FolderUser](/help/assets/icons/FolderUser.svg) 資料夾或[行動計分卡](/help/mobile-app/home.md)。 |
| **[!UICONTROL 標記]** | 套用至專案的標記。 |
| **[!UICONTROL 已排程]** | 是否為專案排程以透過電子郵件發送給收件者。選項包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 開啟]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 關閉]**。請參閱「[發送專案資料給其他人](/help/analysis-workspace/export/t-schedule-report.md)」。 |
| **[!UICONTROL 共用連結 (任何人)]** | 無論是否與任何人共用專案，即使是沒有 Analysis Workspace 存取權的人都可以共用。選項包括 ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 使用中]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 非使用中]**。如需更多資訊，請參閱[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的「[與任何人共用專案 (無需登入)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)」。 |
| **[!UICONTROL 專案角色]** | 您在專案中的角色。選項包括：編輯、複製、檢視。請參閱「[專案角色](/help/analysis-workspace/curate-share/curate.md)」，了解更多資訊。 |
| **[!UICONTROL 資料檢視]** | 與專案相關聯的資料檢視。 |
| **[!UICONTROL 所有者]** | 建立此專案的人 (您或與您共用專案的人)。 |
| **[!UICONTROL 共用對象]** | 已與其共用該專案的使用者。 |
| **[!UICONTROL 上次修改日期]** | 上次修改專案的日期和時間。 |
| **[!UICONTROL 上次開啟]** | 上次開啟專案的日期和時間。 |
| **[!UICONTROL 專案 ID]** | 專案 ID。 |
| **[!UICONTROL 最大日期範圍]** | 專案中任何面板或視覺效果的最長日期範圍。 |
| **[!UICONTROL 查詢數]** | 專案中使用的查詢總數。 |
| **[!UICONTROL 位置]** | 專案所在的資料夾。 |

將滑鼠停留在任何資料欄標題上，即可顯示 ![ChevronDown](/help/assets/icons/ChevronDown.svg) 並從內容選單中選取：

* **[!UICONTROL 升序排列]**
* **[!UICONTROL 降序排序]**
* **[!UICONTROL 調整資料欄大小]**&#x200B;會出現一條藍線，可幫助您調整資料欄的大小。

### 動作

您可以使用內容選單 ![更多的](/help/assets/icons/More.svg) 或藍色動作列，對一個或多個專案執行動作。

| 圖示 | 動作 | 說明 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *已選取]** | 取消選擇您已選的專案和資料夾，並刪除藍色動作列。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除一個或多個專案或資料夾。系統會提示您進行確認。 |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共用]** | 共用專案。請參閱「[共用專案](/help/analysis-workspace/curate-share/share-projects.md)」了解更多。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名專案。開啟&#x200B;**[!UICONTROL 重新命名：*專案名稱對話框&#x200B;*]**。輸入新名稱並選取「**[!UICONTROL 儲存&#x200B;]**」。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 複製]** | 複製一個或多個專案。專案會獲得相同的名稱和字尾 `(Copy)`。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL 釘選]**&#x200B;或&#x200B;**[!UICONTROL 取消釘選]** | 釘選或取消釘選一個或多個專案或資料夾。已釘選的專案和資料夾會出現在清單上方，並忽略您指定的排序順序。 |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 向上移動]** | 在專案清單中，將已釘選的專案或資料夾向上移動。 |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 向下移動]** | 在專案清單中，將已釘選的專案或資料夾向下移動。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標記一個或多個專案或資料夾。**[!UICONTROL 標記元件]**&#x200B;對話框會顯示，即可選取一個或多個標記。選取「**[!UICONTROL 儲存]**」，以儲存所選專案或資料夾的標記。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 核准]**&#x200B;或&#x200B;**[!UICONTROL 取消核准]** | 核准或不核准專案。只有管&#x200B;&#x200B;理員可以核准專案。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出 CSV]** | 將選取的專案匯出為名為 `Project List.csv` 的 CSV 檔案。 |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL 新增專案]** | 將一個或多個專案新增至選取的資料夾。在「**[!UICONTROL 新增專案]**」中，您可以選取一個或多個專案。選取「**[!UICONTROL 新增]**」，將專案新增至資料夾。請參閱「[將項目新增至資料夾](workspace-folders/add-projects.md#from-inside-a-folder)」了解更多。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移動至]** | 將一個或多個選取的專案移動至資料夾。在「**[!UICONTROL 選取資料夾]**」中，選取要將選取的專案移往的資料夾，然後選取「**[!UICONTROL 移動]**」。請參閱「[將項目新增至資料夾](workspace-folders/add-projects.md#from-the-project-list)」了解更多。 |



## 顯示選擇器

您可以使用&#x200B;**[!UICONTROL Show]**&#x200B;選取器➌來切換專案介面的外觀。 **[!UICONTROL 顯示]**&#x200B;選擇器會定義[標題區域](#title-area)中可用的選項，以及[專案清單](#project-list)中顯示的資料欄。

* 若要變更[標題區域](#title-area)中可用的選項，請選取&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 所有專案]**&#x200B;或&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 資料夾和專案]**。

* 若要定義在[專案清單](#project-list)中顯示哪些資料欄，請選取![ColumnSetting](/help/assets/icons/ColumnSetting.svg)，然後從「**[!UICONTROL 自訂表格]**」對話框選取或取消選取資料欄。選取「**[!UICONTROL 套用]**」以套用自訂。若要了解資料欄的更多資訊，請參閱「[專案清單](#project-list)」。

## 篩選面板

您可以使用篩選面板➍來篩選[專案清單](#project-list)中的專案和資料夾。 若要顯示或隱藏篩選器面板，請使用「![篩選器](/help/assets/icons/Filter.svg)」。

篩選器面板由以下部分組成。

### 標記

| 標記 | 說明 |
|---|---|
| ![標記](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | 「**[!UICONTROL 標記]**」部分可讓您按標記進行篩選。 <ul><li>您可以使用 ![搜尋](/help/assets/icons/Search.svg) *「搜尋標記」*&#x200B;來搜尋您想要用來篩選的標記。</li><li>您可以選取多個標記。適用標記取決於篩在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**2︎⃣**：目前篩選器產生的專案適用的標記數量。</li><li>7︎⃣：與特定標記相關聯的專案數量。</li></ul></li></ul> |


### 資料檢視

| 資料檢視 | 說明 |
|---|---|
| ![資料檢視](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;部分可讓您篩選資料檢視。 <ul><li>您可以使用 ![搜尋](/help/assets/icons/Search.svg) *「搜尋資料檢視」*&#x200B;來搜尋您想要用來篩選的資料檢視。</li><li>您可以選取多個資料檢視。適用資料檢視取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**3︎⃣**：目前篩選器產生的專案適用的資料檢視數量。</li><li>4︎⃣：與特定資料檢視相關聯的專案數量。</li></ul></li></ul> |


### 所有者

| 所有者 | 說明 |
|---|---|
| ![所有者](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」部分可讓您篩選所有者。 <ul><li>您可使用 ![搜尋](/help/assets/icons/Search.svg) *「搜尋所有者」*&#x200B;來搜尋您想要用來篩選的所有者。</li><li>您可以選取多個所有者。適用的所有者取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**3︎⃣**：目前篩選器產生的專案適用的所有者數量。</li><li>4︎⃣：與特定所有者相關聯的專案數量。</li></ul></li></ul> |


### 類型

| 類型 | 說明 |
|---|---|
| ![Type](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | **[!UICONTROL 類型]**&#x200B;部分可讓您依照專案或資料夾的類型進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 資料夾]**。</li><li>**[!UICONTROL Analysis Workspace 專案]**</li><li>**[!UICONTROL Mobile 計分卡]**</li></ul> <li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**5︎⃣**：目前篩選器產生的專案適用的其他篩選器數量。</li><li>4︎⃣：與特定其他篩選器相關聯的專案數量。</li></ul></li></ul> |


### 其他篩選器

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} |  **[!UICONTROL 其他篩選器]**&#x200B;部分可讓您根據其他預先定義的篩選器進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的內容取決於您的角色和權限。</li><li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**5︎⃣**：目前篩選器產生的專案適用的其他篩選器數量。</li><li>4︎⃣：與特定其他篩選器相關聯的專案數量。</li></ul></li></ul> |

## 搜尋

您使用[搜尋]區域➎，使用![搜尋](/help/assets/icons/Search.svg)欄位來搜尋專案和資料夾。 開始輸入後，[專案清單](#project-list)會自動篩選您的搜尋輸入。

搜尋區域也會顯示從篩選器面板套用的篩選器。

* 若要移除篩選器，請在篩選器中選取 ![CrossSize75](/help/assets/icons/CrossSize75.svg)。
* 若要刪除所有篩選器，請選取「全部清除」。

如果空間受限而無法顯示個別篩選器，您可以看到&#x200B;**[!UICONTROL 按篩選器 *x* 進行劃分]**。

* 若要移除篩選器：

   1. 使用上方的 **[!UICONTROL *x *篩選器]**![ChevronDown](/help/assets/icons/ChevronDown.svg) 來開啟內容選單，列出篩選器類型和個別篩選器。
   1. 使用 ![CrossSize75](/help/assets/icons/CrossSize75.svg) 來移除篩選器。


<!--

The Projects page contains the following information: 

>[!NOTE]
>
>Some columns are not displayed by default. To customize the columns you see, click the **Customize table** icon ![Customize table](assets/projects-page-customize-columns-icon.png).

|  Element  | Description  |
|---|---|
| [Edit preferences](/help/analysis-workspace/user-preferences.md) | Manage settings for Analysis Workspace and its related components for all new projects or panels that you create.  |
| [Create folder](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)  | Add a new folder or subfolder to the list of projects and folders. |
| [Create project](/help/analysis-workspace/build-workspace-project/create-projects.md)  | Start a new project from scratch.  |
|  Show more  |Reveals options for creating a blank project or mobile scorecard, [viewing training tutorials](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html), or [viewing release notes](/help/release-notes/latest.md).  |
| Show Folders & Projects| Choose whether to show the folder structure of projects. For more information, see [About Folders in Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
|  Customize table (icon)  | Allows you to customize the information that shows for each project on the Projects page.  |
|  Name  | Name of the Workspace project.  |
| Type | Indicates whether this is a Workspace Project, a folder, or a [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
|  Tags  |Tags that were applied to the project.  |
| Scheduled | Indicates whether projects are scheduled to be emailed to recipients on a schedule. See [Send project data to others](/help/analysis-workspace/export/t-schedule-report.md). |
| Shared link (anyone) | Projects can be shared with anyone--even with people who don't have access to Analysis Workspace. This column shows whether projects have been shared in this way. See [Share a project with anyone (no login required)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [Share projects](/help/analysis-workspace/curate-share/share-projects.md) for more information. |
| Data view | The data view that the project is associated with. |
| [Project Role](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Indicates your role for the project - owners, edit, duplicate, view. |
|  Owner  | The person who created this project (either you or someone who shared the project with you.)  |
|  Shared with  | Users that the project has been shared with.  |
|  Last Modified  | Date and time when the project was last modified.  |
|  Last Opened  | Date and time when the project was last opened.  |
|  Project ID  | The ID of the project.  |
|  Longest Date Range  | The longest date range of the project.  |
|  Number of Queries  | The total number of queries contained in the project.  |
|  Location  | The folder where the project resides.  |

## Menu bar {#menu-bar}

Within a project, the menu provides options for managing your project, adding components, finding help, and more. Each menu option can also be accessed by keyboard [shortcuts](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![New Project options including the Project, Edit, Insert, Components, Share, and Help options.](assets/menu.png)

|  Menu item  | Description  |
|---|---|
|  Project  | Includes common actions for project management, including New, Open, Save, and Save As. You can also refresh the entire project to retrieve the most recent data and definitions by clicking Refresh Project. [Download project data](/help/analysis-workspace/export/download-send.md) options enable you to export data from Workspace. **Project Info & Settings** (see below) offers many options for managing your project.  |
|  Edit  | Undo or redo your last action. Clear All will reset your project to a blank starting point. |
|  Insert  | Insert new panels or visualizations from this menu. You can also insert new panels and visualizations from the left panel.  |
|  [Components](/help/components/overview.md)  | Create new segments, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
|  [Share](/help/analysis-workspace/curate-share/send-schedule-files.md)  | Curate, share and schedule PDF/CSV projects to recipients in your organization.  |
|  Help  | Access help documentation, videos, and the Analytics [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Manage the visibility of Workspace tips as well as the [debugger](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/apis/using-analysis-workspace-to-build-api-2-requests). Find details about Workspace and factors that impact project [performance](/help/technotes/optimizing-performance.md).  |
|  Share button or Owner  | If you are in an Own or Edit for the project, the Share button in the top-right gives you one-click access to manage your project recipients. If you are in a Duplicate or View role for the project, you will see the project owner's name. |

### Project Info & Settings {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** provides project-level information on the currently active project.

![The Project Info & Settings window.](assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project Name  | The name given to the project. You can double-click the name to edit it.  |
|  Created By  | Project owner name  |
|  Last Modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances in project  | Specifies whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |

## Left panel

Within a project, various icons are available in the left panel, and each represents important parts of a project:

* [Panels](/help/analysis-workspace/c-panels/panels.md) ![panels icon](assets/panels-icon.png)

* [Visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualizations icon](assets/visualizations-icon.png)

* [Components](/help/components/overview.md)![components icon](assets/components-icon.png)

* [Data dictionary](/help/components/data-dictionary/data-dictionary-overview.md)![data dictionary icon](assets/data-dictionary-icon.png)

* [Table of contents](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![toc icon](assets/toc-icon.png)

Components (Dimensions, Metrics, Segments, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

![The components relating to the active panel data view for Cross-Industry Demo Data data view.](assets/left-rail.png)

## Project canvas {#canvas}

The project canvas is where you bring together panels, tables, visualizations, and components to build your analysis. A project can contain many panels, and each panel can contain many tables and visualizations.

Panels are helpful when you want to organize your projects according to time periods, data views, or analysis use case. The active panel will have a blue border around it, and determines what components are available in the left panel.

Depending on the starting point you chose for your projects, you will either have a [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) or a [blank panel](/help/analysis-workspace/c-panels/blank-panel.md) in the canvas to begin with. The quickest way to start analyzing is to select one or many components and simply drag & drop them into the project canvas. A table of data will automatically be rendered for you. [Learn more](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) about the different options for building a table, or leverage our [training tutorial](/help/analysis-workspace/home.md) for more guidance on building your first project.

![A Freeform Table for the project.](assets/canvas.png)

## Project Manager {#manager}

Analysis Workspace projects can be managed under **Analytics > Components >  Projects**. The Project Manager shows the projects that a specific user created. You can transfer project ownership to a new user under Admin > Analytics Users & Assets > Transfer Assets.

In Projects Manager, you can add, tag, share, duplicate/copy, and more. Search for a project in the search bar or by using the filter options in the left panel. You can filter by tag, owners, project type and more.

![Project Manager Tags search field and Title search field.](assets/project-manager.png)

The following are common actions in the Projects manager, and can be taken on one or many projects at once:

|  Action  | Description  |
|---|---|
|  Add  | Create a new project from scratch.  |
|  Tag or Approve  | Choose "Tag" or "Approve" to organize your projects and make them easier to search for.  |
|  [Share](/help/analysis-workspace/curate-share/share-projects.md)  | Make a project available to other Analysis Workspace users in your organization.  |
|  Delete  | Delete your project.  |
|  Rename  | Edit the name of your project.  |
|  Copy  | Create a duplicate copy of your project. This creates a new project and project ID. Any shares or schedules tied to the original project will not be copied. |
|  Export to CSV  | Download your project as a CSV file, which includes plain-text data.  |

-->

