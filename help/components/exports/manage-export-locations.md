---
description: 管理可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 管理雲端匯出位置和帳戶
feature: Components
exl-id: 8e82fe6f-99df-4360-8693-99692aac002b
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 5%

---

# 管理雲端匯出位置和帳戶

{{release-limited-testing}}

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
   | [!UICONTROL **位置類型**]<!--should this be changed to Account type?--> | 與位置關聯的帳戶型別。 可使用下列帳戶型別： <ul><li>[!UICONTROL **AEP資料登陸區域**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **帳戶**] | 與位置關聯的帳戶名稱。 |
   | [!UICONTROL **建立者**] | 建立位置之使用者的電子郵件地址。 |

   {style="table-layout:auto"}

### 搜尋位置

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤。

1. 在搜尋索引標籤中，開始輸入與您要搜尋的位置相關聯的任何資訊。 您可以從表格中任何可用的欄搜尋資料。

## 編輯位置

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤，然後選取要編輯的位置。

   <!-- add screenshot? -->

1. 選取 [!UICONTROL **編輯**].

1. 進行任何需要的變更，然後選取「 」 [!UICONTROL **儲存**].

## 刪除位置

如果您刪除位置，則使用該位置的任何匯出內容也會一併刪除。

在刪除位置之前，請先選取位置名稱旁的資訊圖示，檢視任何匯出是否正在使用它。

![連線的匯出](assets/location-connected-exports.png)

若要刪除位置：

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 標籤，然後選取一或多個要刪除的位置。

   <!-- add screenshot? -->

1. 選取 [!UICONTROL **刪除**]，然後選取 [!UICONTROL **刪除**] 再次在確認對話方塊中。

## 編輯帳戶

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置帳戶**] 標籤。

   ![帳戶頁面](assets/account-page.png)

1. 選取 [!UICONTROL **檢視詳細資料**] 在您想要編輯的帳戶上。

1. 進行任何需要的變更，然後選取「 」 [!UICONTROL **儲存**].

## 刪除帳戶

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置帳戶**] 標籤。

   ![帳戶頁面](assets/account-page.png)

1. 在您要編輯的帳戶上選取3點圖示，然後選取「 」 [!UICONTROL **刪除帳戶**].

1. 選取 [!UICONTROL **刪除**] 再次在確認對話方塊中。
