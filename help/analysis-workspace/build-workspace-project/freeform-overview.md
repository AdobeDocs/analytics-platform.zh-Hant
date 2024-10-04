---
description: Workspace 專案與選單列和設定概觀
keywords: Analysis Workspace
title: 專案概觀
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '1628'
ht-degree: 7%

---

# 專案概觀

Workspace專案可讓您合併面板、視覺效果和元件，以進行分析並與貴組織的任何人分享。 在開始第一個專案之前，請先瞭解如何存取、導覽及管理您的專案。

若要存取Customer Journey Analytics中的專案，請選取&#x200B;**[!UICONTROL Workspace]**。  **[!UICONTROL 專案]**&#x200B;管理員會列出您擁有的所有專案或與您共用的專案。 具有專案清單的專案管理員也是Customer Journey Analytics的預設登陸頁面，除非您另外在「偏好設定」中設定。

![顯示專案清單的專案登陸頁面。](assets/projects.png)


## 標題區域

在標題區域中，您➊可以建立專案、建立資料夾、編輯您的偏好設定，以及顯示或隱藏具有其他圖磚的面板。

* 若要顯示或隱藏可讓您在&#x200B;**[!UICONTROL 專案]**&#x200B;與&#x200B;**[!UICONTROL 學習]**&#x200B;之間選取的左側面板，請選取![邊欄](/help/assets/icons/Rail.svg)。
* 標題顯示專案，並可選擇新增您已選取資料夾的路徑。 例如[!UICONTROL 專案] > **[!UICONTROL 公司資料夾]**。 您可以選取個別子資料夾零件，直接移至特定資料夾。
* 若要顯示[**[!UICONTROL 空白專案]**](create-projects.md)的圖磚，[**[!UICONTROL 空白行動計分卡]**](/help/mobile-app/create-scorecard.md)，[**[!UICONTROL 引導式分析]**](/help/guided-analysis/overview.md)，**[!UICONTROL 開啟檔案]**&#x200B;和&#x200B;**[!UICONTROL 開啟發行說明]**，請選取![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 顯示更多]**。 若要隱藏有圖磚的區域，請選取![V形向下](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 顯示更少]**。
* 根據您選取要顯示的內容，使用[顯示選取器](#show-selector)，您可以編輯偏好設定並對&#x200B;**[!UICONTROL 專案]**&#x200B;中顯示的目前資料夾執行動作：

  | 動作 | 說明 |
  |---|---|
  | **[!UICONTROL 建立專案]** | 選取以[建立新專案](create-projects.md)。 |
  | **[!UICONTROL 建立資料夾]** | 選取以[建立新資料夾](workspace-folders/create-folders.md)。 |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL 編輯偏好設定]** | [編輯您所有專案的偏好設定](/help/analysis-workspace/user-preferences.md)。 當階層連結導致空間受限時，此動作會成為![更多](/help/assets/icons/More.svg)子功能表的一部分。 |
  | **[!UICONTROL 新增專案]** | 選取以[將專案](workspace-folders/add-projects.md)新增到目前的資料夾。 當階層連結導致空間受限時，此動作會成為![更多](/help/assets/icons/More.svg)子功能表的一部分。 |
  | **[!UICONTROL 重新命名資料夾]** | [重新命名](workspace-folders/manage-folders.md#rename-folders)目前的資料夾。 |
  | **[!UICONTROL 行動資料夾]** | [移動](workspace-folders/manage-folders.md#move-folders)目前的資料夾。 |
  | **[!UICONTROL 刪除資料夾]** | [刪除](workspace-folders/manage-folders.md#delete-folders)目前的資料夾。 |




## 專案清單


專案清單➋會顯示您所擁有以及已經與您共用的所有專案。 此清單包含下列欄：

| 欄 | 說明 |
| --- | --- | 
| ![SelectBox](/help/assets/icons/SelectBox.svg) | 選取一或多個專案時，Project介面的底部會出現一個藍色動作列。 如需詳細資訊，請參閱[動作](#actions)。 |
| ![星形大綱](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)專案。 |
| **[!UICONTROL 標題和說明]** | 若要編輯專案，請選取標題連結，以開啟[Workspace專案](/help/analysis-workspace/home.md)。 與您共用的專案以![共用](/help/assets/icons/ShareAlt.svg)表示。 選取![資訊大綱](/help/assets/icons/InfoOutline.svg)以顯示包含專案詳細資訊的快顯功能表。 選取![更多](/help/assets/icons/More.svg)以開啟包含動作的內容功能表。 如需詳細資訊，請參閱[動作](#actions)。 |
| **[!UICONTROL 類型]** | Workspace專案、![FolderUser](/help/assets/icons/FolderUser.svg)資料夾或[行動計分卡](https://experienceleague.adobe.com/en/docs/analytics/analyze/mobapp/home)。 |
| **[!UICONTROL 標記]** | 套用至專案的標籤。 |
| 已排程 | 專案是否已排程以電子郵件傳送給收件者。 選項為![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL On]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Off]**。 請參閱[將專案資料傳送給其他人](/help/analysis-workspace/export/t-schedule-report.md)。 |
| **[!UICONTROL 共用連結（任何人）]** | 專案是否會與任何人共用，即使對方無權存取Analysis Workspace。 選項為![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL 作用中]**&#x200B;或![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 非作用中]**。 如需詳細資訊，請參閱[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的[與任何人共用專案（不需要登入）](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)。 |
| **[!UICONTROL 專案角色]** | 您在專案中的角色。 選項包括：編輯、複製、檢視。 如需詳細資訊，請參閱[專案角色](/help/analysis-workspace/curate-share/curate.md)。 |
| **[!UICONTROL 資料視圖]** | 與專案相關聯的資料檢視。 |
| **[!UICONTROL 所有者]** | 建立此專案的人 (您或與您共用專案的人)。 |
| **[!UICONTROL 共用對象]** | 已共用專案的使用者。 |
| **[!UICONTROL 上次修改日期]** | 上次修改專案的日期和時間。 |
| **[!UICONTROL 上次開啟]** | 專案上次開啟的日期和時間。 |
| **[!UICONTROL 專案 ID]** | 專案的ID。 |
| **[!UICONTROL 最大日期範圍]** | 專案中任何面板或視覺效果的最長日期範圍。 |
| **[!UICONTROL 查詢數]** | 專案中包含的查詢總數。 |
| **[!UICONTROL 位置]** | 專案所在的資料夾。 |

將滑鼠懸停在任何欄標題上以顯示![V形向下](/help/assets/icons/ChevronDown.svg)，並從內容功能表選取：

* **[!UICONTROL 遞增排序]**
* **[!UICONTROL 遞減排序]**
* **[!UICONTROL 調整資料行大小]**。 會顯示一條藍線，協助您調整欄大小。

### 動作

您可以使用內容功能表![More](/help/assets/icons/More.svg)或藍色動作列，對一或多個專案執行動作。

| 圖示 | 動作 | 說明 |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | 已選取&#x200B;**[!UICONTROL *x *]** | 取消選取您選取的專案和資料夾，並移除藍色動作列。 |
| ![刪除](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除一或多個專案或資料夾。 系統會提示您進行確認。 |
| ![共用](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共用]** | 共用專案。 如需詳細資訊，請參閱[共用專案](/help/analysis-workspace/curate-share/share-projects.md)。 |
| ![編輯](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名專案。 開啟&#x200B;**[!UICONTROL 重新命名： *專案名稱對話方塊&#x200B;*]**。 輸入新名稱並選取**[!UICONTROL 儲存&#x200B;]**。 |
| ![副本](/help/assets/icons/Copy.svg) | **[!UICONTROL 副本]** | 複製一或多個專案。 專案確實有相同的名稱和尾碼`(Copy)`。 |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL 釘選]**&#x200B;或&#x200B;**[!UICONTROL 取消釘選]** | 釘選或取消釘選一個或多個專案或資料夾。 釘選專案和資料夾會出現在清單頂端，並忽略您指定的排序順序。 |
| ![向上鍵](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL 上移]** | 將釘選的專案或資料夾在專案清單中上移。 |
| ![向下箭號](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL 下移]** | 在專案清單中向下移動釘選專案或資料夾。 |
| ![標籤](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標籤一或多個專案或資料夾。 顯示&#x200B;**[!UICONTROL 標籤元件]**&#x200B;對話方塊以選取一或多個標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選專案或資料夾的標籤。 |
| ![核取記號Circle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 核准]**&#x200B;或&#x200B;**[!UICONTROL 取消核准]** | 核准或取消核准專案。 只有管理員可以核准專案。 |
| ![檔案CSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出CSV]** | 將選取的專案匯出至名稱為`Project List.csv`的CSV檔案。 |
| ![專案新增](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL 新增專案]** | 將一或多個專案新增至選取的資料夾。 您可以在&#x200B;**[!UICONTROL 新增專案]**&#x200B;中選取一或多個專案。 選取&#x200B;**[!UICONTROL 新增]**&#x200B;以將專案新增至資料夾。 如需詳細資訊，請參閱[將專案新增至資料夾](workspace-folders/add-projects.md#from-inside-a-folder)。 |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL 移至]** | 將一或多個選取的專案移至資料夾。 在&#x200B;**[!UICONTROL 選取資料夾]**&#x200B;中，選取要移動選取專案的資料夾，並選取&#x200B;**[!UICONTROL 移動]**。 如需詳細資訊，請參閱[將專案新增至資料夾](workspace-folders/add-projects.md#from-the-project-list)。 |



## 顯示選擇器

您可以使用&#x200B;**[!UICONTROL Show]**&#x200B;選擇器來切換Projects介面的外觀➌。 **[!UICONTROL 顯示]**&#x200B;選取器定義[標題區域](#title-area)中可用的選項，以及[專案清單](#project-list)中顯示的欄。

* 若要變更[標題區域](#title-area)的可用選項，請選取&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 所有專案]**&#x200B;或&#x200B;**[!UICONTROL 顯示]** **[!UICONTROL 資料夾與專案]**。

* 若要定義要為[專案清單](#project-list)顯示哪些資料行，請選取![資料行設定](/help/assets/icons/ColumnSetting.svg)，然後從&#x200B;**[!UICONTROL 自訂資料表]**&#x200B;對話方塊中選取或取消選取資料行。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用自訂。 請參閱[專案清單](#project-list)，以取得資料行的詳細資訊。

## 篩選器面板

您可以使用篩選面板來篩選[專案清單](#project-list)中的專案和資➍料夾。 若要顯示或隱藏篩選器面板，請使用![篩選器](/help/assets/icons/Filter.svg)。

「濾鏡」面板由下列區段組成。

### 標記

| 標記 | 說明 |
|---|---|
| ![標記](/help/analysis-workspace/build-workspace-project/assets/projects-filters-tags.png){width="300"} | **[!UICONTROL 標籤]**&#x200B;區段可讓您依標籤篩選。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg) *搜尋標籤*&#x200B;來搜尋要用來篩選的標籤。</li><li>您可以選取多個標籤。 可用的標籤取決於篩選面板中其他區段所做的選取。</li><li>數字表示：<ul><li>**2︎⃣**：目前篩選產生的專案可用的標籤數。</li><li>⃣7︎：與特定標籤相關聯的專案數目。</li></ul></li></ul> |


### 資料視圖

| 資料視圖 | 說明 |
|---|---|
| ![資料檢視](/help/analysis-workspace/build-workspace-project/assets/projects-filters-dataviews.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;區段可讓您篩選資料檢視。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg) *搜尋資料檢視*&#x200B;來搜尋您要用來篩選的資料檢視。</li><li>您可以選取多個資料檢視。 可用的資料檢視視視在篩選器面板的其他區段中選取的專案而定。</li><li>數字表示：<ul><li>**3︎⃣**：目前篩選產生的專案可用的資料檢視數目。</li><li>⃣4︎：與特定資料檢視相關聯的專案數目。</li></ul></li></ul> |


### 擁有者

| 所有者 | 說明 |
|---|---|
| ![擁有者](/help/analysis-workspace/build-workspace-project/assets/projects-filters-owners.png){width="300"} | **[!UICONTROL 所有者]**&#x200B;區段可讓您依所有者篩選。 <ul><li>您使用![搜尋](/help/assets/icons/Search.svg) *搜尋擁有者*&#x200B;來搜尋您要用來篩選的擁有者。</li><li>您可以選取多個擁有者。 可用的擁有者取決於篩選器面板中其他區段中所做的選擇。</li><li>數字表示：<ul><li>**3︎⃣**：目前篩選產生的專案可用的擁有者數目。</li><li>⃣4︎：與特定擁有者相關聯的專案數目。</li></ul></li></ul> |


### 類型

| 類型 | 說明 |
|---|---|
| ![類型](/help/analysis-workspace/build-workspace-project/assets/projects-filters-type.png){width="300"} | **[!UICONTROL 型別]**&#x200B;區段可讓您篩選專案或資料夾的型別。<ul><li>您可以選取下列一或多個選項：<ul><li> **[!UICONTROL 資料夾]**</li><li>**[!UICONTROL Analysis Workspace 專案]**</li><li>**[!UICONTROL Mobile 計分卡]**</li></ul> <li>您可以選取多個其他篩選器。 可用的其他篩選器取決於篩選器面板中其他區段中所做的選擇。</li><li>數字表示：<ul><li>**5︎⃣**：目前篩選產生的專案可用的其他篩選數目。</li><li>⃣4︎：與特定其他篩選器相關聯的專案數。</li></ul></li></ul> |


### 其他篩選器

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](/help/analysis-workspace/build-workspace-project/assets/projects-filters-others.png){width="300"} | **[!UICONTROL 其他篩選器]**&#x200B;區段可讓您在其他預先定義的篩選器上篩選。<ul><li>您可以選取下列一或多個選項：<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的專案取決於您的角色和許可權。</li><li>您可以選取多個其他篩選器。 可用的其他篩選器取決於篩選器面板中其他區段中所做的選擇。</li><li>數字表示：<ul><li>**5︎⃣**：目前篩選產生的專案可用的其他篩選數目。</li><li>⃣4︎：與特定其他篩選器相關聯的專案數。</li></ul></li></ul> |

## 搜尋

您使用[搜尋]區域，➎使用![搜尋](/help/assets/icons/Search.svg)欄位來搜尋專案和資料夾。 開始輸入，[專案清單](#project-list)就會自動篩選您的搜尋輸入。

「搜尋」區域也會顯示從「篩選器」面板套用的篩選器。

* 若要移除篩選器，請選取篩選器中的![CrossSize75](/help/assets/icons/CrossSize75.svg)。
* 若要移除所有篩選器，請選取「全部清除」。

如果空間限製為只能顯示個別的篩選器，您會看到&#x200B;**[!UICONTROL 篩選依據&#x200B;*x*篩選器]**。

* 若要移除篩選器：

   1. 使用&#x200B;**[!UICONTROL *x *篩選器]**![V形向下](/help/assets/icons/ChevronDown.svg)開啟內容功能表，其中列出篩選器的型別和個別篩選器。
   1. 使用![CrossSize75](/help/assets/icons/CrossSize75.svg)移除篩選器。


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
|  [Components](/help/components/overview.md)  | Create new filters, calculated metric, date range, or alert components from your project. You can also create new components from the left panel. If your component definitions have recently changed, Refresh Components will retrieve the latest definitions. |
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

Components (Dimensions, Metrics, Filters, Date Ranges) in the left panel relate to the active panel data view. The active panel is identified by the blue border that surrounds it, and the active data view is listed at the top of the component panel.

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

