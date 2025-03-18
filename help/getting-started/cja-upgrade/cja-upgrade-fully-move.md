---
title: 評估升級至 Customer Journey Analytics 後需要使用 Adobe Analytics 多長的時間
description: 瞭解如何評估升級至Customer Journey Analytics後需要Adobe Analytics多久
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 31%

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
>title="停用 Analytics 來源連接器，以便僅使用來自 Web SDK 的資料"
>abstract="Analytics 來源連接器是用來提供並排資料比較、歷史資料以及存取 Customer Journey Analytics 中未完全提供的部分功能。您不再需要 Adobe Analytics 用於這些目的時，可以停用 Analytics 來源連接器。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

大部分組織在升級至Customer Journey Analytics後，最終都會停用Adobe Analytics。 這是因為維護兩個分析環境的成本和複雜性。

不過，Adobe建議您在實作Customer Journey Analytics後，讓Adobe Analytics環境維持運作一段時間。 以下章節說明這樣做的原因，以及停用Adobe Analytics的建議時間。

## 升級期間和之後的Adobe Analytics使用

在決定您的組織是否以及何時應停用Adobe Analytics時，請考慮在升級至Adobe Analytics期間和之後使用Customer Journey Analytics的下列情形：

| 升級期間和升級後使用Adobe Analytics | 解釋 |
|---------|----------|
| 執行並排資料比較 | Adobe建議您在新的Adobe Analytics環境執行並收集資料後，讓Customer Journey Analytics環境維持執行一段時間。 這是將Customer Journey Analytics資料與Adobe Analytics資料並排比較的最佳方式。<p>在您熟悉Customer Journey Analytics環境中的資料之前，請勿停用Adobe Analytics。</p><p>**注意：** Adobe建議針對您的Customer Journey Analytics環境採用新的Web SDK實作，並搭配歷史資料的Analytics來源聯結器。 [了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 保留來自Adobe Analytics的歷史資料 | Adobe建議您在新的Adobe Analytics環境執行並收集資料後，透過Analytics來源聯結器保留Customer Journey Analytics環境一段時間。 這是將歷史Adobe Analytics資料帶入Customer Journey Analytics的最佳方式。<p>使用新的Web SDK實作在Customer Journey Analytics中收集足夠的歷史資料後，您就可以完全移除Analytics來源聯結器。 當您只能信賴使用新Customer Journey Analytics Web SDK實作收集而來的歷史資料時，才可以執行此動作。</p><p>**注意：** Adobe建議針對您的Customer Journey Analytics環境採用新的Web SDK實作，並搭配歷史資料的Analytics來源聯結器。 [了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 使用資料摘要或其他Adobe Analytics功能 | Customer Journey Analytics中尚未提供一組完整的功能。 如果您需要存取這些功能，您可能需要將Adobe Analytics與Customer Journey Analytics搭配使用，直到這些功能可用為止。 <p>Customer Journey Analytics中尚未完整提供的功能包括資料摘要和貢獻分析。 如需尚未提供的完整功能清單，請參閱[Customer Journey Analytics功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。</p> |

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
>abstract="Web SDK 資料完全可使用後，請與標記管理員合作，將 Adobe Analytics 擴充功能從標記屬性中移除。在執行此動作前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="停用 Adobe Analytics 的 API 資料彙集"
>abstract="Web SDK 資料完全正常運作後，請與適用的工程團隊合作，將 Adobe Analytics 程式碼從專案中移除。在執行此動作前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

您現有的Adobe Analytics實作是成功升級至Customer Journey Analytics的關鍵部分，如上節所述：[升級期間及之後使用Adobe Analytics](#uses-of-adobe-analytics-during-and-after-an-upgrade)。

當您不再需要Adobe Analytics以用於上述用途時，請使用下列資訊來移除Adobe Analytics：

1. 停止使用Adobe Analytics收集資料。

   當您對Adobe Analytics資料和Customer Journey Analytics資料的並排比較感到滿意後，就可以停止在Adobe Analytics實作中收集資料。 新的Adobe Analytics資料將不再透過Analytics來源聯結器流入Customer Journey Analytics。

   不過，您在此時間點之前從Adobe Analytics環境收集的資料，仍可透過Analytics來源聯結器用作Customer Journey Analytics中的歷史資料。

   此程式會因您用來實施Adobe Analytics的資料收集方法而異：

+++ AppMeasurement

   [停用AppMeasurement資料彙集](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

+++

+++ Analytics擴充功能（標籤）

   停用標籤中的Analytics擴充功能。

+++

+++ API

   停用API資料收集。

+++

+++ 第三方

   請與您的標籤管理員合作，從您的協力廠商標籤管理系統移除AppMeasurement資料庫。

+++

1. 從資料流中移除Adobe Analytics即服務。

   有了Web SDK資料完整的功能，請與Platform管理員合作，從資料流中移除Adobe Analytics即服務。

   在移除Adobe Analytics as a Service之前，請確定您的Analytics使用者使用Customer Journey Analytics，而不是Adobe Analytics。

1. 完全移除Analytics來源聯結器。

   使用新的Web SDK實作在Customer Journey Analytics中收集足夠的歷史資料後，您就可以完全移除Analytics來源聯結器。

   當您不再需要透過Analytics來源聯結器從Adobe Analytics環境取得歷史資料，而且您可以僅信賴您在新的Web SDK實作中收集的歷史資料時，即可採取此動作。

{{upgrade-final-step}}

