---
title: 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料
description: 如何設定Adobe Analytics報表套裝以擷取至Adobe Experience Platform和Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 21%

---

# 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料

Adobe Analytics客戶可以在Adobe Experience Platform中輕鬆運用其報表套裝，並使用Customer Journey Analytics [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant). 下面的討論內容將說明如何這樣做。

>[!IMPORTANT]
>
>您必須擁有 **選取** 套裝，以便對多個報表套裝執行資料分析。 如果您不確定擁有哪些Customer Journey Analytics套件，請聯絡管理員。&#x200B;

## 準備

當您準備好在Adobe Experience Platform和Customer Journey Analytics中開始使用Adobe Analytics報表套裝時，您應考慮採取幾項措施準備資料，以順暢地移至Customer Journey Analytics。 如需詳細資訊，請參閱以下頁面：

* [Adobe Analytics 至 Customer Journey Analytics 的發展進程](/help/getting-started/aa-to-cja.md)

## 設定報表套裝以擷取至Adobe Experience Platform和Customer Journey Analytics

準備好資料後，您就可以開始設定用於Adobe Experience Platform和Customer Journey Analytics的報告套裝。

1. **針對您想要在Adobe Experience Platform和Customer Journey Analytics中使用的每個報告套裝建立一個資料流。** 此 [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant) 是工具，可讓您 [建立連線](/help/connections/create-connection.md) （亦即資料流）在Adobe Analytics和Adobe Experience Platform之間。 您將使用來源聯結器為您要在Adobe Experience Platform中使用的每個報告套裝建立一個資料流。 資料流會建立報告套裝資料的復本，其中的結構描述已轉換為  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant) 供Adobe Experience Platform應用程式使用，包括Customer Journey Analytics。<p>每個透過來源聯結器設定了資料流的報告套裝，都會當作個別資料集儲存在Adobe Experience Platform資料湖中。 每個資料流會自動包含13個月的歷史報告套裝資料，而新資料將會持續流入Adobe Experience Platform。 （請注意，從2023年4月26日開始，非生產沙箱中的回填限製為3個月。） 有了Analytics來源聯結器，您就不需要擔心要事先建立結構描述。 系統會自動為您建立 Adobe Analytics 專用的標準化結構描述。不過，Adobe Experience Platform [資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant) 工具可用於在資料儲存於Data Lake並提供給Customer Journey Analytics使用之前先增強此結構描述。 請注意，某些型別的資料會被來源聯結器篩除，而不會出現在Adobe Experience Platform Data Lake的資料集中。 其他資料列可能會在資料湖和Customer Journey Analytics之間被篩選掉。 另請參閱 [將您的Adobe Analytics資料與Customer Journey Analytics資料進行比較](/help/troubleshooting/compare.md) 以取得更多詳細資料。
1. **使用「資料準備」協助您合併Customer Journey Analytics的報表套裝。** 「資料準備」可用於多種型別的資料轉換，Adobe Analytics資料的一個常見用途是解決多個報表套裝中的prop和/或eVar對應差異，以便報表套裝可以輕鬆地在Customer Journey Analytics中合併。 如需詳細資訊，請參閱[結合報告套裝與不同的結構描述](/help/use-cases/aa-data/combine-report-suites.md)。
1. **啟用拼接** 視需要而定。 在Customer Journey Analytics中合併多個資料集時，拼接功能可協助將不同的ID名稱空間解析為單一拼接ID，以實現跨裝置和管道的單一客戶檢視。 另請參閱 [拼接概述](../../stitching/overview.md) 以取得更多詳細資料。
1. **建立一或多個Customer Journey Analytics連線。** 在Adobe Experience Platform Data Lake中使用報表套裝的資料集後，您就可以建立一個或多個資料集 [Customer Journey Analytics連線](/help/connections/overview.md) 將這些資料集帶入Customer Journey Analytics。 在連線中，報告套裝資料可以與其他類型的資料合併，好讓您可以建立真正的跨管道客戶體驗檢視。
1. **建立一或多個Customer Journey Analytics資料檢視。** A [資料檢視](/help/data-views/data-views.md) 是Customer Journey Analytics專屬的容器，可讓您決定如何解譯來自Customer Journey Analytics連線的資料。 資料檢視有許多強大的[設定選項](/help/data-views/create-dataview.md)可用來自訂資料，以便在 [Analysis Workspace](/help/analysis-workspace/home.md) 中呈現資料給您的使用者。

## 比較 Customer Journey Analytics 與 Adobe Analytics

Customer Journey Analytics 和 Adobe Analytics 有許多相似處。例如，Customer Journey Analytics和Adobe Analytics都提供Analysis Workspace的強大功能，提供自由形式的思維速度分析。 不過，由於Customer Journey Analytics是Adobe Experience Platform中的應用程式，並利用Adobe Experience Platform進行資料擷取，因此Customer Journey Analytics和Adobe Analytics在許多重要方面有所不同。 以下文章有助於了解這些差異：

* [將您的Adobe Analytics資料與Customer Journey Analytics資料進行比較](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比較透過Analytics來源聯結器傳遞的Analytics資料的術語](/help/getting-started/aa-vs-cja/terminology.md)
* [比較Adobe Analytics與Customer Journey Analytics報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虛擬報告套裝、資料檢視、Adobe Experience Platform沙箱和Analytics來源聯結器](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [處理規則、VISTA 和分類與「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID和Analytics來源聯結器](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
