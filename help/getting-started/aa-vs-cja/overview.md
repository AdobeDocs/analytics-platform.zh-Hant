---
title: 與 Adobe Analytics 比較
description: 概述如何比較 Customer Journey Analytics 和 Adobe Analytics。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 4cbf01d397e7f89e67ae20702790129478d45cce
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 73%

---

# 與 Adobe Analytics 比較

本檔案的這個章節說明如何比較和瞭解Adobe Customer Journey Analytics與Adobe Analytics之間的差異。

這兩個解決方案的基本差異在於當建立報告和分析時 (可以) 考量的資料寬度。

在 Customer Journey Analytics 中，*任何*&#x200B;資料來源都可以做為報告和分析的資料。Adobe Analytics 主要針對從網站和行動應用程式收集的線上資料。Adobe Analytics提供從其他來源匯入資料的功能，但主要目的是為先前提到的線上資料提供更多相關情境。

## 資料收集

Customer Journey Analytics仰賴儲存在Adobe Experience Platform資料集中的資料。 您有數個選項可以從Experience Platform的這些資料集中收集及擷取資料。 這些選項在[資料擷取概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=zh-Hant)有進一步的扼要說明。

Adobe Analytics 最終在解決方案本身內收集資料。同樣，您有多種選項來收集該資料，這些選項在 [Adobe Analytics 實作指南](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=zh-Hant)有進一步的扼要說明。

您可以使用 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)在 Customer Journey Analytics 使用您的 Adobe Analytics 報告套裝資料。此聯結器會將Adobe Analytics中收集的資料擷取到Experience Platform。 然後，您可以在Customer Journey Analytics中建立與此資料集的連線。 如需詳細資訊，請參閱[在 Customer Journey Analytics 中使用 Adobe Analytics 報告套裝資料](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hant)。


## 資料處理

在您能夠報告資料之前，通常需要處理該資料以確保資料可正確用於報告。 資料處理可在收集時間和報告時間進行。

一般來說，Customer Journey Analytics 旨在報告時處理 Experience Platform 資料集中收集和儲存的資料。Customer Journey Analytics 提供強大的報告時處理功能，以確保資料已準備好用於報告和分析。如果您必須在將資料擷取到 Experience Platform 之前對其進行對應、轉換和驗證，您可以使用 Experience Platform 的[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)功能。

在 Adobe Analytics 中，大部分資料處理作業是在收集資料後立即進行。

如需詳細資訊，請參閱[比較 Adobe Analytics 和 Customer Journey Analytics 之間的資料處理](data-processing-comparisons.md) 和[處理規則、VISTA 和分類與「資料準備」的比較](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=zh-Hant)。


## 術語

Customer Journey Analytics 在定義維度和量度方面提供彈性，這得益於基於底層 Experience Data Model (XDM) 的架構所提供的彈性。例如，當Adobe Analytics使用訪客、造訪和點選時，Customer Journey Analytics會將人員、工作階段和事件當成同等概念（您可以視需要變更命名）。

如需術語差異的詳細資訊，請參閱[比較透過 Analytics 來源連接器傳遞的 Analytics 資料術語](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=zh-Hant)。


## 虛擬報告環境和沙箱

Adobe Analytics具備虛擬報表套裝的概念，可讓您將收集的資料分段並控制對該分段資料的存取權。

Customer Journey Analytics有一個類似的概念，稱為資料檢視。 資料檢視是一種容器，可讓您決定如何解譯來自連線的資料。它們提供極致的靈活性，可讓您指定和設定維度和量度，為您的報告和分析做準備。

Experience Platform 提供沙箱，可將其視為一個容器，其中包含特定環境的資料和應用程式。沙箱的功能與 Adobe Analytics 虛擬報告套件或 Customer Journey Analytics 資料檢視無關。Adobe Analytics 本身與 Experience Platform 沙箱完全沒有相依性或相關性。Customer Journey Analytics不支援Experience Platform沙箱，但有一些重要考量。

如需詳細資訊，請參閱[虛擬報告套裝、資料檢視、Adobe Experience Platform 沙箱和 Analytics 來源連接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=zh-Hant)。


## 身分

Customer Journey Analytics 支援您定義做為結構描述一部分的身分，包含資料的資料集會遵循結構描述。因此，身分是 Experience Platform 的基本概念，Customer Journey Analytics 在設定[連線](../../connections/overview.md) (透過為每個資料集定義人員 ID) 和套用 [拼接](../../stitching/overview.md) 以進行跨管道分析時，會使用身分。Experience Platform SDK 和 API 使用的一個重要身分是 Experience Cloud ID (ECID)。

Adobe Analytics 使用一組更明確的身分欄位，例如 Adobe Analytics ID (AAID)。使用 Analytics 來源連接器時，這些 Adobe Analytics 身分欄位會受到特殊處理。如需詳細資訊，請參閱 [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hant)。


## 支援的功能

有關 Adobe Analytics 功能以及 Customer Journey Analytics 如何支援這些功能的概述，請參閱 [Customer Journey Analytics 功能支援](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=zh-Hant)。





