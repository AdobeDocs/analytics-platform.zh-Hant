---
title: 內容分析概觀
description: 內容分析概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: e29b22fe7ba78faa5d4d169f1ff755b0ca488f8e
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# 內容分析概觀

<!-- 
This is a placeholder article for upcoming Content Analytics documentation. Currently used to set up contextual help entries for developer working on onboarding UI and workspace UI 
-->

>[!WARNING]
>
>本文是即將推出之最終版本的初步非官方草稿版本，屬於內容分析檔案的一部分。 所有內容可能會有所變更，而目前的本文版本概不提供任何法律義務。
>

{#release-limited-testing}

內容分析可協助行銷人員瞭解內容如何影響企業已定義的關鍵績效指標。 除了傳統的以微層級為基礎的功能以外，內容分析還提供測試內容片段（例如A/B測試）的深入分析，瞭解內容如何從巨集層級推動影響。 例如，客戶對特定語調、特定調色盤或特定主題的回應是否更好？

Content Analytics使用AI和機器學習式的&#x200B;**特徵化服務**，將內容細分為元件和屬性。 透過在所有內容上建立結構化的中繼資料設定檔，您可以分析哪些內容以及該內容的哪些屬性可推動業務成果。

除了建立此結構化的中繼資料設定檔之外，Content Analytics還提供使用單一識別碼來識別資產和體驗的&#x200B;**識別服務**。 Identity服務可瞭解資產（例如）是否已重新調整大小、裁切，或儲存為不同的檔案格式。 此服務會將該資產的所有變數指派給相同的單一識別碼。 因此，identity service可讓您根據資產的不同表單和位置彙總資產的效能。

## 值

內容分析提供的價值會越來越高：

1. 內容&#x200B;**使用情形**：透過內容分析，您可以深入瞭解哪些資產會收到曝光數，以及哪些資產會收到曝光數。 這些見解可協助您檢視資產在您的Web屬性上是否未被充分利用或過度使用。
1. 內容&#x200B;**參與**： Content Analytics可提供參與深入分析，例如具有特定屬性之資產的平均點進率。 這些見解可協助您判斷特定型別的體驗是否仍然有效。
1. 內容&#x200B;**歷程**：此外，結合Experience Platform中所有其他可用的資料時，您可以獲得內容歷程的其他深入分析。 例如，在參與度之上，特定內容是否會導致轉換。 有了這些知識，您就可以決定內容型別的ROI。
1. 內容&#x200B;**個人化**： Entially Content Analytics可讓您根據您的見解採取行動，並使用這些見解來決定如何花錢購買內容。 例如，我應該傳送特定型別的內容給特定對象嗎？ 哪些內容為我提供高度個人化的機會？

## 術語

內容分析使用下列主要辭彙：

![Assets與體驗](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **體驗**：體驗是網頁上的所有文字，可以使用造訪該網頁的初始使用者所使用的URL重現。 每個體驗都會取得唯一識別碼。
* **資產**：資產是個別且唯一的內容，例如影像。 每個資產也會取得唯一識別碼。
* **屬性**：屬性是與體驗或資產相關聯的描述性中繼資料元素。 屬性的範例包括：攝影風格、可讀性、說服策略、物件顏色、背景顏色。

## 運作方式

「內容分析」會使用Experience Platform事件資料集中收集的網頁影像檢視資料。 這些資料可透過各種可用方法收集：Experience PlatformEdge Network(網頁SDK、伺服器API)或Analytics來源聯結器。

![內容分析 — 運作方式](assets/how-it-works.png)


1. 任何新資料快照到達啟用「內容分析」的事件資料集時，都會觸發功能化服務的偵測部分。
1. 功能化偵測服務會判斷該快照中的哪些資料與內容分析相關，並修訂這些網頁影像檢視的體驗和資產。
1. 在重新造訪後，系統會透過Experience Platform網站SDK和Experience PlatformEdge Network的正確設定，收集特定的內容分析資料。 然後，資料會傳送至專用的內容分析資料集和相關查詢資料集。
1. 功能化組合器服務和身分識別服務會處理重新造訪的資料。
1. 這些服務（元件、屬性和身分）的結果可用來更新Experience Platform中相關的特定內容分析資料集。
1. 內容分析資料以及行為資料和其他查詢資料集隨後可用於Customer Journey Analytics設定(連線、資料檢視和Workspace)。 該設定提供了對您的內容進行獨特巨集層級深入分析的基礎。

>[!MORELIKETHIS]
>
>[內容分析報告](report/report.md)
>[設定內容分析](config/configuration.md)
