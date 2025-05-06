---
title: 從 Analytics 來源連接器轉換至適用於 Customer Journey Analytics 的 Web SDK
description: 了解升級到 Customer Journey Analytics 時如何從 Analytics 來源連接器轉變換為 Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# 從 Analytics 來源連接器轉變至適用於 Customer Journey Analytics 的 Web SDK {#transition-from-source-connector}

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

使用 Analytics 來源連接器做為 Customer Journey Analytics 的唯一實施方式有其既存的缺點。

如果您的組織僅透過 Analytics 來源連接器實施升級至 Customer Journey Analytics，Adobe 建議在持續資料收集方面改為使用新的 Web SDK 實施，唯有在歷史資料上使用 Analytics 來源連接器。

## 了解僅使用 Analytics 來源連接器的優點和缺點

有關使用 Analytics 來源連接器的優缺點資訊，請參閱「[僅使用 Analytics 來源連接器以升級至 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md)」。

## 從 Analytics 來源連接器轉變為 Web SDK

以下高層級流程是從僅使用 Analytics 來源連接器轉變為由 Analytics 來源連接器和 Web SDK 實施合併組成的實施：

1. 建立 Web SDK 實施，如文章從 [Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) 中的[詳細建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)所述。

   Web SDK 實施設定完成後，請繼續進行以下步驟。

1. [建立 Analytics 來源連接器的 XDM 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

1. 將 Analytics 來源連接器中的每個 Adob&#x200B;&#x200B;e Analytics 維度對應到 Web SDK 結構描述中的維度。

   1. &#x200B;
      <!-- how do you get here -->

   1. 在「**[!UICONTROL 對應標準欄位]**」部分中，選取「**[!UICONTROL 自訂]**」索引標籤。

   1. 選取「**[!UICONTROL 新增對應]**」。

      ![對應結構描述欄位](assets/schema-mapping.png)

   1. 在「**[!UICONTROL 來源欄位]**」中，從 Adob&#x200B;&#x200B;e Analytics ExperienceEvent 範本欄位組中選取一個 Adob&#x200B;&#x200B;e Analytics 欄位。然後，在&#x200B;**[!UICONTROL 目標欄位]**&#x200B;中，選取要對應的 XDM 欄位。

   1. 對於用來 Adob&#x200B;&#x200B;e Analytics 中收集資料的 Adob&#x200B;&#x200B;e Analytics ExperienceEvent 範本欄位群組中，每個欄位都需要重複進行此程序。

1. 將使用原始 Analytics 來源連接器自動建立的資料集新增至 Customer Journey Analytics 連線。

   如需了解更多資訊，請參閱「[將目前 Analytics 來源連接器中的資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)」。

1. (條件) 如果您使用查詢資料集，則必須建立查詢資料集並將其新增至您的連線。若需要更多資訊，請參閱「[建立查詢資料集來將 Customer Journey Analytics 的資料分類](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)」。

1. 刪除原始 Analytics 來源連接器。 <!-- need to add steps somewhere about how to do this -->

1. [建立 Analytics 來源連接器和對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

{{upgrade-final-step}}
