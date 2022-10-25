---
title: 客戶管理金鑰
description: 了解如何為CJA設定客戶管理的金鑰。
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# 客戶管理金鑰

>[!NOTE]
>
>此功能將於2022年11月推出。

Customer Journey Analytics(CJA)提供 [醫療保健盾](https://www.adobe.com/trust/compliance/hipaa-ready.html) 和「隱私與安全防護」客戶可運用Azure客戶管理金鑰(CMK)，套用至您的CJA資料。  請注意，此程式與 [Adobe Experience Platform CMK設定](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>客戶管理金鑰目前僅適用於已購買 [醫療保健盾或隱私和安全盾](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 附加產品。

請依照下列步驟，為CJA設定CMK:

1. 請洽詢您的Adobe帳戶團隊，確認您有權使用CMK。
1. 建立僅與CJA搭配使用的新Azure金鑰保管庫。
1. 將您的Azure金鑰值系結至Azure CJA CMK應用程式（後續連結）。
1. 建立Adobe客戶服務票證，請求CMK設定。 在票證中加入Azure URI。
1. Adobe客戶服務將確認CJA資料上的CMK應用程式已完成。
