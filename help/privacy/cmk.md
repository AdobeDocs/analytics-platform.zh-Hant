---
title: 客戶自控金鑰
description: 了解如何為客 Customer Journey Analytics 設定客戶託管金鑰。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: ht
source-wordcount: '387'
ht-degree: 100%

---

# 客戶自控金鑰

Adobe Customer Journey Analytics 為[Healthcare Shield](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html) 和 Privacy &amp; Security Shield 客戶提供選項，讓他們使用客戶託管金鑰 (CMK) 來儲存 Customer Journey Analytics 資料。請注意，此過程與 [Adobe Experience Platform CMK 設定](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview)不同。客戶自控金鑰僅適用於已購買 [Healthcare Shield 或 Privacy &amp; Security Shield](https://experienceleague.adobe.com/zh-hant/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield) 附加產品的組織。

## 為 Azure 的 Customer Journey Analytics 設定客戶託管金鑰

請依照下列步驟為 Azure 上執行的 Customer Journey Analytics 設定 CMK：

1. 確保您有權使用 Adob&#x200B;&#x200B;e Customer Journey Analytics CMK，並且您的組織使用在 Azure 上執行的 Adob&#x200B;&#x200B;e Experience Platform。您可以透過聯絡 Adob&#x200B;&#x200B;e 帳戶團隊來查看這些權利。
1. 確保在 Azure 中您是具有權限角色的管理員，例如應用程式管理員、雲端應用程式管理員或全域管理員。請參閱「[Microsoft Entra 內建角色](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)」。
1. 建立僅用於 Customer Journey Analytics 的新 Azure Key Vault。有關詳細信息，請參閱 [Microsoft Azure Key Vault 文件](https://learn.microsoft.com/zh-tw/azure/key-vault/general/)。
1. 將 Adobe Azure 應用程式存取權限授予給您的金鑰 (金鑰保存庫中)。請參閱「[為現有帳戶設定客戶託管金鑰](https://learn.microsoft.com/zh-tw/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)」，了解更多資訊。Adobe 應用程式 ID 為：

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. 建立要求 CMK 設定的 Adobe 客戶服務票證。在您的票證中包含 Azure URI。URI 可以在 Azure Key 的&#x200B;**金鑰識別碼**&#x200B;欄位中找到：

   ![顯示後述 URI 的金鑰識別碼欄位：https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. Adobe 客戶服務部門確認您在 Customer Journey Analytics 資料上的 CMK 應用程式已完成。

Platform 使用的所有資料在傳輸和待用時都經過加密，以確保您的資料安全，無論是否使用客戶託管金鑰。有關 Adob&#x200B;&#x200B;e Experience Platform 加密的信息，請參閱「[Adobe Experience Platform 中的資料加密](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/governance-privacy-security/encryption)」。

## 為 Amazon Web Services 上的 Customer Journey Analytics 設定客戶託管金鑰

>[!AVAILABILITY]
>
>本節適用於在 Amazon Web Services (AWS) 上執行的 Experience Platform 實施。目前，在 AWS 上執行的 Experience Platform 僅為有限數量的客戶開放。若要了解更多有關受支援的 Experience Platform 基礎架構，請參閱「[Experience Platform 多雲端概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/landing/multi-cloud)」。

如果您的組織使用在 Amazon Web Services 上執行的 Adob&#x200B;&#x200B;e Experience Platform，則已為您設定好 CMK。無需額外設定。
