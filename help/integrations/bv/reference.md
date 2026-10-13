---
title: 品牌可見度傳入整合資料集參考
description: 瞭解用於Brand Visibility與Customer Journey Analytics整合的資料集的所有詳細資訊
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
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '1894'
ht-degree: 2%
---

# 資料集參考資料

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/home){target="_blank"}是Generative Engine Optimization的創作AI優先應用程式，旨在協助品牌在AI驅動的搜尋環境中提升其可見度、精確度和影響力。 品牌可見度可提供AI產生之答案中品牌存在感的深入分析、提供規範性內容建議，並將最佳化修正作業自動化。

AI已成為主要探索管道。 大型語言模型(LLM)代理程式（例如ChatGPT、Claude、Copilot和Perplexity）會抓取品牌內容。

>[!PREREQUISITES]
>
>您必須擁有品牌可見度付費方案。 然後，您[在您的Experience Platform沙箱中設定並啟用](./configure.md) Adobe Brand Visibility來源。
>


>[!IMPORTANT]
>
>在此整合中，美國會進行一些品牌可見度資料的臨時處理。 資料最終會儲存在您的Customer Journey Analytics合約中設定的指定區域。


## 關於資料集

請參閱[總覽](./bv.md)，以取得有關Brand Visibility與Customer Journey Analytics的傳入和傳出整合使用案例的詳細資料。

Brand Visibility會讀取伺服器端的CDN存取記錄檔，並擷取請求方是機器人或自動化代理程式的記錄。 由於資料來自CDN層，因此Brand Visibility會擷取不會引發任何JavaScript標籤的機器人所提出的請求。 標準網站分析工具完全遺漏此流量。

資料集使用&#x200B;**CDN要求摘要**&#x200B;欄位群組。 每個欄位都位於`cdn`物件下，因此下表中的欄位名稱會採用<code>cdn._name_&#x200B;的形式</code>，例如`cdn.url`和`cdn.botType`。

每筆記錄說明主機、URL路徑、機器人型別、CDN提供者、狀態代碼、反向連結、轉送主機，以及一小時第一個位元組時間的組合。 當相同的組合每小時出現一次以上時，Customer Journey Analytics會將這些記錄合併為一列，並增加請求計數。 使用&#x200B;**CDN要求計數**&#x200B;量度來測量磁碟區。 請勿使用列計數。

## 維度

設定包含品牌可見度資料集的連線後，以下維度可用作資料檢視中的元件。 **欄位**&#x200B;欄顯示CDN要求摘要欄位群組中的來源欄位。

| 維度 | 欄位 | 說明 |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | 要求的標準化完整URL，預期做為聯結金鑰。 Brand Visibility會將主機和要求的路徑結合為單一URL，並將其標準化以符合Customer Journey Analytics為網頁資料儲存的完整URL表單。 使用此維度，將品牌可見度查詢資料集聯結至具有同等完整URL欄位的事件資料集。 它包含主機和路徑，但不包含配置。 |
| CDN URL路徑 | `cdn.path` | 代理程式要求的原始URL路徑和查詢字串，由CDN傳遞。 不包含配置或主機。 當您需要確切的請求路徑（而不是標準化的聯結金鑰）時，請使用此選項。 |
| CDN主機 | `cdn.host` | 收到請求的主機名稱，例如www.example.com。 此主機也是CDN URL加入索引鍵的一部分。 當組織同一CDN帳戶擁有多個子網域時，資料集可包含多個主機。 |
| CDN機器人型別 | `cdn.botType` | 請求代理的Brand Visibility分類。 值涵蓋傳統搜尋爬蟲、AI索引爬蟲和AI即時擷取代理程式。 如需完整分類法，請參閱下列[機器人代理程式類別](#bot-agent-categories)。 |
| CDN使用者代理 | `cdn.userAgent` | CDN記錄檔的原始使用者代理字串。 用於區分機器人分類中的子型別，或用於驗證品牌可見度指派的分類。 |
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

當品牌可見度無法比對使用者代理程式與可辨識的模式時，它會指派值`Unknown`。 您可以使用&#x200B;**CDN使用者代理程式**&#x200B;維度來識別提出這些要求的代理程式。

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

## 量度

設定包含品牌可見度資料集的連線後，下列量度即可作為資料檢視中的元件。 **欄位**&#x200B;欄顯示CDN要求摘要欄位群組中的來源欄位。

| 量度 | 欄位 | 說明 |
|--------|-------|-------------|
| CDN要求計數 | `cdn.requests` | CDN請求的總數，從請求欄位中加總所有列。 請一律使用此量度來測量體積。 請勿使用列計數。 |
| CDN錯誤計數 | `cdn.status`, `cdn.requests` | 傳回4xx或5xx HTTP狀態代碼的請求計數。 |
| CDN錯誤率 | 衍生自CDN錯誤計數 | 錯誤計數為請求總數的百分比。 |
| CDN平均時間至第一個位元組 | `cdn.timeToFirstByte` | CDN收到要求至回應第一個位元組的平均時間（毫秒）。 CDN快取的回應通常少於50毫秒。 由來源提供的回應通常為300毫秒至700毫秒。 AI即時擷取代理程式通常會顯示較高的值，對應至逾時或極慢的原始回應。 即時擷取代理程式型別的高平均值值得調查為AI可見度風險。 |

## 邊界

此資料集只會從CDN存取記錄檔擷取機器人流量。 它不包含下列專案：

* **使用者工作階段、轉換或參與資料。** 從AI答案點進的使用者會在您的頁面上執行JavaScript，因此瀏覽位於您現有的網頁資料中，而非此資料集中。 您可以將兩個資料集匯入Customer Journey Analytics，並比較同一URL和主機的資料集。
* **任何個人識別碼，例如ECID。** 您無法從此資料集執行人員層級聯結。 加入會在URL和主機層級運作。
* **次秒時間粒度。** 時間戳記為每小時。 您無法將一小時內的流量劃分為數分鐘或數秒。
* **頁面內容或轉譯的HTML。** 此資料集會記錄擷取事實及其結果，而非AI從頁面讀取的內容。
* **轉換資料。** 此資料集不會告訴您AI答案是否會導致人員造訪您的網站或進行轉換。 其會保留彙總CDN摘要資料，而非以人員為基礎的事件資料，因此不會將任何請求連結至個別人員或工作階段。
