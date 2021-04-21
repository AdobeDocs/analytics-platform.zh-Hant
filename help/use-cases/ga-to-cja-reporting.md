---
title: 關於Customer Journey Analytics中Google Analytics資料的報告
description: 顯示Google Analytics資料的有用報告Customer Journey Analytics
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# 關於Customer Journey Analytics中Google Analytics資料的報告

現在您已將Google Analytics資料收錄至Experience Platform與Customer Journey Analytics(CJA)](/help/use-cases/ga-to-cja.md)，我們將向您展示一些用於報告該資料的實用藍本。[

## 將網頁資料和應用程式資料視為結合的資料集

此Venn圖表顯示您網站(來自您的Google Analytics資料)和行動應用程式（來自您的Firebase資料）以及來自您客服中心的使用者重疊。 您也可以在網路上，以及行動應用程式中，看到效能最佳的產品。 您甚至可以使用計算度量，從兩者獲得總收入。 請注意，當您查看總收入時，頂尖產品會呈現不同的情況。 如果沒有這些資料集，你永遠不會知道「Twill cap」表現得如此出色。

![](assets/combined-datasets.png)

## 確定呼叫原因並減少呼叫量

為了確認您接到過許多電話，您可以預測我們呼叫中心在過去2個月中所花費的時間。 您很容易就能看出趨勢的增加。 這令人擔憂，因為您的客服中心代表在電話上的每一分鐘，都會花費您的金錢。 這肯定會影響您的獲利。

讓我們來看一下導致呼叫中心增加的主要原因。 請注意，「拒絕信用卡」、「移除信用卡」和「損壞的產品」是主要原因。 這已可提示如何改善線上體驗。 您也可以對這些呼叫原因進行趨勢分析，並瞭解哪些原因對整體尖峰的貢獻最大。 有意思的是，有「損壞的產品」的客戶每次通話花費超過3分鐘。

![](assets/call-volume.png)

讓我們進一步瞭解哪些產品導致呼叫中心的大部分呼叫，以及有多少客戶撥打了這些呼叫。 泡泡圖顯示，有2萬人打電話，花了4小時30多分鐘，退回了33套「男式短袖T恤」產品。

我們可以劃分這種洞見，並瞭解這些人為何拖曳至「呼叫原因」維度來傳回產品。 如您所見，本產品接到如此多呼叫的原因是「損壞的產品」。 下一步是聯絡品質控制部門，瞭解客戶為何收到損壞的T恤。

![](assets/call-reason.png)

現在，讓我們來看看哪些網頁驅動了呼叫中心的來電。 這可讓您瞭解網站上效能不佳的體驗所在位置，並協助您的產品經理解決這些挑戰。

我們透過

* 使用計算量度將資料篩選為只有呼叫中心呼叫結束的工作階段。
* 使用CJA的[Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace)中的「參與率」模型。

您可以輕鬆查看哪些頁面最常參與呼叫結束的作業。 您可以看到「購物車」和「結帳資訊」頁面驅動了大部分的呼叫。 由於您也包含Firebase行動應用程式資料，因此您甚至可以看到頁面錯誤和產生呼叫的應用程式當機。 如果您想要提供絕佳的網路和行動應用程式體驗，這是非常重要的資料點。

![](assets/contributing-pages.png)

最後，使用Analysis Workspace的同類群組表格，很容易看出使用者在造訪網站後，通常需要多長時間才能呼叫我們的客服中心。 您可以看到平均3到4週的時間。

![](assets/cohort.png)

## 使用進階行銷歸因

CJA可讓您在跨通道資料上使用複雜的歸因模型。 在下列範例中，您可看到將收入的「上次接觸」、「首次接觸」、「U形」和演算法歸因套用至「Google Analytics渠道分組」維度的比較。

![](assets/mktg-attribution.png)

使用計算量度，您可以將該歸因套用至您的網頁收入、行動應用程式收入，甚至移除產品退貨。 因此，您可以看到每個行銷渠道的真實淨收入。

![](assets/calc-metric.png)

Attribution IQ也可讓您輕鬆篩選資料。 您只能看到特定使用者集的歸因，例如使用多個裝置的使用者。

![](assets/filter.png)

最後，您也可以將您的網頁和應用程式收入歸因於您的Google廣告內容。 您會注意到，我們的線上Google廣告所驅動的行動應用程式比網頁所帶來的收入更多。 透過依網路和應用程式收入排序廣告，您就可以瞭解您表現最佳的Google廣告。

![](assets/google-ad.png)

沒有CJA，您就無法得知您的線上廣告對行動應用程式上購買的產品有任何影響。 現在您可以看到，與僅網路相比，Google Ads的行動應用程式收入還增加了14,000美元- 5,000美元。

![](assets/google-ad2.png)