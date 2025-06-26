---
description: 如何詢問 Customer Journey Analytics 文件的資料分析問題
title: 使用 Customer Journey Analytics 中的 Data Insights 代理進行資料視覺化
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: 7bf74e02db581bdf11b7efe31b62f018320c7f22
workflow-type: tm+mt
source-wordcount: '2359'
ht-degree: 83%

---

# 使用Data Insights Agent以視覺效果呈現資料

>[!AVAILABILITY]
>
>本文所述的功能將於 2025 年 5 月 28 日開始分階段發佈的版本中，提供給所有符合資格的客戶使用，而您的環境可能尚未能使用這些功能。此功能普遍開放使用時，便會移除此注意事項。有關 Customer Journey Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

>[!AVAILABILITY]
>
>符合資格的客戶可以在限定時間內使用 Data Insights 代理。Data Insights 代理的存取權會於 2025 年 11 月 30 日結束。若要繼續不間斷地使用 Data Insights 代理，請聯絡您的 Adobe 客戶代表以了解關於 Data Insights 代理授權的更多資訊。

Data Insights 代理可以透過 Customer Journey Analytics 中的 AI 助理進行存取，是一個生成式 AI 對話代理程式，能迅速有效地回答您的資料相關問題。此代理會使用來自資料視圖的元件以及您的實際資料，在 Analysis Workspace 建置相關的視覺內容。

使用 Data Insights 代理來回答 Analysis Workspace 中以資料為中心的問題，可以為您節省大量時間，否則您可能需要把這些時間用於在 Analysis Workspace 中手動建置視覺內容，以及熟悉資料視圖元件。

![AI 助理中的 Data Insights 代理](assets/cja-ai-asst-da.gif)

## 範圍內與範圍外之功能的比較

| 功能 | 範圍內 | 範圍外 |
| --- | --- | --- |
| **視覺內容類型** | <ul><li>折線圖</li><li>多折線圖</li><li>自由格式表格</li><li>長條圖</li><li>環形圖</li><li>摘要數字</li></ul> | <ul><li>流量</li><li>流失</li><li>同類群組表格</li><li>區域圖和堆疊區域圖</li><li>堆疊長條圖</li><li>項目符號</li><li>組合</li><li>直方圖</li><li>橫條圖、堆疊橫條圖</li><li>關鍵量度摘要</li><li>散佈圖</li><li>摘要變更</li><li>文字</li><li>樹狀圖</li><li>文氏圖表</li><li>引導式分析：活躍增長、轉換趨勢、參與度、首次使用影響、頻率、漏斗、淨增長、發行影響、保留率、時間軸、趨勢</li></ul> |
| **工作區動作和代理程式功能** | <ul><li>建置及更新視覺內容<p>產生自由格式表格和相關的視覺內容 (例如折線圖、長條圖、環形圖等)。<p>例如，*從二月到五月，各個 SKU 的利潤是多少？*</p></li><li>提出後續問題<p>根據先前任何提示的內容來回覆提示。例如：</p> <ul><li>提示 1：*三月份的趨勢事件。*</li><li>提示 2：*改為顯示三至四月的資料*</li></ul> </li><li>偵測超出範圍的提示<p>如果您提交超出範圍的提示，例如「*匯出此專案*」，Data Insights 代理回覆時會告知您該問題超出範圍。</p></li></ul> | <ul><li>共用</li><li>匯出</li><li>下載</li><li>管理使用者偏好</li><li>管理資料視圖</li><li>Analytics 儀表板應用程式</li><li>歸因</li><li>內嵌摘要或回覆<p>Data Insights 代理無法在聊天邊欄中，透過內嵌方式針對使用者提示給予摘要答覆。超出範圍的提示範例包括：「*請針對我上次的提示提供深入分析摘要*」以及「*請將折線圖視覺內容中的重點進行統整」。*</p></li></ul> |
| **釐清問題** | 如果您提出的問題沒有足夠的背景資訊，或者太過籠統以致無法回答，Data Insights 代理將會透過釐清問題或建議選項來回覆。 <p>以下釐清問題是元件相關問題的範例：</p><ul><li>量度：*您指的是哪一個「收入」量度？*</li><li>維度：*您想聚焦於下列哪個「地區」？*</li><li>區段：*您想套用哪個「客戶」區段？*</li><li>日期範圍：*您所說的「上個月」是指上一個完整月份，還是過去 30 天？*</li></ul><p>以下釐清問題是維度項目相關問題的範例：</p> <ul><li>您所指的「網站商店名稱」是哪一個？(例如：網站商店 #5274、網站商店 #2949 等。)</li></ul> | 釐清問題僅限於元件和維度項目。Data Insights 代理無法釐清資料視圖、視覺內容、資料詳細程度、比較結果和範圍等事項。當無法使用釐清問題時，代理程式會預設您最可能詢問的問題。若其傳回預期外的視覺內容或資料詳細程度，您可以提出後續問題或調整視覺內容及資料。 |
| **資料可驗證性和正確性** | 經由檢視所產生的自由格式表格和資料視覺內容，確認資料的可驗證性和正確性。 <p>例如，若您要求 Data Insights 代理&#x200B;*提供上個月的訂單趨勢*，則您可以藉此確認在新產生的面板、資料視覺內容和自由格式表格中，已選取正確的量度 (「訂單」) 和日期範圍 (「上個月」)。 | Data Insights 代理回覆時不會告知您已新增哪些元件或視覺內容。</p> |
| **意見回饋機制** | <ul><li>肯定</li><li>否定</li><li>標記</li></ul> |  |


## 管理Data Insights Agent的存取權

下列參數能控制對 Customer Journey Analytics 中 Data Insights 代理的存取權：

* **解決方案存取權**：所有 Customer Journey Analytics 客戶皆可透過限期存取方案，在 2025 年 11 月 30 日之前使用 Data Insights 代理。Adobe Analytics 並未提供此代理功能。

* **合約存取權**：如果您在 AI 助理中無法使用 Data Insights 代理，請聯絡您組織的管理員或 Adobe 帳戶團隊。在組織能夠開始使用 Data Insights 代理之前，您必須先同意與生成式 AI 相關的特定法律條款。

* **權限**：使用者必須先在 [!UICONTROL Adobe Admin Console] 中獲得必要的權限，才能存取 Data Insights 代理。

  若要授予權限，[產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)必須在 [!UICONTROL Admin Console] 中完成下列步驟：
   1. 在 **[!UICONTROL Admin Console]** 中，選取「**[!UICONTROL 產品]**」索引標籤，檢視「**[!UICONTROL 所有產品與服務]**」頁面。
   1. 選取「**[!UICONTROL Customer Journey Analytics]**」。
   1. 於「**[!UICONTROL 產品設定檔]**」索引標籤內，選取您想提供「[!UICONTROL AI 助理：產品知識]」存取權的產品設定檔標題。
   1. 在特定的產品設定檔中，選取「**[!UICONTROL 權限]**」索引標籤。

      ![Admin Console 中的「權限」索引標籤](assets/ai-assistant-permissions-tab.png)

   1. 在所提供之表格的「**[!UICONTROL 報告工具]**」列中，選取編輯圖示![編輯](/help/assets/icons/Edit.svg)。
   1. 捲動至或搜尋「**[!UICONTROL AI 助理：產品知識]**」，然後選取此權限旁的加號圖示![加號圓圈](/help/assets/icons/AddCircle.svg)。

      「**[!UICONTROL AI 助理：產品知識]**」權限便會新增至「**[!UICONTROL 包含的權限項目]**」欄位中。

      ![新增權限](assets/ai-assistant-permissions.png)。

   1. 選取「**[!UICONTROL 資料視圖工具]**」索引標籤，然後選取「![Data Insights 代理](/help/assets/icons/AddCircle.svg)」權限旁的加號圖示&#x200B;**[!UICONTROL 加號圓圈]**。

      「**[!UICONTROL Data Insights 代理]**」權限會新增至「**[!UICONTROL 包含的權限項目]**」欄位中。

      ![新增權限](assets/ai-assistant-permissions-dataviewtools.png)。

   1. 選取「**[!UICONTROL 資料視圖]**」索引標籤，選擇要針對 Data Insights 代理啟用的資料視圖。

      >[!IMPORTANT]
      >
      >啟用資料視圖時請將以下事項納入考量：
      >* 每個 IMS 組織最多可以啟用 50 個資料視圖。若特定組織的所有產品設定檔內啟用超過 50 個資料視圖，則 Data Insights 代理會使用最常用的 50 個資料視圖。
      >* 在 Admin Console 中啟用所包含資料視圖當日的某個時間點，Data Insights 代理便可以參照這些資料視圖。

   1. 搜尋或捲動至您想要啟用的資料視圖，然後選取每個資料視圖名稱旁邊的加號圖示![加號圓圈](/help/assets/icons/AddCircle.svg)。

      您新增的每個資料視圖都會顯示在「**[!UICONTROL 包含的權限項目]**」欄位中。

      ![新增權限](assets/ai-assistant-permissions-dataviews.png)。

   1. 選取「**[!UICONTROL 儲存]**」，儲存權限。

  如需關於存取控制的更多資訊，請參閱[存取控制](/help/technotes/access-control.md#access-control)。

## 存取 AI 助理中的 Data Insights 代理

1. 前往 [experience.adobe.com](https://experience.adobe.com/)，並使用您的 Adobe ID 登入。

2. 在 Experience Cloud 首頁上選取「**Customer Journey Analytics**」。

3. 在專案頁面頂部的橫幅中選取「**[!UICONTROL 空白專案]**」，即可開啟一個新的空白專案。

4. 請確認面板所選取的資料視圖，是為了與 Data Insights 代理搭配使用而啟用的資料視圖，如[管理 Customer Journey Analytics 中 Data Insights 代理的存取權](#manage-access-to-data-insights-agent-in-customer-journey-analytics)中所述。

5. 選取頁面右上角的 AI 助理聊天圖示。

   如果您沒有看到聊天圖示，請聯絡您的管理員，以便他們可以在 Admin Conole 中啟用以下功能：

   * 報告工具：**[!UICONTROL AI 助理：產品知識]**

   * 資料視圖工具：**[!UICONTROL Data Insights 代理]**

   如需更多詳細資訊，請參閱[管理 Customer Journey Analytics 中 Data Insights 代理的存取權](#manage-access-to-data-insights-agent-in-customer-journey-analytics)。

   ![AI 助理圖示](/help/assets/ai-asst-icon.png)

6. 在頁面底部的「**[!UICONTROL 詢問 Customer Journey Analytics]**」對話框中，使用 Data Insights 代理提出資料視覺內容的問題。

   如需詳細資訊，請參閱下列範例。

### 範例 1

例如，假設您想知道您的公司在七月的訂單狀況。

**提示：**&#x200B;輸入&#x200B;*「七月訂單趨勢」。*

![AI 提示](/help/assets/ai-asst-prompt1.png)

**回覆：** Data Insights 代理會瀏覽資料視圖中的資料 (包括量度和元件) 以獲取深入分析。它將提示轉換為資料範圍內的正確維度和量度。

如您所見，它自動產生了一張線圖和一個自由格式表格顯示七月的訂單。

![提示答案－線圖和自由格式表格](/help/assets/ai-asst-result.png)

### 範例 2

接下來，您想了解不同區域的收入比較。

**提示：**&#x200B;在提示視窗中，輸入&#x200B;*「依照區域顯示收入」。*

**回覆：** Data Insights 代理擁有的智慧可以理解您所說的「區域」是指「客戶區域」。它產生一張最能清楚顯示各區域收入的長條圖：

![長條圖](/help/assets/ai-asst-result2.png)

### 範例 3

接下來，在了解各區域的收入之外，您還想查看各區域的利潤資料。您可以要求 Data Insights 代理更新最新的視覺內容和自由格式表格，而非重複前一個提示。

**提示：**&#x200B;在提示視窗中，輸入&#x200B;*「新增利潤」。*

**回覆：**&#x200B;**[!UICONTROL 長條圖]**&#x200B;仍然提供最簡潔的答案，但利潤量度已以欄位形式新增至自由格式表格中：

![長條圖](/help/assets/ai-asst-result4.png)

### 範例 4

最後，一起來看看依照產品類別劃分的收入。

**提示：**&#x200B;在提示視窗中，輸入&#x200B;*「依照產品類別劃分的收入比例」。*

**回覆：**&#x200B;同樣地，Data Insights 代理會選擇最合適的視覺內容 (在本案例中是&#x200B;**[!UICONTROL 環形圖]**&#x200B;視覺內容) 來回答問題。

![環形圖](/help/assets/ai-asst-result3.png)

## 資料視覺效果提示範例

以下是一些常見的提示範例，以及 Data Insights 代理回覆這些提示時所使用的視覺內容。

| 範例提示 | 預期中的視覺效果 |
| --- | --- |
| 請顯示[月]的利潤 | 折線圖<p>預設情況下，詢問特定時間範圍內的趨勢或量度，系統預設會傳回折線圖視覺效果。 |
| [月]的訂單趨勢 | 折線圖 |
| 依照區域顯示[月]的收入 | 長條圖 |
| 依照產品類別劃分的收入份額 | 環形圖 |
| 一月至五月，依照星期排序的訂單 | 長條圖 |
| 依照性別顯示三月到六月的訂單 | 長條圖 |
| 從二月到五月，各個 SKU 的利潤是多少？ | 長條圖 |
| [月]依照商店名稱劃分的收入 | 長條圖 |
| [月]利潤最高的 10 個 SKU 是什麼？ | 長條圖 |
| 依照月份劃分的購買比例 | 環形圖 |
| [月]總利潤 | 摘要數字<p>詢問特定時間範圍內的量度「總和」，系統應該會傳回摘要數字視覺效果。 |


## 提示最佳作法

Data Insights 代理會處理每個使用者提示所提供的背景資訊，並嘗試使用自由格式表格中最合適的視覺內容和元件做出聰明的回覆。

回覆可能會隨著提示中使用的特定詞組而有所差異，語言的細微變化也會導致不同的結果。

為了獲得最佳結果，請考慮下列準則：

* **具體：**&#x200B;使用精確的用語來縮小回覆範圍。以下為具體提示的範例：「加州上個月的銷售額」

* **使用明確的量度、維度和區段：**&#x200B;新增特定量度 (例如「收入」)、維度 (例如「網站名稱」)、區段 (例如「iPhone 使用者」) 和日期範圍 (例如「過去三個月」)，有助於 Data Insights 代理聚焦於正確的資料。

* **提出直接的問題：**&#x200B;開門見山地提出問題，可以讓 Data Insights 代理更輕鬆地提供明確、相關的深入分析。以下是在提示中直接提問的範例：「今年各產品類別的平均收入是多少？」

檢視下列表格中的範例用語和句型，您可以在 Data Insights 代理的提示中使用這些用語和句型，並搭配您可以預期的回覆類型。

這些範例旨在幫助您熟悉特定的單字或結構會如何影響 Data Insight 代理的回答，進而確保獲得更精確、更有價值的深入分析。Data Insights 代理會使用生成式 AI，因此在面對類似的提問時，視覺內容或所選取的資料可能會略有不同。

| 期望結果 | 範例術語和詞組 |
| --- | --- |
| 摘要數字視覺效果 | <ul><li>總計</li></ul> |
| 比較元件 | <ul><li>比較</li><li>vs</li><li>對比</li><li>每週</li><li>每月</li><li>每季</li><li>每年</li></ul> |
| 環形圖視覺效果 | <ul><li>比例</li><li>份額</li><li>分佈</li><li>百分比</li><li>貢獻</li><li>部分</li><li>構成項目</li></ul> |
| 折線圖視覺效果 | <ul><li>趨勢</li><li>[時間範圍]中的[量度]</li></ul> |
| 長條圖視覺效果 | <ul><li>依照[維度]劃分的[量度]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## 設定最佳實務

以下是您的Customer Journey Analytics設定（資料檢視、計算量度、區段等）最佳實務，以確保Data Insights Agent可找到正確的元件並傳回較乾淨的答案，而不需要您提示其他資訊。

* **平衡您需要的元件**。 請勿將資料集的所有欄位新增為量度或維度元件至資料檢視。 尤其是您絕不會在分析中使用的分析。 另一方面，請勿嚴格限制自己只能使用您預期分析所需的欄位。 資料檢視太有限，限制了您分析和資料Insight代理程式功能的靈活性。
* **永遠使用好記的顯示名稱**。 確認您在資料檢視中定義的所有欄位（做為量度或維度元件）都有好記的元件名稱。 以易記名稱重新命名欄位的程式與Adobe Analytics來源聯結器資料集中的欄位尤其相關。 這些欄位通常具有不友好的無法識別名稱，例如`eVar41`或`prop25`。
* **使用特殊名稱**。 當您在資料檢視中將欄位同時作為量度和維度元件時，獨特名稱特別相關。 或者，當您在多個元件中使用欄位時，每個元件都有不同的元件設定。
* **使用元件命名慣例**。 您可以使用元件命名慣例來群組元件。 例如，**[!UICONTROL 個訂單 | 產品]**&#x200B;與&#x200B;**[!UICONTROL 訂單 | 客戶]**，以區別資料中可能存在的不同訂購量度。
* **使用資料字典**。 為資料字典中的元件新增說明和其他相關資料。 資料Insight代理程式目前未使用說明和標籤。 但日後可能會使用資料字典說明和標籤。
* **使用核准的計算量度**。 同意僅使用核准的計算量度作為資料檢視中元件的程式，並避免使用實驗性的計算量度。
* **共用必要的區段**。 確保您共用區段，並使區段可見，以利資料分析代理程式提示之用。
* **跨資料檢視標準化元件名稱**。 如果您在多個資料檢視中作為元件使用相同的欄位，請確定您為該元件使用單一易記名稱和單一識別碼。 單一名稱和識別碼可讓資料分析代理程式切換資料檢視，而不會遺失內容。

>[!MORELIKETHIS]
>
>[元件設定](/help/data-views/component-settings/overview.md)
>&#x200B;>[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)
>&#x200B;>[核准計算量度](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>&#x200B;>[共用區段](/help/components/segments/seg-share.md)
>
