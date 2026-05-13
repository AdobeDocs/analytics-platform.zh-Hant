---
title: 為 Customer Journey Analytics 建立結構描述
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f76d098d-d223-40e4-be81-d28e7581396b
TQID: https://experienceleague.adobe.com/s-wqiMU0z0Q5h6qdsqtMPfjdelvqoaAg4rNkvhUEN-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 100%

---

# 建立用於 Customer Journey Analytics 的資料流 {#upgrade-create-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-datastream-create"
>title="在 Adobe Experience Platform 中建立資料流"
>abstract="資料流是將您的資料傳送至所有已設定服務的中介位置。 在 Adobe Experience Platform 中建立此位置。<br><br>在平台介面中初次建立資料流只需幾分鐘。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

資料流代表實作 Adobe Experience Platform Web 和 Mobile SDK 時的伺服器端設定。 使用 Adobe Experience Platform SDK 收集資料時，資料會傳送至 Adobe Experience Platform Edge Network。 此資料流決定資料要轉送到哪些服務。

在設定中，您想設定資料流以傳送收集的資料至您在 Adobe Experience Platform 中的資料集。

>[!NOTE]
>
>以下步驟僅適用於使用 AppMeasurement 或 Analytics 擴充功能 (標記) 的 Adob&#x200B;&#x200B;e Analytics 實施。
>
>如果您的 Adob&#x200B;&#x200B;e Analytics 實施使用 Web SDK 或 Web SDK 擴充功能，則資料流已存在於您的 Adob&#x200B;&#x200B;e Analytics 環境中。

若要設定您的資料流：

1. 在 Adobe Experience Platform 中，從左側邊欄的「[!UICONTROL 資料收集]」中選取「**[!UICONTROL 資料收集]**」。

1. 選取「**[!UICONTROL 新資料流]**」。

1. 命名並描述您的資料流。 從[!UICONTROL 「事件結構描述」]清單中選取您的結構描述。

   ![新資料流](assets/new-datastream.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

{{upgrade-final-step}}
