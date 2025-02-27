---
title: 為Customer Journey Analytics建立結構描述
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 48%

---

# 建立用於 Customer Journey Analytics 的資料流 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="在 Adobe Experience Platform 中建立資料流"
>abstract="資料流是將您的資料傳送至所有已設定服務的中介位置。在 Adobe Experience Platform 中建立這個位置。<br><br>在平台介面中初次建立資料流只需幾分鐘。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料流代表實作 Adobe Experience Platform Web 和 Mobile SDK 時的伺服器端設定。使用 Adobe Experience Platform SDK 收集資料時，資料會傳送至 Adobe Experience Platform Edge Network。是決定要將資料轉送至哪些服務的資料流。

在您的設定中，您想要設定資料串流，以將收集的資料傳送至Adobe Experience Platform中的資料集。

>[!NOTE]
>
>下列步驟僅適用於使用AppMeasurement或Analytics擴充功能（標籤）的Adobe Analytics實施。
>
>如果您的Adobe Analytics實作使用Web SDK或Web SDK擴充功能，則Adobe Analytics環境中已存在資料流。

若要設定您的資料流：

1. 在Adobe Experience Platform中，從左側邊欄的[!UICONTROL 資料彙集]中選取&#x200B;**[!UICONTROL 資料串流]**。

1. 選取「**[!UICONTROL 新資料流]**」。

1. 命名並描述您的資料流。從[!UICONTROL 「事件結構」]清單中選取您的結構。

   ![新資料流](assets/new-datastream.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
