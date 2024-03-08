---
title: 客戶自控金鑰
description: 瞭解如何設定客戶自控金鑰以進行Customer Journey Analytics。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 57%

---

# 客戶自控金鑰

Adobe Customer Journey Analytics為以下專案提供選項 [Health Shield](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html) 以及Privacy &amp; Security Shield客戶，將Azure客戶自控金鑰(CMK)套用至您的Customer Journey Analytics資料。  請注意，此過程與 [Adobe Experience Platform CMK 設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=zh-Hant)不同。

>[!NOTE]
>
>客戶自控金鑰目前僅適用於已購買 [Healthcare Shield 或 Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html) 附加產品的組織。

## 設定CMK以進行Customer Journey Analytics

請依照下列步驟設定CMK以進行Customer Journey Analytics：

1. 與您的Adobe帳戶團隊確認，確定您有權使用Adobe Customer Journey Analytics CMK。
1. 確保在 Azure 中您是具有權限角色的管理員，例如應用程式管理員、雲端應用程式管理員或全域管理員。[從 Microsoft 了解更多資訊](https://learn.microsoft.com/zh-tw/azure/active-directory/roles/permissions-reference)
1. 建立僅用於Customer Journey Analytics的新Azure Key Vault。 [從 Microsoft 了解更多資訊](https://learn.microsoft.com/zh-tw/azure/key-vault/general/)
1. 將 Adobe Azure 應用程式存取權限授予給您的金鑰 (金鑰保存庫中)。這是 Adobe 應用程式 ID：251e3919-1940-4296-bb8b-6b9a5e8a4805。[從 Microsoft 了解更多資訊](https://learn.microsoft.com/zh-tw/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. 建立要求 CMK 設定的 Adobe 客戶服務票證。在您的票證中包含 Azure URI。URI 可以在 Azure Key 的&#x200B;**金鑰識別碼**&#x200B;欄位中找到。

   ![顯示https://cmkoberontest.vault.azure.net URI的金鑰識別碼欄位](assets/key-identifier.png)

1. Adobe客戶服務將確認您Customer Journey Analytics資料上的CMK應用程式已完成。

Platform 使用的所有資料在傳輸和待用時都經過加密，以確保您的資料安全，無論是否使用 CMK。如需 Adobe Experience Platform 加密資訊，請[了解更多](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=zh-Hant)。
