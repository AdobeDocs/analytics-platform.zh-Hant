---
title: 了解升級至 Customer Journey Analytics 時的 Web SDK 實作選項
description: 瞭解升級至Customer Journey Analytics時的Web SDK實作選項
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ac7059e76797b14c00993a2a46aa51b1ebfe6a2
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 38%

---

# 了解升級至 Customer Journey Analytics 時的 Web SDK 實作選項 {#web-sdk-implementation-options}

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
>abstract="(建議) 如果您尚未使用標記，請在您的網站安裝標記 Loader。如果您已使用標記，則可以新增 Web SDK 擴充功能至您的標記屬性。此選項包括在 Adobe Experience Platform 資料收集和第三方標記管理系統中使用標記的實作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="NPM 套件"
>abstract="使用資料收集 API 直接傳送資料至資料流。同時支援未驗證 (用戶端對伺服器) 和已驗證 (伺服器對伺服器) 類型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="為給定的屬性實作 Web SDK"
>abstract="在調查表中選取所需的實施型別，以取得更詳細的指示。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="將 Web SDK 程式庫新增至第三方標記管理系統"
>abstract="透過您的標籤管理系統，與管理員合作，將Web SDK程式庫新增至您的網站。<br><br>此任務的完成時間很大程度上取決於負責您標籤管理系統的個人的回應速度。 新增Web SDK程式庫可能會與相關的實作邏輯搭配使用，並在貴組織的標準發行週期期間部署。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

建議的從Adobe Analytics升級至Customer Journey Analytics程式是Experience Platform Web SDK的新實作，這是Customer Journey Analytics慣用的資料收集方法。

使用Adobe Experience Platform Web SDK有三種受支援的方式：

* [Web SDK標籤延伸模組](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension)： Adobe建議使用此方法。 在您的網站上安裝標籤載入器，然後使用Adobe Experience Platform資料收集UI來設定您的實施。

* [網頁SDK JavaScript程式庫](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)：參考CDN代管的程式庫檔案，或使用您自己的基礎架構代管程式庫檔案。 呼叫網站程式碼中的程式庫。

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm)：使用NPM封裝管理員在您的網站上安裝Web SDK。

如需詳細資訊，請參閱Experience Platform Web SDK指南中的[Web SDK安裝概觀](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview)。



