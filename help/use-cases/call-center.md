---
title: 匯入客服中心和網路資料
description: 了解如何建立連結客服中心和網站資料的資料集。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 98%

---

# 匯入客服中心和網路資料

Customer Journey Analytics 具有重要的強大功能，可將不同來源的資料集合併成單一 Analysis Workspace 專案。使用本指南瞭解貴組織如何結合網站資料與客服中心資料。

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

將您的資料匯入 Adobe Experience Platform。請參閱 Adobe Experience Platform 文件中的[建立結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html)和[匯入資料](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)。

將資料匯入 Platform 時，遵循下列秘訣有助於從產生的報表中獲得更多深入見解：

* 確認連結客服中心和網路資料的識別碼採用類似的格式。
* 在每個資料集中加入資料來源，例如在所有結構描述中加入「`data_source`」欄，並將每個事件的值分別設為「`"Web"`」或「`"Call center"`」。<!--mapper-->

## 彙整人員 ID

CJA 需有共同識別碼才能產生[合併資料集](../connections/combined-dataset.md)。

* 如果您兩個資料集的每個事件已有共同識別碼，您可以略過此步驟，繼續建立連線。
* 如果任一資料集中只有部分事件有共同識別碼，您可以使用跨管道分析來彙整資料。如需為這兩個資料集啟用跨管道分析的相關步驟，請參閱[跨管道分析概述](/help/connections/cca/overview.md)。

## 在 CJA 中建立連線

在 CJA 中[建立連線](/help/connections/create-connection.md)。

* 如果您選擇使用跨管道分析，系統會產生新的彙整資料集供您使用。新建立的彙整 ID 欄位可視為人員 ID。
* 或者，您也可以在連線中選取原本的網路和客服中心資料集，以便使用。

## 建立資料檢視

建立連線後，您可以在 Analysis Workspace 中[建立資料檢視](/help/data-views/create-dataview.md)，以利後續使用。<!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

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
1. 將該量度換成您要測量轉換情形的客服中心量度。
1. 按一下量度標題附近的齒輪圖示。按一下&#x200B;**[!UICONTROL 「使用非預設歸因模型」]**。
1. 設定所需的[歸因模型](/help/data-views/create-dataview.md)。

產生的報告會顯示客服中心資料的主要量度。<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
