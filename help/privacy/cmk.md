---
title: 客戶自控金鑰
description: 了解如何為 CJA 設定客戶自控金鑰。
hide: true
hidefromtoc: true
source-git-commit: 90521aa7326486b9016321d35191a73ef891a0bc
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 95%

---

# 客戶自控金鑰

>[!NOTE]
>
>此功能將於 2022 年 11 月推出。

Customer Journey Analytics (CJA) 讓 [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) 和 Privacy &amp; Security Shield 客戶可選擇將 Azure 客戶自控金鑰 (CMK) 套用於 CJA 資料。請注意，此過程與 [Adobe Experience Platform CMK 設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html)不同。

>[!NOTE]
>
>客戶自控金鑰目前僅適用於已購買 [Healthcare Shield 或 Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 附加產品的組織。

## 為 CJA 設定 CMK

按照以下步驟為 CJA 設定 CMK：

1. 與您的 Adobe 帳戶團隊確認，確定您有權使用 Adobe CJA CMK。
1. 確保在 Azure 中您是具有權限角色的管理員，例如應用程式管理員、雲端應用程式管理員或全域管理員。[從 Microsoft 了解更多資訊](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. 建立僅用於 CJA 的新 Azure Key Vault。[從 Microsoft 了解更多資訊](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. 將 Adobe Azure 應用程式存取權限授予給您的金鑰 (金鑰保存庫中)。這是 Adobe 應用程式 ID：251e3919-1940-4296-bb8b-6b9a5e8a4805。[從 Microsoft 了解更多資訊](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. 建立要求 CMK 設定的 Adobe 客戶服務票證。在您的票證中包含 Azure URI。可在Azure密鑰的「密鑰標識符」欄位中找到URI。
1. Adobe 客戶服務將確認您 CJA 資料上的 CMK 應用程式已完成。