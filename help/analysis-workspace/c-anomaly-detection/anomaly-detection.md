---
description: 了解 Analysis Workspace 中的資料異常偵測。
title: 異常偵測概觀
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 40%

---

# 異常偵測概觀

您可以在 Analysis Workspace 內依內容檢視和分析資料異常的情況。

[異常偵測教學影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=zh-Hant) (4:53)

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測可讓您將「真實訊號」與「雜訊」分開，然後識別造成這些訊號或異常的潛在因素。 換句話說，它可讓您識別哪些統計波動重要，哪些不重要。接著，您就可以找出真正異常的根本原因。 此外，您也可以取得可靠的量度(KPI)預測。

您可能會調查的異常例子包括：

* 平均訂購值大幅降低
* 收入較低的訂單激增
* 試用註冊中的尖峰或下降
* 登陸頁面檢視次數下降
* 視訊緩衝事件的尖峰
* 低視訊位元速率的尖峰

Analysis Workspace的異常偵測演演算法包括

* 除了現有的每日詳細程度，另支援對每小時、每週和每月的詳細程度。
* 注意季節性（例如「黑色星期五」）和假日。
