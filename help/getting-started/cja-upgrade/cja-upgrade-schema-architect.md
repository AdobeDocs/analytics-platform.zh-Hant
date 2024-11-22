---
title: 架構您的結構以用於Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# 架構您的結構以用於Customer Journey Analytics

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

Adobe建議在升級至Customer Journey Analytics時建立Experience Data Model (XDM)結構描述。 XDM結構描述可讓您根據組織需求以及您使用的特定平台應用程式量身打造簡化的結構描述。 當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。

開始建立XDM結構描述時，請檢閱下列章節。

## 避免XDM結構描述中的Adobe Analytics限制

Customer Journey Analytics的底層架構提供比Adobe Analytics更大的彈性。 建立新的XDM結構描述是解鎖靈活性的關鍵方式。 當您升級至Customer Journey Analytics，請務必避免在結構描述中沿用不必要的Adobe Analytics限制。

| Adobe Analytics資料架構 | XDM結構描述架構 |
|---------|----------|
| 個別量度會新增至Analytics資料架構。<br/>例如，在Adobe Analytics中，您對每個事件有不同的eVar。 | 在資料檢視中建立個別量度，而不是在XDM結構描述中建立。 若日後需要進行變更，這麼做可為提供更大的彈性。<br/>例如，在Customer Journey Analytics中，您在結構描述中有單一事件，並在資料檢視中使用建立事件。 |
| 建立自訂變數需要prop和eVar。 | B2 |
| A3 | B3 |

## 識別您的資料團隊和整個組織的其他利害關係人


## 考慮一下貴組織中使用的其他Adobe Experience Platform應用程式



1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
