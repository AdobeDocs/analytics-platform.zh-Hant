---
title: 實作Web SDK擴充功能的載入器標籤
description: 瞭解如何為Web SDK擴充功能實作載入器標籤
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 937a7f31361027438929194f8ccc5aee83c33bc0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 34%

---

# 實作Web SDK擴充功能的載入器標籤

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

您必須在要追蹤的網站上安裝標籤，這表示要將程式碼放置在網站範本的標頭標籤中。

以下程式說明如何取得參考您標籤的程式碼。 如需補充資訊，請參閱Experience Platform檔案中的[標籤和事件轉送的實作指南](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides)。

若要取得參考標籤的程式碼：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「環境」]**。

1. 從環境清單中，選取正確的安裝 (框) 按鈕。

   在[!UICONTROL 「Web 安裝指示」]對話框中，選取指令碼旁的複製按鈕，如下所示：

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![環境](assets/environment.png)

1. 選取&#x200B;**[!UICONTROL 「關閉」]**。

   您可以根據您部署 Adobe Experience Platform Web SDK 的流程，選取其他環境 (中繼、生產)，而非開發環境的程式碼。

   如需詳細資訊，請參閱[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?)。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。