---
title: 了解 Customer Journey Analytics 獨有的功能
description: 了解關於 Customer Journey Analytics 專屬的獨特功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 100%

---

# 了解 Customer Journey Analytics 獨有的功能 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="將不同來源的資料相結合"
>abstract="(建議) 將來自各種網路、行動和離線屬性的資料相結合，以建立單一、整合的客戶行為檢視。這種結合來自其他管道之分析資料的功能，是 Customer Journey Analytics 的主要使用案例。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="拼接來自多個資料集的相符項目"
>abstract="如果您有任何資料集不共用主要識別碼 (例如 Experience Cloud ID)，您仍然可以使用其他維度 (例如登入使用者名稱或電子郵件地址) 拼接該資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="聯絡 Adobe 客戶服務以產生拼接資料集"
>abstract="如果您的某個欄位包含存在於多個資料集中但並非主要識別碼的識別碼，則可以使用該識別碼產生具有一致識別碼的新資料集。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="與 Real-Time CDP 整合"
>abstract="結合來自多個來源的設定檔資料，根據使用者特徵產生受眾和細分。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="暫時與 Adobe Target 整合"
>abstract="針對個人化使用案例，Adobe 建議與 Adobe Journey Optimizer 整合。與 Adobe Target 整合為可行的做法，但僅是短期的解決方案。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="與 Journey Optimizer 整合"
>abstract="為客戶帶來相互連結的情境式個人化體驗。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="暫時與 Adobe Audience Manager 整合"
>abstract="針對以受眾為基礎的使用案例，Adobe 建議與 Adobe Real-Time CDP 整合。與 Audience Manager 整合為可行的做法，但僅是短期的解決方案。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

以下列表僅顯示升級過程中需要考慮的 Customer Journey Analytics 功能。關於顯示哪些 Adobe Analytics 功能在 Customer Journey Analytics 中完全支援、部分支援或不支援的完整清單，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)」。

當您升級到 Customer Journey Analytics 時，請考慮要採用下列哪些 Customer Journey Analytics 功能：

| Customer Journey Analytics 功能 | 函數 |
|---------|----------|
| [將網路資料與其他管道的資料 (例如呼叫中心資料) 連結起來](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics 可結合 Experience Platform 的功能，儲存各種資料結構描述和類型。使用 [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-hant)，能以統一方式呈現和組織資料，可進行組合和探索。Adobe Analytics 主要專注於 Web 和行動分析資料，並具有一些[匯入資料](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=zh-hant)的功能。 |
| [使用自訂維度來拼接其他資料集中的點擊](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics 可讓您[組合多個報告套件的資料](/help/connections/combined-dataset.md)，如同 Adobe Analytics 中的單一報告套件。 |
| [與 Adobe Real-time CDP 整合](/help/components/audiences/audiences-overview.md) | 您可以建立客群，並將於 Customer Journey Analytics 中所發現的[客群發佈](/help/components/audiences/audiences-overview.md)至 Adobe Experience Platform 中的 Real-Time Customer Profile，用於客戶目標選擇和個人化。 |
| [與 Adobe Target (A4T) 整合](/help/integrations/at.md) | Customer Journey Analytics 中的目標選擇報告讓您可以直接在 Customer Journey Analytics 內[衡量及報告 Adobe Target 活動](/help/integrations/at.md)。不過，針對個人化使用案例，Adobe 建議與 Adobe Journey Optimizer 整合。 |
| [與 Adobe Journey Optimizer 整合](/help/integrations/ajo.md) | 您可以設定 Journey Optimizer 產生的資料，用於[在 Customer Journey Analytics 中執行進階分析](/help/integrations/ajo.md)。 |
| [與 Adobe Audience Manager 整合](https://experienceleague.adobe.com/zh-hant/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | 您可以[將 Audience Manager 特徵和區段共用至 Adobe Experience Platform](https://experienceleague.adobe.com/zh-hant/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing)。不過，針對以客群為基礎的使用案例，Adobe 建議與 Adobe Real-Time CDP 整合。 |
