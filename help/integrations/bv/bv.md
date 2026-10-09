---
title: 品牌可見度整合
description: 將Brand Visibility與Customer Journey Analytics整合
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Adobe Brand Visibility整合

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/home){target="_blank"}是Generative Engine Optimization的創作AI優先應用程式，旨在協助品牌在AI驅動的搜尋環境中提升其可見度、精確度和影響力。 品牌可見度可提供AI產生之答案中品牌存在感的深入分析、提供規範性內容建議，並將最佳化修正作業自動化。

AI已成為主要探索管道。 大型語言模型(LLM)代理程式（例如ChatGPT、Claude、Copilot和Perplexity）會抓取品牌內容。

>[!NOTE]
>
>您必須布建品牌可見度付費方案，並透過受管理的聯結器連線至您的Experience Platform設定。


>[!IMPORTANT]
>
>在此整合中，美國會進行一些品牌可見度資料的臨時處理。 資料最終會儲存在您的Customer Journey Analytics合約中設定的指定區域。


## 使用案例

您可以透過兩種方式從Customer Journey Analytics和Brand Visibility之間的整合獲益：

* **傳入整合**：使用Customer Journey Analytics中的品牌可見度資料，搭配現有的網頁、行動裝置和其他型別的資料，測量LLM導向的流量（機器人爬蟲、RAG要求、代理程式活動）。 例如，您可以：

  * 透過代理程式來源與傳統管道一起測量LLM驅動流量。

  * 識別LLM大量使用但在人工轉換中表現不佳的內容。

  * 偵測LLM-agent請求在關鍵路徑上失敗的位置。

  * 在URL和主機層級，比較頁面的LLM機器人需求與網頁資料中的轉換和收入。

* **輸出整合**：將Customer Journey Analytics效能資料傳送至Brand Visibility，如此一來，您便可以最佳化LLM來源的AI可見性，這些來源會傳送您有價值的流量，例如ChatGPT或Perplexity。 例如，您可以：

  * 檢視哪些LLM來源會傳送繼續轉換或產生收入的人類訪客。 Customer Journey Analytics會從參照的網路流量（而非機器人資料集）測量這項資訊。
  * 根據LLM來源所傳送之訪客的下游值來排名，然後將您的AI可見度工作集中在績效最佳的來源上。


## 傳入整合

LLM流量透過兩種方式到達您的網站。 Customer Journey Analytics會分別從不同資料來源測量每個路徑。

第一種方式是讀取人工智慧答案，然後點進您的網站。 該次造訪執行的JavaScript與收集您其餘網頁資料相同。 因此，您現有的Customer Journey Analytics網頁資料包含造訪以及將使用者傳送給您的反向連結網域，例如chatgpt.com。 Customer Journey Analytics本身不會將這些造訪標示為AI流量。 若要識別並群組這些欄位，您可在符合AI反向連結網域的連線上建立衍生欄位，然後在該欄位上建立區段和報表。 請參閱[衍生欄位](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}。 您不需要此人為流量的品牌可見度資料集。

第二種方式是直接要求您頁面的機器人或代理程式。 這包括建置AI索引和即時擷取的爬蟲，這些擷取會在使用者向AI助理提交提示時發生。 這些請求不會執行任何JavaScript，因此您現有的網頁資料不會記錄這些請求。 品牌可見度資料集從CDN層擷取此流量。 本節的其餘部分說明該資料集。


### 載入資料集

Brand Visibility Managed Connector會將資料作為摘要資料集傳送給Experience Platform。 若要在Customer Journey Analytics中進行測量，請自行完成兩個設定步驟：

1. 建立包含品牌可見度資料集的連線。
2. 在該連線上建立資料檢視。 資料檢視可讓以下維度和量度在Analysis Workspace中使用。

資料集：

* 使用以XDM摘要度量類別為基礎的[摘要資料集](/help/data-views/summary-data.md)。
* 依URL和主機、時間及請求特性（例如機器人型別、CDN提供者和狀態）儲存資料。

>[!NOTE]
>
>品牌可見度資料集包含彙總資料。 其中不包含任何PII，例如使用者識別碼、提示或回應。
>

由於這是摘要資料集，您可以將其當作查詢資料集，並以完整URL索引鍵將其聯結至事件資料集。

Brand Visibility會在&#x200B;**CDN URL**&#x200B;維度中為您提供此金鑰。 此維度會將主機和要求的路徑合併為單一正規化的完整URL，類似於Customer Journey Analytics儲存網頁資料的方式。 加入是否成功取決於您自己的資料收集。 您的事件資料集需要等同的完整URL欄位，或可剖析和正規化以符合Brand Visibility所提供URL的欄位。 當雙方解析成相同的完整URL時，品牌可見度記錄會符合您網路資料中對應的頁面。

如需詳細資訊，請參閱：

* [設定和設定傳入整合](/help/integrations/bv/configure.md)
* [資料集參考資料](/help/integrations/bv/reference.md)

## 傳出整合

如需傳出整合的資訊，請參閱Adobe Brand Visibility檔案中的[Customer Journey Analytics整合](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"}。
