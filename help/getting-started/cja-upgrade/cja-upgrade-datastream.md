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
source-wordcount: '229'
ht-degree: 35%

---

# 建立資料串流以用於Customer Journey Analytics

>[!NOTE]
>
>完成[Adobe Analytics以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)後，應使用此檔案。
> 
>您必須先完成先前為您的組織動態產生的所有步驟，才能依照本頁面的步驟操作。
>
>完成此頁面上的步驟後，請繼續依照為您的組織從[Adobe Analytics動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料流代表實作 Adobe Experience Platform Web 和 Mobile SDK 時的伺服器端設定。使用 Adobe Experience Platform SDK 收集資料時，資料會傳送至 Adobe Experience Platform Edge Network。是決定要將資料轉送至哪些服務的資料流。

在設定中，您想要將從網站收集的資料傳送至 Adobe Experience Platform 中的資料集。

若要設定您的資料流：

1. 在Adobe Experience Platform中，從左側邊欄的[!UICONTROL 資料彙集]中選取&#x200B;**[!UICONTROL 資料串流]**。

1. 選取「**[!UICONTROL 新資料流]**」。

1. 命名並描述您的資料流。從[!UICONTROL 「事件結構」]清單中選取您的結構。

   ![新資料流](assets/new-datastream.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續依照從[Adobe Analytics為您的組織動態產生的升級步驟來Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

