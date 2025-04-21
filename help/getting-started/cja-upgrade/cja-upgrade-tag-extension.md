---
title: 建立標記屬性並新增 Web SDK 擴充功能
description: 了解如何建立標記屬性並新增 Web SDK 擴充功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# 將 Web SDK 擴充功能新增至您的標記 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="新增 Platform Web SDK 擴充功能至您的標記屬性"
>abstract="新增 Adobe Experience Platform Web SDK 擴充功能至您的標記屬性。新增 Web SDK 擴充功能至您的標記屬性的程序已經簡化，只需幾分鐘即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您可以使用 Adobe Experience Platform 中的「標籤」功能，在您的網站上實施程式碼以收集資料。此標記管理解決方案可讓您部署程式碼以及其他標記需求。 標籤可使用 Adobe Experience Platform Web SDK 擴充功能與 Adobe Experience Platform 緊密整合。

以下資訊說明如何將 Web SDK 擴充功能新增到您的標記。若要了解補充資訊，請參閱 Experience Platform 文件中的「[設定 Web SDK 標記擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)」。Web SDK 原本就包括 [!UICONTROL Adobe Experience Cloud ID 服務]，因此您不需要新增 ID 服務擴充功能至您的標記中。

您[建立標記](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)以後，您必須使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 擴充功能進行設定。這可確保您可以將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform (透過您的資料流)。

若要新增 Web SDK 擴充功能至您的標記：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「擴充功能」]**。

1. 在頂端列中選取 **[!UICONTROL 「目錄」]**。

1. 搜尋或捲動至 **[!UICONTROL Adobe Experience Platform Web SDK 擴充功能]**，然後選取「**[!UICONTROL 安裝]**」以進行安裝。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. 為您的[!UICONTROL 生產環境]和 (可選) [!UICONTROL 中繼環境]以及[!UICONTROL 開發環境]選取您的沙箱和先前建立的資料流。

   ![AEP Web SDK 擴充功能設定](assets/aepwebsk-extension-datastreams.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

{{upgrade-final-step}}
