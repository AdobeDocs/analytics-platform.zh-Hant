---
title: 內容分析概觀
description: 內容分析概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: a7bed5bdab20c1a995ccaf4294a5f9ba5918f43d
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# 內容分析概觀

{{release-limited-testing}}

內容分析可協助行銷人員瞭解內容如何影響企業已定義的關鍵績效指標。 除了行為資料外，Content Analytics還收集有關內容使用方式以及內容如何推動影響的資料。 例如，客戶對特定語調、特定調色盤或特定主題的回應是否更好？ 這些資訊，再加上特別設計的報告工作流程和範本，可協助您執行更好的分析，並在Customer Journey Analytics中獲得客戶歷程資料的更深入見解。

Content Analytics使用AI和機器學習式的&#x200B;**特徵化服務**，將內容細分為元件和屬性。 透過在所有內容上建立結構化的中繼資料設定檔，您可以分析哪些內容以及該內容的哪些屬性可推動業務成果。

除了建立此結構化的中繼資料設定檔之外，Content Analytics還提供使用單一識別碼來識別資產和體驗的&#x200B;**識別服務**。 Identity Service可識別同一資產何時出現在多個位置。 發生此情況時，會將此資產的例項視為相同的資產，以更全面的方式檢視內容使用情況和耗用量。

## 值

內容分析提供的價值會越來越高：

1. 內容&#x200B;**使用情形**：透過內容分析，您可以深入瞭解哪些資產會收到曝光數，以及哪些資產會收到曝光數。 這些見解可協助您檢視資產在您的Web屬性上是否未被充分利用或過度使用。
1. 內容&#x200B;**參與**： Content Analytics可提供參與深入分析，例如具有特定屬性之資產的平均點進率。 這些見解可協助您判斷特定型別的體驗是否仍然有效。
1. 內容&#x200B;**歷程**：此外，結合Experience Platform中可用的所有其他資料時，您可以獲得有關內容歷程的其他深入分析。 例如，在參與度之上，特定內容是否會導致轉換。 有了這些知識，您就可以決定內容型別的ROI。
1. 內容&#x200B;**個人化**： Entially Content Analytics可讓您根據您的見解採取行動，並使用這些見解來決定如何花錢購買內容。 例如，我應該傳送特定型別的內容給特定對象嗎？ 哪些內容為我提供高度個人化的機會？

## 術語

內容分析使用下列主要辭彙：

![Assets與體驗](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **體驗**：體驗是網頁上的所有文字，網頁可透過造訪該網頁的初始使用者所使用的URL重現。 每個體驗都會取得唯一識別碼。 頁面變更會導致頁面的HTML變更，進而產生新體驗。
* **資產**：資產是個別且唯一的內容，例如影像。 每個資產也會取得唯一識別碼和感應式ID。 可感知ID是與視覺上相同的資產共用的識別碼。 可感知ID有助於對可能有不同資產URL並因此有不同資產ID，但概念上相同的資產進行重複資料刪除。
* **屬性**：屬性是與體驗或資產相關聯的描述性中繼資料元素。 屬性的範例包括：攝影風格、可讀性、說服策略、物件顏色、背景顏色。

## 運作方式

內容分析會使用Experience Platform事件資料集中收集的網頁影像檢視資料。 這些資料可透過各種可用方法來收集： Experience Platform Edge Network (網頁SDK、伺服器API)或Analytics來源聯結器。

![內容分析 — 運作方式](assets/aca-overview.gif)


1. 當使用者造訪為Content Analytics](config/configuration.md)設定的網站[時，Experience Platform Web SDK會記錄曝光次數以及與內容的互動。
1. 身分和功能化服務會處理這些互動。 該程式包含一個編目程式，可修訂定義互動的已設定URL的公開版本。 對於這些編目的URL，Identity Service會唯一識別體驗和資產。 此外，功能化服務會套用AI/ML服務，探索體驗和資產中繼資料與屬性。
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


>[!MORELIKETHIS]
>
>[Content Analytics報告](report/report.md)
>[設定內容分析](config/configuration.md)
>
