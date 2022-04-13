---
title: 在 Customer Journey Analytics 中報告 Google Analytics 資料
description: 在 Customer Journey Analytics 中顯示有關 Google Analytics 資料的實用報表
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 98%

---

# 在 Customer Journey Analytics 中報告 Google Analytics 資料

現在您已將 Google Analytics 資料內嵌至 Experience Platform 和 Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md)，接下來我們會針對該資料顯示一些實用的報表案例。[

## 以視覺化方式將網頁資料和應用程式資料呈現為合併的資料集

這張文氏圖表顯示您的網站上的使用者 (來自您的 Google Analytics 資料)、您的行動應用程式上的使用者 (來自您的 Firebase 資料) 以及您的客服中心的使用者重疊的情況。 您也可以查看績效最高的商品 - 不只可以在網頁上查看，也可以在行動應用程式中查看。 您甚至可以使用計算量度來取得這兩者的總收入。 當您查看合併收入時，請注意績效最好的商品如何講述不同的故事。 如果沒有合併資料集，您永遠不會知道「斜紋帽」的績效如此高。

![](assets/combined-datasets.png)

## 找出客戶來電的原因，並減少來電數量

若要確認您最近是否接到許多電話，您可以對客服中心在過去兩個月期間所花的時間進行趨勢分析。 我們很容易看到遞增的趨勢。 這很令人擔心，因為您的客服中心代表在電話上的每一分鐘都會損耗您的成本。 這樣絕對會影響您的盈虧底線。

讓我們來審視造成客服中心來電增加的主要原因。 請注意，「信用卡被拒絕」、「移除信用卡」和「商品損壞」是來電的主要原因。 這已經可以暗示改善線上體驗的方法。 您也可以對這些來電理由進行趨勢分析，並了解哪些理由對整體飆升的貢獻最大。 有趣的是，「商品損壞」在每通電話中所花的時間都超過 3 分鐘。

![](assets/call-volume.png)

讓我們來進一步觀察，看看客服中心最常接到有關哪些商品的來電，以及有多少客戶撥打了這類電話。 泡泡圖指出有 20,000 個人打了電話，一共花了超過 4 小時又 30 分鐘的時間，並且退回了 33 件「男士短袖 T 恤」商品。

我們可以分析此洞察資訊，並藉由拖入「來電原因」維度來了解這些人退貨的原因。 如您所見，此商品之所以接到這麼多客戶來電是因為「商品損壞」。 下一步是聯絡品質控制部門，並了解為何客戶會收到損壞的 T 恤。

![](assets/call-reason.png)

現在，讓我們來審視哪些網站頁面造成客服中心來電增加。 這樣可讓您知道網站上表現不佳的體驗位在何處，並幫助產品經理解決這些難題。

我們透過以下方式採取這種做法

* 使用計算量度來篩選資料，找出僅限於以客服中心電話結尾的互動。
* 使用 CJA 的 [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace) 中的「參與」模型。

您可以輕鬆地查看哪些頁面最常參與以電話結尾的互動。 您可以看到「購物車」和「結帳資訊」頁面吸引了大多數的來電。 因為您已經納入 firebase 行動應用程式資料，所以您甚至可以看到造成這些來電的頁面錯誤和應用程式當機狀況。 如果您想要提供絕佳的網頁和行動應用程式體驗，這是非常重要的資料點。

![](assets/contributing-pages.png)

最後，使用 Analysis Workspace 中的同類群組表格時，就很容易了解使用者在瀏覽網站後，通常過了多久才會撥電話到我們的客服中心。 您可以看到平均時間為 3 到 4 週之間。

![](assets/cohort.png)

## 使用進階行銷歸因

CJA 可讓您針對跨管道資料使用複雜的歸因模型。 在以下範例中，您可以看到將收入的最後接觸、首次接觸、U 型及演算法歸因套用到 Google Analytics 管道分組維度的比較。

![](assets/mktg-attribution.png)

使用計算量度時，您可以將該歸因套用到您的網頁收入、行動應用程式收入，甚至可以移除商品退貨。 因此，您可以看到每個行銷管道的真正淨收入。

![](assets/calc-metric.png)

Attribution IQ 也可讓您輕鬆地篩選資料。 您可以查看僅限特定組使用者的歸因，例如使用多台裝置使用者。

![](assets/filter.png)

最後，您也可以將您的網頁和應用程式收入歸因於您的 Google 廣告內容。 您會注意到，您從我們的線上 Google 廣告所驅動的行動應用程式中獲得的收入高於從網頁上獲得的收入。 當您根據網頁和應用程式收入來排序廣告時，您對於您的哪些 Google 廣告成效最佳會有非常不同的觀點。

![](assets/google-ad.png)

如果沒有 CJA，您就無法得知您的線上廣告影響了客戶在您的行動應用程式上購買的商品。 現在您可以看到，相較於網頁本身的收入，來自 Google 廣告的行動應用程式收入增加了 14000 美元到 5000 美元。

![](assets/google-ad2.png)
