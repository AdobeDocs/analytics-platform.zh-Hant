---
title: 建立您的結構描述以便與 Customer Journey Analytics 搭配使用
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 26%

---

# 建立您的結構描述以便與 Customer Journey Analytics 搭配使用 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="建立結構描述"
>abstract="在您的組織內討論資料收集的需求，並確定您想要如何建置在 Adobe Experience Platform 內使用的結構描述。之所以顯示這個步驟，是因為您要使用推薦流程，即使用針對您組織量身打造的結構描述。正確執行此步驟極為重要，因為組織內所有團隊均遵循一個結構描述，可以十分輕鬆地完成資料攝取。<br><br>將組織中所有相關方整合以便遵循統一的結構描述，預估要花費 1-2 個月時間。這個時間段極度依賴所要協調的團隊數量，以及要遵循的維度 + 量度數量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe建議建立自訂Experience Data Model (XDM)結構描述，以便在從Adobe Analytics升級至Customer Journey Analytics時與Web SDK搭配使用。 或者，您也可以使用預設的Adobe Analytics結構描述，此結構描述會使用Adobe Analytics ExperienceEvent欄位群組。

自訂XDM結構描述可讓您根據組織需求以及您使用的特定平台應用程式量身打造簡化的結構描述。 與使用Adobe Analytics ExperienceEvent欄位群組的預設Adobe Analytics結構描述不同，當需要變更自訂XDM結構描述時，您不必在數千個未使用的欄位中尋找需要更新的欄位。

如需這些結構描述選項的詳細資訊，請參閱[選擇您的Customer Journey Analytics結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

開始建立XDM結構描述時，請檢閱下列章節。

## 避免XDM結構描述中的Adobe Analytics限制

Customer Journey Analytics的底層架構提供比Adobe Analytics更大的彈性。 建立新的XDM結構描述是解鎖靈活性的關鍵方式。 當您升級至Customer Journey Analytics時，請務必避免在結構描述中沿用不必要的Adobe Analytics限制。

>[!NOTE]
>
>下列資訊尚未完成。 這將在不久的將來完成。

| Adobe Analytics資料架構 | XDM結構描述架構 |
|---------|----------|
| 個別量度會新增至Analytics資料架構。<br/>例如，在Adobe Analytics中，您對每個事件有不同的eVar。 | 在資料檢視中建立個別量度，而不是在XDM結構描述中建立。 若日後需要進行變更，這麼做可為提供更大的彈性。<br/>例如，在Customer Journey Analytics中，您在結構描述中有單一事件，並在資料檢視中使用建立事件。 |
| 建立自訂變數需要prop和eVar。 |  |

## 識別您的資料團隊和整個組織的其他利害關係人

>[!NOTE]
>
>此資訊尚未提供。 不久將推出此功能。

## 考慮一下貴組織中使用的其他Adobe Experience Platform應用程式

>[!NOTE]
>
>此資訊尚未提供。 不久將推出此功能。
