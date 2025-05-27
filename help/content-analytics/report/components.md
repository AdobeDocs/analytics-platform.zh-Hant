---
title: Content Analytics 元件
description: 有關特定 Content Analytics 元件的詳細資訊，例如維度、(已計算的) 量度和衍生欄位
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: ht
source-wordcount: '910'
ht-degree: 100%

---

# Content Analytics 元件

Content Analytics 將以下類別的元件 (維度、(已計算的) 量度和衍生欄位) 新增至 Customer Journey Analytics 中已經可用的元件：

* [體驗中繼資料](#experience-metadata)
* [體驗屬性](#experience-attributes)
* [體驗事件](#experience-events)
* [資產中繼資料](#asset-metadata)
* [資產屬性](#asset-attributes)
* [資產事件](#asset-events)
* [計算量度](#calculated-metrics)

在以下表格中，![AI 生成](/help/assets/icons/AI.svg)表示 AI/ML 產生的屬性/值對。

## 體驗中繼資料

| 標題 | 說明 | 類型 |
|---|---|---|
| 體驗管道 | 體驗的管道。 | 維度 |
| 體驗 ID | 體驗的唯一 ID。 | 維度 |
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
| 體驗說服策略 | ![AI 生成](/help/assets/icons/AI.svg)出現於假定體驗中的說服策略。可能的價值有：社會認同、社會認同效應、權威性、具體性、得寸進尺效應、克服抗拒、互惠原則、錨定效應和比較、社會影響、稀有性和擬人化。 | 維度<br/>衍生欄位 |
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
| 資產 ID | 資產的唯一識別碼。資產二進位決定唯一性。如果資產二進位變更，則 ID 也會隨之變更。唯一 ID 可以是 URL，也可以是建立的雜湊值。 | 維度 |
| 資產 HTML 路徑 | 資產的串連 HTML 路徑。 | 維度 |
| 資產連結 URL | 距離資產最近的頁面錨點。 | 維度 |
| 資產顯示寬度 | 內容資產顯示寬度。 | 維度 |
| 資產顯示高度 | 內容資產顯示高度。 | 維度 |
| 資產絕對左側 | 內容資產絕對左側。 | 維度 |
| 資產絕對頂端 | 內容資產絕對頂端。 | 維度 |

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
| 資產影像類型 | ![AI 生成](/help/assets/icons/AI.svg) 資產的影像類型。可能的值有：照片、素描、繪畫、digital_cartoon、資訊圖表、graphic_design、拼貼和 software_screenshot。 | 維度<br/>衍生欄位 |
| 資產相機位置 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機位置。 | 維度<br/>衍生欄位 |
| 資產相機鄰近度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機鄰近度。 | 維度<br/>衍生欄位 |
| 資產人員類別 | ![AI 生成](/help/assets/icons/AI.svg) 資產的人員類別。可能的值有：人、男人、女人、社會群組、人群、人員、男孩、女孩和小孩。 | 維度<br/>衍生欄位 |
| 資產視覺內容密度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的視覺內容密度。可能的值有：低、中或高。低內容密度表示影像的每單位面積上出現的資訊量很少。 | 維度 |
| 資產視覺注意力分散度 | ![AI 生成](/help/assets/icons/AI.svg) 資產的視覺注意力分散度。可能的值有：低、中或高。注意力分散度是指檢視者的注意力在畫面不同部分之間分配的程度。 | 維度<br/>衍生欄位 |
| 資產光線條件 | ![AI 生成](/help/assets/icons/AI.svg) 資產的光線條件。可能的值有：黃金時段、藍色時段、中午、陰天、夜晚、高光調、低光調、自然光、白熾燈、螢光燈、色彩繽紛和攝影棚。 | 維度<br/>衍生欄位 |
| 資產相機設定 | ![AI 生成](/help/assets/icons/AI.svg) 資產的相機設定。可能的值有：快速快門速度、長時間曝光。散焦模糊、動態模糊、移軸模糊、閃光燈、廣角、黑白、超現實、雙重曝光、微距和正常模式。 | 維度<br/>衍生欄位 |

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

## 計算量度

| 標題 | 說明 | 類型 |
|---|---|---|
| 資產點按率 | 資產點擊次數/資產瀏覽次數 | 計算量度 |
| 體驗點按率 | 體驗點擊次數/體驗瀏覽次數 | 計算量度 |

{style="table-layout:fixed"}

