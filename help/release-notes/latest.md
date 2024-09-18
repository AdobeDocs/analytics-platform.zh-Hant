---
title: 檢視目前的 Customer Journey Analytics 發行說明
description: 最新的 Customer Journey Analytics 發行說明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 38%

---

# 目前的 Adobe Customer Journey Analytics 發行說明 (2024 年 ９ 月)

**上次更新日期**：2024年9月11日

這些發行說明涵蓋2024年9月11日到10月初的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。因此，這些發行說明每月會更新好幾次。請定期進行檢查。

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在計算量度管理員和篩選器管理員的「用於」欄中的其他資訊** | 計算量度管理員和篩選器管理員中的「使用位置」欄包含下列新報表區域：<ul><li>**Report Builder**：顯示Report Builder中使用的計算量度或篩選器數目。</li><li>**臨時元件**：顯示專案中使用的臨時計算量度或臨時篩選數目。 這些臨時計算量度和篩選器（又稱為「快速計算量度」和「快速篩選器」）只能用於建立它們的專案中，因此會與「用於」欄中的「專案」報告區域分開報告。</li></ul>如需詳細資訊，請參閱[計算量度管理員](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager)和[篩選器管理員](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-filters/manage-filters)。 |  | 2024年9月11日 |
| **警報** | Customer Journey Analytics中的警報可讓您根據變更的百分比或特定資料點收到通知。<p>視您的Customer Journey Analytics封裝而定，您也可以使用要根據異常臨界值觸發的警報。 這些警報（也稱為「智慧型警報」）提供與異常偵測整合的精細控制項，會在您最需要時觸發。</p><p>在Customer Journey Analytics中使用警報的程式幾乎與在Adobe Analytics中使用警報的程式相同。 一個主要差異是 Customer Journey Analytics 未提供每小時警報。會有此項差異是因為可擷取的各種事件資料，僅能以延遲方式完成資料擷取 (通常在資料事件時間之後 3 至 9 小時)。</p><p>如需有關在Adobe Analytics的Customer Journey Analytics中使用警示時差異的詳細資訊，請參閱[警示功能比較](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)。</p><p>若要深入瞭解警示，請參閱[警示概述](/help/components/c-intelligent-alerts/intelligent-alerts.md) |  | 2024年9月13日 |
| **更新Adobe Analytics來源聯結器** | 由於 Analytics 來源連接器完全由 Adobe 管理，因此資料集活動頁面不會顯示有關批次的資訊。您可以透過查看已收錄記錄的相關指標來監控資料的流動。如需詳細資訊，請參閱[建立Analytics資料的來源連線](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)指南。 |  | 現已提供 |
| **使用情況分析** | 瞭解您的組織如何使用Customer Journey Analytics。 啟用此功能會在Adobe Experience Platform中建立資料集，當貴組織中的任何人使用Analysis Workspace時便會收集資料。 系統也會自動建立連線和資料檢視，讓您存取熱門專案型別、最活躍的使用者及專案中最常用的元件等維度。 (文件連結待補充) |  | 2024 年 9 月 18 日 |
| **引導式分析：內嵌於Workspace** | 在Analysis Workspace中將多個引導式分析結合為單一檢視。 (文件連結待補充) | 2024年9月22日 | 2024年10月2日 |


## Customer Journey Analytics 中的修正

AN-352461； AN-355446： AN-355665

## 給 Customer Journey Analytics 管理員的重要通知

| 通知 | 新增或更新通知 | 說明 |
| --- | --- | --- |
| 不適用 | | |

{style="table-layout:auto"}

## 相關資源

* [2024 年的先前 Customer Journey Analytics 發行說明](/help/release-notes/2024.md)
* [Adobe Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hant)
* [串流媒體收集附加元件發行說明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hant)
* [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hant)
* [Customer Journey Analytics 文件更新](/help/release-notes/doc-changes.md)
