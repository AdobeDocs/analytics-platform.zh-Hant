---
title: 建立您的結構描述以便與 Customer Journey Analytics 搭配使用
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 91%

---

# 建立您的結構描述以便與 Customer Journey Analytics 搭配使用 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="建立結構描述"
>abstract="在您的組織內討論資料收集的需求，並確定您想要如何建置在 Adobe Experience Platform 內使用的結構描述。之所以顯示這個步驟，是因為您要使用推薦流程，即使用針對您組織量身打造的結構描述。正確執行此步驟極為重要，因為組織內所有團隊均遵循一個結構描述，可以十分輕鬆地完成資料攝取。<br><br>將組織中所有相關方整合以便遵循統一的結構描述，預估要花費 1-2 個月時間。這個時間段極度依賴所要協調的團隊數量，以及要遵循的維度 + 量度數量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

從 Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics 時，Adobe 建議建立自訂體驗資料模型 (XDM) 結構描述，以便與 Web SDK 搭配使用。或者，您可以使用預設 Adob&#x200B;&#x200B;e Analytics 結構描述，且該結構描述是使用 Adob&#x200B;&#x200B;e Analytics ExperienceEvent 欄位群組。

自訂 XDM 結構描述允許根據您的組織需求和您使用的特定平台應用程式量身定制的簡化結構描述。與使用 Adob&#x200B;&#x200B;e Analytics ExperienceEvent 欄位群組的預設 Adob&#x200B;&#x200B;e Analytics 結構描述不同，當需要變更自訂 XDM 結構描述時，您不必篩選數千個未使用的欄位來尋找需要更新的欄位。

有關這些結構描述選項的更多資訊，請參閱「[選擇您的 Customer Journey Analytics 結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)」。

在開始建構 XDM 結構描述時，請查看以下部分。

## 避免 XDM 結構描述中的 Adob&#x200B;&#x200B;e Analytics 限制

比起 Adob&#x200B;&#x200B;e Analytics，Customer Journey Analytics 基本架構提供更大的靈活性。建立新的 XDM 結構描述是取得這種靈活性的關鍵方法。當您升級到 Customer Journey Analytics 時，請確保避免將不必要的 Adob&#x200B;&#x200B;e Analytics 限制帶入您的結構描述中。

>[!NOTE]
>
>下列資訊尚未完成。 這將在不久的將來完成。

| Adobe Analytics 資料架構 | XDM 結構描述架構 |
|---------|----------|
| 個別量度會加入 Analytics 資料架構中。<br/>例如，在 Adob&#x200B;&#x200B;e Analytics 中，每個事件都有不同的 eVar。 | 在資料檢視中建立個別指量度，而不是在 XDM 結構描述中建立。如果您以後需要進行變更，這樣做可以提供更大靈活性。<br/>例如，在 Customer Journey Analytics 中，您在結構描述中有一個事件，並在資料檢視中使用建立事件。 |
| 建立自訂變數需要 prop 和 eVar。 |  |

## 確定您的資料團隊以及整個組織內的其他利害關係人

>[!NOTE]
>
>此資訊尚未提供。 不久將推出此功能。

## 考慮您組織中使用的其他 Adob&#x200B;&#x200B;e Experience Platform 應用程式

>[!NOTE]
>
>此資訊尚未提供。 不久將推出此功能。
