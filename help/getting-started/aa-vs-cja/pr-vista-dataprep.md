---
title: 處理規則、VISTA和分類與Analytics來源聯結器的「資料準備」的比較
description: 了解使用處理規則和 VISTA 以及使用「資料準備」的資料轉換的異同
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 65%

---

# 處理規則、VISTA 和分類與「資料準備」的比較

Adobe Analytics [處理規則和 VISTA 規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=zh-Hant)提供一種轉換和操作傳遞到 Adobe Analytics [資料彙集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=zh-Hant)中資料的方法。 這些轉換屬於將資料儲存到 Adobe Analytics (以用於報告和分析) 之前的 Adobe 資料處理的一部分。

[「資料準備」](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)是一種工具，可讓您將根據列的對應和轉換套用到擷取至 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=zh-Hant) 的資料上。 隨後，資料便可用於Experience Platform應用程式，包括Customer Journey Analytics和其他應用程式。 「資料準備」已與許多平台整合 [來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)，以及使用 [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant). 此連接器提供從 Adobe Analytics 將報告套裝資料擷取到 Platform 的方法。

## 使用「資料準備」進行進一步轉換 {#data-prep}

Adobe Analytics 收集且儲存的資料，可以透過處理規則或 VISTA 規則 (或兩者) 來轉換。 但隨後透過Analytics來源聯結器轉送至Platform的報告套裝，可能會再次使用「資料準備」進行轉換。 這可用於多種目的：

* **解決用於Customer Journey Analytics和/或RTCDP的報告套裝之間的結構描述差異**. 例如，假設報告套裝 A 將 `eVar1` 定義為「搜尋字詞」，而報告套裝 B 將 `eVar2` 定義為「搜尋字詞」。 您可以使用「資料準備」將兩個不同的 eVar 對應到一個通用欄位，其中包含來自兩個 eVar 的資料。 這可讓您 [結合報告套裝與不同的結構描述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=zh-Hant) 在 [Customer Journey Analytics連線](/help/connections/overview.md) 或用於 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=zh-Hant).
* **將 `eVars` 欄位對應到語義上有意義的名稱**。 `eVars` 和 `props` 透過Analytics來源聯結器傳入的欄位會對應到 _\_experience.analytics.customDimensions.eVars.eVar1_. 「資料準備」可用於將 `eVar` 和 `prop` 欄位對應到具有對使用者更有意義的名稱，或是符合其他資料來源名稱的新欄位。 (這也可以透過其他方法完成，例如重新命名 [Customer Journey Analytics資料檢視](/help/data-views/create-dataview.md).)
* **一般轉換資料方式**。 「資料準備」有數百個對應函式，可用來根據來自Analytics來源聯結器的資料計算新欄位。 您可以將分隔欄位分割為單獨的欄位。 您可以組合欄位。 您可以操作字串。 您可以根據規則運算式從欄位中擷取資訊等等。

## 「資料準備」與分類 {#classifications}

在某些情況下，「資料準備」與[分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hant)有交叉。

例如，在分隔欄位中，您可以使用「資料準備」將該欄位分割為多個個別的欄位，不必用到分類。 通常，分類是透過上傳在傳入Analytics事件串流之外提供的查閱檔案，來將中繼資料新增到欄位。

例如，您可以上傳一個分類檔案，將SKU分為「大小」、「品牌」、「顏色」等。 分類和「資料準備」的另一個差異，是分類同時適用於&#x200B;_歷史資料和未來資料_。 另一方面，「資料準備」對應是從建立對應&#x200B;_以後_&#x200B;開始套用至資料。
