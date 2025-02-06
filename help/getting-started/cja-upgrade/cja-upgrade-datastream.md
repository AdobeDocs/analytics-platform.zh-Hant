---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 20%

---

# 建立資料串流以用於Customer Journey Analytics {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="在Adobe Experience Platform中建立資料串流"
>abstract="資料串流是中間位置，可將您的資料傳遞至所有已設定的服務。 在Adobe Experience Platform中建立此位置。<br><br>在Platform介面中初次建立資料串流只需要幾分鐘的時間。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料流代表實作 Adobe Experience Platform Web 和 Mobile SDK 時的伺服器端設定。使用 Adobe Experience Platform SDK 收集資料時，資料會傳送至 Adobe Experience Platform Edge Network。是決定要將資料轉送至哪些服務的資料流。

在您的設定中，您想要設定資料串流，以將收集的資料傳送至Adobe Experience Platform中的資料集。

>[!NOTE]
>
>只有使用AppMeasurement或Analytics擴充功能（標籤）的Adobe Analytics實作才需要下列步驟。
>
>如果您的Adobe Analytics實作使用Web SDK或Web SDK擴充功能，則Adobe Analytics環境中已存在資料流。

若要設定您的資料流：

1. 在Adobe Experience Platform中，從左側邊欄的[!UICONTROL 資料彙集]中選取&#x200B;**[!UICONTROL 資料串流]**。

1. 選取「**[!UICONTROL 新資料流]**」。

1. 命名並描述您的資料流。從[!UICONTROL 「事件結構」]清單中選取您的結構。

   ![新資料流](assets/new-datastream.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
