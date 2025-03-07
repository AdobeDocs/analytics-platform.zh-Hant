---
title: 實作適用於 Web SDK 擴充功能的 Loader 標記
description: 瞭解如何為Web SDK擴充功能實作載入器標籤
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 63%

---

# 實作適用於 Web SDK 擴充功能的 Loader 標記 {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="在您的網站上實作 Loader 標記"
>abstract="與您的網站開發團隊合作，在您網站的每個頁面上安裝 Loader 標記。<br><br>此任務的完成時間在很大程度上取決於與您合作部署程式碼的工程團隊之回應時間。某些擁有高適應性工程團隊的組織可以在幾天內完成這個步驟，而擁有大量待辦任務的工程團隊可能需要一個月或更長的時間。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

您必須在要追蹤的網站上安裝標籤，這表示要將程式碼放置在網站範本的標頭標籤中。

以下程式說明如何取得參考您標籤的程式碼。 如需補充資訊，請參閱Experience Platform檔案中的[標籤和事件轉送實作指南](https://experienceleague.adobe.com/en/docs/experience-platform/tags/get-started/implementation-guides)。

若要取得參考標籤的程式碼：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 在&#x200B;**[!UICONTROL 標籤屬性]**&#x200B;頁面上，從屬性清單中選取您新建立的標籤以開啟它。

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

{{upgrade-final-step}}
