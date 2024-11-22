---
title: 從Analytics來源聯結器轉換至Web SDK以進行Customer Journey Analytics
description: 瞭解在升級至Customer Journey Analytics時，如何從Analytics來源聯結器轉換至Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 從Analytics來源聯結器轉換至Web SDK以進行Customer Journey Analytics

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

使用Analytics來源聯結器作為Customer Journey Analytics的唯一實作時，有其固有的缺點。

如果您的組織已升級為僅使用Analytics來源聯結器實作的Customer Journey Analytics，您應考慮轉型為使用Analytics來源聯結器的實作（用於引進歷史資料），並結合Web SDK的新實作（用於持續性資料收集）。

## 瞭解僅使用Analytics來源聯結器的優缺點

如需有關使用Analytics來源聯結器的優點的資訊，請參閱[僅使用Analytics來源聯結器升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)。

## 從Analytics來源聯結器轉換至Web SDK

以下是從專門使用Analytics來源聯結器轉換為同時包含Analytics來源聯結器和Web SDK實作的高階程式：

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

1. （條件式）如果您使用查詢資料集，則必須建立查詢資料集並將其新增至您的連線。 如需詳細資訊，請參閱[建立查詢資料集以分類Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)中的資料。

1. 刪除您原始的Analytics來源聯結器。<!-- need to add steps somewhere about how to do this -->

1. [建立新的Analytics來源聯結器並對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。
