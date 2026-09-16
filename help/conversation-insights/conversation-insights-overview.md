---
title: 交談深入分析概觀
description: 瞭解交談深入分析的價值和術語，並瞭解交談深入分析的運作方式。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 39d6847296cc385d501defda292b5b3cae98b46a
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 1%
---
# 交談見解

對話深入解析可讓您從提供給客戶的代理程式體驗中分析對話。 這些代理程式體驗可以基於大型語言模型(LLM)或基於人類對話。 對話深入分析會大規模分析對話，並在完整的客戶歷程中提供這些對話的情境。 透過交談深入分析，您可以瞭解代理程式對實際使用者結果的影響。

對話深入分析可解決您可能會遇到的問題。 例如：

* 您沒有使用insight瞭解客戶在歷程內容中與代理程式（LLM或人類）互動時會發生什麼情況。
* 您沒有能力瞭解：
  * 哪些代理商正在大規模地告訴客戶。
  * 客戶如何大規模與代理商互動。
  * 這些互動對KPI的整體影響為何？
* 您可以建立代理式體驗來因應不斷變化的使用者偏好設定。

透過交談深入分析，您可以瞭解：

* 代理程式告訴使用者的內容。
* 使用者向代理程式詢問。
* 交談對您的KPI有何影響。

您可以決定代理程式如何依照指示執行、代理程式遵守品牌指引的程度，以及執行代理程式的成本是否由結果所證明。


## 概念

在「交談深入分析」的高階層，[交談](#conversation)是一系列相互關聯的[個回合](#turn)。 每個回合都可以獨立傳遞[提示](#prompt)、[回應](#response)和[回饋](#feedback)事件。 [訊號](#signal)是從交談衍生的結構化觀察，而混合資料集會將來源事件和訊號彙整在一起，以便報告。

交談深入分析會分析兩個層級的代理程式互動：

* [交談](#conversation)層級：使用者與代理程式之間的完整互動（包含多個輪迴）。
* [Turn](#turn)層級：該交談中的一個互動週期，包含使用者提示和代理程式回應。

代理程式應用程式或服務會將交談相關的體驗事件傳送至Experience Platform。 提示、回應和回饋意見事件資料可單獨送達。 Platform服務會將這些事件建立關聯並混合為事件層級記錄，選擇性地使用擷取的訊號擴充資料，並讓產生的資料可供Customer Journey Analytics報表使用。

### 對話

交談是指使用者與代理程式之間的完整互動。 它可以包含一或多個車輪。

交談是容器或群組層級。 該容器適合用於下列問題：

* 有多少交談發生？
* 交談的整體主題為何？
* 交談中的情緒有何變更？
* 哪些對話最終會導致轉換？

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[交談](./conversation-insights-implement.md#conversation)物件。

### 翻轉

回合是指對話中的一個互動週期。

典型的車削包括

* 使用者提示
* 代理程式回應
* （選用）使用者回饋

轉彎是報告用途的主要分析物件。 交談混合器服務將可用的提示、回應、回饋和訊號資訊合併成回合層級記錄。

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[turn](./conversation-insights-implement.md#turn)物件。

### 提示

提示是提交給代理程式的輸入。 在大多數客戶案例中，此輸入是使用者的問題、請求、指示或訊息。

提示可包含多個原始區段。 例如，使用者輸入文字並包含URL。

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

提示是「交談見解」可從中衍生分析資訊的主要輸入，例如：

* 使用者的目的
* 主旨或主題
* 使用者的語調
* 使用者情緒
* 其他支援的訊號

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[提示](./conversation-insights-implement.md#prompt)物件。

### 回應

回應是代理程式或其他回應方傳回的內容。

回應通常包含不同型別的內容。 例如：

* 主要答案
* 引文或引用
* 連結
* 影像
* 促銷內容

這種區分很有用，因為分析需要將主要答案與支援連結、引文、廣告或其他回應元件區分開來。

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[回應](./conversation-insights-implement.md#response)物件。

### 意見反應

回饋意見是使用者對互動的明確評估或反應。

意見反應可包含：

* 自由格式意見回饋文字
* 數值評等
* 評等分類
* 評等的一個或多個原因

回饋不一定與提示或回應同時提供。 您可以在使用者評估答案後，稍後從代理程式應用程式或服務傳送意見回饋。

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[意見反應](./conversation-insights-implement.md#feedback)物件。

### 訊號

訊號是對交談內容的結構化分析觀察。 訊號擷取服務會擷取訊號。

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[訊號](./conversation-insights-implement.md#signal)物件。


### 代理程式

若要識別代理程式應用程式或服務，每個「交談見解」事件（提示、回應、回饋、訊號）都需要代理程式資訊。

#### 技能叫用

如果您的代理程式體驗應用程式支援技能的呼叫，這些技能代表處理期間呼叫的功能，您可以將這些技能呼叫新增為代理程式資訊欄位群組的一部分。

如需實作詳細資料，請參閱[實作交談見解](./conversation-insights-implement.md)檔案中的[代理資訊](./conversation-insights-implement.md#agentic-information-field-group)欄位群組。

## 運作方式

交談深入分析建置在三個核心功能上：

* **資料彙集**：讓使用者瞭解LLM和代理程式執行工作的狀況。 需要資料收集，才能收集所有必要的資料點。
* **訊號擷取與交談混合**：將非結構化提示與回應（也稱為turns）轉換為可報告的資料點，例如意圖與情緒。 以便使用者能大規模報告這些資料點。
* **報告**：若要判斷代理程式的功效和ROI，請在客戶歷程中大規模分析交談。

資料收集、訊號擷取和交談混合的整體程式如下所示。

![對話深入解析其運作方式](assets/conversation-insights.png){zoomable="yes"}

| | 說明 |
|---|---|
| 1 | 您可以檢測代理程式應用程式或服務，以建立包含提示![CommentText](/help/assets/icons2/CommentText.svg)、回應![CommentReply](/help/assets/icons2/CommentReply.svg)和回饋![回饋](/help/assets/icons2/Feedback.svg)資料集的事件。<br/>如需如何檢測代理程式應用程式或服務的詳細資訊，請參閱[實作檔案](./conversation-insights-implement.md)。 |
| 2 | 訊號擷取服務會從提示![CommentText](/help/assets/icons2/CommentText.svg)、回應![CommentReply](/help/assets/icons2/CommentReply.svg)和意見資料集![Feedback](/help/assets/icons2/Feedback.svg)擷取訊號，做為訊號事件![OnAir](/help/assets/icons/OnAir.svg)，並將這些訊號事件儲存在新的資料集中。<br>此步驟已實作為[交談深入分析設定](./conversation-insights-configure.md)定義的一部分。 |
| 3 | 交談混合器服務會混合來自提示![CommentText](/help/assets/icons2/CommentText.svg)、回應![CommentReply](/help/assets/icons2/CommentReply.svg)、回饋![Feedback](/help/assets/icons2/Feedback.svg)和訊號![OnAir](/help/assets/icons/OnAir.svg)事件資料集的事件，並將混合的![Merge](/help/assets/icons/Merge.svg)事件輸出到新的資料集中。<br>此步驟已實作為[交談深入分析設定](./conversation-insights-configure.md)定義的一部分。 |
| 4 | 混合的![Merge](/help/assets/icons/Merge.svg)資料整合為連線的一部分，而用於混合資料集的結構描述中所定義的元件成為資料檢視的一部分。<br>此步驟已實作為[交談深入分析設定](./conversation-insights-configure.md)定義的一部分。 |

