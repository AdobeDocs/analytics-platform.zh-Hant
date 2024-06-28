---
title: Adobe Customer Journey Analytics中的Target報表
description: 將Adobe Target與Customer Journey Analytics整合
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: b189776de8cadae3a93c717b6814f2130ab1be43
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 40%

---

# Adobe Customer Journey Analytics中的Target報表

Customer Journey Analytics中的Target報表功能可讓您直接在Customer Journey Analytics中測量及報告Adobe Target活動。 此功能相當於Adobe Analytics (AA)中透過Analytics for Target (A4T)所執行的工作，但與Adobe Experience Platform (AEP)連線。

將Target分類查詢資料集(預設可在Experience Platform中使用)新增到Customer Journey Analytics連線中，使用者現在可以適當存取Target報告工具、Target訂單歸因和其他功能。 只需在Customer Journey Analytics資料檢視中進行一些細微的準備和調整，任何想要將Target資料直接傳送到CJA的使用者都可以立即使用這些活動。

## 主要優點

* 行銷人員可隨時動態地將 Customer Journey Analytics 成功量度套用至 Target 活動報表。執行活動之前完全不需要指定。
* 行銷人員可以利用 Customer Journey Analytics 功能 (例如實驗面板) 來進一步分析其網站個人化。
* 行銷人員可以擁有 Adobe Journey Optimizer 和 Target 的單一報告來源。兩種個人化產品都可以連接到 Customer Journey Analytics，就能更全面地了解您的網頁個人化。

## 附註和考量事項

目標分類事件資料集新增到CJA連線後，在CJA資料檢視中這些元件新增為維度後，有一些要做的細微調整，包括：

* 設定持續性，使其類似於Target中的追蹤方式（請洽詢Target顧問或客戶以確保設定正確）。

* 將持續性設定為ALL，以便同時追蹤多個Target活動且不會被未來或先前的活動覆寫。

## 更多詳細資訊

請參閱 Target 文件中的 [Adobe Customer Journey Analytics 的 Target 報告](https://experienceleague.adobe.com/tw/docs/target/using/integrate/cja/target-reporting-in-cja)，了解更多資訊。

請參閱[實驗面板](../analysis-workspace/c-panels/experimentation.md)，深入了解分析師如何比較不同的使用者體驗、行銷或傳送訊息變化等資訊，確定哪一個產生特定結果的績效最好。您可以透過任何實驗平台 (線上、離線、Target 或 Journey Optimizer 等 Adobe 解決方案，甚至 BYO (自備) 資料) 評估任何 A/B 實驗的提升度和信賴度。
