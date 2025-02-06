---
title: 評估升級至Customer Journey Analytics後需要Adobe Analytics多久
description: 瞭解如何評估升級至Customer Journey Analytics後需要Adobe Analytics多久
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# 評估升級至Customer Journey Analytics後需要Adobe Analytics多久 {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="完全移至Customer Journey Analytics"
>abstract="（建議）Customer Journey Analytics旨在成為貴組織的主要Analytics工具。 不過，如果貴組織嚴重依賴該工具專屬的功能，且這些工作流程無法變更，則可能仍需要Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="保留兩個分析產品"
>abstract="（不建議）如果選取此選項，則您與Adobe的合約會包含Adobe Analytics和Customer Journey Analytics，而兩者的成本會隨著時間推移而提高。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>此檔案應該用作[Adobe Analytics的Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)的一部分。

大部分組織在升級至Customer Journey Analytics後，最終都會停用Adobe Analytics。 這是因為維護兩個分析環境的成本和複雜性。

不過，Adobe建議您在實作Customer Journey Analytics後，讓Adobe Analytics環境持續執行一段時間。 以下章節說明這樣做的原因，以及停用Adobe Analytics的建議時間。

## 升級期間和之後的Adobe Analytics使用

在決定您的組織是否以及何時應停用Adobe Analytics時，請考慮在升級至Customer Journey Analytics期間和之後使用Adobe Analytics的下列情形：

| 升級期間和升級後使用Adobe Analytics | 解釋 |
|---------|----------|
| 執行並排資料比較 | Adobe建議您在新的Adobe Analytics環境執行並收集資料後，讓Customer Journey Analytics環境維持執行一段時間。 這是將Customer Journey Analytics資料與Adobe Analytics資料並排比較的最佳方式。<p>在您熟悉Customer Journey Analytics環境中的資料之前，請勿停用Adobe Analytics。</p><p>**注意：** Adobe建議針對您的Customer Journey Analytics環境採用新的Web SDK實作，並搭配歷史資料的Analytics來源聯結器。 [了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 保留來自Adobe Analytics的歷史資料 | Adobe建議您在新的Adobe Analytics環境執行並收集資料後，使用Analytics來源聯結器保留Customer Journey Analytics環境一段時間。 這是將歷史Adobe Analytics資料匯入Customer Journey Analytics的最佳方式。<p>當您收集足夠的歷史資料與新的Web SDK實作Customer Journey Analytics後，可以完全移除Analytics來源聯結器。 當您只能信賴使用新Customer Journey AnalyticsWeb SDK實作收集到的歷史資料時，才可以執行此動作。</p><p>**注意：** Adobe建議針對您的Customer Journey Analytics環境採用新的Web SDK實作，並搭配歷史資料的Analytics來源聯結器。 [了解更多](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| 使用資料摘要或其他Adobe Analytics功能 | Customer Journey Analytics中尚未完全提供少部分功能。 如果您需要存取這些功能，您可能需要將Adobe Analytics與Customer Journey Analytics搭配使用，直到這些功能可用為止。 <p>Customer Journey Analytics中未完全提供的功能包括「資料摘要」和「貢獻分析」。 如需尚未提供的完整功能清單，請參閱[Customer Journey Analytics功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)。</p> |

## 停用Adobe Analytics的流程和時間表 {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="停用協力廠商標籤管理系統"
>abstract="透過Web SDK資料完全正常運作，請與您的標籤管理員合作，將AppMeasurement程式庫從您的協力廠商標籤管理系統中移除。<br><br>執行此步驟的預計時間取決於標籤管理產品停用AppMeasurement的容易程度，以及貴組織部署和管理標籤程式碼的發行週期。"

<!-- markdownlint-enable MD034 -->

您現有的Adobe Analytics實作是成功升級至Customer Journey Analytics的關鍵部分，如上節所述，[在升級期間及之後使用Adobe Analytics](#uses-of-adobe-analytics-during-and-after-an-upgrade)。

當您不再需要Adobe Analytics以用於上述用途時，請使用下列資訊來移除Adobe Analytics：

1. 停止使用Adobe Analytics收集資料。

   當您對Adobe Analytics資料和Customer Journey Analytics資料的並排比較感到滿意後，就可以停止在Adobe Analytics實作中收集資料。 新的Adobe Analytics資料將不再透過Analytics來源聯結器流入Customer Journey Analytics。

   不過，在此時間點之前，您從Adobe Analytics環境收集的資料仍可透過Analytics來源聯結器用作Customer Journey Analytics中的歷史資料。

   此程式會因您用來實施Adobe Analytics的資料收集方法而異：

+++ AppMeasurement

   [停用AppMeasurement資料集合](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)。

+++

+++ Analytics擴充功能（標籤）

   停用標籤中的Analytics擴充功能。

+++

+++ API

   停用API資料收集。

+++

+++ 第三方

   請與您的標籤管理員合作，從您的協力廠商標籤管理系統中移除AppMeasurement程式庫。

+++

1. 從資料流中移除Adobe Analytics即服務。

   有了Web SDK資料完整的功能，請與Platform管理員合作，從資料流中移除Adobe Analytics即服務。

   在移除Adobe Analytics as a Service之前，請確定您的Analytics使用者使用Customer Journey Analytics，而不是Adobe Analytics。

1. 完全移除Analytics來源聯結器。

   當您收集足夠的歷史資料與新的Web SDK實作Customer Journey Analytics後，可以完全移除Analytics來源聯結器。

   當您不再需要透過Analytics來源聯結器從Adobe Analytics環境取得歷史資料，而且您可以僅信賴您在新的Web SDK實作中收集的歷史資料時，即可採取此動作。

