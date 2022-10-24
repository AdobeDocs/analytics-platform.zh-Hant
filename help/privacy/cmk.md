---
title: 客戶管理金鑰
description: 了解如何為CJA設定客戶管理的金鑰。
source-git-commit: 4894519f618b79a5ca29952df48291c44915adae
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# 客戶管理金鑰

>[!NOTE]
>
>此功能將於2022年11月推出。

Customer Journey Analytics(CJA)提供Healthcare Shield和Privacy &amp; Security Shield客戶使用Azure客戶管理金鑰(CMK)來套用至CJA資料的選項。  請注意，此程式與Adobe Experience Platform CMK設定（後續連結）不同。

>[!NOTE]
>
>客戶管理金鑰目前僅適用於已購買 [醫療保健盾或隱私和安全盾](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) 附加產品。

請依照下列步驟，為CJA設定CMK:

1. 請洽詢您的Adobe帳戶團隊，確認您有權使用CMK。
1. 建立僅與CJA搭配使用的新Azure金鑰保管庫。
1. 將您的Azure金鑰值系結至Azure CJA CMK應用程式（後續連結）。
1. 建立Adobe客戶服務票證，請求CMK設定。 在票證中加入Azure URI。
1. Adobe客戶服務將確認CJA資料上的CMK應用程式已完成。
