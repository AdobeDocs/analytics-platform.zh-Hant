---
title: 與 Adobe Analytics 比較
description: 概述Customer Journey Analytics與Adobe Analytics的落差。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 59aabb38ea3e5ba1501ab8da11d14ea2385d8a6b
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# 與 Adobe Analytics 比較

本檔案的這個章節說明如何比較和瞭解Customer Journey Analytics與Adobe Analytics之間的差異。

這兩個解決方案之間的根本差異，在於您在建立報表和分析時（可能）會考慮的資料範圍。

在Customer Journey Analytics中， *任何* 資料來源可以是您用於報告和分析的資料的一部分。 Adobe Analytics主要針對從網站和行動應用程式收集的線上資料。 Adobe Analytics提供從其他來源匯入資料的功能，但主要目的是為先前提到的線上資料提供更多內容。

## 資料收集

Customer Journey Analytics仰賴儲存在Experience Platform資料集中的資料。 您有數個選項可以收集這些資料集中的資料並將資料擷取到Experience Platform中。 這些選項在 [資料擷取概觀](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics最終會收集解決方案本身的資料。 同樣地，您有數個選項可收集該資料，這些選項在 [Adobe Analytics實作指南](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hant).

您可以使用以下專案在Customer Journey Analytics中使用您的Adobe Analytics報表套裝資料： [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant). 此聯結器會使用Adobe Analytics中收集的資料來擷取Experience Platform，然後用於Customer Journey Analytics。 另請參閱 [在Customer Journey Analytics中使用Adobe Analytics報表套裝資料](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hant) 以取得詳細資訊。


## 資料處理

在您能夠報告資料之前，通常需要處理該資料以確保資料可正確用於該目的。 可以在收集時間和報告時間處理資料。

一般而言，Customer Journey Analytics的設計目的是在報表時間處理Experience Platform資料集中收集和儲存的資料。 Customer Journey Analytics提供強大的報表時間處理功能，確保資料準備好進行報告和分析。 如果您必須在資料以Experience Platform擷取之前對應、轉換及驗證資料，可以使用 [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) Experience Platform功能。

在Adobe Analytics中，大部分的資料處理作業會在收集資料後立即進行。

另請參閱 [比較Adobe Analytics和Customer Journey Analytics的資料處理](data-processing-comparisons.md) 和 [處理規則、VISTA和分類與「資料準備」的比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=zh-Hant) 以取得詳細資訊。


## 術語

Customer Journey Analytics可讓您靈活定義維度和量度，基礎體驗資料模型(XDM)架構提供的彈性就是讓此功能發揮作用。 例如，當Adobe Analytics使用訪客、造訪和點選時，Customer Journey Analytics會將人員、工作階段和事件當成同等概念，但您可以視需要變更命名。

另請參閱 [比較透過Analytics來源聯結器傳遞的Analytics資料的術語](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) 以取得術語差異的詳細資訊。


## 虛擬報告環境和沙箱

Adobe Analytics具備虛擬報表套裝的概念，可讓您將收集的資料分段並控制對該分段資料的存取。

Customer Journey Analytics有一個類似的概念，名為資料檢視。 資料檢視是容器，可讓您決定如何詮釋來自連線的資料。 它提供極致的彈性，可讓您指定和設定維度和量度，為您的報表和分析做準備。

Experience Platform提供的沙箱可視為一個容器，其中包含特定環境的資料和應用程式。 沙箱的功能與Adobe Analytics虛擬報告套裝或Customer Journey Analytics資料檢視無關。 Adobe Analytics本身與Experience Platform沙箱完全沒有相依性或關聯。 Customer Journey Analytics不支援Experience Platform沙箱，但有一些重要的考量。

另請參閱 [虛擬報告套裝、資料檢視、Adobe Experience Platform沙箱和Analytics來源聯結器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=zh-Hant) 以取得詳細資訊。


## 身分

Customer Journey Analytics支援您在包含您資料的資料集符合的結構描述中定義的身分識別。 因此，身分是Experience Platform的基本概念，Customer Journey Analytics在設定 [連線](../../connections/overview.md) （為每個資料集定義人員ID）和套用時 [拼接](../../stitching/overview.md) 進行跨管道分析。 Experience PlatformSDK和API使用的重要身分識別是Experience CloudID (ECID)。

Adobe Analytics使用一組更明確的身分識別欄位，例如Adobe Analytics ID (AAID)。 使用Analytics來源聯結器時，這些Adobe Analytics識別欄位會獲得特殊處理。 另請參閱 [AAID、ECID、AACUSTOMID和Analytics來源聯結器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) 以取得詳細資訊。


## 功能

如需Adobe Analytics功能以及Customer Journey Analytics如何支援這些功能的概述，請參閱 [Customer Journey Analytics功能支援](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





