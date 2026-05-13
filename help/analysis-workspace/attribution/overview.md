---
title: 成效歸因概觀
description: 了解將成功事件的功勞分配於多個維度項目的概念。
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
TQID: https://experienceleague.adobe.com/ncY8TuwUb3duwfK3n8u69eyXWUDzI5OMF-AACOoDmIY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 453
ht-degree: 96%

---

# 成效歸因概觀

歸因可讓分析人員自訂維度項目獲得成功事件評分的方式。 例如：

1. 您的網站訪客按了一下您其中一個產品頁面的付費搜尋連結。 他們將產品新增至購物車，但並未購買。
2. 隔天，他們看到了朋友的社交媒體貼文，就按下連結，並完成購買。

在某些報告中，您可能想要將訂單歸因於「付費」搜尋。 在其他報告中，則可能會將訂單歸因至「社交」。 歸因可讓您控制報表的這個方面。 Adobe Analytics Ultimate、Prime、Select 和 Foundation 的所有組織都可使用。 如果您不確定您與 Adobe 的合約類型，請聯絡貴組織的 Adobe 帳戶團隊。

## 成效歸因的價值

客戶歷程並非線性，且經常無法預測。 每位客戶都以自己的步調前進，常常會流連往返、停滯不動、重新開始，或以其他非線性行為進行互動。 這些非機械性的行為使得我們很難掌握行銷活動在客戶歷程中的影響， 也會阻礙我們將多個資料管道聯繫在一起的努力。

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics 強化歸因功能，讓您可以：

* 定義付費媒體以外的歸因：任何維度、量度，管道或事件均可套用在模式上 (例如內部搜尋)，而不僅限於行銷活動。
* 不限次數利用歸因模式比較功能：動態比較任意數量的模式。
* 避免實施變更：透過報告時間處理功能和內容感知工作階段，可以建置客戶歷程內容並套用在執行階段中。
* 建構與您的歸因情境最相符的工作階段。
* 按區段劃分歸因：輕鬆比較行銷管道在任何重要區段中的效能 (例如，新客與常客、產品 X 與產品 Y、忠誠度或 CLV)。
* 跨管道檢查和多點接觸分析：使用文氏圖表和直方圖，並計算歸因結果趨勢。
* 以視覺化方式分析關鍵行銷序列活動：透過多節點流量和流失視覺效果，以視覺效果方式探究帶來轉換的路徑。
* 建立計算量度：使用任何數量的歸因配置方法。

## 功能

Attribution 包含下列功能：

* [歸因面板](/help/analysis-workspace/c-panels/attribution.md)：取用任何維度和量度，並將其與不同的歸因模式快速比較。
* [將歸因套用至量度](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)：對專案中的任何量度使用非預設歸因。
* [將歸因套用至劃分](/help/components/dimensions/t-breakdown-fa.md#apply-attribution-models-to-breakdowns)：對劃分使用非預設歸因。
* [比較歸因模式](/help/components/apply-create-metrics.md#compare-metrics-with-different-attribution-models)：快速瞭解不同歸因模式與任何量度的比較情形。

## 影片


<!--  
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in Freeform tables](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-attribution-iq-in-freeform-tables){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

<!-- 
Attribution IQ 
>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Attribution in calculated metrics](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/attribution-iq-in-calculated-metrics){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


>[!BEGINSHADEBOX]

請參閱![影片簽出](/help/assets/icons/VideoCheckedOut.svg) [使用成效歸因面板](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/panels/build-the-attribution-panel){target="_blank"}，以觀看示範影片。

>[!ENDSHADEBOX]


<!-- 
Attribution IQ

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding side-by-side comparisons of Attribution models](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/adding-side-by-side-comparisons-of-attribution-iq-models){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

