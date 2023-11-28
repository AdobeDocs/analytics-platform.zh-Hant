---
description: 管理可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 管理雲端匯出位置和帳戶
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 管理雲端匯出位置和帳戶

您可以檢視、編輯和刪除雲端匯出位置。

如需有關如何建立新位置的資訊，請參閱 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

## 篩選和搜尋位置

若要尋找您需要的資訊，您可以篩選位置清單或搜尋位置。

### 篩選位置清單

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤。

1. 選取 **篩選** 圖示。

   <!-- add screenshot -->

   您可以依下列條件篩選：

   | 篩選器 | 說明 |
   |---------|----------|
   | [!UICONTROL **位置類型**]<!--should this be changed to Account type?--> | 與位置關聯的帳戶型別。 可使用下列帳戶型別： <ul><li>[!UICONTROL **AEP 資料登陸區域**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **帳戶**] | 與位置關聯的帳戶名稱。 |
   | [!UICONTROL **建立者**] | 建立位置之使用者的電子郵件地址。 |

   {style="table-layout:auto"}

### 搜尋位置

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤。

1. 在搜尋欄位中，開始輸入與您要搜尋的位置相關聯的任何資訊。 您可以從表格中任何可用的欄搜尋資料。

## 編輯位置

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤，然後選取要編輯的位置。

   ![顯示位置標籤和位置清單的匯出視窗。](assets/locations-edit.png)

1. 選取 [!UICONTROL **編輯**].

1. 進行任何需要的變更，然後選取「 」 [!UICONTROL **儲存**].

## 刪除位置

如果您刪除位置，則使用該位置的任何匯出內容也會一併刪除。 刪除時勾選確認對話方塊，以確保沒有任何匯出專案與該位置相關聯。

若要刪除位置：

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤，然後選取一或多個要刪除的位置。

   ![顯示[位置]索引標籤和位置清單的[匯出]視窗](assets/locations-edit.png)

1. 選取「[!UICONTROL **刪除**]」。

   「刪除位置」對話方塊隨即顯示。

1. 在「刪除位置」對話方塊中，在確認刪除之前，請確定該位置未與任何匯出相關聯。

   ![刪除位置確認對話方塊](assets/delete-location-confirmation-dialog.png)

1. 選取 [!UICONTROL **刪除**] 再次確認。

## 編輯帳戶

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置帳戶**] 標籤。

   ![顯示[Location accounts]索引標籤的[Exports]視窗](assets/account-add.png)

1. 選取 [!UICONTROL **檢視詳細資料**] 在您想要編輯的帳戶上。

1. 進行任何需要的變更，然後選取「 」 [!UICONTROL **儲存**].

## 檢視帳戶金鑰

建立帳戶之後，您可以檢視該帳戶的任何關聯帳戶金鑰。 如果您沒有向雲端提供者完成設定帳戶，您可能需要檢視此資訊 [當您最初設定帳戶時](/help/components/exports/cloud-export-accounts.md).

若要檢視與匯出帳戶相關聯的金鑰，請執行下列動作：

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置帳戶**] 標籤。

   ![顯示[Location accounts]索引標籤的[Exports]視窗](assets/account-add.png)

1. 在您要編輯的帳戶上選取3點圖示，然後選取「 」 [!UICONTROL **帳戶金鑰**].

## 刪除帳戶

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置帳戶**] 標籤。

   ![顯示[Location accounts]索引標籤的[Exports]視窗](assets/account-add.png)

1. 在您要編輯的帳戶上選取3點圖示，然後選取「 」 [!UICONTROL **刪除帳戶**].

1. 選取 [!UICONTROL **刪除**] 再次在確認對話方塊中。
