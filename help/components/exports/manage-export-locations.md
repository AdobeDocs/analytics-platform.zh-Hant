---
description: 管理可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 管理雲端匯出位置和帳戶
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
role: User, Admin
source-git-commit: 4bfa32ba3a7902d31edefab17a00206f922a8382
workflow-type: tm+mt
source-wordcount: '1371'
ht-degree: 3%

---

# 管理雲端匯出位置和帳戶

您可以檢視、編輯和刪除雲端匯出位置。

如需如何建立新位置的詳細資訊，請參閱[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)。

## 篩選和搜尋位置

若要尋找您需要的資訊，您可以在位置清單上篩選或搜尋位置。

### 篩選位置清單

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤。

1. 選取&#x200B;**篩選器**&#x200B;圖示。

   <!-- add screenshot -->

   您可以依下列條件篩選：

   | 篩選器 | 說明 |
   |---------|----------|
   | [!UICONTROL **位置型別**]<!--should this be changed to Account type?--> | 與位置關聯的帳戶型別。 可使用下列帳戶型別： <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **帳戶**] | 與位置關聯的帳戶名稱。 |
   | [!UICONTROL **建立者**] | 建立位置之使用者的電子郵件地址。 |

   {style="table-layout:auto"}

### 搜尋位置

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的位置**]&#x200B;選項，以檢視組織中的所有使用者建立的位置。

1. 在搜尋欄位中，開始輸入與您要搜尋的位置相關聯的任何資訊。 您可以從表格中任何可用的欄搜尋資料。

## 編輯位置

位置只能由建立該位置的使用者或系統管理員編輯。

若要編輯位置：

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的位置**]&#x200B;選項，以檢視組織中的所有使用者建立的位置。

1. 選取您要編輯的位置。

   ![顯示[位置]索引標籤和位置清單的[匯出]視窗。](assets/locations-edit.png)

1. 選取「[!UICONTROL **編輯**]」。

1. 進行任何需要的變更，然後選取[儲存]。[!UICONTROL **&#x200B;**]

## 刪除位置

如果您刪除位置，則使用該位置的任何匯出內容也會一併刪除。 刪除時勾選確認對話方塊，以確保沒有任何匯出專案與該位置相關聯。

若要刪除位置：

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤。

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的位置**]&#x200B;選項，以檢視組織中的所有使用者建立的位置。

1. 選取一或多個要刪除的位置。

   ![顯示[位置]索引標籤與位置清單的[匯出]視窗](assets/locations-edit.png)

1. 選取「[!UICONTROL **刪除**]」。

   「刪除位置」對話方塊隨即顯示。

1. 在「刪除位置」對話方塊中，在確認刪除之前，請確定該位置未與任何匯出相關聯。

   ![刪除位置確認對話方塊](assets/delete-location-confirmation-dialog.png)

1. 再次選取&#x200B;[!UICONTROL **刪除**]&#x200B;以進行確認。

## 編輯帳戶

只有建立帳號的使用者或系統管理員才能編輯帳號。

若要編輯帳戶：

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

   ![顯示[位置帳戶]索引標籤的[匯出]視窗](assets/account-add.png)

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的帳戶**]&#x200B;選項，以檢視貴組織中所有使用者建立的位置。

1. 在您要編輯的帳戶上選取&#x200B;[!UICONTROL **檢視詳細資料**]。

1. 進行任何需要的變更，然後選取[儲存]。[!UICONTROL **&#x200B;**]

## 檢視帳戶金鑰

建立帳戶之後，您可以檢視該帳戶的任何關聯帳戶金鑰。 如果您在最初設定帳戶[時，尚未完成雲端提供者](/help/components/exports/cloud-export-accounts.md)的帳戶設定，您可能需要檢視此資訊。

若要檢視與匯出帳戶相關聯的金鑰，請執行下列動作：

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

   ![顯示[位置帳戶]索引標籤的[匯出]視窗](assets/account-add.png)

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的帳戶**]&#x200B;選項，以檢視貴組織中所有使用者建立的位置。

1. 在您要編輯的帳戶上選取3點圖示，然後選取&#x200B;[!UICONTROL **帳戶金鑰**]。

## 刪除帳戶

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤。

   ![顯示[位置帳戶]索引標籤的[匯出]視窗](assets/account-add.png)

1. （視條件而定）如果您是系統管理員，可以啟用&#x200B;[!UICONTROL **檢視所有使用者的帳戶**]&#x200B;選項，以檢視貴組織中所有使用者建立的位置。

1. 在您要編輯的帳戶上選取3點圖示，然後選取&#x200B;[!UICONTROL **刪除帳戶**]。

1. 在確認對話方塊中再次選取&#x200B;[!UICONTROL **刪除**]。

## 設定全公司設定（僅限管理員）

系統管理員可以限制使用者建立帳戶和位置，也可以限制使用者可以建立和使用的帳戶型別。

![管理員設定標籤](assets/locations-admin-settings.png)

### 設定使用者是否可以建立和編輯帳戶

依預設，組織中的所有使用者都可以建立帳戶，並編輯他們在Customer Journey Analytics環境中建立的帳戶，如[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)中所述。

您可以限制使用者建立帳戶。 當您這樣做時，使用者仍然可以使用他們已建立的任何帳戶，但他們無法再編輯這些帳戶。 您可以刪除使用者已建立的帳戶，如[刪除帳戶](#delete-an-account)中所述。

若要限制所有使用者建立和編輯帳戶：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 匯出]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;區段中，取消選取&#x200B;[!UICONTROL **允許使用者建立和管理位置帳戶**]&#x200B;選項。

1. 選取「[!UICONTROL **儲存**]」。

1. （選擇性）刪除使用者已建立而您不再想要他們使用的任何帳戶，如[刪除帳戶](#delete-an-account)中所述。

### 設定使用者是否可以建立和編輯位置

根據預設，組織中的所有使用者都可以在Customer Journey Analytics環境中建立位置並編輯他們建立的位置，如[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)中所述。

您可以限制使用者建立位置。 當您這樣做，使用者仍然可以使用他們已建立的任何位置，但他們無法再編輯這些位置。 您可以刪除使用者已建立的位置，如[刪除位置](#delete-a-location)中所述。

若要限制所有使用者建立和編輯位置：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 報表]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 在&#x200B;[!UICONTROL **位置**]&#x200B;區段中，取消選取&#x200B;[!UICONTROL **允許使用者建立和管理位置**]&#x200B;選項。

1. 選取「[!UICONTROL **儲存**]」。

1. （選擇性）刪除使用者已建立而您不再希望他們使用的任何位置，如[刪除位置](#delete-a-location)中所述。

### 限制使用者可以建立和使用的帳戶型別

您可以在下列情況下限制使用者看到的帳戶型別：

* 當[建立新帳戶](/help/components/exports/cloud-export-accounts.md)時。
* 選擇使用[完整資料表匯出](/help/analysis-workspace/export/export-cloud.md)匯出檔案時要使用的帳戶時。

當您依照本節所述限制帳戶型別時，使用者將無法再看見您所限制型別的任何帳戶。 這表示在使用完整表格匯出來匯出檔案時，無法建立該型別的新帳戶，也無法使用該型別的現有帳戶。

但是，如果您想要限制使用為排程匯出設定的現有帳戶，則必須刪除這些帳戶。

#### 確保帳戶不會用於排程的匯出

當您限制帳戶型別時，會隱藏現有的帳戶，而不會將其刪除。

如果排程已設定為傳送資料至您所限制型別的帳戶，則排程仍會繼續執行，即使您限制帳戶型別後，資料也會繼續傳送至帳戶。 例如，如果排程完整表格匯出，以將資料傳送至您限制的帳戶型別，則排程將繼續執行。

如果您需要確保排程的匯出不會使用特定型別的帳戶，您可以在[限制帳戶型別](#limit-the-account-types-that-are-available-to-users)之前刪除帳戶。

若要刪除帳號：

1. 找出您計畫限制的帳戶型別帳戶，這些帳戶用於排程匯出。

1. 刪除帳戶，如[刪除帳戶](#delete-an-account)中所述。

1. 繼續下列章節，[限制使用者可用的帳戶型別](#limit-the-account-types-that-are-available-to-users)。

#### 限制使用者可用的帳戶型別

若要限制使用者建立和使用帳戶時可用的帳戶型別：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 匯出]**，然後選取&#x200B;[!UICONTROL **管理員設定**]&#x200B;索引標籤。

1. 找到&#x200B;[!UICONTROL **允許的帳戶型別**]&#x200B;區段。

   使用者預設可使用下列帳戶型別。 取消選取您要限制使用者使用的任一帳戶型別。

   * [!UICONTROL **AEP Data Landing Zone**]

   * [!UICONTROL **Amazon S3 Role ARN**]

   * [!UICONTROL **Google Cloud Platform**]

   * [!UICONTROL **Azure SAS**]

   * [!UICONTROL **Azure RBAC**]

   * [!UICONTROL **Snowflake**]

1. 選取「[!UICONTROL **儲存**]」。
