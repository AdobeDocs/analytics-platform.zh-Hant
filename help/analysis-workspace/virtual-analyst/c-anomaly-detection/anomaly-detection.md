---
description: 您可以在 Analysis Workspace 中根據內容檢視和分析資料異常。
title: 異常偵測概述
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 96%

---


# 異常偵測概述

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

您可以根據 Analysis Workspace 中的內容檢視和分析資料異常。

[在 YouTube 觀看「異常偵測」](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)(4:53)

「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。

異常偵測可讓您區隔「真實訊號」與「雜訊」，接著找出形成這些訊號或異常情形的可能因素。換句話說，可讓您識別哪些統計波動是重要的、哪些不重要。接著您可以找出真正異常的根本原因。此外，您還可以取得可靠的量度 (KPI) 預測。

您可能會調查的異常例子包括：

* 訂單平均值大幅下降
* 低收入訂單發生尖峰
* 試用版註冊發生尖峰或下降
* 登陸頁面檢視次數下降
* 影片緩衝事件的尖峰
* 低影片位元率的尖峰

異常偵測和[貢獻分析](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)是 Analysis Workspace 的核心工作流程。您可以對任何每日異常情形執行貢獻分析，並將結果內嵌至 Analysis Workspace 專案。

>[!IMPORTANT]
>
>「客戶歷程分析」尚未提供「貢獻分析」。

Analysis Workspace 異常偵測的演算法包含

* 除了現有的每日粒度，另支援對每小時、每週和每月的粒度。
* 感知季節性 (例如「黑色星期五」) 和假日。

## 關閉異常偵測

前往欄設定並取消勾選&#x200B;**[!UICONTROL 「異常」]**，即可關閉欄層級的異常偵測。

![](assets/turnoff_anomalies.png)
