---
description: 顯示計算量度的範例。
title: 計算量度範例
feature: Calculated Metrics
exl-id: 5e73ab52-627a-4064-bfb7-354c0ba1e4ee
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# 計算量度範例

本文舉例說明如何定義更進階的計算量度。

## 跳出率

您要計算跳出率。

+++ 詳細內容

跳出的定義會受到另一個討論的影響，但在此範例中，您會定義「跳出」事件區段，其中「工作階段開始」等於1，「工作階段結束」等於1。 您使用此區段來定義工作階段的跳出工作階段率。


### 區段

![退回事件](assets/example-bounce-bouncedevents.png)

### 計算量度

![跳出率](assets/example-bounce-rate.png)


### 衍生欄位

或者，您可以使用衍生欄位[來定義](/help/data-views/derived-fields/derived-fields.md#bounces)跳出率。

衍生欄位是資料檢視的一部分，其優點是不是每個使用者都可以覆寫或修改跳出率量度的定義。 這個優點也帶來了限制。 無權存取資料檢視的使用者無法使用衍生欄位，且必須訴諸區段和計算量度來定義跳出率。

請參閱此[部落格](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=zh-Hant)，以取得有關如何在Customer Journey Analytics中計算跳出數和跳出率的詳細背景資訊。

+++


## 條件式頁面檢視

您想要定義一個計算量度，只計算超過100個工作階段造訪過之頁面的頁面檢視。

+++ 詳細內容 

![條件式頁面檢視](assets/conditional-page-views.png)

+++

## 前30%個工作階段的頁面檢視

您要定義只計算前30%階段作業頁面檢視的計算量度。

+++ 詳細內容

![前30%的頁面檢視](assets/top30-page-views.png)

+++
