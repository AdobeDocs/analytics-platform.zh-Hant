---
title: 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料
description: 如何設定 Adobe Analytics 報告套件以擷取至 Adobe Experience Platform 和 Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 100%

---

# 在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料

Adobe Analytics 客戶可以使用 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)輕鬆地在 Adobe Experience Platform 和 Customer Journey Analytics 中利用他們的報告套裝。下面的討論內容將說明如何這樣做。

>[!IMPORTANT]
>
>您必須擁有&#x200B;**選取**&#x200B;套件，才能跨多個報告套裝執行資料分析。如果您不確定您擁有的 Customer Journey Analytics 套件是哪一種，請聯絡您的管理員。&#x200B;

## 準備

當您準備開始在 Adobe Experience Platform 和 Customer Journey Analytics 中使用 Adobe Analytics 報告套裝時，您應該考慮做幾件事來準備您的資料，以順暢地移至 Customer Journey Analytics。如需詳細資訊，請參閱以下頁面：

* [Adobe Analytics 至 Customer Journey Analytics 的發展進程](/help/getting-started/aa-to-cja.md)

## 設定報告套件以擷取至 Adobe Experience Platform 和 Customer Journey Analytics

當您準備好資料後，就可以開始設定要在 Adobe Experience Platform 和 Customer Journey Analytics 中使用的報告套裝。

1. **為您希望在 Adobe Experience Platform 和 Customer Journey Analytics 中使用的每個報告套裝建立資料流。**[Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)工具可讓您在 Adobe Analytics 與 Adobe Experience Platform 之間[建立連線](/help/connections/create-connection.md) (亦即資料流)。您將使用來源連接器針對您想要在 Adobe Experience Platform 中使用的每個報告套裝建立一個資料流。資料流會建立報告套裝資料的複本，其中的綱要已轉換為 [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant) 以供 Adobe Experience Platform 應用程式 (包括 Customer Journey Analytics) 使用。<p>每個透過來源連接器設定了資料流的報告套裝都會當作個別資料集儲存在 Adobe Experience Platform 資料湖中。每個資料流將自動隨附 13 個月的歷史報告套裝資料，新的資料將會持續流入 Adobe Experience Platform。(請注意，從 2023 年 4 月 26 日開始，非生產沙箱的回填期限為 3 個月。)使用 Analytics 來源連接器時，您無需擔心必須事先建立綱要。系統會自動為您建立 Adobe Analytics 專用的標準化綱要。不過，Adobe Experience Platform 的[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)工具可用於在資料儲存於資料湖並提供給 Customer Journey Analytics 使用之前先強化此綱要。請注意，某些類型的資料會被來源連接器篩除，而不會出現在 Adobe Experience Platform 資料湖的資料集中。其他資料列可能會在資料湖與 Customer Journey Analytics 之間被過濾掉。如需詳細資訊，請參閱[比較 Adobe Analytics 資料與 Customer Journey Analytics 資料](/help/troubleshooting/compare.md)。
1. **使用「資料準備」協助您在 Customer Journey Analytics 中組合報告套裝。**「資料準備」可用於多種類型的資料轉換，Adobe Analytics 資料的一個常見用途是解決多個報告套裝中的 prop 及/或 eVar 對應差異，以便報告套裝可以輕鬆地在 Customer Journey Analytics 中合併。如需詳細資訊，請參閱[將報告套裝與不同的綱要組合](/help/use-cases/aa-data/combine-report-suites.md)。
1. 必要時&#x200B;**啟用拼接**。在 Customer Journey Analytics 中合併多個資料集時，拼接功能可以協助將不同 ID 命名空間解析為單一拼接 ID，以實現跨裝置和管道的單一客戶檢視。如需詳細資訊，請參閱「[拼接概觀](../../stitching/overview.md)」。
1. **建立一個或多個 Customer Journey Analytics 連線。**&#x200B;報表套裝的資料集可在 Adobe Experience Platform 資料湖中使用後，就可以建立一個或多個 [Customer Journey Analytics 連線](/help/connections/overview.md)，將這些資料集引入 Customer Journey Analytics。在連線中，報告套裝資料可以與其他類型的資料合併，好讓您可以建立真正的跨管道客戶體驗檢視。
1. **建立一個或多個 Customer Journey Analytics 資料檢視。**&#x200B;資料檢視是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自 Customer Journey Analytics 連線的資料。[](/help/data-views/data-views.md)資料檢視有許多強大的[設定選項](/help/data-views/create-dataview.md)可用來自訂資料，以便在 [Analysis Workspace](/help/analysis-workspace/home.md) 中呈現資料給您的使用者。

## 比較 Customer Journey Analytics 與 Adobe Analytics

Customer Journey Analytics 和 Adobe Analytics 有許多相似處。例如，Customer Journey Analytics 和 Adobe Analytics 都提供 Analysis Workspace 的強大功能以進行自由形式的思維等速分析。但是，由於 Customer Journey Analytics 是 Adobe Experience Platform 中的一個應用程式，並使用 Adobe Experience Platform 擷取資料，因此 Customer Journey Analytics 和 Adobe Analytics 在許多重要方面存在差異。以下文章有助於了解這些差異：

* [比較 Adobe Analytics 資料與 Customer Journey Analytics 資料](/help/troubleshooting/compare.md)
* [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)
* [比較透過 Analytics 來源連接器傳遞的 Analytics 資料術語](/help/getting-started/aa-vs-cja/terminology.md)
* [比較 Adobe Analytics 和 Customer Journey Analytics 報告功能的資料處理](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [虛擬報告套裝、資料檢視、Adobe Experience Platform 沙箱和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [處理規則、VISTA 和分類與「資料準備」的比較](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID、ECID、AACUSTOMID 和 Analytics 來源連接器](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
