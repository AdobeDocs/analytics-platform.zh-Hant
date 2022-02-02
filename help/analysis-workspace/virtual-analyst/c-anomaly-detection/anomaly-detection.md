---
description: 您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。
title: 異常偵測概述
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 100%

---

# 異常偵測概觀

您可以根據 Analysis Workspace 中的內容檢視和分析資料異常。

[「異常偵測」教學影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=zh-Hant) (4:53)

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測可讓您區隔「真實訊號」與「雜訊」，接著找出形成這些訊號或異常情形的可能因素。換句話說，可讓您識別哪些統計波動是重要的、哪些不重要。接著您可以找出真正異常的根本原因。此外，您還可以取得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 訂單平均值大幅下降
* 低收入訂單發生尖峰
* 試用版註冊發生尖峰或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件的尖峰
* 低影片位元率的尖峰

Analysis Workspace 異常偵測的演算法包含

* 除了現有的每日詳細程度，另支援對每小時、每週和每月的詳細程度。
* 感知季節性 (例如「黑色星期五」) 和假日。
