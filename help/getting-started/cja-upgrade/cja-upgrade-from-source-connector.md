---
title: 從Analytics來源聯結器移至Web SDK以進行Customer Journey Analytics
description: 瞭解在升級至Customer Journey Analytics時，如何從Analytics來源聯結器移至Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# 從Analytics來源聯結器移至Web SDK以進行Customer Journey Analytics

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

使用Analytics來源聯結器作為Customer Journey Analytics的唯一實作時，有其固有的缺點。 如果您的組織已升級為僅使用Analytics來源聯結器實作的Customer Journey Analytics，您應考慮改用Web SDK實作。

Adobe建議搭配使用Analytics來源聯結器（用於引進歷史資料），以及新的Web SDK實作（用於持續收集資料）。

## 瞭解僅使用Analytics來源聯結器的優缺點

如需有關使用Analytics來源聯結器的優點的資訊，請參閱[僅使用Analytics來源聯結器升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)。

## 從Analytics來源聯結器移至Web SDK

以下是從Analytics來源聯結器移至由Analytics來源聯結器和Web SDK實施所組成的實施的高階流程：

1. 建立Web SDK實作，如[詳細建議升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) (在文章中，[從Adobe Analytics升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md))中所述。

   設定Web SDK實作後，請繼續下列步驟。

1. 決定您要在Web SDK實作中使用Adobe Analytics結構描述或XDM結構描述。

   如需詳細資訊，請參閱[選擇您的Customer Journey Analytics結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

1. （視條件而定）如果您打算使用Adobe Analytics結構描述，請將Analytics來源聯結器自動建立的資料集新增至您的Customer Journey Analytics連線。

   如需詳細資訊，請參閱[將Analytics來源聯結器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

1. （視條件而定）如果您打算建立XDM結構描述：

   1. [為Analytics來源聯結器建立XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。

   1. 將使用原始Analytics來源聯結器自動建立的資料集新增至Customer Journey Analytics連線。

      如需詳細資訊，請參閱[將資料集從您目前的Analytics來源聯結器新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)。

   1. 刪除您原始的Analytics來源聯結器。<!-- need to add steps somewhere about how to do this -->

   1. [建立新的Analytics來源聯結器並對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。








