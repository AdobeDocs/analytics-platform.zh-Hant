---
title: 處理規則、VISTA和分類與分析源連接器的資料準備
description: 瞭解使用處理規則和VISTA與使用資料準備的資料轉換
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# 處理規則、VISTA和分類與資料準備

Adobe Analytics [處理規則和VISTA規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) 提供了轉換和處理傳入Adobe Analytics的資料的手段 [資料收集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en)。 這些轉換作為Adobe資料處理的一部分，在Adobe Analytics儲存資料以用於報告和分析目的之前進行。

[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) 是一種工具，它允許您將基於行的映射和轉換應用到所接收的資料 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en)。 隨後，該資料被提供給包括CJA和其它應用的Experience Platform。 資料準備與許多平台整合 [源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en)，以及 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。 此連接器提供了將報表套件資料從Adobe Analytics接收到平台的方法。

## 使用資料準備進行進一步轉換 {#data-prep}

由Adobe Analytics收集和儲存的資料可以通過處理規則或VISTA規則或兩者進行轉換。 但隨後通過分析源連接器轉發到平台的報告套件可能會再次使用資料準備進行轉換。 這對於以下幾個目的是可取的：

* **解決在CJA和/或RTCDP中使用的報表套件之間的架構差異**。 例如，假設報告套件A定義了 `eVar1` 「搜索術語」和報告套件B定義 `eVar2` 「搜索術語」。 可以使用資料準備將兩個不同的eVar映射到包含兩個eVar的資料的公用欄位。 這使得 [將不同架構的報表套件組合在一起](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 在 [CJA連接](/help/connections/overview.md) 或用於 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=zh-Hant)。
* **映射 `eVars` 欄位用於語義有意義的名稱**。 `eVars` 和 `props` 通過分析源連接器來到的欄位被映射到 _\_experience.analytics.customDimensions.eVars.eVar1_。 資料準備可用於映射 `eVar` 和 `prop` 欄位到新欄位，這些欄位對您的用戶具有更有意義的名稱，或者與來自其他資料源的名稱匹配。 (這也可以通過其他方法實現，例如更名 [CJA資料視圖](/help/data-views/create-dataview.md)。)
* **通常轉換資料**。 資料準備具有數百個映射函式，可用於根據通過分析源連接器獲得的資料計算和計算新欄位。 您可以將分隔的欄位拆分為單獨的欄位。 可以合併欄位。 你可以操縱字串。 您可以基於規則運算式從欄位中提取資訊，等等。

## 資料準備和分類 {#classifications}

資料準備與 [分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hant) 在某些情況下。

例如，在分隔欄位中，您可以使用「資料準備」將該欄位拆分為多個單獨的欄位，而無需使用分類。 通常，分類是通過上載在傳入分析命中流之外提供的查找檔案向欄位添加元資料的一種方法。

例如，您可以上載將SKU分組為「size」、「brand」、「color」等的分類檔案。 分類與資料準備之間的另一個區別是分類適用於資料 _無論是歷史還是未來_。 另一方面，應用了資料準備映射 _向前_ 到建立映射時的資料。

