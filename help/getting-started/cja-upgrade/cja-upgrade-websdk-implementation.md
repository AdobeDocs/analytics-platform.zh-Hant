---
title: 瞭解升級至Customer Journey Analytics時的Web SDK實作選項
description: 瞭解升級至Customer Journey Analytics時的網路SDK實作選項
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# 瞭解升級至Customer Journey Analytics時的Web SDK實作選項 {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Web SDK JavaScript資料庫(alloy.js)"
>abstract="在網站的每個頁面上加入網頁SDK資料庫(alloy.js)。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Web SDK標籤擴充功能"
>abstract="（建議）如果您尚未使用標籤，請在網站上安裝標籤載入器。 如果您已在使用標籤，您可以將網頁SDK擴充功能新增至標籤屬性。 此選項包括使用Adobe Experience Platform Data Collection和協力廠商標籤管理系統中的標籤的實作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM套件"
>abstract="使用資料收集API將資料直接傳送至資料流。 同時支援未驗證（使用者端對伺服器）和已驗證（伺服器對伺服器）的型別。"

<!-- markdownlint-enable MD034 -->

建議的從Adobe Analytics升級為Customer Journey Analytics的程式是Experience PlatformWeb SDK的新實作，這是Customer Journey Analytics的偏好資料收集方法。

使用Adobe Experience Platform Web SDK有三種受支援的方式：

* [Web SDK標籤延伸模組](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)：Adobe建議使用此方法。 在您的網站上安裝標籤載入器，然後使用Adobe Experience Platform資料收集UI來設定您的實施。

* [網頁SDK JavaScript程式庫](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)：參考CDN代管的程式庫檔案，或使用您自己的基礎架構代管程式庫檔案。 呼叫網站程式碼中的程式庫。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm)：使用NPM封裝管理員在您的網站上安裝Web SDK。

如需詳細資訊，請參閱Experience Platform《網頁SDK指南》中的[網頁SDK安裝概觀](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)。



