---
title: 處理規則、VISTA 和分類與 Analytics 來源連接器的「資料準備」的比較
description: 了解使用處理規則和 VISTA 以及使用「資料準備」的資料轉換的異同
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/MuJbtTwSbGbKBifnyWz6SNybYX9JsMpIL9QwVJv031Y
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 92%

---

# 處理規則、VISTA 和分類與資料準備的比較

Adobe Analytics [處理規則和 VISTA 規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html)提供一種轉換和操作傳遞到 Adobe Analytics [資料彙集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=zh-Hant)中資料的方法。 這些轉換屬於將資料儲存到 Adobe Analytics (以用於報告和分析) 之前的 Adobe 資料處理的一部分。

[「資料準備」](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)是一種工具，可讓您將根據列的對應和轉換套用到擷取至 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html) 的資料上。 隨後，資料即可供 Experience Platform 應用程式使用，包括 Customer Journey Analytics 和其他應用程式。 「資料準備」可與許多 Platform [來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant)以及 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)整合。 此連接器提供從 Adobe Analytics 將報告套裝資料擷取到 Platform 的方法。

## 使用「資料準備」進行進一步轉換 {#data-prep}

Adobe Analytics 收集且儲存的資料，可以透過處理規則或 VISTA 規則 (或兩者) 來轉換。 但隨後透過 Analytics 來源連接器轉送到 Platform 的報告套裝，可能會再次使用「資料準備」進行轉換。 這可用於多種目的：

* **解決用於 Customer Journey Analytics 和/或 RTCDP 的報告套裝之間的結構描述差異**。 例如，報告套裝 A 將 `eVar1` 定義為「搜尋字詞」，而報告套裝 B 將 `eVar2` 定義為「搜尋字詞」。 您可以使用資料準備將兩個不同的 eVar 對應到一個通用欄位，其中包含來自兩個 eVar 的資料。 這樣就可以在 [Customer Journey Analytics 連線](/help/connections/overview.md)中[結合報告套裝與不同的結構描述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html)，或是用於 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html)。
* **將 `eVars` 欄位對應到語義上有意義的名稱**。 透過 Analytics 來源連接器傳入的 `eVars` 和 `props` 對應到 _\_ experience.analytics.customDimensions.eVars.eVar1_ 之類的欄位。 「資料準備」可用於將 `eVar` 和 `prop` 欄位對應到具有對使用者更有意義的名稱，或是符合其他資料來源名稱的新欄位。 (另有其他可行方式，例如重新命名 [Customer Journey Analytics 資料檢視](/help/data-views/create-dataview.md)中的欄位)。
* **一般轉換資料方式**。 「資料準備」具有數百個對應函數，可根據來自 Analytics 來源連接器的資料運算和計算新欄位。 您可以將分隔欄位分割為單獨的欄位。 您可以組合欄位。 您可以操作字串。 您可以根據規則運算式從欄位中擷取資訊等等。

## 「資料準備」與分類 {#classifications}

在某些情況下，「資料準備」與[分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html)有交叉。

例如，在分隔欄位中，您可以使用「資料準備」將該欄位分割為多個個別的欄位，不必用到分類。 通常，分類是透過上傳在傳入 Analytics 事件串流之外提供的查閱檔案，來將中繼資料新增到欄位。

例如，您可以上傳一個分類檔案，將SKU分為「大小」、「品牌」、「顏色」等。分類和「資料準備」的另一個差異，是分類同時適用於歷史資料和未來資料&#x200B;__。 另一方面，「資料準備」對應是從建立對應&#x200B;_以後_&#x200B;開始套用至資料。
