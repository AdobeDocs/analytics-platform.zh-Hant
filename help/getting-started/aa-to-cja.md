---
title: 從Adobe Analytics遷移到Customer Journey Analytics
description: 從Adobe Analytics遷移到Customer Journey Analytics的步驟
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 868cd819148b29436fbd92cf220c8bc4cb9e0725
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 5%

---


# 準備從Adobe Analytics遷移到Customer Journey Analytics

在將資料從Adobe Analytics遷移到Customer Journey Analytics之前，請先瞭解這些注意事項，以準備資料並瞭解這兩種技術之間的關鍵區別。

## 準備資料

準備您的Adobe Analytics資料以無縫遷移到Customer Journey Analytics對資料完整性和報告一致性至關重要。

### 1。收集身份

瞭解客戶旅程的最關鍵部分可能是瞭解客戶在每一步驟中所處的位置。 對於Customer Journey Analytics，具有跨所有通道和相應資料的標識符允許在CJA內將多個源拼接在一起。
標識示例可能是客戶ID、帳戶ID或電子郵件ID。 無論身份是什麼（可能有多個），請確保為每個ID考慮以下內容：

* 存在或可以添加到要引入CJA的所有資料源上
* 在每行資料上填充
* 不包含PII。 對任何可能敏感的內容應用散列。
* 在所有源之間使用相同格式（相同長度、相同散列方法等）

在像Adobe Analytics這樣的資料集中，身份可能並不存在於每一行資料中，但是輔助身份卻存在。 在這種情況下，跨渠道分析（以前稱為「基於欄位的縫合」）可用於在僅由客戶的ECID標識和收集身份時（例如，當客戶驗證時）彌合行之間的差距。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hant)

### 2.調整變數

將Adobe Analytics資料遷移到Customer Journey Analytics的最直接方法是使用 [Adobe Analytics源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。 此連接器將您的Adobe Analytics變數直接映射到AEP中的XDM架構和資料集，而XDM架構和資料集又可輕鬆連接到CJA。

完整的全球報告套件可能並不總是可用於實施。 如果計畫將多個報表套件Customer Journey Analytics，則必須提前計畫使變數在這些報表套件中對齊。

例如，報表套裝 1 中的 eVar1 可能指向[!UICONTROL 頁面]。在報告套件2中，eVar1可以指向 [!UICONTROL 內部市場活動]。 在引入CJA時，這些變數將混合到單個eVar1維中，導致可能的混淆和不準確的報告。

如果您由於與 [!UICONTROL 已超出Uniques] 或 [!UICONTROL 低流量]知道CJA沒有 [維上的基數限制](/help/components/dimensions/high-cardinality.md)。 它允許顯示和計數任何唯一值。

### 3. （重新）配置您的營銷渠道

傳統的Adobe Analytics營銷渠道設定在CJA中不執行相同的設定。 原因有二：

* Adobe Analytics資料的處理水準，以及

* 報告時間性質的Customer Journey Analytics

Adobe已發佈 [市場營銷渠道實施的最新最佳做法](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en)。 這些更新的建議可幫助您充分利用Adobe Analytics已具備的與Attribution IQ相關的功能。 它們還會設定您在過渡到Customer Journey Analytics時是否成功。

### 4.決定使用分析資料連接器與Experience PlatformSDK

作為 [體驗邊緣](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant) 資料收集會不斷發展，您可能會遷移到Adobe Experience PlatformWeb SDK或具有Adobe Experience Platform邊緣網路的Adobe Experience Platform移動SDK。 SDK的典型實施將將資料發送到Adobe Analytics，但直接將資料發送到Adobe Experience Platform的新機會也隨之而來。 然後，它可以被攝入Customer Journey Analytics，同時保留發送到Adobe Analytics的資料。

這種方法極大地擴展了資料採集的可能性：欄位數不再有限制，也不再需要將資料元素映射到道具、變數和事件（如在分析中）。 可以使用不同類型的無限架構元素，並使用CJA以多種方式表示它們 [資料視圖](/help/data-views/data-views.md)。 當直接發送到Adobe Experience Platform時，資料可用性的速度會加快，因為通過Adobe Analytics進行資料處理的時間會縮短。

**使用Experience PlatformSDK的優勢**

* 靈活的架構，可定義您需要的任何欄位
* 不依賴Adobe Analytics命名法(道具、eVar、事件等)
* 無字元限制問題（道具有100個字元）
* 加快Adobe Experience Platform的資料可用性

**使用Experience PlatformSDK的缺點**

不支援以下Adobe Analytics元件：

* 行銷管道
* 機器人篩選
* 地理、域、設備查找
* Analytics for Target (A4T)

## 為重大差異做好準備

### 輕鬆處理報告時間

Adobe Analytics的報告依賴大量資料預處理來生成結果，如您在eVars中看到的持久性。 Customer Journey Analytics在報告運行時運行這些計算。

報告時間處理開啟了應用追溯設定並建立多個版本的可變持久性的功能，而無需更改基礎資料的收集方式。

此轉換將導致報告資料的方式出現一些差異，特別是對於可能具有較長過期窗口的任何變數。 您可以首先使用 [虛擬報告套件](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html)。

### 確定關鍵段和計算度量

Adobe Analytics段（在CJA中稱為篩選器）和計算度量與Customer Journey Analytics不相容。 在很多情況下，這些元件可以在CJA中使用新的模式和可用資料重建。

要使用戶在系統之間轉換時盡可能順利地進行轉換，請提前規劃

1. 確定這些元件中最關鍵的元件。

1. 記錄他們的定義，

1. 確定在CJA中複製資料所需的欄位 [篩選器](/help/components/filters/filters-overview.md) 和 [計算度量](/help/components/calc-metrics/calc-metr-overview.md)。

下面是幾段視頻來指導您：

* [將Adobe Analytics段移到Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [將計算量度從 Adobe Analytics 移至 Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
