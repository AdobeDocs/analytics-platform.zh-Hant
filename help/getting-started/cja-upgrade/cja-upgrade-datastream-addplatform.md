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
source-wordcount: '318'
ht-degree: 29%

---

# 將Platform作為服務新增到您的資料流

>[!NOTE]
>
>完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)後，應使用此檔案。
> 
>您必須先完成先前為您的組織動態產生的所有步驟，才能依照本頁面的步驟操作。
>
>完成此頁面上的步驟後，請繼續依照為您的組織從[Adobe Analytics動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

在您完成本節中的步驟之前，資料流應該已經存在。 資料串流的建立時間和方式取決於您的Adobe Analytics實作，如下所示：

* 如果您的Adobe Analytics實作使用Web SDK或Web SDK擴充功能，則在升級程式之前，資料流可用於Adobe Analytics環境。

* 對於其他Adobe Analytics實作，建立資料串流是升級程式的一部分，如[建立資料串流以搭配Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)使用中所述。

有了可用的資料流，您需要將Platform新增為服務：

1. 在 Adobe Experience Platform UI 中，從左側邊欄的[!UICONTROL 「資料收集」]中選取&#x200B;**[!UICONTROL 「資料流」]**。

1. 選取先前設定的資料流。<!--true?-->

1. 選取&#x200B;**[!UICONTROL 「新增服務」]**。

1. 在[!UICONTROL 「新增服務畫面」]中：

   1. 從[!UICONTROL 「服務」]清單中選取&#x200B;**[!UICONTROL 「Adobe Experience Platform」]**。

   1. 確保已選取&#x200B;**[!UICONTROL 「啟用」]**。

   1. 從[!UICONTROL 「事件資料集」]清單中選取您的資料集。

      ![資料流 AEP 服務](./assets/datastream-aep-service.png)

   1. 保留其他設定並選取&#x200B;**[!UICONTROL 「儲存」]**&#x200B;以儲存資料流。

   您的資料流現在已設定為將從您網站收集的資料轉送至 Adobe Experience Platform 中的資料集。

   請參閱[資料流概觀](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html)，了解如何設定資料流以及如何處理敏感資料的詳細資訊。

1. 繼續依照從[Adobe Analytics為您的組織動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
