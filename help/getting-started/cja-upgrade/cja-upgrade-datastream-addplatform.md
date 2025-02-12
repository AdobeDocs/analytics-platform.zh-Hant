---
title: 為Customer Journey Analytics建立結構描述
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 42%

---

# 新增平台即服務至您資料流 {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="將 Adobe Experience Platform 即服務新增至資料流"
>abstract="資料流需要一個或多個服務作為傳送資料的目的地。在您的資料流中設定 Adobe Experience Platform 即服務。<br><br>新增服務至資料流是簡單的流程，僅需幾分鐘即可完成。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics到Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)為您的組織動態產生的升級步驟操作。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

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

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
