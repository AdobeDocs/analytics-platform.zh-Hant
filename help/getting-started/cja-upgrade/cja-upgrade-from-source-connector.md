---
title: 從 Analytics 來源連接器轉換至適用於 Customer Journey Analytics 的 Web SDK
description: 瞭解在升級至Customer Journey Analytics時，如何從Analytics來源聯結器轉換至Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 30%

---

# 從 Analytics 來源連接器轉換至適用於 Customer Journey Analytics 的 Web SDK {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Analytics 來源連接器實作"
>abstract="Analytics 來源連接器可讓您輕鬆從 Customer Journey Analytics 中獲取價值，但會要求您同時支付 Adobe Analytics 和 Customer Journey Analytics 的費用。此指南可以協助您邁向獨立的 Web SDK 實作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="刪除現有的 Analytics 來源連接器"
>abstract="您目前擁有的 Analytics 來源連接器與您組織的自訂結構描述不相容。但是，此資料仍然存在於 Analytics 報告套裝中。此步驟會移除目前的 Analytics 來源連接器，讓您可以在後續步驟中使用正確的結構描述加以重新建立。<br><br>在刪除來源連接器之前，您可能需要與組織中的其他人員協調，以確保移除來源連接器不會影響組織內的報告。此協調作業可能需要數週才能完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

使用Analytics來源聯結器當作Customer Journey Analytics的唯一實作時，有其固有的缺點。

如果您的組織已僅使用Analytics來源聯結器實作升級至Customer Journey Analytics，Adobe建議轉換為新的Web SDK實作，以持續收集資料，並僅對歷史資料使用Analytics來源聯結器。

## 瞭解僅使用Analytics來源聯結器的優缺點

如需有關使用Analytics來源聯結器的優點的資訊，請參閱[僅使用Analytics來源聯結器升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)。

## 從Analytics來源聯結器轉換至Web SDK

以下是有關從專門使用Analytics來源聯結器轉換為同時包含Analytics來源聯結器和Web SDK實作的高階程式：

1. 建立Web SDK實作，如[詳細建議升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) (在文章中，[從Adobe Analytics升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md))中所述。

   設定Web SDK實作後，請繼續下列步驟。

1. [為Analytics來源聯結器建立XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. 將Analytics來源聯結器中的每個Adobe Analytics維度對應至Web SDK結構描述中的維度。

   1. 
      <!-- how do you get here -->

   1. 在&#x200B;**[!UICONTROL 對應標準欄位]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 自訂]**&#x200B;索引標籤。

   1. 選取&#x200B;**[!UICONTROL 新增對應]**。

      ![對應結構描述欄位](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL Source欄位]**&#x200B;中，從Adobe Analytics ExperienceEvent範本欄位群組中選取Adobe Analytics欄位。 然後，在&#x200B;**[!UICONTROL 目標欄位]**&#x200B;中，選取您要將它對應到的XDM欄位。

   1. 為您在Adobe Analytics中用來收集資料的Adobe Analytics ExperienceEvent範本欄位群組中的每個欄位重複此程式。

1. 將使用原始Analytics來源聯結器自動建立的資料集新增至Customer Journey Analytics連線。

   如需詳細資訊，請參閱[將資料集從您目前的Analytics來源聯結器新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （條件式）如果您使用查詢資料集，則必須建立查詢資料集並將其新增至您的連線。 如需詳細資訊，請參閱[在Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)中建立查詢資料集以分類資料。

1. 刪除您原始的Analytics來源聯結器。<!-- need to add steps somewhere about how to do this -->

1. [建立新的Analytics來源聯結器並對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

{{upgrade-final-step}}
