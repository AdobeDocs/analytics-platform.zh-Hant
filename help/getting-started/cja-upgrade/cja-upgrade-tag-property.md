---
title: 建立標記屬性並新增 Web SDK 擴充功能
description: 了解如何建立標記屬性並新增 Web SDK 擴充功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 100%

---

# 為您的屬性建立標記 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="在 Adobe Experience Platform 資料收集中建立標記屬性。"
>abstract="使用標記是資料收集的典型標準。在 Adobe Experience Platform 介面中建立標記，以便您可以隨時更新資料收集的變數。<br><br>只需幾分鐘點選數次，標記屬性即可建立完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您可以使用 Adobe Experience Platform 中的「標籤」功能，在您的網站上實施程式碼以收集資料。此標記管理解決方案可讓您部署程式碼以及其他標記需求。 標籤可使用 Adobe Experience Platform Web SDK 擴充功能與 Adobe Experience Platform 緊密整合。

以下資訊說明如何為您的屬性建立標記。若要了解補充資訊，請參閱 Experience Platform 文件中的「[設定 Web SDK 標記擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)」。Web SDK 原本就包括 [!UICONTROL Adobe Experience Cloud ID 服務]，因此您不需要新增 ID 服務擴充功能至您的標記中。

屬性基本上是個容器，當您將標記部署至網站時，在其中裝入擴充功能、規則、資料元素和程式庫。許多人會針對要部署相同標記集的每個網站 (或具有密切關聯的網站群組) 建立屬性。若要了解屬性的更多資訊，請參閱 Experience Platform 資料收集文件中的「[屬性](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/admin/companies-and-properties)」。

若要為您的屬性建立標記：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 選取&#x200B;**[!UICONTROL 「新屬性」]**。

   為標籤命名，選取 **[!UICONTROL Web]** 並輸入域名。選取&#x200B;**[!UICONTROL 「儲存」]**&#x200B;以繼續。

   ![建立屬性](assets/create-property.png)

{{upgrade-final-step}}
