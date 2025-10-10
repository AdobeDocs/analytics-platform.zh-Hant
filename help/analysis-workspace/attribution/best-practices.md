---
title: 歸因最佳實務
description: 瞭解最佳實務，以決定要使用的歸因模型。
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 1b6e1d432bfe4b0574b8ee68bcfa940941f3c36f
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 66%

---

# 歸因最佳做法

為您的組織選擇正確的歸因模型取決於許多考量因素。 本文章探索方法及部分最佳實務：

* [探索性分析](#exploratory-analysis)
* [規則型歸因](#rule-base-attribution)
* [使用演演算法歸因](#use-algorithmic-attribution)

## 探索性分析

>[!NOTE]
>選擇歸因模型前，必須進行此分析。

此階段包括在最初了解客戶行為，並定義轉換量度。 根據轉換量度，類似[資料摘要](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/analytics-data-feed/data-feed-overview) (適用於原始資料) 或 Analysis Workspace 等工具有助於您了解

* 轉換前接觸過不同行銷管道的客戶數量
* 這些行為的比例/分佈

例如，如果 50% 的客戶在轉換前接觸 3 個管道，那麼在這 3 個管道中是否有任何互動？
您應該進行上層與下層漏斗分析，以擴大您的理解。

### 上層漏斗分析

上層漏斗分析管道用於建立品牌或產品知名度。例如，大多數電視廣告的目標是品牌知名度。 您可能會使用[時間衰減歸因模型](/help/analysis-workspace/attribution/models.md)，因為人們會隨著時間逐漸淡忘電視廣告。

### 下層漏斗分析

在下層漏斗分析中，假設人們已經知道您的品牌且您想要轉換。使用電子郵件、推播通知或 Facebook 廣告。

## 以規則為基礎的歸因

此步驟的目的是驗證您的假設。

**範例 1**

假設您的假設為：「*我的首次接觸管道對轉換的影響比上次接觸管道大。*」

在這種情況下，您會使用[反向J形歸因模型](/help/analysis-workspace/attribution/models.md)來測試此假設。 此模型將 60% 的功勞歸於首次接觸點。

**範例 2**

假設您的假設為： *&quot;在特定產業（例如旅遊業），歸因時段為60或90天，而不是30天，因為客戶在購買產品之前會深入研究一番。*&quot;

在這種情況下，您可能會將[回顧期間](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/attribution/models)改成 90 天。

## 使用演演算法歸因

如果您還沒有可以為您的所有問題提供滿意答案的歸因模型，您可以使用[演算法歸因](/help/analysis-workspace/attribution/algorithmic.md)。由於很難驗證大量可能的假設及各種組合，演算法歸因使用內建演算法跨維度項目分配信用。

## 其他考量

* 您可能需要使用資料科學家的服務，而非僅仰賴 Analysis Workspace。
* 您可以仰賴原始資料，就像在 Adobe 資料摘要中一樣。
* 例如，如果您想要考量您的曝光數資料，可考慮使用[Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview)。
