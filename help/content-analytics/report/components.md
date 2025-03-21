---
title: Content Analytics元件
description: 特定「內容分析」元件的詳細資料，例如維度、（計算）量度和衍生欄位
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 18%

---

# Content Analytics元件

{{draft-aca}}

{{release-limited-testing}}

內容分析將下列類別的元件(維度、 （計算）量度、衍生欄位)新增至Customer Journey Analytics中現有的元件：

* [體驗中繼資料](#experience-metadata)
* [體驗屬性](#experience-attributes)
* [體驗事件](#experience-events)
* [資產中繼資料](#asset-metadata)
* [資產屬性](#asset-attributes)
* [Assets事件](#asset-events)
* [計算量度](#calculated-metrics)

在下清單格中，![AI產生](/help/assets/icons/AI.svg)表示AI/ML產生的屬性/值組。

## 體驗中繼資料

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 體驗管道 | 體驗的管道。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗來源 | 體驗的Source URL。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗 ID | 體驗的唯一ID。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗名稱 | 體驗的名稱。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗說明 | 體驗的說明。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗縮圖 URL | 體驗縮圖的URL。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗水平百分比深度 | 體驗水準百分比深度的可量化值。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗垂直百分比深度 | 體驗垂直百分比深度的可量化值。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗水平像素深度 | 體驗水準畫素深度的可量化值。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗垂直像素深度 | 體驗的垂直畫素深度的可量化值。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |

{style="table-layout:fixed"}



## 體驗屬性

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 體驗可讀性分數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的可讀性分數。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗關鍵字 | ![AI已為體驗產生](/help/assets/icons/AI.svg)關鍵字。 | Dimension<br>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗說服策略 | ![AI已產生](/help/assets/icons/AI.svg)存在於指定體驗中的勸說策略。 可能的值包括：社會身分、社會證明、權威、具體性、踏進門中、克服抗拒性、互惠性、錨定和比較、社會影響、稀缺性和擬人化。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗敘述 | ![AI已產生](/help/assets/icons/AI.svg)體驗根據行銷人員檢視點的相關性所建置的敘述。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗基調 | ![AI已產生](/help/assets/icons/AI.svg)色調，體驗是根據行銷人員檢視點的相關性所建置 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗行銷情感 | ![由AI產生](/help/assets/icons/AI.svg)閱讀體驗中所使用的文字時，讀者會叫用情緒：急迫性、排他性、鼓勵、挑戰、好奇、成就、信任、簡單和迷戀。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 體驗表情符號計數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的Emoji數目。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗雜湊標籤計數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的雜湊標籤數。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗句子計數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的句子數。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗停用詞比率 | ![AI已產生](/help/assets/icons/AI.svg)體驗的停用字數。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗文字引用計數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的文字引號數目。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗字數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的字數。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗每個句子字數 | ![AI已產生](/help/assets/icons/AI.svg)體驗的每句字數。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |

{style="table-layout:fixed"}


## 體驗事件

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 體驗檢視 | 體驗檢視次數的可量化測量值。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 體驗點按次數 | 可量化的體驗點按次數測量方式。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |

{style="table-layout:fixed"}


## 資產中繼資料

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 資產來源 | 資產的公開可存取來源URL。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產 ID | 資產的唯一識別碼。 資產二進位檔決定唯一性。 如果資產二進位檔案變更，ID就會變更。 唯一識別碼可以是URL，也可以是已建立的雜湊。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產名稱 | 資產名稱。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產類型 | 資產型別。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產縮圖 URL | 資產縮圖的URL。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產 HTML 路徑 | 資產的串連HTML路徑。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產連結 URL | 資產最近的頁面錨點。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產顯示寬度 | 內容資產顯示寬度。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產顯示高度 | 內容資產顯示高度。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產絕對左側 | 內容資產絕對左側。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產絕對頂端 | 內容資產絕對頂端。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產建立者 | 用於建立資產的識別碼。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產建立日期 | 資產建立日期。 | 維度 | 最近\| 工作階段 |
| 資產上次更新者 | 用於資產更新的識別碼。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產上次更新日期 | 資產更新日期。 | 維度 | 最近\| 工作階段 |

{style="table-layout:fixed"}


## 資產屬性

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 資產方向 | ![AI已產生](/help/assets/icons/AI.svg)資產方向。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產整體基調 | ![AI已產生](/help/assets/icons/AI.svg)資產的整體色調。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產前景顏色 | ![AI已產生](/help/assets/icons/AI.svg)資產的前景顏色。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產背景顏色 | ![AI已產生](/help/assets/icons/AI.svg)資產的背景顏色。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產標記 | ![AI已為資產產生](/help/assets/icons/AI.svg)個標籤。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產場景 | ![AI已為資產產生](/help/assets/icons/AI.svg)個場景。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產物件 | ![AI已產生資產的](/help/assets/icons/AI.svg)物件。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產攝影風格 | ![AI已產生資產的](/help/assets/icons/AI.svg)攝影樣式。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產影像類型 | ![AI已產生](/help/assets/icons/AI.svg)資產的影像型別。 可能的值包括：photographic、sketch、painting、digital_cartoon、infographics、graphic_design、collage和software_screenshot。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產相機位置 | ![AI已產生資產的](/help/assets/icons/AI.svg)個相機位置。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產相機鄰近度 | ![AI已產生](/help/assets/icons/AI.svg)資產的相機近似值。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產人員類別 | ![AI已為資產產生](/help/assets/icons/AI.svg)人員類別。 可能的值包括：人、男人、女人、社交群組、人群、人、男孩、女孩和孩子。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產視覺內容密度 | ![AI已產生](/help/assets/icons/AI.svg)資產的視覺內容密度。 可能的值包括：低、中或高。 低內容密度表示每個影像單位區域呈現的資訊量較少。 | 維度 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產視覺注意力分散度 | ![AI已產生](/help/assets/icons/AI.svg)資產的視覺注意分攤。 可能的值包括：低、中或高。 注意力擴散是指檢視者注意力在圖片不同部分之間的分散程度。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產光線條件 | ![AI已產生](/help/assets/icons/AI.svg)資產的照明條件。 可能的值包括：黃金時間、藍色時間、正午、陰天、夜間、高鍵、低鍵、日光、白熾燈、熒光、彩色和攝影棚。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |
| 資產相機設定 | ![AI已產生](/help/assets/icons/AI.svg)資產的相機設定。 可能的值包括：快門速度、長曝光。 Bokeh blur、motion blur、tilt-shift blur、flash、wide-angle、black and white、surreal、double-exposure、macro和normal模式。 | Dimension<br/>衍生欄位 | 顯示\| 沒有值<br/>最近\| 工作階段 |

{style="table-layout:fixed"}


## 資產事件

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 資產檢視 | 可量化的資產檢視次數測量方式。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |
| 資產點擊次數 | 資產點選次數的可量化測量方式。 | 量度 | 計算值<br/>小數\| 小數位數： 0 |

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

| 標題 | 說明 | 類型 | 設定 |
|---|---|---|---|
| 資產點進率 | 資產點選次數/資產檢視 | 計算量度 | |
| 體驗點進率 | 體驗點按次數/體驗檢視 | 計算量度 | |

{style="table-layout:fixed"}

