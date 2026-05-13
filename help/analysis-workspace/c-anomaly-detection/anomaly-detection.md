---
description: 了解 Analysis Workspace 中的資料異常偵測。
title: 異常偵測概觀
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
TQID: https://experienceleague.adobe.com/beFLMQfzXJUoCbg6fSLpFqcbaB7GSuo6SHroSS6V5wI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: aff2ef09-fc60-4018-9197-e2befd623064
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 83%

---

# 異常偵測概觀

您可以在 Analysis Workspace 內依內容檢視和分析資料異常的情況。

[異常偵測教學影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) (4:53)

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測讓您能夠將「真實信號」與「噪音」區分開來，並進一步找出可能對這些信號或異常產生影響的因素。 換句話說，它可讓您識別哪些統計波動重要，哪些不重要。 接著，您就可以找出真正異常的根本原因。 此外，您還可以獲得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 平均訂購值的劇烈下降
* 訂單激增但低收入
* 試用版註冊數量激增或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件激增
* 低影片位元速率激增

Analysis Workspace 的異常偵測演算法包括

* 除了現有的每日顆粒度，另支援對每小時、每週和每月的顆粒度。
* 意識到季節性 (如「黑色星期五」) 和假期的情形。
