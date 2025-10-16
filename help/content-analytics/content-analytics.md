---
title: Content Analytics 概觀
description: Content Analytics 概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 100%

---

# Content Analytics 概觀

Content Analytics 能幫助行銷人員了解內容如何影響企業已定義的關鍵績效指標。除了行為資料之外，Content Analytics 還會收集關於內容使用方式和內容產生影響的資料。例如，客戶對於特定語調、特定色調或特定主題的反應是否較好？這些資訊與專門設計的報告工作流程和範本，可以幫助您在 Customer Journey Analytics 中進行更好的分析並，獲得有關客戶歷程資料的更深入。

Content Analytics 會使用人工智慧式和機器學習式的&#x200B;**特徵化服務**，將內容劃分為元件和屬性。透過在所有內容上建立結構化中繼資料設定檔，您可以分析哪些內容以及這些內容的哪些屬性可以推動業務成長。

除了結構化中繼資料設定檔的建立之外，Content Analytics 還提供&#x200B;**身分識別服務**，使用單一識別碼來識別資產和體驗。身分識別服務可以識別完全相同資產出現在多個地方的情況。當這種情況發生時，此資產的實例將被視為相同資產，這樣可以更全面地了解內容的使用和消費。

## 值

Content Analytics 確實不斷提升其價值：

1. 內容&#x200B;**使用方式**：透過 Content Analytics，您可以了解哪些資產正獲得曝光度，以及資產是在哪裡獲得曝光度。這些分析可以幫助您了解具一些網頁屬性的資產是否未充分利用或過度使用。
1. 內容&#x200B;**參與度**：Content Analytics 可以提供參與度分析，例如某些屬性的資產平均點擊率。這些分析可以幫助您確定特定類型的體驗是否仍然有效。
1. 內容&#x200B;**歷程**：此外，當與 Experience Platform 的所有其他資料合併時，您可以獲得有關內容歷程的更多內容。例如，除了參與度之外，特定內容是否會造成瀏覽轉換。了解這些事情後，您就可以確定內容類型的投資報酬率。
1. 內容&#x200B;**個人化**：最終，Content Analytics 可讓您根據自己的分析採取行動，並使用這些分析來確定如何花錢在內容上。例如，我應該向特定客群發送特定類型的內容嗎？哪些內容能為我提供高度個人化的機會？

## 術語

Content Analytics 會使用以下關鍵用語：

![資產和體驗](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **體驗**：體驗是指網頁上的所有文字，可以使用最初造訪該網頁之使用者所使用的 URL 進行複製。每次體驗都會有一個唯一識別碼。針對頁面的變更會導致頁面 HTML 的變更，因而帶來新的體驗。
* **資產**：資產是獨立且獨特的內容，例如影像。每項資產亦會獲得一個唯一識別碼和一個感知 ID。感知 ID 是與視覺上相同的資產共用的識別碼。感知 ID 有助於對可能具有不同資產 URL 並因此具有不同資產 ID，但感知上相同的資產進行重複資料刪除。
* **屬性**：屬性是與體驗或資產相關的描述性中繼資料元素。屬性的範例有：攝影風格、可讀性、說服策略、物件顏色、背景顏色。

## 運作方式

Content Analytics 使用 Experience Platform 事件資料集中的網頁影像檢視資料[收集內容事件資料](config/datacollection.md)。並將內容資料收集與 (現有的) 行為資料收集實施結合。

![Content Analytics：如何運作](assets/aca-overview.gif)

1. 當使用者瀏覽網站時，[設定為適用於 Content Analytics](config/configuration.md)，Experience Plarform Web SDK 會記錄內容的印象和互動。
1. 身分識別和特徵化服務會處理這些互動。過程包括一項獲取服務，其會重新檢視定義互動之已設定 URL 的公開版本。對於所有這些獲取到的 URL，身分識別服務是唯一識別體驗和資產的服務。特徵化服務應用 AI/ML 服務來探索體驗和資產中繼資料和屬性。
1. 這些服務 ([元件、屬性和身分識別](/help/content-analytics/report/components.md)) 的結果將用於更新 Experience Platform 中相關的特定 Content Analytics 資料集。
1. Content Analytics 資料，以及行為資料和其他查詢資料，可於 Customer Journey Analytics 設定 ([連線](/help/connections/overview.md)、[資料視圖](/help/data-views/data-views.md)和 [Workspace](/help/analysis-workspace/home.md)) 中使用。設定可為您對內容的獨特宏觀分析奠定基礎。<br/>您可以使用 [Content Analytics 範本](/help/content-analytics/report/report.md#template)快速開始您的 Content Analytics 報告和分析。


>[!NOTE]
>
>Content Analytics 利用 AI/ML 服務，可能會產生不準確或誤導性的結果。因此，請運用您的判斷力來檢閱和驗證 AI/ML 所產生的輸出。
>
>您可以使用&#x200B;**[!UICONTROL 意見回饋]**&#x200B;索引標籤，可從主介面上的 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 找到，提供有關 AI/ML 產生之輸出的意見回饋。
>

>[!NOTE]
>
>如果您已獲得 Privacy and Security Shield 附加元件的授權，請注意，遵守 Content Analytics 規定的體驗和資產 (所產生的任何資料)，並不涵蓋在 DULE 標籤或客戶管理金鑰的範圍內。此外，Content Analytics 不是符合 HIPAA 標準的服務。
>


>[!MORELIKETHIS]
>
>[Content Analytics 報告](report/report.md)
>>[設定 Content Analytics](config/configuration.md)
>>[在 Customer Journey Analytics 中計算退回與退回率](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)
>

