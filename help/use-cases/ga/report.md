---
title: 在 Customer Journey Analytics 中報告 Google Analytics 資料
description: 在 Customer Journey Analytics 中顯示有關 Google Analytics 資料的實用報表
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# 在 Customer Journey Analytics 中報告 Google Analytics 資料

在Customer Journey Analytics中提供資料後，下列範例將為報告該資料提供實用的案例。

## 以視覺化方式將網頁資料和應用程式資料呈現為合併的資料集

這張文氏圖表顯示您的網站上的使用者 (來自您的 Google Analytics 資料)、您的行動應用程式上的使用者 (來自您的 Firebase 資料) 以及您的客服中心的使用者重疊的情況。 您也可以查看績效最高的商品 - 不只可以在網頁上查看，也可以在行動應用程式中查看。 您甚至可以使用計算量度從兩者取得總收入。 當您查看合併收入時，請注意績效最好的商品如何講述不同的故事。 如果沒有合併資料集，您永遠不會知道「斜紋帽」的績效如此高。

![合併的資料集](../assets/combined-datasets.png)

## 找出客戶來電的原因，並減少來電數量

您可以分析過去兩個月呼叫中心逗留時間的趨勢，以判斷呼叫量。 下列範例顯示過去兩個月的資料趨勢。 下列範例顯示日益增加的趨勢，這可能會影響組織成本。

![呼叫量](../assets/call-volume.png)

使用「呼叫原因」維度可提示改善網路體驗的方式，使訪客一開始無法呼叫。 上例顯示，「損壞產品」的每次呼叫平均呼叫時間接近3分鐘，為貴組織提供了改善客戶體驗並降低呼叫中心成本的精確方法。

您可以檢視哪些產品造成呼叫中心的大部分呼叫，以及有多少客戶進行這些呼叫。 泡泡圖顯示，2萬人打電話，花了4小時30多分鐘，還回了33個單位的「男性短袖T恤」產品。

![通話原因](../assets/call-reason.png)

套用「呼叫原因」的維度劃分，範例會顯示「損壞的產品」維度項目。 下一步是聯絡品質控制部門，並了解為何客戶會收到損壞的 T 恤。

您可以查看哪些網頁將呼叫引導至呼叫中心。 此報表可讓您知道網站上哪些體驗不佳，並協助您的產品經理解決這些難題。 下列範例使用計算量度來將資料篩選下去，僅限以客服中心呼叫結束的工作階段。 此外，CJA中也使用「參與」模式 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace).

下列範例顯示「購物車」和「結帳資訊」頁面驅動大部分的呼叫。

![貢獻頁面](../assets/contributing-pages.png)

同類群組表格可讓您查看使用者造訪網站後，呼叫客服中心通常需要多久的時間。 以下範例指出此範例資料集的平均時間介於三週到四週之間。

![同類群組](../assets/cohort.png)

## 使用進階行銷歸因

CJA可讓您針對跨管道資料使用複雜的歸因模型。 在以下範例中，您可以看到將收入的最後接觸、首次接觸、U 型及演算法歸因套用到 Google Analytics 管道分組維度的比較。

![行銷歸因](../assets/mktg-attribution.png)

使用計算量度時，您可以將該歸因套用到您的網頁收入、行動應用程式收入，甚至可以移除商品退貨。 因此，您可以看到每個行銷管道的真正淨收入。

![計算量度](../assets/calc-metric.png)

Attribution IQ也可讓您篩選資料。 您可以查看僅限特定組使用者的歸因，例如使用多台裝置使用者。

![篩選器](../assets/filter.png)

您也可以將網頁和應用程式收入歸因於您的Google廣告內容。 此資料集的範例收入來自線上Google Ads驅動的行動應用程式，而非網路。 透過依網頁和應用程式收入排序廣告，您可獲得最佳Google廣告的不同圖片。

![Google廣告](../assets/google-ad.png)

在CJA中合併資料集可讓您在此範例中查看，線上廣告對您行動應用程式上購買的產品有任何影響。 以下視覺效果顯示，與單獨使用網路相比，來自Google Ads的行動應用程式收入額外1.4萬至1.5萬美元。

![Google廣告2](../assets/google-ad2.png)
