---
title: 匯入客服中心和Web資料
description: 瞭解如何建立連結客服中心和網站資料的資料集。
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# 匯入客服中心和Web資料

「客戶歷程分析」提供有價值且強穩的功能，可將不同來源的資料集合併為單一工作區專案。 使用本指南瞭解貴組織如何將您網站的資料接合到來自您呼叫中心的資料。

## 必要條件

* 結合這兩組資料的最重要元件是每個資料來源之間的共同識別碼。 例如客戶ID、雜湊電子郵件、登入使用者名稱或電話號碼。
* 存取Adobe Experience Platform和客戶歷程分析
* 如果您的資料集包含來自互動式語音回應系統的記錄檔，Adobe建議處理資料時，只要在將資料匯入平台之前加入提示互動。
* 如果您的資料集包含呼叫記錄，Adobe建議包含下列欄：
   * 呼叫開始的日期／時間
   * 呼叫原因
   * 呼叫中心ID
   * 呼叫中心代理ID
   * 呼叫持續時間
   * 通話結果
   * 通話費用（如果有的話）
   * 您的組織想要包含的任何其他呼叫中繼資料

## 將網路和客服中心資料匯入平台

開始將資料匯入Adobe Experience Platform。 請參閱Adobe Experience Platform檔案中的[建立架構](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/tutorials/create-schema-ui.html)和[收錄資料](https://docs.adobe.com/content/help/zh-Hant/experience-platform/ingestion/home.html)。

將資料匯入平台時，遵循下列提示有助於增加產生報表的洞察力：

* 請確定用來連結呼叫中心和Web資料的識別碼格式類似。
* 在每個資料集中包含資料來源。 例如，在每個架構中包含`data_source`欄，並將每個事件的值分別設為`"Web"`或`"Call center"`。<!--mapper-->

## 將人證縫合在一起

CJA需要通用識別碼來產生[組合資料集](../connections/combined-dataset.md)。

* 如果您的資料集在兩個資料集上的每個事件上都有共同的識別碼，您可以略過此步驟，繼續建立連線。
* 如果您的其中一個資料集只有某些事件有一個通用識別碼，您可以使用跨通道分析將資料拼湊在一起。 如需為這兩個資料集啟用CCA的步驟，請參閱[跨通道分析概述](/help/connections/cca/overview.md)。

## 在CJA中建立連線

[在CJA中](/help/connections/create-connection.md) 建立連線。

* 如果使用CCA，則有新的銜接資料集可供您使用。 使用新建立的銜接ID欄位作為人員ID。
* 否則，您可以選擇在連接中使用的原始Web和呼叫中心資料集。

## 建立資料檢視

建立連線後，您可以「建立資料檢視」[，以便用於分析工作區。<!-- page dimension last touch, session persistence -->](/help/data-views/create-dataview.md)
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## 建立視覺化

下列視覺化可用於從您的銜接資料集獲得見解。

### 資料集重疊

此視覺化功能可協助您瞭解CCA將資料連結在一起的程度。

1. 建立兩個篩選。 這兩個篩選中使用的變數與上述反映每個事件資料來源的變數相同。 如需詳細資訊，請參閱[建立篩選器](/help/components/filters/create-filters.md)。
   * 資料集ID等於您網頁資料的人員容器
   * 資料集ID等於呼叫中心資料的人員容器
2. 在分析工作區中，將[Venn](/help/analysis-workspace/visualizations/venn.md)視覺化拖曳至工作區畫布上。
3. 將兩個新建立的篩選器拖曳至&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;區域，將人員量度拖曳至&#x200B;**[!UICONTROL 新增量度]**&#x200B;區域。

產生的Venn視覺化會顯示資料集中同時包含Web和客服中心資料的人數。 重疊越大，成功縫合的人就越多。 不重疊的區域代表僅位於一個資料集或另一個資料集的人。

### 將呼叫中心事件歸因於網頁

此自由表格可讓您查看對呼叫中心事件有貢獻的熱門頁面。 首先，請確定所需的維度和量度具有正確的歸因模型：

1. 將包含網頁名稱的維度拖曳至自由表格視覺化。
1. 將量度取代為您要測量轉換的所需呼叫中心量度。
1. 按一下量度頁首附近的齒輪圖示。 按一下「使用非預設歸因模型&#x200B;]**」。**[!UICONTROL 
1. 設定所要的[歸因模型](/help/data-views/configure-dataviews.md#Attribution-model)。

產生的報表顯示來自客服中心資料的排名最前的量度。<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->