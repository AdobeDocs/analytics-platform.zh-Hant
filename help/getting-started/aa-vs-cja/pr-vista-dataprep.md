---
title: 處理規則、VISTA 和分類與 Analytics 來源連接器的「資料準備」的比較
description: 了解使用處理規則和 VISTA 以及使用「資料準備」的資料轉換的異同
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 95%

---

# 處理規則、VISTA 和分類與「資料準備」的比較

Adobe Analytics [處理規則和 VISTA 規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=zh-Hant)提供一種轉換和操作傳遞到 Adobe Analytics [資料彙集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=zh-Hant)中資料的方法。 這些轉換屬於將資料儲存到 Adobe Analytics (以用於報告和分析) 之前的 Adobe 資料處理的一部分。

[「資料準備」](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)是一種工具，可讓您將根據列的對應和轉換套用到擷取至 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=zh-Hant) 的資料上。 隨後，資料即可供 Experience Platform 應用程式使用，包括 CJA 和其他應用程式。 「資料準備」可與許多 Platform [來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)以及 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)整合。 此連接器提供從 Adobe Analytics 將報告套裝資料擷取到 Platform 的方法。

## 使用「資料準備」進行進一步轉換 {#data-prep}

Adobe Analytics 收集且儲存的資料，可以透過處理規則或 VISTA 規則 (或兩者) 來轉換。 但隨後透過 Analytics 來源連接器轉送到 Platform 的報告套裝，可能會再次使用「資料準備」進行轉換。 這可用於多種目的：

* **解決用於 CJA 和/或 RTCDP 的報告套裝之間的結構描述差異**。 例如，假設報告套裝 A 將 `eVar1` 定義為「搜尋字詞」，而報告套裝 B 將 `eVar2` 定義為「搜尋字詞」。 您可以使用「資料準備」將兩個不同的 eVar 對應到一個通用欄位，其中包含來自兩個 eVar 的資料。 這樣就可以在 [CJA 連線](/help/connections/overview.md)中[結合報告套裝與不同的結構描述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=zh-Hant)，或是用於 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=zh-Hant)。
* **將 `eVars` 欄位對應到語義上有意義的名稱**。 透過 Analytics 來源連接器傳入的 `eVars` 和 `props` 對應到 _\_experience.analytics.customDimensions.eVars.eVar1_ 之類的欄位。 「資料準備」可用於將 `eVar` 和 `prop` 欄位對應到具有對使用者更有意義的名稱，或是符合其他資料來源名稱的新欄位。 (另有其他可行方式，例如重新命名 [CJA 資料檢視](/help/data-views/create-dataview.md)中的欄位)。
* **一般轉換資料方式**。 「資料準備」具有數百個對應函數，可根據來自 Analytics 來源連接器的資料運算和計算新欄位。 您可以將分隔欄位分割為單獨的欄位。 您可以組合欄位。 您可以操作字串。 您可以根據規則運算式從欄位中擷取資訊等等。

## 「資料準備」與分類 {#classifications}

在某些情況下，「資料準備」與[分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hant)有交叉。

例如，在分隔欄位中，您可以使用「資料準備」將該欄位分割為多個個別的欄位，不必用到分類。 通常，分類是通過上載在傳入分析事件流外部提供的查找檔案將元資料添加到欄位的一種方法。

例如，您可以上傳一個分類檔案，將 SKU 分為「尺寸」、「品牌」、「顏色」等。 分類和「資料準備」的另一個差異，是分類同時適用於&#x200B;_歷史資料和未來資料_。 另一方面，「資料準備」對應是從建立對應&#x200B;_以後_&#x200B;開始套用至資料。
