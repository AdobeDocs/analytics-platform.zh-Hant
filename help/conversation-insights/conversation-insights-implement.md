---
title: 實作交談深入分析
description: 瞭解如何檢測您的代理程式應用程式或服務，以進行交談深入分析。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 8e446c15e998e660b42a09681fe78b885711e41f
workflow-type: tm+mt
source-wordcount: '2257'
ht-degree: 6%
---
# 實作交談深入分析

若要將交談資料產生為XDM體驗事件，並確保這些交談體驗事件最終在Adobe Experience Platform中成為資料集，請檢測您的代理程式應用程式或服務以使用交談見解。

本文會記錄必要的實作步驟。

>[!PREREQUISITES]
>
>您必須有Experience Platform環境（組織和沙箱）可供收集資料。
>您的Adobe組織必須為實驗代理和交談欄位群組啟用。

## 結構描述和資料集

設定主要交談事件的資料集：提示、回應、回饋。 這些資料集可以相同結構為基礎（例如，通用的交談見解結構描述），或根據個別結構描述。
您可以為提示、回應和回饋定義單獨的資料集，或將資料合併到資料集中。 例如，使用一個資料集進行提示和回應，並使用另一個資料集進行意見回饋。 或針對所有交談事件使用單一資料集。

用於提示、回應和意見資料集的結構描述必須使用必要欄位群組來擴充XDM體驗事件基本結構描述。 而且可以使用其他欄位群組來擴充XDM體驗事件基本結構描述。

### 代理資訊欄位群組

**[!UICONTROL 代理資訊]**&#x200B;欄位群組是必要的欄位群組，並使用`agenticExperience`物件。

+++ 詳細資料

| 欄位路徑（點標籤法） | 類型 | 範例值 | 附註 |
|---|---|---|---|
| `conciergeID` | 字串 | `"concierge-abc123"` | **新增。** Concierge 的唯一識別碼 |
| `name` | 字串 | `"Brand Concierge"` | 結合一組代理的 Concierge 名稱 |
| `version` | 字串 | `"1.0.0"` | 結合一組代理的 Concierge 版本 |
| `environment` | 字串 | `"prod"` | 環境此事件源自（開發、階段、生產） |
| `mode` | 字串 | `"release"` | 代理程式所處的模式（測試、預覽、發行） |
| `agents[]` | 陣列 | 請參閱下方的代理程式物件 | 使用的代理程式陣列 |
| `agents[].agentID` | 字串 | `"agent-001"` | **新增。** 代理程式的唯一識別碼，由下方的`skills[].agentID`參照 |
| `agents[].name` | 字串 | `"Chatbot Assistant"` | 代理程式名稱 |
| `agents[].version` | 字串 | `"2.1.3"` | 代理程式版本 |
| `agents[].score` | 數字 | `0.92` | 在其傳回值中的代理程式信賴分數 |
| `agents[].skills[]` | 陣列 | 檢視下方的技能物件 | **已棄用** — 請改用下方最上層`skills[]`陣列，此陣列擁有完整的技能電話順序清單，並透過`agentID`將每個電話連結至其代理程式 |
| `agents[].skills[].name` | 字串 | `"Intent Recognition"` | 技能名稱（已棄用的陣列） |
| `agents[].skills[].version` | 字串 | `"1.0.0"` | 技能版本（已棄用的陣列） |
| `agents[].skills[].score` | 數字 | `0.95` | 技能信賴分數(0-1) （已棄用的陣列） |
| `agents[].skills[].parameters[]` | 陣列 | 請參閱下列引數 | 傳送給技能的引數（索引鍵值配對） （已棄用的陣列） |
| `agents[].skills[].parameters[].key` | 字串 | `"language"` | 引數索引鍵 |
| `agents[].skills[].parameters[].value` | 字串 | `"en-US"` | 引數值 |
| `skills[]` | 陣列 | 請參閱下方的技能叫用物件 | **新增，實驗性。** 跨所有代理程式，針對此體驗提供完整、有序的技能叫用清單。 取代已棄用的每個代理程式`agents[].skills[]`陣列 |
| `skills[].skillID` | 字串 | `"skill-intent-recognition"` | 呼叫的技能定義的識別碼 |
| `skills[].skillInvocationID` | 字串 | `"inv-9f2a-001"` | 此個別技能呼叫的唯一識別碼，即使與重新傳遞一致。 合併下游技能陣列時的重複資料刪除索引鍵 |
| `skills[].name` | 字串 | `"Intent Recognition"` | 呼叫的技能名稱 |
| `skills[].version` | 字串 | `"1.0.0"` | 呼叫的技能版本 |
| `skills[].agentID` | 字串 | `"agent-001"` | 叫用此技能之代理程式的識別碼，與`agents[].agentID`相關。 由於子代理會平行執行，群組關鍵消費者會使用在代理程式中排序技能 |
| `skills[].invocationSource` | 字串 | `"main"` | 由主要代理程式回圈(`main`)或子代理程式(`subagent`)呼叫 |
| `skills[].score` | 數字 | `0.95` | 符合技能而得的分數 |
| `skills[].failed` | 布林值 | `false` | 指出技能執行失敗的旗標 |
| `skills[].errorReason` | 字串 | `"timeout"` | 當`failed`為True時技能失敗的原因 |
| `skills[].sequenceNumber` | integer | `1` | 在單一代理程式執行中單調地增加此技能呼叫的索引 — 而不是變成全域，因為子代理程式並行執行。 消費者依序以`agentID`、`sequenceNumber`、`timestamp`作為分頁器訂購。 選填 |
| `skills[].timestamp` | 字串（日期時間） | `"2026-09-11T00:03:15Z"` | 啟動此技能的時間，ISO 8601 UTC。 在`sequenceNumber`之後使用的排序金鑰。 製作者應一律填入此專案 |
| `skills[].skillSource` | 字串 | `"inline"` | 如何將技能定義傳遞至執行階段： `inline` （內嵌載入內容）或`deferred` （隨選載入） |
| `skills[].executionContext` | 字串 | `"inline"` | 相對於呼叫代理程式執行技能的位置： `inline`或`forked` （在分支的子代理程式內容中執行） |
| `skills[].reasoning.narration` | 字串 | `"Recognized an intent to verify a geography fact"` | 呼叫此技能原因的自然語言說明 |
| `skills[].parameters[]` | 陣列 | 請參閱下列引數 | 傳入「 」技能的引數 |
| `skills[].parameters[].key` | 字串 | `"language"` | 引數索引鍵 |
| `skills[].parameters[].value` | 字串 | `"en-US"` | 引數值 |

+++

若要實施使用資料傳播「代理資訊」欄位群組的事件，您應確保：

* 代理程式設定

  * 每個代理程式都有專屬的agentID、名稱和版本組合。
  * 代理程式分數在`0.0`到`1.0`之間標準化。
  * 使用`agentID`以依據技能叫用來參照代理程式。

* 技能引動過程

  * 在所有代理程式中，每個技能呼叫僅發出一個專案，而不是在每個代理程式下巢狀巢狀技能。
  * 填入skillInvocationID，以便下游混合可以移除重複的重傳事件。
  * 正確排序消費者。 依`agentID`分組，然後依`sequenceNumber`排序，遞補為`timestamp`。 需要排序，因為子代理可以並行執行
  * 使用`invocationSource`和`executionContext`來區分主要和子代理程式技能，以及內嵌和分支執行。
  * 避免使用已棄用的`agents[].skills[]`陣列。 如果您過去曾使用陣列，請將陣列視為唯讀物件。

* 技能引數

  * 引數會使用Adobe XDM索引鍵值資料型別，並使用語言設定、臨界值、模型設定的常見引數型別。 例如，`"key":"language", "value":"en-US"`。

+++ 代理資訊欄位群組的使用範例 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### 交談事件欄位群組

**[!UICONTROL 交談事件]**&#x200B;欄位群組是必要的欄位群組，並使用`conversation`物件。

交談物件會擷取下列專案的資料：

#### 對話

唯一的`conversationID`可識別交談。 例如：`conversationID = "conv-001"`。 結構描述也支援`conversationName`。 描述交談整體內容的易讀名稱，例如： `France Geography Q&A`。

`conversationID`允許將所有相關的轉換事件分組到相同的對話體驗。

#### 翻轉

回合是指對話中的一個互動週期。

`turnID`唯一的`turnID`可識別翻頁。 例如：

`conversationID = "conv-001"`
`turnID = "turn-001"`

相同的`conversationID`和`turnID`可用來關聯與該回合相關的提示、回應和回饋。 此關聯適用於單獨交付或最終位於不同資料集的記錄。


#### 提示

提示是提交給代理程式的輸入。 在大多數客戶案例中，此輸入是使用者的問題、請求、指示或訊息。

提示使用以下表示方式： `conversation.prompt`

重要提示欄位包括：

| 欄位 | 含義 |
|---|---|
| `prompt.source` | 產生提示的人員或內容，通常是一般使用者。 |
| `prompt.raw[]` | 一或多個原始內容區段。 |
| `prompt.raw[].text` | 實際的提示文字或內容。 |
| `prompt.raw[].purpose` | 內容的用途，例如，使用者輸入或連結。 |

提示可包含多個原始區段。 例如，使用者輸入文字並包含URL。

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### 回應

回應是代理程式或其他回應方傳回的內容。

`conversation.response`唯一的`responseID`代表回應。

重要回應欄位包括：

| 欄位 | 含義 |
|---|---|
| `response.source` | 產生回應的人員或原因。 |
| `response.raw[]` | 一或多個回應內容區段 |
| `response.raw[].text` | 回應文字或內容。 |
| `response.raw[].purpose` | 內容區段的用途。 |

記錄的來源型別包括：

| 來源 | 含義 |
|---|----|
| `bot` | 自動代理程式回應。 |
| `canned` | 預先定義或樣板化的回應。 |
| `concierge` | 人力代理程式回應。 |
| `end-user` | 在適用的情況下，由使用者人工產生的內容。 |

#### 意見反應

回饋意見是使用者對互動的明確評估或反應。

意見反應結構包含： `conversation.feedback`。

範例：

* `feedback.raw[].text: "Great help"`
* feedback.rating.score： 1
* feedback.rating.classification： &quot;Thumbs Up&quot;
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

記錄的評等分數範圍是從`-1.0`到`1.0`。

意見反應事件可以使用`eventType = "conversation.feedback"`表示為僅限意見反應的事件。

當回饋套用至特定回合時，請保留適當的`conversationID`和`turnID`，以便交談混合器能夠將回饋與相關互動建立關聯。


#### 訊號

訊號是對交談內容的結構化分析觀察。 訊號擷取服務會擷取訊號。

訊號有下列欄位。

| 欄位 | 含義 |
|---|----|
| `scope` | 用來衍生訊號的輸入範圍，例如轉換或迄今交談。 |
| `name` | 訊號識別碼，例如，主旨、意圖、音調或情緒。 也支援生產者定義的訊號名稱。 |
| `type` | 值型別：字串、數字或布林值。 |
| `values[]` | 一或多個與訊號相關的值。 |
| `stringValue` | 字串訊號值，例如目的、色調或主旨。 |
| `numberValue` | 數值訊號值，例如情緒分數。 |
| `booleanValue` | 真/假訊號值。 |
| `confidence` | 訊號值中的選擇性製作者信賴度，通常介於0和1之間。 |
| `qualifiers[]` | 將內容新增至訊號值的選用描述元。 |
| `metadata[]` | 選擇性製作者定義的索引鍵/值中繼資料。 |


#### 對話

如需交談物件的完整詳細資料，請參閱下文。

+++ 詳細資料 

| 欄位路徑（點標籤法） | 類型 | 範例值 | 附註 |
|---|---|---|---|
| `conversationID` | 字串 | `"conv-001"` | 將多個專案組合在一起 |
| `conversationName` | 字串 | `"France Geography Q&A"` | **新增。** 為對話指定的名稱，代表其整體內容 |
| `turnID` | 字串 | `"turn-001"` | 此回合的唯一識別碼 |
| `prompt.source` | 字串 | `"end-user"` | Source （提示），其他選項可能包括快取值、固定值等。 |
| `prompt.raw[]` | 陣列 | 請參閱下方的原始物件 | 原始提示資料 |
| `prompt.raw[].text` | 字串 | `"What is the capital of France?"` | 實際文字內容 |
| `prompt.raw[].purpose` | 字串 | `"User Input"` | 此文字區段的用途 |
| `response.source` | 字串 | `"bot"` | 回應的Source |
| `response.raw[]` | 陣列 | 請參閱下方的原始物件 | 原始回應資料 |
| `response.raw[].text` | 字串 | `"The capital of France is Paris."` | 回應文字內容 |
| `response.raw[].purpose` | 字串 | `"main"` | 回應區段的用途，其他選項可能包括連結、圖片等。 |
| `feedback.source` | 字串 | `"end-user"` | 意見反應的Source |
| `feedback.raw[]` | 陣列 | 請參閱下方的原始物件 | 原始意見反應資料 |
| `feedback.raw[].text` | 字串 | `"Great help"` | 意見回饋文字 |
| `feedback.raw[].purpose` | 字串 | `"free-form text"` | 為了提供意見區段，其他選項可能包括熒幕擷圖、媒體等。 |
| `feedback.rating.score` | 數字 | `1` | 數值評等分數從–1.0到1.0 |
| `feedback.rating.classification` | 字串 | `"Thumbs Up"` | 評等分類 |
| `feedback.rating.reasons[]` | 陣列 | `["Accurate", "Quick response"]` | 評等原因的陣列 |
| `signals[]` | 陣列 | 請參閱下方的訊號物件 | 根據此事件和迄今的交談衍生訊號。 每個專案都是具有其範圍之單一命名訊號 |
| `signals[].scope` | 字串 | `"turn"` | 衍生此訊號集的輸入範圍（迴轉、迄今交談、最後N個迴轉、回饋） |
| `signals[].attributes` | 物件 | 請參閱下列屬性 | **已棄用。** 訊號屬性的容器。 每個屬性都是一個物件，其中包含一或多個值。 這是為了滿足支援用於產生訊號的ML/代理程式資訊的預期需求。 |
| `signals[].attributes.subjects` | 物件 | 請參閱下列主題 | **已棄用。** 主題容器 |
| `signals[].attributes.subjects.values[]` | 陣列 | 請參閱下方的主旨值 | **已棄用。** 主旨值的陣列 |
| `signals[].attributes.subjects.values[].phrase` | 字串 | `"product pricing"` | **已棄用。** 從範圍內的輸入中擷取的短語或關鍵字 |
| `signals[].attributes.subjects.values[].qualifiers[]` | 陣列 | `["important", "urgent"]` | **已棄用。** 片語的限定詞清單 |
| `signals[].attributes.intents` | 物件 | 檢視以下意圖 | **已棄用。** 意圖容器 |
| `signals[].attributes.intents.values[]` | 陣列 | `["make a purchase", "learn more"]` | **已棄用。** 從範圍輸入衍生的意圖 |
| `signals[].attributes.tones` | 物件 | 檢視下方的色調 | **已棄用。** 色調容器 |
| `signals[].attributes.tones.values[]` | 陣列 | `["thrilled", "contemplative"]` | **已棄用。** 從範圍輸入衍生的色調 |
| `signals[].attributes.sentiment` | 物件 | 請參閱下方的情緒 | **已棄用。** 情緒容器 |
| `signals[].attributes.sentiment.value` | 數字 | `0.71` | **已棄用。** 分數從–1 （負數）到1 （正數），表示情緒 |
| `signals[].name` | 字串 | `"sentiment"` | **新** （取代已棄用的`attributes`容器）。 此訊號的識別碼，例如「主體」、「意圖」、「色調」、「情緒」或任何製作者定義的名稱 — 製作者可以新增訊號型別，而不變更結構 |
| `signals[].type` | 字串 | `"number"` | **新增。** 此訊號值（`string`、`number`或`boolean`）的資料型別 — 告知消費者在`values[]`的每個專案上填入了哪個型別的值欄位 |
| `signals[].values[]` | 陣列 | 請參閱下方的值物件 | 此訊號的一或多個值 |
| `signals[].values[].stringValue` | 字串 | `"curious"` | 當`type`為「字串」時填入 — 類別值，例如意圖、音調或擷取的片語 |
| `signals[].values[].numberValue` | 數字 | `0.71` | 當`type`為「數字」時填入 — 例如，從–1到1的情緒分數或強度 |
| `signals[].values[].booleanValue` | 布林值 | `true` | 當`type`為「布林值」 — 真/假旗標時填入 |
| `signals[].values[].confidence` | 數字 | `0.9` | **新增。** 製作者指派給此值的信賴度，從0到1 |
| `signals[].values[].qualifiers[]` | 陣列 | `["important", "urgent"]` | 此值的其他描述元，類似於關鍵字，但更有意義 |
| `signals[].values[].metadata[]` | 陣列 | 請參閱下列引數 | **新增。** 此值的製作者定義中繼資料為索引鍵/值組，例如產生訊號之ML/代理程式的上下文 |

+++


訊號擷取服務會針對訊號資料集填入`signals`物件。

先前的`signals[].attributes.{subjects,intents,tones,sentiment}`容器已棄用。


### 其他欄位群組

您可以將選用的欄位群組新增到結構描述中，以用於提示、回應和意見回饋資料集。 例如：

* **網頁詳細資料**&#x200B;欄位群組。 若要擷取對話所內嵌之網頁的詳細資訊。
* **Commerce詳細資料**&#x200B;欄位群組。 擷取對話中提及之建議產品的產品詳細資料。



客戶負責產生來源交談事件。 Adobe平台隨後會執行訊號擷取和資料混合。 客戶不需要實作訊號擷取或混合服務。

本文介紹交談見解MVP輸入要求和目前的代理結構描述更新。 其中不包含Conversation Insights 1.0功能或更新版本的需求。

### 事件型別

您必須為每個交談事件設定`eventType` （字串）的下列其中一個值：

| 值 | 說明 |
|---|---|
| `conversation turn` | 完成交談並提示及回應 |
| `conversation recommendation` | 以交談為基礎的建議 |
| `conversation feedback` | 僅限回饋意見的事件 |


### Source型別

您必須為事件中的每個`prompt`、`response`或`feedback`物件設定`source`的下列其中一個值：

| 值 | 說明 |
|---|---|
| `end-user` | 人工使用者輸入 |
| `bot` | 自動代理程式回應 |
| `canned` | 預先定義/樣板化的回應 |
| `concierge` | 人力代理程式回應 |

### 用途型別（原始文字）

您必須在`prompt`、`response`或`feedback`物件中`raw`物件的任何元素上，設定`purpose`屬性的下列其中一個值。

| 值 | 說明 |
|---|---|
| `User Input` | 主要使用者輸入 |
| `main` | 主要回應內容 |
| `advertisement` | 促銷內容 |
| `citation` | 參考/來源連結 |
| `link` | 外部連結 |
| `image` | 影像參考 |
| `enum picker` | 結構化意見選擇 |


### 範例

請參閱下方範例，瞭解在各種情況下交談事件欄位群組的使用方式。

+++ 詳細資料 

>[!BEGINTABS]

>[!TAB 轉換事件範例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB 回應事件範例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB 意見反應事件範例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB 產品推薦事件範例]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## 資料收集

針對交談深入分析使用下列資料收集策略。


### 事件類型

您的代理程式應用程式或服務會儘快傳送事件。 確認應用程式或服務不會等待回應，再使用事件時可用的資訊傳送提示。

此建議表示：

* 提示、回應和意見回饋物件會獨立填入，不應強制納入單一事件。
* 跨資料集應該有多個具有相同`conversationID`和`turnID`的事件。

### 事件關聯

代理程式應用程式或服務必須在所有相關事件中保留穩定的識別碼。

| 欄位路徑 | 說明 |
|---|---|
| `conversation.conversationID` | 整體交談的唯一識別碼。 |
| `conversation.turnID` | 交談中個別回合的唯一識別碼。 |
| `_id` | 體驗事件記錄識別碼。 |
| `timestamp` | 事件發生的時間。 |
| `eventType` | 識別交談事件的型別。 |

* 屬於相同交談的所有事件都必須使用相同的`conversationID`。

* 相同的`turnID`必須用於提示、回應，以及與同一回合關聯的任何回饋意見。 提示、回應和意見回應資料集中可以存在多個具有相同`turnID`的事件。

代理程式應用程式或服務產生的ID在重試或重新傳遞期間保持穩定。 這可讓下游處理正確關聯事件，並避免意外重複事件。

## 訊號擷取

訊號擷取會在資料收集後進行。 您的代理程式應用程式或服務未填入其他訊號。

+++ 含有訊號的翻動事件範例

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## 資料混合

交談混合器服務會將提示、回應、回饋和訊號事件資料集中的事件合併到專用的混合交談事件資料集中。 該資料集在Customer Journey Analytics中作為連線的一部分使用。 該資料集中的元件會新增到您為「交談見解」設定指定的資料檢視。
