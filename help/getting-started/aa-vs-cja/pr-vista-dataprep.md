---
source-git-commit: 8943af2bc81de5ece238dc7647ff3f66b14b9776
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 4%

---
# Adobe Analytics處理規則、VISTA和分類與分析源連接器的資料準備

[處理規則和VISTA規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) 提供了轉換和處理傳入Adobe Analytics的資料的手段 [資料收集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en)。 這些轉換作為Adobe資料處理的一部分，在Adobe Analytics儲存資料以用於報告和分析目的之前進行。


[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) 是一種工具，它允許您應用基於行的映射和對所接收到的資料的轉換 [AEP](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en) 在AEP應用程式（包括CJA和其他應用程式）中提供資料之前。 資料準備與許多AEP整合 [源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) 現在也與 [分析源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)它提供了將報表套件資料從Adobe Analytics接收到AEP的方法。

由Adobe Analytics收集和儲存的資料可以通過處理規則或VISTA規則或兩者進行轉換。 但隨後通過分析源連接器轉發到AEP的報告套件可能會再次使用資料準備進行轉換。 這對於以下幾個目的可能是可取的：

* **解決在CJA和/或RTCDP中使用的報表套件之間的架構差異**。 例如，如果報表套件A將eVar1定義為搜索項，而報表框B將eVar2定義為搜索項，則可以使用資料準備將兩個不同的eVar映射到包含兩個eVar的資料的公用欄位。 這使得 [將不同架構的報表套件組合在一起](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 在CJA連接中或在RTCDP中使用。
* **將Vars欄位映射到語義上有意義的名稱**。 通過分析源連接器的變數和道具映射到欄位，如 _\_experience.analytics.customDimensions.eVars.eVar1_。  資料準備可用於將eVar和屬性欄位映射到對您的用戶具有更有意義名稱的新欄位，或與來自其他資料源的名稱相匹配的新欄位。 (儘管如此，也可以通過其他方式（如更名CJA資料視圖中的欄位）來完成。)
* **通常轉換資料**。 資料準備具有數百個映射函式，這些映射函式可用於根據通過ADC的資料計算和計算新欄位。 您可以將分隔的欄位拆分為單獨的欄位。 可以合併欄位。 你可以操縱字串。 您可以基於規則運算式從欄位中提取資訊，等等。


您還可能注意到資料準備與 [分類](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hant) 在某些情況下。 例如，如果您有一個分隔欄位，則可以使用「資料準備」將該欄位拆分為多個單獨的欄位，而不使用分類。 不過，通常，分類是通過上載在傳入分析命中流外部提供的查找檔案來向欄位添加元資料的方法。 例如，您可以上載將SKU分組為「size」、「brand」、「color」等的分類檔案。 分類和資料準備之間的另一個區別是分類適用於歷史資料和未來資料。 另一方面，資料準備映射應用於自映射被正向建立時起的資料。