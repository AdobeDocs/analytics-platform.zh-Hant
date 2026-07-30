---
title: LLM Optimizer整合
description: 將LLM Optimizer與Customer Journey Analytics整合
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
source-git-commit: 3aa4e0c98e9a3e4163dad992e598638892fc88cd
workflow-type: tm+mt
source-wordcount: 2539
ht-degree: 2%

---


# LLM Optimizer整合

[Adobe LLM Optimizer](https://experienceleague.adobe.com/zh-hant/docs/llm-optimizer/using/home){target="_blank"}是Generative Engine Optimization的創作AI優先應用程式，旨在協助品牌在AI驅動的搜尋環境中提升其可見度、精確度和影響力。 LLM Optimizer可提供AI產生之答案中品牌存在感的深入分析、提供規範性內容建議，並自動化最佳化修正。

AI已成為主要探索管道。 LLM代理程式（例如ChatGPT、Claude、Copilot和Perplexity）會抓取品牌內容。

>[!PREREQUISITES]
>
>您必須布建LLM Optimizer付費產品，並透過受管理的聯結器連線至您的Experience Platform設定。


>[!IMPORTANT]
>
>在此整合中，美國會進行一些LLM Optimizer資料的臨時處理。 資料最終會儲存在您的Customer Journey Analytics合約中設定的指定區域。


## 使用案例

Customer Journey Analytics與LLM Optimizer的整合可讓您透過兩個方式受益：

* **傳入整合**：在Customer Journey Analytics中使用LLM Optimizer資料，連同現有的網頁、行動裝置和其他型別的資料，一起測量LLM導向的流量（機器人爬蟲、RAG要求、代理程式活動）。 例如，您可以：

  * 透過代理程式來源與傳統管道一起測量LLM驅動流量。

  * 識別LLM大量使用但在人工轉換中表現不佳的內容。

  * 偵測LLM-agent請求在關鍵路徑上失敗的位置。

  * 在URL和主機層級，比較頁面的LLM機器人需求與網頁資料中的轉換和收入。

* **輸出整合**：將Customer Journey Analytics效能資料傳送至LLM Optimizer，如此一來，您便可以最佳化LLM來源的AI可見性，這些來源會傳送您有價值的流量，例如ChatGPT或Perplexity。 例如，您可以：

  * 檢視哪些LLM來源會傳送繼續轉換或產生收入的人類訪客。 Customer Journey Analytics會從參照的網路流量（而非機器人資料集）測量這項資訊。
  * 根據LLM來源所傳送之訪客的下游值來排名，然後將您的AI可見度工作集中在績效最佳的來源上。


## 傳入整合

LLM流量透過兩種方式到達您的網站。 Customer Journey Analytics會分別從不同資料來源測量每個路徑。

第一種方式是讀取人工智慧答案，然後點進您的網站。 該次造訪執行的JavaScript與收集您其餘網頁資料相同。 因此，您現有的Customer Journey Analytics網頁資料包含造訪以及將使用者傳送給您的反向連結網域，例如chatgpt.com。 Customer Journey Analytics本身不會將這些造訪標示為AI流量。 若要識別並群組這些欄位，您可在符合AI反向連結網域的連線上建立衍生欄位，然後在該欄位上建立區段和報表。 請參閱[衍生欄位](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}。 您不需要LLM Optimizer資料集來進行此人為流量。

第二種方式是直接要求您頁面的機器人或代理程式。 這包括建置AI索引和即時擷取的爬蟲，這些擷取會在使用者向AI助理提交提示時發生。 這些請求不會執行任何JavaScript，因此您現有的網頁資料不會記錄這些請求。 LLM Optimizer資料集會從CDN層擷取此流量。 本節的其餘部分說明該資料集。

### 將資料集上線到Customer Journey Analytics

LLM Optimizer Managed Connector會將資料以摘要資料集的形式傳送至Experience Platform。 若要在Customer Journey Analytics中進行測量，請自行完成兩個設定步驟：

1. 建立包含LLM Optimizer資料集的連線。 請參閱[建立或編輯連線](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}。
2. 在該連線上建立資料檢視。 資料檢視可讓以下維度和量度在Analysis Workspace中使用。 請參閱[建立或編輯資料檢視](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}。

資料集：

* 使用以XDM摘要度量類別為基礎的[摘要資料集](/help/data-views/summary-data.md)。
* 依URL和主機、時間及請求特性（例如機器人型別、CDN提供者和狀態）儲存資料。

>[!NOTE]
>
>LLM Optimizer資料集包含彙總資料。 其中不包含任何PII，例如使用者識別碼、提示或回應。
>

由於這是摘要資料集，您可以將它視為查詢資料集，並以完整URL索引鍵將其聯結至事件資料集。

LLM Optimizer會在&#x200B;**CDN URL**&#x200B;維度中為您提供此金鑰。 此維度會將主機和要求的路徑合併為單一正規化的完整URL，類似於Customer Journey Analytics儲存網頁資料的方式。 加入是否成功取決於您自己的資料收集。 您的事件資料集需要等同的完整URL欄位，或可剖析和正規化以符合LLM Optimizer所提供URL的欄位。 當雙方解析為相同的完整URL時，LLM Optimizer記錄會比對您網路資料中對應的頁面。

### 關於資料集

LLM Optimizer會讀取伺服器端的CDN存取記錄檔，並擷取請求方為機器人或自動化代理程式的記錄。 由於資料來自CDN層，因此LLM Optimizer會擷取不會引發任何JavaScript標籤的機器人所提出的請求。 標準網站分析工具完全遺漏此流量。

資料集使用&#x200B;**CDN要求摘要**&#x200B;欄位群組。 每個欄位都位於`cdn`物件下，因此下表中的欄位名稱會採用`cdn.<name>`的形式，例如`cdn.url`和`cdn.botType`。

每筆記錄說明主機、URL路徑、機器人型別、CDN提供者、狀態代碼、反向連結、轉送主機，以及一小時第一個位元組時間的組合。 當相同的組合每小時出現一次以上時，Customer Journey Analytics會將這些記錄合併為一列，並增加請求計數。 使用&#x200B;**CDN要求計數**&#x200B;量度來測量磁碟區。 請勿使用列計數。

### 維度

設定包含LLM Optimizer資料集的連線後，以下維度可用作資料檢視中的元件。 **欄位**&#x200B;欄顯示CDN要求摘要欄位群組中的來源欄位。

| 維度 | 欄位 | 說明 |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | 要求的標準化完整URL，預期做為聯結金鑰。 LLM Optimizer將主機和要求的路徑結合為單一URL，並將其標準化以符合Customer Journey Analytics為網頁資料儲存的完整URL表單。 使用此維度，將LLM Optimizer查詢資料集聯結至具有同等完整URL欄位的事件。 它包含主機和路徑，但不包含配置。 |
| CDN URL路徑 | `cdn.path` | 代理程式要求的原始URL路徑和查詢字串，由CDN傳遞。 不包含配置或主機。 當您需要確切的請求路徑（而不是標準化的聯結金鑰）時，請使用此選項。 |
| CDN主機 | `cdn.host` | 收到請求的主機名稱，例如www.example.com。 此主機也是CDN URL加入索引鍵的一部分。 當組織同一CDN帳戶擁有多個子網域時，資料集可包含多個主機。 |
| CDN機器人型別 | `cdn.botType` | LLM Optimizer對請求代理的分類。 值涵蓋傳統搜尋爬蟲、AI索引爬蟲和AI即時擷取代理程式。 如需完整分類法，請參閱下列[機器人代理程式類別](#bot-agent-categories)。 |
| CDN使用者代理 | `cdn.userAgent` | CDN記錄檔的原始使用者代理字串。 用於區分機器人分類中的子型別，或驗證LLM Optimizer指派的分類。 |
| CDN HTTP狀態 | `cdn.status` | HTTP回應狀態代碼。 指出機器人是否收到其要求的內容。 請參閱下列[狀態碼](#status-codes)，以取得AI流量專屬的解譯指南。 |
| CDN供應商 | `cdn.cdnProvider` | 哪個CDN處理了要求。 值為`akamai`、`byocdn-akamai`、`byocdn-fastly`和`byocdn-cloudfront`。 `byocdn-`首碼表示記錄收集路徑，而不是不同的CDN廠商。 當組織有主機採用不同的CDN設定時，資料集可包含多個值。 |
| CDN反向連結 | `cdn.referer` | CDN記錄檔的HTTP Referer標頭值。 機器人流量通常為空。 當出現時，它可以指出觸發擷取的AI產品或網域。 例如， chat.openai.com。 |
| CDN轉送主機 | `cdn.xForwardedHost` | X-Forwarded-Host標頭值（如果存在）。 當請求在到達來源之前透過反向Proxy或CDN遮蔽層傳遞時相關。 |
| CDN事件日期 | 衍生自記錄時間戳記 | 此記錄每小時批次時間戳記的日期部分。 |
| CDN事件小時 | 衍生自記錄時間戳記 | 此記錄每小時批次時間戳記的小時部分。 |

### 機器人代理類別

**CDN機器人型別**&#x200B;維度將代理程式組織成三個類別。 每個類別都會回答不同的分析問題。

**傳統搜尋爬蟲**&#x200B;傳統搜尋引擎的索引內容。 使用此類別來測量您的內容對於傳統搜尋引擎的可見度。

| 機器人型別值 | 廠商 | 說明 |
|---|---|---|
| `GoogleBot` | Google | Google的主要搜尋索引爬蟲。 也提供Google Discover和Google新聞。 |
| `BingBot` | Microsoft | Bing的搜尋索引爬蟲。 同時提供Microsoft Copilot的網路接地指數。 |

**AI索引爬蟲**&#x200B;抓取內容以建置或更新AI產品的訓練語料庫或搜尋索引。 這些爬蟲正在準備模型的知識庫，未回應即時使用者請求。 當URL具有大量爬蟲時，AI廠商會認為內容值得索引。 當URL的爬蟲數量低但即時擷取數量高時，模型會從快取知識中擷取，而非擷取最新內容。

| 機器人型別值 | 廠商 | 說明 |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI用於模型訓練資料和知識庫建構的主要爬蟲。 |
| `OAI-SearchBot` | OpenAI | ChatGPT網頁搜尋產品的OpenAI爬蟲。 與GPTBot不同。 此代理程式會建立即時搜尋索引，而非訓練語料庫。 |
| `ClaudeBot` | 人類 | 人類模型訓練資料的主要爬蟲。 |
| `Claude-SearchBot` | 人類 | Claude的搜尋和擷取索引的Anthropic爬蟲。 與ClaudeBot不同。 |
| `PerplexityBot` | 複雜性 | 複雜度的索引爬蟲。 Perplexity使用此代理程式來建立其答案產生的語料庫。 |

**AI即時擷取**&#x200B;發生於真實使用者將提示提交給AI小幫手，而小幫手在回應之前即時擷取頁面。 使用此類別來測量透過AI助理到達的直接使用者需求。

| 機器人型別值 | 廠商 | 說明 |
|---|---|---|
| `ChatGPT-User` | OpenAI | 使用者向ChatGPT提出問題。 ChatGPT已擷取此URL以讀取並形成其答案。 |
| `ChatGPT Clients` | OpenAI | ChatGPT行動應用程式（iOS和Android）進行即時擷取。 使用者代理字串包含應用程式版本和裝置。 |
| `Claude-User` | 人類 | 使用Claude的使用者或應用程式已即時擷取此URL。 使用者代理字串可識別特定的Claude產品，例如claude-code。 |
| `Perplexity-User` | 複雜性 | 使用者向「Perplexity」提出問題。 困惑功能已擷取此URL以基礎其答案。 |
| `Google-NotebookLM` | Google | 使用者已開啟Google NotebookLM且來源為此網域。 NotebookLM會擷取來源網域內的每個可連線的URL。 |
| `Google-ai-mode` | Google | Google搜尋的AI概述功能會擷取此URL，並將其納入搜尋結果的AI產生答案面板中。 |
| `Gemini-Deep-Research` | Google | 一位使用者執行了Gemini深度研究會議。 Deep Research會跨多個來源進行許多循序擷取，以編譯研究報告。 |
| `GoogleAgent-URLContext` | Google | 使用者與Gemini共用URL並詢問有關該頁面的問題。 Gemini已擷取URL Live來回答有關該特定內容的問題。 |
| `Amzn-User` | Amazon | Amazon Alexa或Amazon AI代理程式即時擷取此URL。 通常出現在參考和檔案內容上。 |
| `MistralAI-User` | Mistral | 從Mistral支援的產品或API消費者即時擷取。 |

當LLM Optimizer無法比對使用者代理程式與可辨識的模式時，它會指派值`Unknown`。 您可以使用&#x200B;**CDN使用者代理程式**&#x200B;維度來識別提出這些要求的代理程式。

### 狀態代碼

此資料集中的HTTP狀態碼會指出AI代理程式是否收到其要求的內容。

| 狀態 | 名稱 | 解釋 |
|--------|------|----------------|
| 200 | 確定 | 機器人已收到完整回應。 內容可供AI使用。 |
| 304 | 未修改 | 機器人確認內容未變更，並使用其快取版本。 內容可供使用。 |
| 301 | 已永久移動 | 已將機器人重新導向至新的URL。 每個重新導向都會增加額外的來回次數。 經常抓取的URL上的301數量較多表示重新導向應在CDN層級解決。 |
| 302 | 找到（暫時重新導向） | 延遲罰金與301相同。 不同於301，它不會表示永久移動，因此機器人會繼續點選原始URL。 |
| 403 | 禁止 | CDN或來源封鎖了機器人。 這可能是有意為之（例如，透過robots.txt規則或WAF政策），或無意為之（例如，透過過於廣泛的速率限制）。 當AI擷取遭到封鎖時，該內容無法出現在AI答案中。 |
| 404 | 找不到 | URL不存在。 AI代理程式型別上的404數量上限表示AI的索引包含過期的URL。 使用410狀態告知爬蟲從索引中永久移除URL。 |
| 429 | 太多請求 | CDN速率限制了機器人。 即時擷取代理程式型別持續發生429個錯誤，表示向AI助理詢問內容相關問題的使用者會收到不完整或遺漏的回應。 |
| 504 | 閘道逾時 | CDN已停止等待來源回應。 內容未送達AI。 當頁面逾時，AI將無法存取其內容，也無法將其納入答案中。 即時擷取代理程式型別上的高504數量是直接的AI可見度風險。 |

### 量度

設定包含LLM Optimizer資料集的連線後，下列量度即可作為資料檢視中的元件。 **欄位**&#x200B;欄顯示CDN要求摘要欄位群組中的來源欄位。

| 量度 | 欄位 | 說明 |
|--------|-------|-------------|
| CDN要求計數 | `cdn.requests` | CDN請求的總數，從請求欄位中加總所有列。 請一律使用此量度來測量體積。 請勿使用列計數。 |
| CDN錯誤計數 | `cdn.status`, `cdn.requests` | 傳回4xx或5xx HTTP狀態代碼的請求計數。 |
| CDN錯誤率 | 衍生自CDN錯誤計數 | 錯誤計數為請求總數的百分比。 |
| CDN平均時間至第一個位元組 | `cdn.timeToFirstByte` | CDN收到要求至回應第一個位元組的平均時間（毫秒）。 CDN快取的回應通常少於50毫秒。 由來源提供的回應通常為300毫秒至700毫秒。 AI即時擷取代理程式通常會顯示較高的值，對應至逾時或極慢的原始回應。 即時擷取代理程式型別的高平均值值得調查為AI可見度風險。 |

### 資料集邊界

此資料集只會從CDN存取記錄檔擷取機器人流量。 它不包含下列專案：

* **使用者工作階段、轉換或參與資料。** 從AI答案點進的使用者會在您的頁面上執行JavaScript，因此瀏覽位於您現有的網頁資料中，而非此資料集中。 您可以將兩個資料集匯入Customer Journey Analytics，並比較同一URL和主機的資料集。
* **任何個人識別碼，例如ECID。** 您無法從此資料集建立人員層級聯結。 加入會在URL和主機層級運作。
* **次秒時間粒度。** 時間戳記為每小時。 您無法將一小時內的流量劃分為數分鐘或數秒。
* **頁面內容或轉譯的HTML。** 此資料集會記錄擷取事實及其結果，而非AI從頁面讀取的內容。
* **轉換資料。** 此資料集不會告訴您AI答案是否會導致人員造訪您的網站或進行轉換。 其會保留彙總CDN摘要資料，而非以人員為基礎的事件資料，因此不會將任何請求連結至個別人員或工作階段。

## 傳出整合

待定。


<!-- 

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/zh-hant/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl and reference brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII, such as user identifiers, prompts, or responses.
>

You use the LLM Optimizer dataset in a connection. Because the dataset is a summary dataset, you can use the dataset as a lookup dataset and potentially join to an event dataset on a full-URL key.

LLM Optimizer provides this key for you in the **CDN URL** dimension. The key combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. This join-key field facilitates the join. The outcome depends on your Customer Journey Analytics implementation and whether your event dataset has a page URL field that matches the URL representation LLM Optimizer provides. When both sides resolve to the same full URL, the LLM Optimizer record matches the corresponding page in your web data.

### About the dataset

LLM Optimizer reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, LLM Optimizer captures requests from bots that do not execute any JavaScript tag. Standard web analytics tools miss this traffic entirely.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears multiple times hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| CDN URL | The normalized full URL for the request, intended as the join key. LLM Optimizer combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the LLM Optimizer lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | LLM Optimizer's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by LLM Optimizer. |
| CDN HTTP Status | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and b`yocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When LLM Optimizer cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| CDN Request Count | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **Human sessions, conversions, or engagement data.** Human sessions are in your existing web analytics dataset. To correlate AI demand with human outcomes, join the two datasets in CJA at the URL and host level.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join works at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** Whether an AI answer led a user to visit the site or convert is not in this dataset. That analysis requires joining to human session data in CJA.

## Outbound integration

To be determined.

-->