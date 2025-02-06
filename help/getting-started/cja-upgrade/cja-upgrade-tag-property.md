---
title: 建立標籤屬性並新增網頁SDK擴充功能
description: 瞭解如何建立標籤屬性並新增網頁SDK擴充功能
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 156df830-541d-4c92-9c49-98f346e040a7
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 20%

---

# 為您的屬性建立標記 {#upgrade-tag-property}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-property"
>title="在Adobe Experience Platform資料彙集中建立標籤屬性"
>abstract="使用標籤是資料收集的典型標準。 在Adobe Experience Platform介面中建立標籤，以便您隨時更新資料收集變數。<br><br>只要按幾下即可完成標籤屬性的建立，只需要幾分鐘的時間。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

您可以使用Adobe Experience Platform中的標籤功能，在您的網站上實作程式碼以收集資料。 此標記管理解決方案可讓您部署程式碼以及其他標記需求。 標籤可使用 Adobe Experience Platform Web SDK 擴充功能與 Adobe Experience Platform 緊密整合。

以下資訊說明如何為屬性建立標籤。 如需補充資訊，請參閱Experience Platform檔案中的[設定Web SDK標籤擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)。 Web SDK原生包含[!UICONTROL Adobe Experience Cloud ID服務]，因此您不需要將ID服務擴充功能新增至標籤。

屬性基本上是個容器，當您將標記部署至網站時，在其中裝入擴充功能、規則、資料元素和程式庫。許多人會針對要部署相同標籤集的每個網站（或一組密切相關的網站）建立屬性。 如需屬性的詳細資訊，請參閱Experience Platform資料收集檔案中的[屬性](https://experienceleague.adobe.com/en/docs/experience-platform/tags/admin/companies-and-properties)。

若要為屬性建立標籤：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 選取&#x200B;**[!UICONTROL 「新屬性」]**。

   為標籤命名，選取 **[!UICONTROL Web]** 並輸入域名。選取&#x200B;**[!UICONTROL 「儲存」]**&#x200B;以繼續。

   ![建立屬性](assets/create-property.png)

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
