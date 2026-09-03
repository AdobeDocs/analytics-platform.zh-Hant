---
title: Content Analytics元件
description: 瞭解特定Content Analytics元件的詳細資訊，例如維度、 （計算）量度和衍生欄位
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ad5685a0-8296-4a0c-814c-658c10b4af12id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 3e9a9042bfe707971c4e37d319a23ab9bdc80075
workflow-type: tm+mt
source-wordcount: 1869
ht-degree: 56%

---


# Content Analytics 元件

Content Analytics 將以下類別的元件 (維度、(已計算的) 量度和衍生欄位) 新增至 Customer Journey Analytics 中已經可用的元件：

* [體驗中繼資料](#experience-metadata)
* [體驗屬性](#experience-attributes)
* [體驗事件](#experience-events)
* [資產中繼資料](#asset-metadata)
* [資產屬性](#asset-attributes)
* [資產事件](#asset-events)
* [付費媒體](#paid-media)
* [計算量度](#calculated-metrics)

在以下表格中，![AI 生成](/help/assets/icons/AI.svg)表示 AI/ML 產生的屬性/值對。

## 體驗中繼資料

| 標題 | 說明 | 類型 |
|---|---|---|
| ID SOURCE | 若為Content Analytics，值為`ContentAnalytics`。 | 維度 |
| 管道 | 體驗的管道。 值為`Web`、`Mobile`或`Paid Media`。 | 維度 |
| 內容體驗ID | 體驗的不重複 IＤ。 <br>針對&#x200B;**網頁**：網頁的URL。 <br/>針對&#x200B;**精細網路**：雜湊計算使用者端，根據前置詞為`web-`的內容裝載（文字、影像、CTA）。 <br/>對於&#x200B;**行動裝置**：根據內容承載（文字、影像、CTA）計算且首碼為`mobile-`的雜湊使用者端。 | 維度 |
| 內容體驗Source | 針對&#x200B;**網頁**：網頁的URL。<br/>適用於&#x200B;**行動裝置**：畫面名稱，透過Experience Platform Mobile SDK傳入。 | 維度 |
| 體驗管道（已棄用） | 體驗的管道。 值為`Web`或`Mobile`。 | 維度 |
| Experience Extras | 您要追蹤的任何其他資料。 例如外部ID或位置。 | 維度 |
| 體驗縮圖 URL | 體驗縮圖的 URL。 | 維度 |
| 體驗水平百分比深度 | 體驗的水平百分比深度可量化值。 | 維度<br/>衍生欄位 |
| 體驗垂直百分比深度 | 體驗的垂直百分比深度可量化值。 | 維度<br/>衍生欄位 |

{style="table-layout:fixed"}



## 體驗屬性

| 標題 | 說明 | 類型 |
|---|---|---|
| 體驗屬性 | ![AI 生成](/help/assets/icons/AI.svg)所有體驗屬性名稱和值的完整清單 | 維度<br>衍生欄位 |
| 體驗可讀性分數 | ![AI 生成](/help/assets/icons/AI.svg) 可讀性分數 | 維度 |
| 體驗關鍵字 | ![AI 生成](/help/assets/icons/AI.svg) 體驗的關鍵字。 | 維度<br>衍生欄位 |
| 體驗說服策略 | ![AI 生成](/help/assets/icons/AI.svg)出現於假定體驗中的說服策略。 可能的價值有：社會認同、社會認同效應、權威性、具體性、得寸進尺效應、克服抗拒、互惠原則、錨定效應和比較、社會影響、稀有性和擬人化。 | 維度<br/>衍生欄位 |
| 體驗敘述 | ![AI 生成](/help/assets/icons/AI.svg)從行銷人員的觀點而言，根據相關性建構體驗的敘述。 | 維度<br/>衍生欄位 |
| 體驗基調 | ![AI 生成](/help/assets/icons/AI.svg)從行銷人員的觀點而言，根據相關性建構體驗的基調。 | 維度<br/>衍生欄位 |
| 體驗行銷情感 | ![AI 生成](/help/assets/icons/AI.svg) 讀者在閱讀使用做為體驗一部分的文字時所激發的情感：迫切性、排他性、鼓勵、挑戰、好奇心、成就感、信任、單純和迷戀。 | 維度<br/>衍生欄位 |
| 體驗表情符號計數 | ![AI 生成](/help/assets/icons/AI.svg)為體驗產生的表情符號計數。 | 量度 |
| 體驗主題標籤計數 | ![AI 生成](/help/assets/icons/AI.svg)為體驗產生的主題標籤計數。 | 量度 |
| 體驗句子計數 | ![AI 生成](/help/assets/icons/AI.svg)體驗的句子計數。 | 量度 |
| 體驗停用詞比率 | ![AI 生成](/help/assets/icons/AI.svg) 體驗的停用詞計數。 | 量度 |
| 體驗文字引用計數 | ![AI 生成](/help/assets/icons/AI.svg)體驗的文字引用計數。 | 量度 |
| 體驗字詞計數 | ![AI 生成](/help/assets/icons/AI.svg) 體驗的字詞數量。 | 量度 |
| 體驗每個句子字詞計數 | ![AI 生成](/help/assets/icons/AI.svg)體驗的每個句子字詞數量。 | 量度 |

{style="table-layout:fixed"}


## 體驗事件

| 標題 | 說明 | 類型 |
|---|---|---|
| 體驗檢視 | 體驗的檢視次數可量化測量。 | 量度 |
| 體驗點擊 | 體驗的點擊數可量化測量。 | 量度 |

{style="table-layout:fixed"}


## 資產中繼資料

| 標題 | 說明 | 類型 |
|---|---|---|
| 資產 ID | 資產的唯一識別碼。 資產二進位決定唯一性。 如果資產二進位變更，則 ID 也會隨之變更。 不重複 IＤ 可以是 URL，也可以是建立的雜湊值。 | 維度 |
| 資產來源 | | 維度 |
| 資產 HTML 路徑 | 資產的串連 HTML 路徑。 | 維度 |
| 資產連結 URL | 距離資產最近的頁面錨點。 | 維度 |
| 資產顯示寬度 | 內容資產顯示寬度。 | 維度 |
| 資產顯示高度 | 內容資產顯示高度。 | 維度 |
| 資產絕對左側 | 內容資產絕對左側。 | 維度 |
| 資產絕對頂端 | 內容資產絕對頂端。 | 維度 |
| 資產額外專案 | 您要追蹤的任何其他資料。 例如外部ID或位置。 | 維度 |

{style="table-layout:fixed"}


## 資產屬性

| 標題 | 說明 | 類型 |
|---|---|---|
| 資產屬性 | ![AI 生成](/help/assets/icons/AI.svg) 所有資產屬性名稱和值的完整清單 | 維度<br>衍生欄位 |
| 資產方向 | ![AI 生成](/help/assets/icons/AI.svg) 資產的方向。 | 維度<br/>衍生欄位 |
| 資產整體基調 | ![AI 生成](/help/assets/icons/AI.svg) 資產的整體基調。 | 維度<br/>衍生欄位 |
| 資產前景顏色 | ![AI 生成](/help/assets/icons/AI.svg) 資產的前景顏色。 | 維度<br/>衍生欄位 |
| 資產背景顏色 | ![AI 生成](/help/assets/icons/AI.svg) 資產的背景顏色。 | 維度<br/>衍生欄位 |
| 資產標記 | ![AI 生成](/help/assets/icons/AI.svg) 資產的標籤。 | 維度<br/>衍生欄位 |
| 資產場景 | ![AI 生成](/help/assets/icons/AI.svg) 資產的場景。 | 維度<br/>衍生欄位 |
| 資產物件 | ![AI 生成](/help/assets/icons/AI.svg) 資產的物件。 | 維度<br/>衍生欄位 |
| 資產攝影風格 | ![AI 生成](/help/assets/icons/AI.svg) 資產的攝影風格。 | 維度<br/>衍生欄位 |
| 資產影像類型 | ![AI 生成](/help/assets/icons/AI.svg) 資產的影像類型。 可能的值有：照片、素描、繪畫、digital_cartoon、資訊圖表、graphic_design、拼貼和 software_screenshot。 | 維度<br/>衍生欄位 |
| 資產相機位置 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機位置。 | 維度<br/>衍生欄位 |
| 資產相機鄰近度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機鄰近度。 | 維度<br/>衍生欄位 |
| 資產人員類別 | ![AI 生成](/help/assets/icons/AI.svg) 資產的人員類別。 可能的值有：人、男人、女人、社會群組、人群、人員、男孩、女孩和小孩。 | 維度<br/>衍生欄位 |
| 資產視覺內容密度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的視覺內容密度。 可能的值有：低、中或高。 低內容密度表示影像的每單位面積上出現的資訊量很少。 | 維度 |
| 資產視覺注意力分散度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的視覺注意力分散度。 可能的值有：低、中或高。 注意力分散度是指檢視者的注意力在畫面不同部分之間分配的程度。 | 維度<br/>衍生欄位 |
| 資產光線條件 | ![AI 生成](/help/assets/icons/AI.svg) 資產的光線條件。 可能的值有：黃金時段、藍色時段、中午、陰天、夜晚、高光調、低光調、自然光、白熾燈、螢光燈、色彩繽紛和攝影棚。 | 維度<br/>衍生欄位 |
| 資產相機設定 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機設定。 可能的值有：高速快門、長時間曝光。 散焦模糊、動態模糊、移軸模糊、閃光燈、廣角、黑白、超現實、雙重曝光、微距和正常模式。 | 維度<br/>衍生欄位 |

{style="table-layout:fixed"}


## 資產事件

| 標題 | 說明 | 類型 |
|---|---|---|
| 資產檢視 | 資產的檢視次數可量化測量。 | 量度 |
| 資產點擊次數 | 資產的點擊次數可量化測量。 | 量度 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## 付費媒體

透過[Adobe Experience Platform付費媒體來源聯結器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/home)啟用&#x200B;**付費媒體**&#x200B;頻道時（例如Meta Ads或Google Ads），這些元件會新增至資料檢視。 它們可讓您報告付費媒體實體、創意內容，並與您的網頁和行動內容一起支出。

上述AI產生的&#x200B;**Asset屬性**&#x200B;和&#x200B;**體驗屬性**&#x200B;也可用於付費媒體創意 — 相同的功能在Web、行動和付費媒體頻道中執行。

### 付費媒體維度

| 標題 | 說明 | 類型 |
|---|---|---|
| 廣告網路 | 從中擷取付費媒體資料的廣告平台。 | 維度 |
| 帳戶名稱 | 廣告帳戶的名稱。 | 維度 |
| 行銷活動名稱 | 付費媒體行銷活動的名稱。 | 維度 |
| 廣告群組名稱 | 廣告群組的名稱（Meta廣告集/ Google廣告群組）。 | 維度 |
| 廣告名稱 | 個別廣告的名稱。 | 維度 |
| 體驗名稱 | 廣告體驗（創意構成）的名稱。 | 維度 |
| 資產名稱 | 創意資產的名稱。 | 維度 |
| 促銷活動狀態 | 行銷活動的狀態。 | 維度 |
| 廣告群組狀態 | 廣告群組的狀態。 | 維度 |
| 廣告狀態 | 廣告的狀態。 | 維度 |
| 服務狀態 | 表示實體目前是否正在傳遞的詳細服務狀態。 | 維度 |
| 帳戶貨幣 | 廣告帳戶的貨幣。 | 維度 |
| 帳戶時區 | 廣告帳戶的時區。 | 維度 |
| 帳戶型別 | 廣告帳戶的型別。 | 維度 |
| 帳戶公司名稱 | 與廣告帳戶相關聯的企業名稱。 | 維度 |
| 行銷活動型別 | 行銷活動的主要管道型別。 | 維度 |
| 行銷活動目標 | 行銷活動的目標或目的。 | 維度 |
| 行銷活動競標策略 | 活動的競標策略。 | 維度 |
| 行銷活動預算型別 | 行銷活動的預算分配型別。 | 維度 |
| 行銷活動每日預算 | 每日預算金額（以廣告帳戶幣別表示）。 | 維度 |
| 行銷活動期限預算 | 期限預算金額（以廣告帳戶幣別表示）。 | 維度 |
| 行銷活動開始時間 | 行銷活動開始的時間。 | 維度 |
| 行銷活動結束時間 | 行銷活動結束的時間。 | 維度 |
| 廣告群組型別 | 廣告群組的型別。 | 維度 |
| 廣告群組競標策略 | 廣告群組的競標策略。 | 維度 |
| 廣告群組最佳化目標 | 廣告群組的最佳化目標。 | 維度 |
| 廣告群組開始時間 | 廣告群組開始的時間。 | 維度 |
| 廣告群組結束時間 | 廣告群組結束的時間。 | 維度 |
| 廣告型別 | 廣告型別/格式。 | 維度 |
| 廣告檢閱狀態 | 廣告的檢閱/核准狀態。 | 維度 |
| 廣告Creative型別 | 廣告使用的創意型別。 | 維度 |
| 廣告標題 | 廣告創意的標題/標題。 | 維度 |
| 廣告Call to action | 廣告創意的Call-to-action。 | 維度 |
| 廣告目的地URL | 廣告的登陸/目的地URL。 | 維度 |
| 廣告顯示URL | 在廣告上顯示URL。 | 維度 |
| 體驗型別 | 廣告體驗的型別/格式。 | 維度 |
| 體驗登陸頁面URL | 體驗的登陸頁面URL。 | 維度 |
| 體驗Call to action | call-to-action的體驗。 | 維度 |
| 資產類型 | 創意資產的型別（例如影像或影片）。 | 維度 |
| 資產寬度 | 資產的寬度（畫素）。 | 維度 |
| 資產高度 | 資產的高度（畫素）。 | 維度 |
| 資產外觀比例 | 資產的外觀比例。 | 維度 |
| 資產方向 | 資產方向。 | 維度 |
| 裝置類型 | 報告的量度的裝置型別劃分。 | 維度 |
| 放置環境 | 報告的量度的位置劃分。 | 維度 |
| 平台 | 報告的量度的平台劃分。 | 維度 |
| 國家/地區 | 報告的量度的國家/地區劃分。 | 維度 |
| 區域 | 報告的量度的區域劃分。 | 維度 |

{style="table-layout:fixed"}

### 付費媒體量度

| 標題 | 說明 | 類型 |
|---|---|---|
| 曝光數 | 廣告顯示次數。 | 量度 |
| 點擊數 | 廣告點選次數。 | 量度 |
| 支出 | 花費金額（以廣告帳戶貨幣表示）。 | 量度 |
| 轉換 | 轉換總數。 | 量度 |
| 轉換值 | 轉換的總值。 | 量度 |
| 觸及 | 不重複觀看廣告的人數。 | 量度 |
| 參與 | 與廣告互動的次數。 | 量度 |
| 視訊檢視 | 影片觀看次數。 | 量度 |
| 視訊完成 | 觀看至結束的影片數量。 | 量度 |
| 視訊播放 | 影片播放次數。 | 量度 |
| 購買 | 購買轉換次數。 | 量度 |
| 新增至購物車 | 加入購物車的轉換次數。 | 量度 |
| 銷售機會 | 潛在客戶轉換次數。 | 量度 |
| 註冊 | 註冊轉換次數。 | 量度 |
| 下載 | 下載轉換次數。 | 量度 |
| 訂閱 | 訂閱轉換次數。 | 量度 |
| 登陸頁面檢視 | 登陸頁面檢視次數。 | 量度 |
| 點按後轉換 | 歸因於點選的轉換。 | 量度 |
| 貼文檢視轉換 | 歸因到檢視的轉換。 | 量度 |
| 訂單值總計 | 訂單的總值。 | 量度 |
| 連結點按次數 | 連結點選次數。 | 量度 |
| 傳出點按 | 傳出點按的次數。 | 量度 |
| 應用程式安裝 | 應用程式安裝次數。 | 量度 |
| 潛在客戶提交 | 潛在客戶表單提交次數。 | 量度 |

{style="table-layout:fixed"}

### 付費媒體計算量度

| 標題 | 說明 | 類型 |
|---|---|---|
| 點進率 | 點按數除以曝光數。 | 計算量度 |
| 每次點按成本 | 支出除以點按。 | 計算量度 |
| 每毫升成本 | 每千次曝光的成本。 | 計算量度 |
| 每次轉換成本 | 支出除以轉換。 | 計算量度 |
| 廣告投資報酬率 | 轉換值除以支出。 | 計算量度 |
| 頻率 | 曝光數除以觸及率。 | 計算量度 |
| 參與率 | 參與次數除以曝光次數。 | 計算量度 |
| 視訊完成率 | 視訊完成數除以視訊播放數。 | 計算量度 |
| 轉換率 | 轉換次數除以點選次數。 | 計算量度 |
| 平均訂購值 | 訂單總值除以購買。 | 計算量度 |

{style="table-layout:fixed"}


## 計算量度

| 標題 | 說明 | 類型 |
|---|---|---|
| 資產點按率 | 資產點擊次數/資產瀏覽次數 | 計算量度 |
| 體驗點進率 | 體驗點擊次數/體驗瀏覽次數 | 計算量度 |

{style="table-layout:fixed"}

