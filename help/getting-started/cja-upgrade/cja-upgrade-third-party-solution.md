---
title: 從第三方分析解決方案升級至 Customer Journey Analytics
description: 瞭解如何從第三方分析解決方案升級至Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 16%

---

# 從第三方分析解決方案升級至 Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="非 Adobe Analytics 產品"
>abstract="為一種實作方式，會收集 Adobe Analytics 以外產品 (例如 Google Analytics) 的資料。選取此選項會停用升級指南中的多個選項，這些選項在從非Adobe Analytics產品升級至Customer Journey Analytics時並不適用。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

建議的從Adobe Analytics以外的分析解決方案升級為Customer Journey Analytics的程式，是Experience Platform Web SDK的新實作，這是Customer Journey Analytics慣用的資料收集方法。 結合使用Web SDK時，Adobe也建議將協力廠商分析解決方案的歷史資料擷取至Adobe Experience Platform。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

從協力廠商分析解決方案(例如Google Analytics)移至Customer Journey Analytics時，請使用下列程式：

1. 請依照[詳細的建議升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)操作。

   這些步驟適用於從Adobe Analytics升級的組織。 依照下列步驟操作時，請瞭解下列內容：

   * 您必須建立資料串流。

   * 您無法從非Adobe Analytics解決方案移轉專案和元件。

   * 根據您的分析解決方案，來源聯結器可能可用於擷取歷史資料。 如需詳細資訊，請參閱Experience Platform檔案中[Source聯結器總覽](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)中的[Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics)。


如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

