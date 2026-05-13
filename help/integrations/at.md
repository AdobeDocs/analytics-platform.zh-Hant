---
title: Target報告
description: 將Adobe Target與Customer Journey Analytics整合
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# Target報告

Customer Journey Analytics中的Target報告功能可讓您直接在Customer Journey Analytics中測量及報告Adobe Target活動。 此功能可與透過Analytics for Adobe Analytics (A4T)在Analytics (AA)中執行的功能比較，但可連線至Adobe Experience Platform (AEP)。

將Target分類查詢資料集（預設可在Experience Platform中使用）新增至Customer Journey Analytics連線後，使用者現在可以適當存取Target報告工具、Target訂單歸因和其他功能。 只要在Customer Journey Analytics資料檢視中進行一些細微的準備和調整，任何想要將Target資料直接傳送到CJA的使用者都可以立即使用這些活動。

## 主要優點

* 行銷人員可隨時動態地將 Customer Journey Analytics 成功量度套用至 Target 活動報表。 執行活動之前完全不需要指定。
* 行銷人員可以利用 Customer Journey Analytics 功能 (例如實驗面板) 來進一步分析其網站個人化。
* 行銷人員可以擁有 Adobe Journey Optimizer 和 Target 的單一報告來源。 兩種個人化產品都可以連接到 Customer Journey Analytics，就能更全面地了解您的網頁個人化。

## 附註和考量事項

您的Target活動必須[使用Customer Journey Analytics作為報表來源](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/cja/target-reporting-in-cja)。

將「目標分類事件資料集」新增至連線後，當這些元件新增為維度時，資料檢視中將會進行一些微幅調整，包括：

* 設定持續性，使其類似於Target中的追蹤方式（請洽詢Target顧問或客戶以確保設定正確）。

* 將持續性設定為ALL，以便同時追蹤多個Target活動且不會被未來或先前的活動覆寫。

## 更多詳細資訊

請參閱 Target 文件中的 [Adobe Customer Journey Analytics 的 Target 報告](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/cja/target-reporting-in-cja)，了解更多資訊。

請參閱[實驗面板](../analysis-workspace/c-panels/experimentation.md)，深入了解分析師如何比較不同的使用者體驗、行銷或傳送訊息變化等資訊，確定哪一個產生特定結果的績效最好。 您可以透過任何實驗平台 (線上、離線、Target 或 Journey Optimizer 等 Adobe 解決方案，甚至 BYO (自備) 資料) 評估任何 A/B 實驗的提升度和信賴度。
