---
title: 客戶自控金鑰
description: 瞭解如何設定客戶自控金鑰以進行Customer Journey Analytics。
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 14%

---

# 客戶自控金鑰

Adobe Customer Journey Analytics為[Healthcare Shield](https://www.adobe.com/tw/trust/compliance/hipaa-ready.html)和Privacy &amp; Security Shield客戶提供了使用客戶自控金鑰(CMK)進行Customer Journey Analytics資料的選項。 請注意，此程式與[Adobe Experience Platform CMK設定](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview)不同。 客戶管理的金鑰僅適用於已購買[Healthcare Shield或Privacy &amp; Security Shield](https://experienceleague.adobe.com/zh-hant/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield)附加產品的組織。

## 設定客戶自控金鑰以在Azure上Customer Journey Analytics

請依照下列步驟為Azure上執行的Customer Journey Analytics設定CMK：

1. 確定您有權使用Adobe Customer Journey Analytics CMK，且您的組織使用在Azure上執行的Adobe Experience Platform。 您可以連絡您的Adobe帳戶團隊以檢查這些權益。
1. 確保在 Azure 中您是具有權限角色的管理員，例如應用程式管理員、雲端應用程式管理員或全域管理員。如需詳細資訊，請參閱[Microsoft Entra內建角色](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference)。
1. 建立僅用於Customer Journey Analytics的新Azure Key Vault。 如需詳細資訊，請參閱[Microsoft Azure金鑰儲存庫檔案](https://learn.microsoft.com/zh-tw/azure/key-vault/general/)。
1. 將 Adobe Azure 應用程式存取權限授予給您的金鑰 (金鑰保存庫中)。如需詳細資訊，請參閱[為現有帳戶](https://learn.microsoft.com/zh-tw/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)設定客戶管理的金鑰。 Adobe應用程式ID為：

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. 建立要求 CMK 設定的 Adobe 客戶服務票證。在您的票證中包含 Azure URI。URI可以在Azure金鑰的&#x200B;**金鑰識別碼**&#x200B;欄位中找到：

   顯示https://cmkoberontest.vault.azure.net](assets/key-identifier.png)之URI的![金鑰識別碼欄位

1. Adobe客戶服務會確認您Customer Journey Analytics資料上的CMK應用程式已完成。

Platform使用的所有資料在傳輸和待用時都會經過加密，以確保您的資料安全，無論是否使用客戶自控金鑰。 如需Adobe Experience Platform加密的資訊，請參閱[Adobe Experience Platform中的資料加密](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption)。

## 設定客戶自控金鑰以在Amazon Web Services上Customer Journey Analytics

>[!AVAILABILITY]
>
>本節適用於在Amazon Web Services (AWS)上執行的Experience Platform實作。 在AWS上執行的Experience Platform目前可供有限數量的客戶使用。 若要深入瞭解支援的Experience Platform基礎結構，請參閱[Experience Platform多雲端總覽](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud)。

如果您的組織使用在Amazon Web Services上執行的Adobe Experience Platform，則已為您設定CMK。 不需要其他設定。
