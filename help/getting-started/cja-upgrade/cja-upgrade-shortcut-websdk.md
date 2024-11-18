---
title: 升級捷徑移轉AppMeasurement或Analytics擴充功能實作以使用Web SDK
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 83927cf0-b3b4-42b4-9ca5-0c81c091383f
source-git-commit: daa07b603caa613ca49b61c2e8e461d558459f57
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 9%

---

# 升級捷徑：移轉 AppMeasurement 或 Analytics 擴充功能實作以使用 Web SDK {#shortcut-migrate-websdk}

>[!NOTE]
>
>此檔案應該用作[Adobe Analytics的Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)的一部分。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_migrate_aa_to_websdk"
>title="移轉您的 Analytics 實作以使用 Web SDK"
>abstract="您可以透過資料物件以 AppMeasurement 格式傳送所有變數，而非透過 XDM 物件傳送資料。您可以利用此捷徑，繼續使用 AppMeasurement 邏輯將資料傳送到 Platform。"

<!-- markdownlint-enable MD034 -->

升級至Customer Journey Analytics時，Adobe[建議Experience PlatformWeb SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)的新實作。 不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。

如果您的Adobe Analytics實作AppMeasurement或Analytics擴充功能，有升級捷徑可讓您移轉Adobe Analytics實作，以便使用Adobe Experience Platform Web SDK開始傳送資料給Edge Network和Adobe Analytics，然後再傳送給Customer Journey Analytics。

## 優點與缺點

請考量下列升級捷徑的優缺點，以移轉您的AppMeasurement或Analytics擴充功能實作來使用Web SDK：

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在體驗Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Experience Cloud產品(AJO、RTCDP等)之間整合Adobe Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供彈性，以便稍後為您的組織建立XDM結構描述**：您可以移轉現有的Adobe Analytics實作以使用Web SDK並驗證一切都在Adobe Analytics中正常運作，然後建立XDM結構描述。 此彈性可讓Customer Journey Analytics升級更循序漸進、考慮周到。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**技術債**：因為此方法使用您現有實作的修改形式，所以可能更難追蹤實作邏輯並在日後需要時執行變更。 </li></ul> |

{style="table-layout:auto"}

## 基本步驟

如果您決定採取升級捷徑來移轉您的AppMeasurement或Analytics擴充功能實作，以使用Web SDK，則會在[Adobe Analytics中為貴組織新增動態產生的步驟，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。

移轉AppMeasurement或Analytics擴充功能實作以使用Web SDK的基本步驟如下：

1. 開始傳送資料至Platform。

   如果您已使用Adobe Analytics實作將資料傳送至Platform，則不需要執行此步驟。 您只需要在Platform資料集和Customer Journey Analytics之間建立連線，如本程式稍後所述。

1. （選用）隨時為您的組織建立XDM結構描述。

1. （條件式）如果您已建立XDM結構描述，請使用資料流對應來將資料物件中的所有欄位對應到您的XDM結構描述。
