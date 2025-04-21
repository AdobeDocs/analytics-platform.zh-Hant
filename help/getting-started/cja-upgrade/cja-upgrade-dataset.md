---
title: 為 Customer Journey Analytics 建立結構描述
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: d686dcdd-08d5-4e8f-8f0d-76c8c7b0427f
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# 建立用於 Customer Journey Analytics 的資料集 {#upgrade-create-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-create"
>title="在 Adobe Experience Platform 中建立資料集"
>abstract="資料集是存放所收集資料的位置。在 Adobe Experience Platform 中建立這個位置。<br><br>根據特定的結構描述建立資料集僅需幾分鐘。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料集是儲存和管理您收集至 Adob&#x200B;&#x200B;e Experience Platform 的資料結構。

若要建立資料集：

1. 在左側邊欄的 Adobe Experience Platform 中，選取[!UICONTROL 「資料管理」]中的&#x200B;**[!UICONTROL 「資料集」]**。

1. 選取&#x200B;**[!UICONTROL 「建立資料集」]**。

   ![建立資料集](assets/create-dataset.png)

1. 選取&#x200B;**[!UICONTROL 「從結構建立資料集」]**。

   ![從結構建立資料集](assets/create-dataset-from-schema.png)

1. 選取您先前建立的結構並選取&#x200B;**[!UICONTROL 「下一個」]**。

1. 為資料集命名，並 (可選) 提供說明。

   ![命名資料集](assets/name-your-datatest.png)

1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 選取&#x200B;**[!UICONTROL 「設定檔」]**&#x200B;切換。

   系統會提示您啟用設定檔的資料集。資料集一經啟用，即可透過攝取的資料豐富即時客戶設定檔。

   >[!IMPORTANT]
   >
   >    只有當資料集所遵循的結構同樣啟用設定檔時，您才能啟用設定檔的資料集。

   ![啟用設定檔結構](assets/aepwebsdk-dataset-profile.png)

   請參閱[資料集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant)，了解如何檢視、預覽、建立和刪除資料集的詳細資訊。您也可了解為即時客戶設定檔啟用資料集的方法。

{{upgrade-final-step}}
