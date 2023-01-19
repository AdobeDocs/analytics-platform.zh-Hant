---
title: 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料
description: 如何設定 Adobe Analytics 報告套裝以擷取至 AEP 和 CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 100%

---

# 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料

Adobe Analytics 客戶可以使用 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)輕鬆地在 Adobe Experience Platform 和 Customer Journey Analytics 中利用他們的報告套裝。下面的討論內容將說明如何這樣做。

## 準備

當您準備開始在 AEP 和 CJA 中使用 Adobe Analytics 報告套裝時，您應該考慮做幾件事來準備您的資料，以順暢地移至 Customer Journey Analytics。如需詳細資訊，請參閱以下頁面：

* [Adobe Analytics 至 Customer Journey Analytics 的發展進程](/help/getting-started/aa-to-cja.md)

## 設定報告套裝以擷取至 Adobe Experience Platform 和 CJA

當您準備好資料後，就可以開始設定用於 AEP 和 CJA 的報告套裝。

1. **針對您想要在 AEP 和 CJA 中使用的每個報告套裝建立一個資料流。** [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)工具可讓您在 Adobe Analytics 與 AEP 之間[建立連線](/help/connections/create-connection.md) (亦即資料流)。您將使用來源連接器針對您想要在 AEP 中使用的每個報告套裝建立一個資料流。該資料流會建立報告套裝資料的複本，其中的結構描述已轉換為 [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant) 以供 AEP 應用程式 (包括 CJA) 使用。每個透過來源連接器設定了資料流的報告套裝都會當作個別資料集儲存在 AEP 資料湖中。每個資料流將自動隨附 13 個月的歷史報告套裝資料，新的資料將會持續流入 AEP。使用 Analytics 來源連接器時，您無需擔心必須事先建立結構描述。系統會自動為您建立 Adobe Analytics 專用的標準化結構描述。不過，AEP 的[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)工具可用於在資料儲存於資料湖並提供給 CJA 使用之前先強化此結構描述。請注意，某些類型的資料會被來源連接器篩除，而不會出現在 AEP 資料湖的資料集中。其他資料列可能會在資料湖與 CJA 之間被篩除。如需詳細資訊，請參閱[將您的 Adobe Analytics 資料與 CJA 資料進行比較](/help/troubleshooting/compare.md)。
1. **使用「資料準備」協助您在 CJA 中合併報告套裝。**「資料準備」可用於多種類型的資料轉換，Adobe Analytics 資料的一個常見用途是解決多個報告套裝中的 prop 及/或 eVar 對應差異，以便報告套裝可以輕鬆地在 CJA 中合併。如需詳細資訊，請參閱[結合報告套裝與不同的結構描述](/help/use-cases/aa-data/combine-report-suites.md)。
1. 必要時&#x200B;**啟用跨管道分析**。在 CJA 中合併多個資料集時，跨管道分析的身分拼接功能可以協助將不同 ID 命名空間解析為單一 stitchedID，以實現跨裝置和管道的單一客戶檢視。如需詳細資訊，請參閱[跨管道分析總覽](/help/cca/overview.md)。
1. **建立一個或多個 CJA 連線。**&#x200B;一旦您的報告套裝的資料集可以在 AEP 資料湖中使用後，您就可以建立一個或多個 [CJA 連線](/help/connections/overview.md)以將這些資料集引進 CJA。在連線中，報告套裝資料可以與其他類型的資料合併，好讓您可以建立真正的跨管道客戶體驗檢視。
1. **建立一個或多個 CJA 資料檢視。**[資料檢視](/help/data-views/data-views.md)是 Customer Journey Analytics 專用的容器，可讓您決定如何解譯來自 CJA 連線的資料。資料檢視有許多強大的[設定選項](/help/data-views/create-dataview.md)可用來自訂資料，以便在 [Analysis Workspace](/help/analysis-workspace/home.md) 中呈現資料給您的使用者。

## 比較 Customer Journey Analytics 與 Adobe Analytics

Customer Journey Analytics 和 Adobe Analytics 有許多相似處。例如，CJA 和 Adobe Analytics 都提供 Analysis Workspace 的強大功能以進行自由形式的思維等速分析。不過，由於 CJA 是 Adobe Experience Platform 中的一個應用程式而且會利用 AEP 進行資料擷取，所以 CJA 和 Adobe Analytics 在許多重要方面有所差異。以下文章有助於了解這些差異：

* [將您的 Adobe Analytics 資料與 CJA 資料進行比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比較透過 Analytics 來源連接器傳遞的 Analytics 資料的術語](/help/getting-started/aa-vs-cja/terminology.md)
* [比較 Adobe Analytics 和 CJA 報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虛擬報告套裝、資料檢視、AEP 沙箱和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [處理規則、VISTA 和分類與「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
