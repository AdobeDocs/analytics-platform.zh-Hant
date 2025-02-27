---
title: 建立標籤屬性並新增網頁SDK擴充功能
description: 瞭解如何建立標籤屬性並新增網頁SDK擴充功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 382d2b00-939a-4fff-be02-7a98d457a455
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 40%

---

# 將 Web SDK 擴充功能新增至您的標記 {#upgrade-tag-extension}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-extension"
>title="新增 Platform Web SDK 擴充功能至您的標記屬性"
>abstract="新增 Adobe Experience Platform Web SDK 擴充功能至您的標記屬性。新增 Web SDK 擴充功能至您的標記屬性的程序已經簡化，只需幾分鐘即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您可以使用Adobe Experience Platform中的標籤功能，在您的網站上實作程式碼以收集資料。 此標記管理解決方案可讓您部署程式碼以及其他標記需求。 標籤可使用 Adobe Experience Platform Web SDK 擴充功能與 Adobe Experience Platform 緊密整合。

下列資訊說明如何將Web SDK擴充功能新增至您的標籤。 如需補充資訊，請參閱Experience Platform檔案中的[設定Web SDK標籤擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)。 Web SDK原生包含[!UICONTROL Adobe Experience Cloud ID服務]，因此您不需要將ID服務擴充功能新增至標籤。

在您[建立標籤](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)之後，您必須使用Adobe Experience Platform Web SDK擴充功能來設定標籤。 這可確保您可以（透過資料流）將資料傳送至Adobe Experience Platform。

若要將網頁SDK擴充功能新增至您的標籤：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「擴充功能」]**。

1. 在頂端列中選取 **[!UICONTROL 「目錄」]**。

1. 搜尋或捲動至&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK擴充功能]**，然後選取「安裝」**[!UICONTROL 以安裝]**。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. 為您的[!UICONTROL 生產環境]和 (可選) [!UICONTROL 中繼環境]以及[!UICONTROL 開發環境]選取您的沙箱和先前建立的資料流。

   ![AEP Web SDK 擴充功能設定](assets/aepwebsk-extension-datastreams.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
