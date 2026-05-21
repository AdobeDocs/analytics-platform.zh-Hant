---
title: 使用個人化物件以便與 Adobe Journey Optimizer 搭配使用
description: 了解如何使用個人化物件以便與 Adobe Journey Optimizer 搭配使用
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5086ac6e-5bee-4f0f-b7e5-a3d9bd8a1332
autotag-review: '2026-05-19T08:15:27.160Z'
TQID: 'https://experienceleague.adobe.com/5XSv4yQAi5iaQp35AzS7sLNoH40-DFilzZheETca5MQ'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 100%

---

# 使用個人化物件以便與 Adobe Journey Optimizer 搭配使用 {#upgrade-personalization}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-personalization"
>title="使用個人化物件來執行 Adobe Journey Optimizer"
>abstract="個人化最佳化會利用監督機器學習和深度學習領域的先進技術，讓商業使用者 (行銷人員) 定義業務目標，並利用他們的客戶資料來訓練商業導向的模型，以提供個人化產品建議並將 KPI 最大化。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

個人化最佳化會利用監督機器學習和深度學習領域的先進技術，讓商業使用者 (行銷人員) 定義業務目標，並利用他們的客戶資料來訓練商業導向的模型，以提供個人化產品建議並將 KPI 最大化。

1. 請依照以下 Journey Optimizer 指南中的[個人化最佳化模型](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/decisioning/offer-decisioning/rankings/ai-models/personalized-optimization-model)資訊。

{{upgrade-final-step}}

<!--

The result of the personalization object ends up in a dataset. The result of experimentation. When a customer has used AA with Target, that ends up in a complete different space than when they're migrating to CJA and they're going to use CJA with Adobe Target. 

Target was the old way of setting up an A/B test or experimentation. Then ensuring the results of those tests in Target ended up in AA for reporting. Now if you're using Target, instead of saying that you want the data in Target, you can now select CJA as your reporting source for an Adobe Target activity. So if a customer is doing this in AA and they want to move to CJA, ...

If a customer has AJO, and is using Offers in AJO, then they can set up offers, and that also creates datasets in Platform... But that's not relevant with upgrade, exactly.



Questions we need to answer:

1. How do we determine the personalization criteria (Red for user A and blue for User B)

1. What do we implement on the site to determine the red / blue object?


2 ways we can do it:

Manually rendering content or Automatically rendering content. 


## Manual implementation of the Web SDK


## Mobile SDK implementation 





## Tags

-->
