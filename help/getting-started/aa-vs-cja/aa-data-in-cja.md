---
title: 將Adobe Analytics報表套裝資料用於Customer Journey Analytics
description: 如何設定Adobe Analytics報表套裝以擷取至AEP和CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# 將Adobe Analytics報表套裝資料用於Customer Journey Analytics

Adobe Analytics客戶可以透過 [Analytics來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant). 以下討論將說明如何這樣做。

## 準備

準備好在AEP和CJA中開始使用Adobe Analytics報表套裝時，您應考慮進行幾項動作，以準備資料以順暢地移動至Customer Journey Analytics。 請參閱下列頁面以取得詳細資訊：

* [Adobe Analytics 至 Customer Journey Analytics 的發展進程](/help/getting-started/aa-to-cja.md)

## 設定要擷取至Adobe Experience Platform和CJA的報表套裝

準備好資料後，您就可以開始設定報表套裝以用於AEP和CJA。

1. **為您要在AEP和CJA中使用的每個報表套裝建立資料流。** 此 [Analytics來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) 是可讓您 [建立連線](/help/connections/create-connection.md) （亦即資料流）。 您將使用來源連接器，為每個要在AEP中使用的報表套裝建立一個資料流。 資料流會建立報表套裝資料的復本，其中架構已轉換為  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant) 供AEP應用程式（包括CJA）使用。 每個透過來源連接器設定有資料流的報表套裝，都會儲存為AEP Data Lake中的個別資料集。 每個資料流都會自動包含13個月的歷史報表套裝資料，而新資料會持續流入AEP。 使用Analytics來源連接器時，您不必擔心會提前建立結構。 系統會自動為您建立Adobe Analytics專用的標準化結構。 然而，AEP [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) 工具可用來增強此結構，資料才會儲存在Data Lake中，並可供CJA使用。 請注意，某些類型的資料會由來源連接器篩選掉，因此不會出現在AEP Data Lake的資料集中。 Data Lake和CJA之間可篩選掉其他列。 請參閱 [比較Adobe Analytics資料與CJA資料](/help/troubleshooting/compare.md) 以取得更多詳細資訊。
1. **使用「資料準備」可協助您在CJA中結合報表套裝。** 資料準備可用於許多類型的資料轉換，Adobe Analytics資料的常見用途之一，是解決多個報表套裝的prop和/或eVar對應差異，以便在CJA中輕鬆結合報表套裝。 請參閱 [結合不同結構的報表套裝](/help/use-cases/aa-data/combine-report-suites.md) 以取得更多詳細資訊。
1. **啟用跨管道分析** 視需要。 在CJA中合併多個資料集時，跨管道分析的身分連結功能有助於將不同的ID命名空間解析為單一匯整的ID，以便跨裝置和管道檢視客戶。 請參閱 [跨管道分析概觀](/help/connections/cca/overview.md) 以取得更多詳細資訊。
1. **建立一或多個CJA連線。** 在AEP Data Lake中提供報表套裝的資料集後，您就可以建立一或多個資料集 [CJA連線](/help/connections/overview.md) 將這些資料集匯入CJA。 在連線中，報表套裝資料可與其他類型的資料結合，讓您建立客戶體驗的真正跨管道檢視。
1. **建立一或多個CJA資料檢視。** A [資料檢視](/help/data-views/data-views.md) 是Customer Journey Analytics專用的容器，可讓您判斷如何解譯CJA連線的資料。 資料檢視有許多功能強大 [配置選項](/help/data-views/create-dataview.md) 用於自訂顯示給您的使用者的資料(在 [Analysis Workspace](/help/analysis-workspace/home.md).

## 比較Customer Journey Analytics和Adobe Analytics

Customer Journey Analytics和Adobe Analytics有許多相似之處。 例如，CJA和Adobe Analytics都提供Analysis Workspace的強大功能，可自由格式進行思維速度分析。 不過，由於CJA是Adobe Experience Platform中的應用程式，且會利用AEP擷取資料，因此CJA和Adobe Analytics在許多重要方面有所不同。 下列文章有助於了解這些差異：

* [將您的 Adobe Analytics 資料與 CJA 資料進行比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比較透過 Analytics 來源連接器傳遞的 Analytics 資料的術語](/help/getting-started/aa-vs-cja/terminology.md)
* [比較 Adobe Analytics 和 CJA 報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虛擬報告套裝、資料檢視、AEP 沙箱和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [處理規則、VISTA 和分類與「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、ACUSTOMID 和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
