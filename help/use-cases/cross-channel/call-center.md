---
title: 匯入客服中心和網頁的資料
description: 了解如何建立連結客服中心和網站資料的資料集。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: ht
source-wordcount: '1148'
ht-degree: 100%

---

# 匯入客服中心和網頁的資料

Customer Journey Analytics 具有重要的強大功能，可將不同來源的資料集合併成單一 Analysis Workspace 專案。使用本指南瞭解貴組織如何結合網站資料與客服中心資料。例如，您可以在聯絡客戶支援之前先了解客戶採取了哪些動作、他們查看了哪些內容以及他們搜尋了哪些術語。然後，您可以確定要改進的內容和自助服務工具，以便客戶可以更好地自行解決問題而無需致電。

## 先決條件

* 合併這兩組資料最重要的元件，是資料來源之間必須具有共同識別碼，例如客戶 ID、雜湊電子郵件、登入使用者名稱或電話號碼。
* 存取 Adobe Experience Platform 和 Customer Journey Analytics
* 如果您的資料集內含有互動式語音回應系統的記錄檔，Adobe 建議您在匯入 Platform 前先處理資料，僅加入提示互動內容。
* 如果您的資料集內含有通話記錄檔，Adobe 建議您加入下列各欄：
   * 通話開始日期/時間
   * 通話原因
   * 客服中心 ID
   * 客服中心專員 ID
   * 通話長度
   * 通話結果
   * 通話費用 (若有)
   * 貴組織想加入的其他任何通話中繼資料

## 將網路和客服中心資料匯入 Platform

將您的資料匯入 Adobe Experience Platform。請參閱 Adobe Experience Platform 文件中的[建立結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)和[匯入資料](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hant)。

將資料匯入 Platform 時，遵循下列秘訣有助於從產生的報表中獲得更多深入見解：

* 確認連結客服中心和網路資料的識別碼採用類似的格式。
* 在每個資料集中加入資料來源，例如在所有結構描述中加入「`data_source`」欄，並將每個事件的值分別設為「`"Web"`」或「`"Call center"`」。<!--mapper-->

## 彙整人員 ID

CJA 需有共同識別碼才能產生[合併資料集](/help/connections/combined-dataset.md)。

* 如果您兩個資料集的每個事件已有共同識別碼，您可以略過此步驟，繼續建立連線。
* 如果任一資料集中只有部分事件有共同識別碼，您可以使用跨管道分析來彙整資料。如需為這兩個資料集啟用跨管道分析的相關步驟，請參閱[跨管道分析總覽](/help/cca/overview.md)。

## 在 CJA 中建立連線

在 CJA 中[建立連線](/help/connections/create-connection.md)。

* 如果您選擇使用跨管道分析，系統會產生新的彙整資料集供您使用。新建立的彙整 ID 欄位可視為人員 ID。
* 或者，您也可以在連線中選取原本的網路和客服中心資料集，以便使用。

## 建立資料檢視

建立連線後，您可以在 Analysis Workspace 中[建立資料檢視](/help/data-views/create-dataview.md)，以利後續使用。有用的元件包括：

* 具有最後接觸和工作階段持續性的頁面維度。您可以將客服中心量度與客戶在致電之前檢視的最後一頁聯繫起來。
* 使用「客服中心原因」結構描述欄位來增加出現次數的呼叫量度。使用[量度重複資料刪除](/help/data-views/component-settings/metric-deduplication.md)，以便每個工作階段僅增加一次。

## 建立視覺效果

下列視覺效果可協助您從彙整的資料集中獲取深入見解。

### 資料集重疊

此視覺效果可協助您了解跨管道分析功能彙整資料的成效。

1. 建立兩個篩選器。這兩個篩選器所使用的變數，即為上述反映每個事件資料來源的變數。如需詳細資訊，請參閱[建立篩選器](/help/components/filters/create-filters.md)。
   * 在一個人員容器中，讓資料集 ID 等同於網路資料
   * 在另一個人員容器中，讓資料集 ID 等同於客服中心資料
2. 在 Analysis Workspace 中，將[「文氏圖」](/help/analysis-workspace/visualizations/venn.md)視覺效果拖放至工作區域的畫布。
3. 將兩個新建立的篩選器拖放至&#x200B;**[!UICONTROL 「新增篩選器」]**&#x200B;區域，接著將「人員」量度拖放至&#x200B;**[!UICONTROL 「新增量度」]**&#x200B;區域。

所產生的「文氏圖」視覺效果會顯示資料集 (包含網路和客服中心資料) 的人員數量。重疊範圍越大，表示成功彙整越多人員。未重疊的區域代表人員只隸屬於一個資料集。

### 將客服中心事件歸因於發生事件的原始網頁

此自由表格可讓您查看客服中心事件的幾大來源頁面。首先，確認所需的維度和量度具備正確的歸因模型：

1. 將具網頁名稱的維度拖曳至「自由表格」視覺效果上。
1. 將該量度換成您要測量的客服中心量度。
1. 按一下量度標題附近的齒輪圖示。按一下&#x200B;**[!UICONTROL 「使用非預設歸因模型」]**。
1. 設定所需的[歸因模型](/help/analysis-workspace/attribution/models.md)。例如，半衰期為 15 分鐘的「時間衰減」模型和工作階段的「回顧視窗」。此歸因模型將點數歸於導致致電客服中心的頁面。

產生的報告會顯示驅動致電客服中心的熱門頁面。<!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

您可以依照原因或類別分割來電以進一步了解此表格。

1. 按一下元件清單中「來電原因」維度下的右＞形箭號。此動作會顯示各個維度值。
2. 將所需的維度值拖到「來電」量度下，該量度會依每個相應的來電原因篩選該量度。
3. 對您想要深入了解的每個來電原因重複此動作。使用「所有工作階段」篩選來檢視彙總總數。

<!-- screenshot -->

### 流量視覺效果

您可以深入了解客戶在使用客服中心通道之前嘗試做什麼。此流程視覺效果可協助您了解客戶到達客服中心的最頻繁旅程。借助此洞察力，您可以確定對網站進行最有效改進，進而降低客戶致電的可能性。

1. 按一下左側的&#x200B;**[!UICONTROL 「視覺效果」]**&#x200B;索引標籤，然後將流量視覺效果拖曳到工作區畫布上。
2. 按一下左側的&#x200B;**[!UICONTROL 「元件」]**&#x200B;索引標籤並找到「來電原因」維度。
3. 按一下此維度旁邊的右＞形箭號。此動作會顯示各個維度值。
4. 將所需的來電原因維度項目拖曳到流量視覺效果的中心位置。
5. 流量視覺效果會自動填入上一個和下一個來電原因。用網站頁面維度替換之前的來電原因。
6. 按一下流量視覺效果右上角的齒輪圖示，並將流容器變更為&#x200B;**[!UICONTROL 工作階段]**。

### 長條圖

有多少客戶打過一次電話、打過兩次電話或打過 6 次以上電話？其中一些人從不造訪網站。使用長條圖視覺效果來確定落入每個值區的人數。對於從未造訪過網站的人，請參閱我們如何鼓勵他們自助服務。

1. 按一下左側的&#x200B;**[!UICONTROL 「視覺效果」]**&#x200B;索引標籤並將長條圖視覺效果拖曳到工作區畫布上。
2. 按一下左側的&#x200B;**[!UICONTROL 「元件」]**&#x200B;索引標籤並將呼叫量度拖曳到長條圖視覺效果中。
3. 按一下視覺效果中心的&#x200B;**[!UICONTROL 「顯示進階設定」]**&#x200B;並自訂所需的值區。
4. 按一下&#x200B;**[!UICONTROL 「建置」]**。

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
