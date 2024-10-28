---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 30%

---

# 建立資料集以與Customer Journey Analytics搭配使用

>[!NOTE]
>
>完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)後，應使用此檔案。
> 
>您必須先完成先前為您的組織動態產生的所有步驟，才能依照本頁面的步驟操作。
>
>完成此頁面上的步驟後，請繼續依照為您的組織從[Adobe Analytics動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

建立XDM結構描述後，您現在必須定義結構來儲存和管理該資料，這會透過資料集在Adobe Experience Platform中完成。

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

1. 繼續依照從[Adobe Analytics為您的組織動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

