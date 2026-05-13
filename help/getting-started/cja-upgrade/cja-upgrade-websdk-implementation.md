---
title: 了解升級至 Customer Journey Analytics 時的 Web SDK 實作選項
description: 了解關於升級至 Customer Journey Analytics 時的 Web SDK 實施選項
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
TQID: https://experienceleague.adobe.com/oNG3Vw5t42dZWsyCuhW-ahajCgnc6sOs6QuC4vPhJuQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 100%

---

# 了解升級至 Customer Journey Analytics 時的 Web SDK 實施選項 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript 資料庫 (alloy.js)"
>abstract="在您網站的每個頁面上包括 Web SDK 資料庫 (alloy.js)。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK 標記擴充功能"
>abstract="(建議) 如果您尚未使用標記，請在您的網站安裝標記 Loader。 如果您已使用標記，則可以新增 Web SDK 擴充功能至您的標記屬性。 此選項包括在 Adobe Experience Platform 資料收集和第三方標記管理系統中使用標記的實作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM 套件"
>abstract="使用資料收集 API 直接傳送資料至資料流。 同時支援未驗證 (用戶端對伺服器) 和已驗證 (伺服器對伺服器) 類型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="為指定的屬性實作 Web SDK"
>abstract="選取升級指南中所需的實作類型，以了解更詳細的說明。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="將 Web SDK 程式庫新增至第三方標記管理系統"
>abstract="與標記管理系統的管理員合作，將 Web SDK 程式庫新增至您的網站。<br><br>此任務的完成時間有很大程度取決於負責標記管理系統之個人的回應能力。 新增 Web SDK 程式庫可能會與相關聯的實作邏輯整合在一起，並在組織的標準發行週期內進行部署。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

從 Adobe Analytics 升級到 Customer Journey Analytics 的推薦流程是 Experience Platform Web SDK 的新實施，這是最適月合 Customer Journey Analytics 的資料收集方法。

使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 的三種支援方式：

* [Web SDK 標記擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/extension)：Adobe 建議使用此方法。 在您的網站上安裝標記載入器，然後使用 Adob&#x200B;&#x200B;e Experience Platform 資料收集 UI 來設定您的實施。

* [Web SDK JavaScript 資料庫](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/library)：引用 CDN 託管的資料庫檔案，或使用您自己的基礎架構來託管資料庫檔案。 在您網站的程式碼內呼叫該資料庫。

* [NPM](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/npm)：使用 NPM 套件管理器在您的網站上安裝 Web SDK。

如需了解更多資訊，請參閱 Experience Platform Web SDK 指南中的「[ Web SDK 安裝概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/overview)」。
