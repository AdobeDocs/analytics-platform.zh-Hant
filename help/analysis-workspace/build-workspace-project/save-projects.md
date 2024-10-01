---
description: 了解不同的儲存選項 (包括 AutoSave、另存為、另存為範本)，以及開啟先前的版本。
title: 儲存專案
feature: Workspace Basics
role: User
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 17%

---

# 儲存專案 {#save-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_addnotes"
>title="新增附註"
>abstract="新增有關正在儲存的專案版本的附註。 這些筆記將與版本一起儲存，並可在&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 開啟先前版本]**&#x200B;功能表下存取。"

<!-- markdownlint-enable MD034 -->


Analysis Workspace中的專案會每兩分鐘自動儲存一次。 您也可以自行儲存專案、將專案儲存為重複專案，或儲存含有版本注意事項的專案。

## 儲存

若要在Analysis Workspace中開啟專案的情況下手動儲存專案，請選取「**[!UICONTROL 專案]**」，然後從下列選項中選擇：

* **[!UICONTROL 儲存]**

  儲存專案的變更項目。如果專案已共用，專案的收件者也會看到變更專案。

  第一次儲存專案時，會顯示&#x200B;**[!UICONTROL 儲存]**&#x200B;對話方塊。

  ![儲存專案](assets/save-project.png)

   1. 指定下列專案：

      * **[!UICONTROL 名稱]** （必要）。 專案名稱。
      * **[!UICONTROL 描述]**。 專案的說明。
      * **[!UICONTROL 標籤]**。 搜尋&#x200B;[!UICONTROL *搜尋標籤*]&#x200B;欄位中的標籤，或使用&#x200B;**[!UICONTROL ENTER]**&#x200B;新增標籤。
      * **[!UICONTROL 資料夾]**。 從&#x200B;[!UICONTROL *選取資料夾*]&#x200B;下拉式功能表中選取資料夾。 如果您未指定資料夾，專案會儲存在您建立新專案的目前資料夾中。
      * **[!UICONTROL 版本注意事項]**。 在&#x200B;*新增附註*&#x200B;文字區域中新增版本附註。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存您的專案。

  儲存您的專案實際上會儲存專案版本，並儲存90天。

  如果您儲存已共用的專案，會出現&#x200B;**[!UICONTROL 儲存對共用專案的變更]**&#x200B;警告對話方塊提示您確認。

  ![儲存共用的專案](assets/save-project-shared.png)

   * 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存專案。
   * 選取&#x200B;**[!UICONTROL 另存新檔]**，將專案另存為新名稱的重複專案。


* **[!UICONTROL 一併儲存註釋]**

  ![一併儲存註釋](assets/save-version-notes.png)

  儲存專案時，請新增關於專案中變更內容的附註。 在「儲存版本注意事項」對話方塊中：

   1. 在&#x200B;**[!UICONTROL 新增備註]**&#x200B;文字區域中輸入您的&#x200B;**[!UICONTROL 版本備註]**。
   1. 選取「**[!UICONTROL 儲存]**」。

  筆記與專案版本一起儲存，當您[開啟專案的先前版本](open-projects.md#open-previous-version)時即可使用。 與附註一起儲存的版本會自動儲存一年。

* **[!UICONTROL 另存新檔]**

  ![將專案儲存為](assets/save-project-as.png)

  以新名稱建立專案的復本。 「另存新檔」對話方塊隨即顯示。

   1. 指定下列專案：

      * **[!UICONTROL 名稱]** （必要）。 專案名稱。
      * **[!UICONTROL 描述]**。 專案的說明。
      * **[!UICONTROL 標籤]**。 搜尋&#x200B;[!UICONTROL *搜尋標籤*]&#x200B;欄位中的標籤，或使用&#x200B;**[!UICONTROL ENTER]**&#x200B;新增標籤。
      * **[!UICONTROL 資料夾]**。 從&#x200B;[!UICONTROL *選取資料夾*]&#x200B;下拉式功能表中選取資料夾。 如果您未指定資料夾，專案會儲存在您建立新專案的目前資料夾中。
      * **[!UICONTROL 版本注意事項]**。 在&#x200B;*新增附註*&#x200B;文字區域中新增版本附註。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存您的專案。

  您可以將專案儲存到其他資料夾。 原始專案不受影響。


<!-- Cannot find this option in CJA 
| **[!UICONTROL Save as template]** | Save your project as a [custom template](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) that becomes available to your organization under **[!UICONTROL Project > New]** | 
-->

## 自動儲存


>[!IMPORTANT]
>
>即使新專案已自動儲存，您也必須在&#x200B;**前**&#x200B;次手動儲存每個新專案。
>

Analysis Workspace 中的所有專案均每 2 分鐘自動儲存至本機電腦。此自動儲存包含尚未手動儲存的新建立專案。

### 新專案

Analysis Workspace 會在切換至其他專案、關閉瀏覽器索引標籤等動作時，提示您手動儲存新專案。

如果您在手動儲存新建立的專案之前，由於任何原因，意外地失去存取權，專案的復原版本會儲存在Analysis Workspace登陸頁面名為「**[!UICONTROL 復原的專案（過去7天）]**」的資料夾中。 還原復原的專案，並手動將其儲存至所需位置。

若要還原已恢復的專案，請執行以下操作：

1. 前往Analysis Workspace登陸頁面上的&#x200B;**[!UICONTROL 復原的專案（過去7天）]**&#x200B;資料夾。

<!-- 
     ![The list of folders highlighting the Recovered Project folder.](assets/recovered-folder.png)
  -->

1. 開啟您的專案並儲存至所需位置。


### 現有專案

如果您因為任何原因離開專案而變更尚未自動儲存，Analysis Workspace會提示您儲存變更或提供警告訊息。


一些常見情境：

#### 開啟另一個專案

如果您在處理包含尚未自動儲存之變更的專案時開啟另一個專案，Analysis Workspace會提示您儲存目前的專案。

提供下列選項：

* **[!UICONTROL 儲存]**：以您的最新變更取代最近自動儲存的專案本機復本。
* **[!UICONTROL 捨棄變更]**：捨棄您最新的變更。 專案會保留最近自動儲存的本機副本。
* **[!UICONTROL 取消]**：取消開啟其他專案的動作，並保持現有專案開啟。

<!-- ![Click Save to save changes to a project.](assets/existing-save.png) -->

#### 離開或關閉索引標籤

如果您在檢視含有尚未自動儲存之變更的專案時離開頁面或關閉瀏覽器索引標籤，瀏覽器會警告您未儲存的變更遺失。 您可以選擇離開或取消。 瀏覽器警告您的方式取決於您使用的瀏覽器。


### 瀏覽器當機或工作階段逾時

如果您的瀏覽器當機或工作階段逾時，則下次存取Analysis Workspace時，系統會提示您復原尚未自動儲存的任何專案變更。

* 選取&#x200B;**[!UICONTROL 「是」]**，從最新的自動儲存副本還原專案。

* 選取&#x200B;**[!UICONTROL 「否」]**，刪除自動儲存的副本，並開啟上次使用者儲存的專案版本。

<!--![The Project Recovery dialog box.](assets/project-recovery.png)-->



若為從未儲存的&#x200B;**新**&#x200B;專案，未儲存的變更無法復原。


<!-- Shouldn't this belong to another page?  Moved it to a new open projects page


## Open previously saved version

To open a previously saved version of a project:

1. Select **[!UICONTROL Open previous version]** from the **[!UICONTROL Project]** menu.

   ![The Previously saved project versions list and options to show All versions or Only versions with notes.](assets/open-previously-saved.png)

1. Review the list of previous versions available. You can switch between **[!UICONTROL All versions]** and **[!UICONTROL Only versions with notes]**.

   For each version, the list shows a timestamp
   [!UICONTROL Timestamp] and [!UICONTROL Editor] are shown, in addition to [!UICONTROL Notes] if they were added when the [!UICONTROL Editor] saved. Versions without notes are stored for 90 days; versions with notes are stored for 1 year.
1. Select a previous version and click **[!UICONTROL Load]**.
   The previous version then loads with a notification. The previous version does not become the current saved version of your project until you click **[!UICONTROL Save]**. If you navigate away from the loaded version, when you return, you will see the last saved version of the project.

-->
