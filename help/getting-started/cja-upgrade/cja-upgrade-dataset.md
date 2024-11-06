---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 33%

---

# 建立資料集以與Customer Journey Analytics搭配使用

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料集是儲存和管理您收集到Adobe Experience Platform中之資料的建構。

若要建立資料集：

1. 在Adobe Experience Platform的左側邊欄中，選取[!UICONTROL 資料管理]中的&#x200B;**[!UICONTROL 資料集]**。

1. 選取&#x200B;**[!UICONTROL 「建立資料集」]**。

   ![建立資料集](assets/create-dataset.png)

1. 選取&#x200B;**[!UICONTROL 「從結構建立資料集」]**。

   ![從結構建立資料集](assets/create-dataset-from-schema.png)

1. 選取您先前建立的結構並選取&#x200B;**[!UICONTROL 「下一個」]**。

1. 為資料集命名，並 (可選) 提供說明。

   ![命名資料集](assets/name-your-datatest.png)

1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 選取&#x200B;**[!UICONTROL 「輪廓」]**&#x200B;切換。

   系統會提示您啟用輪廓的資料集。資料集一經啟用，即可透過攝取的資料豐富即時客戶輪廓。

   >[!IMPORTANT]
   >
   >    只有當資料集所遵循的結構同樣啟用輪廓時，您才能啟用輪廓的資料集。

   ![啟用輪廓結構](assets/aepwebsdk-dataset-profile.png)

   如需更多有關如何檢視、預覽、建立和刪除資料集的資訊，請參閱[資料集UI指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant)。 您也可以瞭解如何為即時客戶個人檔案啟用資料集。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

