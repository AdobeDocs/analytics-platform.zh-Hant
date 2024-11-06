---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# 建立查詢資料集以分類Customer Journey Analytics中的資料

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

與Adobe Analytics中的分類資料類似，查詢資料集是將資料分類Customer Journey Analytics的方法。

使用Analytics來源聯結器時，某些標準查詢資料集會在報告時自動套用。 如需詳細資訊，請參閱[將標準查詢新增至資料集](/help/connections/standard-lookups.md)。

若要使用Experience Platform Web SDK的新實作方式分類資料，您必須為包含您要分類之資料的每個維度建立查詢資料集。

若要建立查詢資料集以用於Customer Journey Analytics：

1. 在AEP中，建立新結構描述。 這是專用於查詢資料集的新結構描述。 您無法使用現有的結構描述。

1. 您必須建立用於查閱的新結構描述類別。

1. 從中建立查詢資料集。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
