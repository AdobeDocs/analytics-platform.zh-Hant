---
title: 客戶自控金鑰
description: 了解如何為 CJA 設定客戶自控金鑰。
hide: true
hidefromtoc: true
source-git-commit: 3aa5d9e1b426e67f27ef1909a2640f335719502a
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 33%

---

# 客戶自控金鑰

>[!NOTE]
>
>此功能將於 2022 年 11 月推出。

Customer Journey Analytics(CJA)提供 [醫療保健盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) 和「隱私與安全防護」客戶可運用Azure客戶管理金鑰(CMK)，套用至您的CJA資料。  請注意，此程式與 [Adobe Experience Platform CMK設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>客戶自控金鑰目前僅適用於已購買 [Healthcare Shield 或 Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 附加產品的組織。

## 為CJA設定CMK

按照以下步驟為 CJA 設定 CMK：

1. 請洽詢您的Adobe帳戶團隊，確認您有權AdobeCJA CMK。
1. 確保在Azure中，您是具有特權角色的管理員，如應用程式管理員、雲應用程式管理員或全局管理員。 [進一步了解Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. 建立僅用於 CJA 的新 Azure Key Vault。[進一步了解Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. 授予AdobeAzure應用程式對金鑰保管庫中您金鑰的存取權。 這是Adobe應用程式ID:251e3919-1940-4296-bb8b-6b9a5e8a4805。 [了解更多Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. 建立要求 CMK 設定的 Adobe 客戶服務票證。在您的票證中包含 Azure URI。
1. Adobe客戶服務將確認CJA資料上的CMK應用程式已完成。
