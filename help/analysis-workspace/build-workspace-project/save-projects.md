---
description: 了解不同的儲存選項 (包括 AutoSave、另存為、另存為範本)，以及開啟先前的版本。
title: 儲存專案
feature: Workspace 基本知識
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 734f1fe702398034090e25c251b5ff193db8381e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# 儲存專案

若要儲存您對專案所做的變更，請前往 Analysis Workspace 的&#x200B;**[!UICONTROL 「專案」]**&#x200B;功能表。在特定情況下，Workspace 也會自動儲存專案。

## 儲存專案選項 {#Save}

您可以在&#x200B;**[!UICONTROL 「專案」]**&#x200B;功能表底下執行不同的儲存操作，取決於您日後要如何存取分析。

| 動作 | 說明 |
|---|---| 
| **[!UICONTROL 儲存]** | 儲存專案的變更項目。如果已共用專案，專案的收件者也會看到變更項目。當您第一次儲存專案時，系統會提示您提供專案名稱、(選用) 說明和新增 (選用) 標籤。  |
| **[!UICONTROL 一併儲存註釋]** | 在專案儲存之前，請新增關於專案變動的註釋。註釋會和專案版本儲存在「[!UICONTROL 專案] > [!UICONTROL 開啟先前版本]」下，可供編輯人員使用。 |
| **[!UICONTROL 另存新檔]** | 建立專案的複本。原始專案不受影響。 |
| **[!UICONTROL 另存為範本]** | 將專案儲存為[自訂範本](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=zh-Hant)，您的組織可在&#x200B;**[!UICONTROL 「專案 > 新增」]**&#x200B;下使用 |

![](assets/save-project.png)

## 自動儲存 {#Autosave}

現有專案 (即之前至少已儲存一次的專案) 每兩分鐘會自動儲存至您的本機電腦一次。從未儲存過的新專案目前不會自動儲存。

有些情況可能會導致您遠離未儲存的專案變更項目，進而產生不同的可用操作。

### 開啟另一個 Analysis Workspace 專案

Adobe 提供在離開頁面前儲存的選項。離開現有專案後，自動儲存的本機副本即會刪除。

![](assets/existing-save.png)

### 離開或關閉索引標籤

瀏覽器會警告未儲存的變更將遺失。您可以選擇離開或取消。

![](assets/browser-image.png)

### 瀏覽器當機或工作階段逾時

若為&#x200B;**現有**&#x200B;專案，返回 Workspace 後，您將會看到&#x200B;**專案復原**&#x200B;強制回應視窗。選取「是」，會從自動儲存的本機版本復原專案。若選擇「否」，則會刪除自動儲存的本機副本，並開啟上次用戶儲存的專案版本。

![](assets/project-recovery.png)

若為從未儲存的&#x200B;**新**&#x200B;專案，未儲存的變更無法復原。

## 開啟先前版本 {#previous-version}

>[!NOTE]
>
>先前專案版本目前為限時提供。

若要開啟專案的先前版本：

1. 前往「**[!UICONTROL 專案]** > **[!UICONTROL 開啟先前版本]**」

   ![](assets/previous-versions.png)

1. 檢視現有的先前版本清單。
   除了顯示[!UICONTROL 註釋]外，也會顯示[!UICONTROL 時間戳記]和 [!UICONTROL 編輯者] (如果[!UICONTROL 編輯者]儲存時都加入這些內容)。未附註釋的版本會儲存達 90 天；附註釋的版本會儲存達 1 年。
1. 選取先前版本並按一下「**[!UICONTROL 載入]**」。先前版本然後載入通知。在按一下「**[!UICONTROL 儲存]**」以前，先前版本不會成為專案的目前儲存版本。如果您瀏覽時離開載入的版本，當您回來時，您將看到專案最後儲存的版本。
