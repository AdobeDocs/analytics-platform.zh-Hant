---
title: 歸因最佳實務
description: 決定歸因模型有何最佳實務？
source-git-commit: 0e0d77425edeceb3ede6d2d7ca81846b30179607
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---


# 歸因最佳實務

為貴組織挑選合適的歸因模型取決於多項考量事項。 本文探討方法及一些一般最佳實務。

## 步驟1:探索分析

>[!NOTE]
>您必須先進行此分析，才能挑選歸因模型。

此階段最初包括了解客戶行為並定義轉換量度。 根據轉換量度，Analysis Workspace等工具以及從多個管道提取資料來源（例如曝光數資料），可協助您了解

* 轉換前，有多少客戶接觸到不同的行銷管道？
* 這些行為的比例/分佈。

例如，如果有50%的客戶在轉換前接觸了3個管道，這3個管道之間是否有任何互動？
接著，您可以進行漏斗上下兩個分析，以擴大您的了解。

### 漏斗上部分析

漏斗上方分析會分析用來建立品牌或產品認知度的管道。 例如，大部分電視廣告的目標都是品牌認知度。 您可能會使用[&quot;時間耗損&quot;歸因模型](/help/analysis-workspace/attribution/models.md)，因為人們會隨著時間而忘記您的電視廣告。

### 漏斗下部分析

在這個分析中，假設人們已經知道您的品牌，而您希望他們改變。 使用電子郵件、推播通知或Facebook廣告。

## 步驟2:規則基礎歸因

此步驟的目的是驗證您的假設。

**範例 1**

假設您的假設是「我的首次接觸管道對我的轉換影響比上次接觸管道大。 然後，您可以使用[「反向J形」歸因模型](/help/analysis-workspace/attribution/models.md)來測試此假設。 此模型會將60%的評分給予首次接觸點。

**範例 2**

您的假設可能是：「在我們的行業（如旅行業），歸因期限是60天或90天，而不是30天，因為客戶在購買產品之前會做很多研究。 然後您會將[回顧期間](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows)變更為90天。

## 步驟3:使用演算法歸因

由於很難驗證大量可能的假設和組合，因此您可以使用[演算法歸因](/help/analysis-workspace/attribution/algorithmic.md)，將這項工作留給內建演算法處理。 如果您已找到可回答所有問題且完全適合的完美歸因模型，那麼您顯然不需要採取此步驟。

## 其他考量

* 您可能需要使用資料科學家的服務，而不是只依賴Analysis Workspace。
