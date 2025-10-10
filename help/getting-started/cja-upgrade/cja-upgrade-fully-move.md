---
title: 評估升級至 Customer Journey Analytics 後需要使用 Adobe Analytics 多長的時間
description: 了解如何評估升級至 Customer Journey Analytics 後，有多長時間需要使用 Adobe Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 100%

---

# 評估升級至 Customer Journey Analytics 後，何時需要停用 Adobe Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="完全轉移至 Customer Journey Analytics"
>abstract="(建議) Adobe 建議您從 Adobe Analytics 完全轉移至 Customer Journey Analytics。在轉移期間，您應規劃同時使用 Adobe Analytics 和 Customer Journey Analytics，以便執行並列資料對照。資料經確認無誤後，即可停用 Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="保留兩種分析產品"
>abstract="(不建議) 如果您選取此選項，您與 Adobe 簽訂的合約將同時包括 Adobe Analytics 和 Customer Journey Analytics，長時間而言您的組織可能要付出更昂貴的成本。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="停用 Analytics 來源連接器，以僅使用來自 Web SDK 的資料"
>abstract="Analytics 來源連接器是用來提供並排資料比較、歷史資料，以及存取 Customer Journey Analytics 中尚未完全提供的部分功能。您不再需要 Adobe Analytics 用於這些目的時，可以停用 Analytics 來源連接器。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

大多數組織在升級到 Customer Journey Analytics 後，最後將會停用 Adob&#x200B;&#x200B;e Analytics。這是因為維護兩個分析環境的費用高且較複雜。

但是，Adobe 建議您在實施 Customer Journey Analytics 後，讓 Adob&#x200B;&#x200B;e Analytics 環境持續執行一段時間。以下幾個部分內容說明這樣做的原因，以及停用 Adob&#x200B;&#x200B;e Analytics 的建議時間。

## 升級期間和之後使用 Adob&#x200B;&#x200B;e Analytics

在決定您的組織是否以及何時應停用 Adob&#x200B;&#x200B;e Analytics 時，請考慮在升級至 Customer Journey Analytics 期間和之後，以下列方式使用 Adob&#x200B;&#x200B;e Analytics：

| 升級期間和之後使用 Adob&#x200B;&#x200B;e Analytics | 解釋 |
|---------|----------|
| 執行並排的資料比較 | Adobe 建議您在執行全新 Customer Journey Analytics 環境並收集資料後，讓 Adob&#x200B;&#x200B;e Analytics 環境持續執行一段時間。這是將您的 Customer Journey Analytics 資料與 Adob&#x200B;&#x200B;e Analytics 資料並排比較的最佳方法。<p>在您對 Customer Journey Analytics 環境中的資料感到滿意之前，請不要停用 Adob&#x200B;&#x200B;e Analytics。</p><p>**註：**  Adobe 建議為您的 Customer Journey Analytics 環境進行全新的 Web SDK 實施，並將其與用於歷史資料的 Analytics 來源連接器結合使用。[了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 保留 Adobe Analytics 的歷史資料 | Adobe 建議您在執行全新 Customer Journey Analytics 環境並收集資料後，將 Adob&#x200B;&#x200B;e Analytics 環境與 Analytics 來源連接器保留一段時間。這是將歷史 Adob&#x200B;&#x200B;e Analytics 資料納入 Customer Journey Analytics 的最佳方式。<p>使用全新 Web SDK 實施在 Customer Journey Analytics 中收集足夠的歷史資料後，您可以完全移除 Analytics 來源連接器。當您可以完全依賴使用全新 Customer Journey Analytics Web SDK 實施收集的歷史資料時，請執行此操作。</p><p>**註：**  Adobe 建議為您的 Customer Journey Analytics 環境進行全新的 Web SDK 實施，並將其與用於歷史資料的 Analytics 來源連接器結合使用。[了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 使用資料摘要或其他 Adob&#x200B;&#x200B;e Analytics 功能 | Customer Journey Analytics 有一小部分功能尚無法完全使用。如果您需要存取這些功能，可能需要將 Adob&#x200B;&#x200B;e Analytics 與 Customer Journey Analytics 結合使用，直到這些功能可供使用為止。 <p>Customer Journey Analytics 中未完全可使用的功能包括資料摘要和 Contribution Analysis。有關還不能使用的功能完整列表，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)」。</p> |

## 停用 Adobe Analytics 的流程和時間表 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="停用第三方標記管理系統"
>abstract="在 Web SDK 資料完全正常運作的情況下，與您的標記管理員合作從第三方標記管理系統中移除 AppMeasurement 資料庫。<br><br>執行此步驟的預估時間取決於在標記管理產品中停用 AppMeasurement 的難易程度，以及您的組織部署和管理標記代碼的發行週期。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="在標記中停用 Analytics 擴充功能"
>abstract="Web SDK 資料完全可使用後，請與標記管理員合作，將 Adobe Analytics 擴充功能從標記屬性中移除。執行此動作前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="停用 Adobe Analytics 的 API 資料收集"
>abstract="Web SDK 資料完全正常運作後，請與適用的工程團隊合作，將 Adobe Analytics 程式碼從專案中移除。執行此動作前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

您現有的 Adob&#x200B;&#x200B;e Analytics 實施是成功升級至 Customer Journey Analytics 的關鍵部分，如上一節所述， [升級期間及其後使用 Adob&#x200B;&#x200B;e Analytics](#uses-of-adobe-analytics-during-and-after-an-upgrade)。

當您不再需要使用 Adob&#x200B;&#x200B;e Analytics 來達到上節所述的目的時，請使用以下資訊移除 Adob&#x200B;&#x200B;e Analytics：

1. 停止使用 Adob&#x200B;&#x200B;e Analytics 收集資料。

   在您對 Adob&#x200B;&#x200B;e Analytics 資料和 Customer Journey Analytics 資料的並排比較感到滿意後，您可以停止使用 Adob&#x200B;&#x200B;e Analytics 實施的收集資料。全新 Adob&#x200B;&#x200B;e Analytics 資料將不再透過 Analytics 來源連接器流向 Customer Journey Analytics。

   但是，您在此之前從 Adob&#x200B;&#x200B;e Analytics 環境收集的資料，仍然可以透過 Analytics 來源連接器作為 Customer Journey Analytics 中的歷史資料使用。

   此流程會因您用來實施 Adob&#x200B;&#x200B;e Analytics 的資料收集方法而異：

   +++ AppMeasurement

   [停用 AppMeasurement 資料收集](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

   +++

   +++ Analytics 擴充功能 (標籤)

   在標記中停用 Analytics 擴充功能。

   +++

   +++ API

   停用 API 資料收集。

   +++

   +++ 第三方

   與您的標記管理員合作從第三方標記管理系統中移除 AppMeasurement 資料庫。

   +++

1. 將 Adobe Analytics 當作服務從資料流中移除。

   在 Web SDK 資料完全可使用後，與平台管理員合作從資料流中移除 Adob&#x200B;&#x200B;e Analytics。

   在移除 Adob&#x200B;&#x200B;e Analytics 的服務以前，請確保您的 Analytics 使用者是在使用 Customer Journey Analytics 而不是 Adob&#x200B;&#x200B;e Analytics。

1. 完全移除 Analytics 來源連接器。

   使用全新 Web SDK 實施在 Customer Journey Analytics 中收集足夠的歷史資料後，您可以完全移除 Analytics 來源連接器。

   當您不再需要透過 Analytics 來源連接器取得 Adob&#x200B;&#x200B;e Analytics 環境的歷史資料時，請執行此操作，且您可以完全依賴使用全新 Web SDK 實施收集的歷史資料。

{{upgrade-final-step}}

