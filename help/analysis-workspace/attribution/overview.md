---
title: 歸因概觀
description: 將成功事件的評分歸因於多個維度項目的概念。
exl-id: 845b4310-e1b2-4690-b267-6f6d211845fb
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 90%

---

# 歸因概觀

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[深入了解...](/help/getting-started/cja-aa.md)

歸因可讓分析人員自訂維度項目獲得成功事件評分的方式。例如：

1. 您的網站訪客按了一下您其中一個產品頁面的付費搜尋連結。他們將產品新增至購物車，但並未購買。
2. 隔天，他們看到了朋友的社交媒體貼文，就按下連結，並完成購買。

在某些報表中，您可能想要將訂單歸因於「付費」搜尋。在其他報表中，則可能會將訂單歸因至「社交」。歸因可讓您控制報表的這個方面。

## 歸因 IQ 的價值

客戶歷程並非線性，且經常無法預測。每位客戶都以自己的步調前進，常常會流連往返、停滯不動、重新開始，或以其他非線性行為進行互動。這些非機械性的行為使得我們很難掌握行銷活動在客戶歷程中的影響，也會阻礙我們將多個資料管道聯繫在一起的努力。

![歸因 IQ 問題](assets/attribution_iq_problem.png)

Customer Journey Analytics可讓您：

* 定義付費媒體以外的歸因：任何維度、量度，管道或事件都可以套用在模型上 (例如內部搜尋)，而不僅限於行銷活動。
* 不限次數利用歸因模型比較功能：動態比較任意數量的模型。
* 避免實施變更：透過報表時間處理功能和內容感知工作階段，可以建置客戶歷程內容並套用在執行階段中。
* 建構與您的歸因狀況最相符的工作階段。
* 依篩選條件劃分歸因：輕鬆比較任何重要篩選條件（例如新客戶與回頭客戶、產品X與產品Y、忠誠度或CLV）的行銷管道效能。
* 跨管道檢查和多點接觸分析：使用 Venn 圖表和色階分佈圖，並計算歸因結果趨勢。
* 以視覺化方式分析關鍵行銷序列活動：透過多節點流量和流失視覺效果，以視覺效果方式探究帶來轉換的路徑。
* 建立計算量度：使用任何數量的歸因配置方法。

## 功能

歸因 IQ 包含下列功能:

* [歸因面板](../c-panels/attribution.md)：取用任何維度和量度，並將其與不同的歸因模型快速比較。
* [將歸因套用至量度](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)：對專案中的任何量度使用非預設歸因。
* [將歸因套用至劃分](/help/components/dimensions/t-breakdown-fa.md)：對劃分使用非預設歸因。
* [比較歸因模型](/help/components/apply-create-metrics.md)：快速瞭解不同歸因模型與任何量度的比較情形。
