---
title: 升級捷徑移轉AppMeasurement或Analytics擴充功能實作以使用Web SDK
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8ef60cc3918b79919674e3c0478a2c1b1bd21d27
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# 升級捷徑：移轉AppMeasurement或Analytics擴充功能實施，以使用Web SDK {#shortcut-migrate-websdk}

>[!NOTE]
>
>此檔案應該用作[Adobe Analytics的Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="移轉Analytics實作以使用Web SDK"
>abstract="您可以透過資料物件以AppMeasurement格式傳送所有變數，而不需透過XDM物件傳送資料。 此捷徑可讓您繼續使用AppMeasurement邏輯將資料傳送至Platform。"

<!-- markdownlint-enable MD034 -->

When upgrading to Customer Journey Analytics, Adobe [recommends a new implementation of the Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). 不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。

If your Adobe Analytics implementation is AppMeasurement or the Analytics extension, an upgrade shortcut is available that allows you to migrate your Adobe Analytics implementation to use the Adobe Experience Platform Web SDK to begin sending data to Edge Network and Adobe Analytics, prior to sending it to Customer Journey Analytics.

## Advantages and disadvantages

請考量下列升級捷徑的優缺點，以移轉您的AppMeasurement或Analytics擴充功能實作來使用Web SDK：

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在體驗Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Experience Cloud產品(AJO、RTCDP等)之間整合Adobe Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供彈性，以便稍後為您的組織建立XDM結構描述**：您可以移轉現有的Adobe Analytics實作以使用Web SDK並驗證一切都在Adobe Analytics中正常運作，然後建立XDM結構描述。 此彈性可讓Customer Journey Analytics升級更循序漸進、考慮周到。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**技術債**：因為此方法使用您現有實作的修改形式，所以可能更難追蹤實作邏輯並在日後需要時執行變更。 </li></ul> |

{style="table-layout:auto"}

## Basic steps

If you decide to take the upgrade shortcut to migrate your AppMeasurement or Analytics extension implementation to use the Web SDK, a new step is added to the dynamically generated steps for your organization in the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

The basic steps for migrating an AppMeasurement or Analytics extension implementation to use the Web SDK are:

1. 開始傳送資料至Platform。

   如果您已使用Adobe Analytics實作將資料傳送至Platform，則不需要執行此步驟。 您只需要在Platform資料集和Customer Journey Analytics之間建立連線，如本程式稍後所述。

1. （選用）隨時為您的組織建立XDM結構描述。

1. （條件式）如果您已建立XDM結構描述，請使用資料流對應來將資料物件中的所有欄位對應到您的XDM結構描述。

