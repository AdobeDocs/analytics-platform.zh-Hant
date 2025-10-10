---
title: 從第三方分析解決方案升級至 Customer Journey Analytics
description: 了解如何從第三方分析解決方案升級至 Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 100%

---

# 從第三方分析解決方案升級至 Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="非 Adobe Analytics 產品"
>abstract="為一種實作方式，會收集 Adobe Analytics 以外產品 (例如 Google Analytics) 的資料。從非 Adobe Analytics 產品升級至 Customer Journey Analytics 時，選取此選項會停用升級指南中多個不適用的選項。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

從 Adobe Analytics 以外的解決方案升級至 Customer Journey Analytics 的推薦流程是 Experience Platform Web SDK 的新實施，這是較適合 Customer Journey Analytics 的資料收集方法。結合 Web SDK 後，Adobe 也建議將第三方分析解決方案的歷史資料攝取至 Adob&#x200B;&#x200B;e Experience Platform。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

從第三方分析解決方案 (如 Google Analytics) 移動至 Customer Journey Analytics 時，請使用下列流程：

1. 請依循[詳細的建議升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)執行。

   這些步驟適合從 Adobe Analytics 升級的組織。執行這些步驟時，請了解以下內容：

   * 您必須建立一個資料流。

   * 您無法從非 Adobe Analytics 解決方案移轉專案和元件。

   * 根據您的分析解決方案，可能會有一個來源連接器可用於攝取歷史資料。如需詳細資訊，請參閱 Experience Platform 文件中[來源連接器概觀](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/home)內的[分析](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/home#analytics)。


如果您需要更具體的建議、指引或支援，請聯絡您的 Adobe 代表。

