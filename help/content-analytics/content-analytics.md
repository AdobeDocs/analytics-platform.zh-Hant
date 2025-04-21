---
title: Content Analytics 概觀
description: Content Analytics 概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: feb253b20820112d5aa4b4eee31cff74d99fa186
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 44%

---

# Content Analytics 概觀

{{release-limited-testing}}

Content Analytics 可幫助行銷人員了解內容如何影響企業已定義的關鍵績效指標。除了行為資料外，Content Analytics還收集有關內容使用方式以及內容如何推動影響的資料。 例如，客戶對特定語調、特定調色盤或特定主題的回應是否更好？ 這些資訊與專門設計的報告工作流程和範本，可以幫助您在 Customer Journey Analytics 中進行更好的分析並，獲得有關客戶歷程資料的更深入。

Content Analytics 會使用人工智慧式和機器學習式的&#x200B;**特徵化服務**，將內容劃分為元件和屬性。透過在所有內容上建立結構化中繼資料設定檔，您可以分析哪些內容以及這些內容的哪些屬性可以推動業務成長。

除了結構化中繼資料設定檔的建立之外，Content Analytics 還提供&#x200B;**身分識別服務**，使用單一識別碼來識別資產和體驗。身分識別服務可以識別完全相同資產出現在多個地方的情況。發生此情況時，會將此資產的例項視為相同的資產，以更全面的方式檢視內容使用情況和耗用量。

## 值

Content Analytics 確實不斷提升其價值：

1. 內容&#x200B;**使用方式**：透過 Content Analytics，您可以了解哪些資產正獲得曝光度，以及資產是在哪裡獲得曝光度。這些分析可以幫助您了解具一些網頁屬性的資產是否未充分利用或過度使用。
1. 內容&#x200B;**參與度**：Content Analytics 可以提供參與度分析，例如某些屬性的資產平均點擊率。這些分析可以幫助您確定特定類型的體驗是否仍然有效。
1. 內容&#x200B;**歷程**：此外，當與 Experience Platform 的所有其他資料合併時，您可以獲得有關內容歷程的更多內容。例如，除了參與度之外，特定內容是否會造成瀏覽轉換。了解這些事情後，您就可以確定內容類型的投資報酬率。
1. 內容&#x200B;**個人化**：最終，Content Analytics 可讓您根據自己的分析採取行動，並使用這些分析來確定如何花錢在內容上。例如，我應該向特定客群發送特定類型的內容嗎？哪些內容能為我提供高度個人化的機會？

## 術語

Content Analytics 會使用以下關鍵用語：

![資產和體驗](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **體驗**：體驗是網頁上的所有文字，網頁可透過造訪該網頁的初始使用者所使用的URL重現。 每個體驗都會取得唯一識別碼。 頁面變更會導致頁面的HTML變更，進而產生新體驗。
* **資產**：資產是獨立且獨特的內容，例如影像。每個資產也會取得唯一識別碼和感應式ID。 可感知ID是與視覺上相同的資產共用的識別碼。 可感知ID有助於對可能有不同資產URL並因此有不同資產ID，但概念上相同的資產進行重複資料刪除。
* **屬性**：屬性是與體驗或資產相關的描述性中繼資料元素。屬性的範例有：攝影風格、可讀性、說服策略、物件顏色、背景顏色。

## 運作方式

Content Analytics在Experience Platform的事件資料集中使用Web影像檢視資料來[收集內容事件資料](config/datacollection.md)。 並將該內容資料收集與行為資料的（現有）資料收集實作結合在一起。

![Content Analytics - 如何運作](assets/aca-overview.gif)

1. 當使用者造訪為Content Analytics](config/configuration.md)設定的網站[時，Experience Platform Web SDK會記錄曝光次數以及與內容的互動。
1. 身分和功能化服務會處理這些互動。 該程式包含擷取服務，可修訂定義互動之已設定URL的公開版本。 對於這些擷取的URL，身分識別服務會唯一識別體驗和資產。 此外，功能化服務會套用AI/ML服務，探索體驗和資產中繼資料與屬性。
1. 這些服務（[元件、屬性和身分](/help/content-analytics/report/components.md)）的結果可用來更新Experience Platform中的相關特定內容分析資料集。
1. 內容分析資料，連同行為資料和其他查詢資料，您可以在Customer Journey Analytics設定([連線](/help/connections/overview.md)、[資料檢視](/help/data-views/data-views.md)和[Workspace](/help/analysis-workspace/home.md))中使用。 該設定提供了對您的內容進行獨特巨集層級深入分析的基礎。 <br/>您可以使用[Content Analytics範本](/help/content-analytics/report/report.md#template)，快速開始您的Content Analytics報表和分析。


>[!NOTE]
>
>Content Analytics運用的AI/ML服務可能產生不準確或誤導的結果。 因此，請依據您的判斷檢閱及驗證AI/ML產生的輸出。
>
>您可以使用主要介面上的![資訊大綱](/help/assets/icons/InfoOutline.svg)提供的&#x200B;**[!UICONTROL 意見反應]**&#x200B;標籤，針對AI/ML產生的輸出提供意見反應。
>

>[!NOTE]
>
>如果您已授權Privacy and Security Shield附加元件，請注意（從產生的任何資料）體驗和資產(受Content Analytics限制)不屬於DULE標籤或客戶自控金鑰的涵蓋範圍。
>

>[!NOTE]
>
>Content Analytics [傳送其他事件](config/datacollection.md#content-analytics-event)，這些事件極有可能影響任何以工作階段或頁面中的事件數目為基礎的跳出率定義。
>

>[!MORELIKETHIS]
>
>[Content Analytics 報告](report/report.md)
>[設定 Content Analytics](config/configuration.md)
>[正在計算Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)中的跳出數和跳出率
>

