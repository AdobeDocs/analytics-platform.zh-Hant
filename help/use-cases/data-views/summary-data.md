---
title: 在Customer Journey Analytics中使用摘要資料
description: 說明如何將摘要資料帶入Customer Journey Analytics之所有詳細資訊的使用案例
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 80139806-618a-46ff-b2c4-32d7bb85a526
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '5021'
ht-degree: 15%

---

# 使用摘要資料

此使用案例有助於您瞭解如何在報告和分析中使用摘要資料。 使用案例詳細說明在Customer Journey Analytics中使用摘要資料所需的所有步驟：

- 在Experience Platform中[擷取](#ingest)摘要資料和其他資料來源。
- 設定摘要資料和其他資料來源的[連線](#connection)。
- 設定您的[資料檢視](#data-view)以合併您的資料來源。
- 在[Workspace](#workspace)中針對您的合併資料製作報表和分析。

使用案例提供摘要資料、事件資料和查詢資料的範例資料。 所有資料都包含隨機值。

## 擷取

您會針對此使用案例使用下列範例摘要資料，顯示在Facebook上執行行銷活動的摘要資料。

+++摘要資料

| _id | campaign_name | 成本 | 印象 | campaign_id | network | ad_group | timestamp |
|---|---|---:|---:|---|---|---|---|
| 1 | 123行銷活動 | 100 | 5000 | abc123 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 2 | 123行銷活動 | 50 | 4000 | def123 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 3 | 123行銷活動 | 125 | 6000 | ghi123 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 4 | 456行銷活動 | 25 | 2500 | abc456 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 5 | 456行銷活動 | 10 | 1000 | def456 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 6 | 456行銷活動 | 115 | 5500 | ghi456 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 7 | 789行銷活動 | 200 | 9000 | abc789 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 8 | 789行銷活動 | 20 | 2000 | def789 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 9 | 789行銷活動 | 225 | 12000 | ghi789 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 10 | 987行銷活動 | 125 | 10000 | abc987 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 11 | 987行銷活動 | 120 | 15000 | def987 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 12 | 987行銷活動 | 315 | 22500 | ghi987 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 13 | 654行銷活動 | 325 | 20000 | abc654 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 14 | 654行銷活動 | 320 | 25000 | def654 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 15 | 654行銷活動 | 315 | 22500 | ghi654 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |
| 16 | 321行銷活動 | 25 | 2000 | abc321 | facebook | abc-adgroup | 2024-07-18T18:20:39.000Z |
| 17 | 321行銷活動 | 20 | 2500 | def321 | facebook | def-adgroup | 2024-07-18T18:20:39.000Z |
| 18 | 321行銷活動 | 15 | 2250 | ghi321 | facebook | ghi-adgroup | 2024-07-18T18:20:39.000Z |

[！[資料下載](/help/assets/icons/DataDownload.svg)](./assets/summary-data.csv)

+++

若要在Customer Journey Analytics、報表中或在Workspace分析資料時使用「摘要」資料，您需要

- Experience Platform中的摘要結構，
- Experience Platform中的摘要資料集，
- Customer Journey Analytics中的連線已設定為使用摘要資料集，
- Customer Journey Analytics中的資料檢視，並已正確設定摘要資料的量度和維度。

您可以將此摘要資料與事件資料的資料集和查詢資料的資料集搭配使用。

+++事件資料

事件資料可在範例事件資料集中使用。 範例資料如下所示：

| timestamp | _id | page_name | person_id | tracking_code | 訂單 | revenue_amont |
|---|---:|---|---|---|---:|---:|
| 2024-07-18T19:15:39+00:00 | 1 | 首頁 | person-1abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 2 | 確認頁面 | person-1abc123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 3 | 首頁 | person-2def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 4 | 首頁 | person-3ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 5 | 確認頁面 | person-3ghi123 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 6 | 首頁 | person-4abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 7 | 首頁 | person-5def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 8 | 首頁 | person-6ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 9 | 確認頁面 | person-6ghi456 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 10 | 首頁 | person-7abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 11 | 首頁 | person-8def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 12 | 首頁 | person-9ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 13 | 確認頁面 | person-9ghi789 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 14 | 首頁 | person-10abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 15 | 首頁 | person-11def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 16 | 首頁 | person-12ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 17 | 首頁 | person-13abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 18 | 首頁 | person-14def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 19 | 首頁 | person-15ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 20 | 確認頁面 | person-15ghi654 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 21 | 首頁 | person-16abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 22 | 首頁 | person-17def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 23 | 首頁 | person-18ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 24 | 首頁 | person-19abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 25 | 首頁 | person-20def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 26 | 首頁 | person-21ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 27 | 確認頁面 | person-21ghi123 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 28 | 首頁 | person-22abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 29 | 首頁 | person-23def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 30 | 首頁 | person-24ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 31 | 首頁 | person-25abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 32 | 確認頁面 | person-25abc789 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 33 | 首頁 | person-26abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 34 | 首頁 | person-27def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 35 | 首頁 | person-28ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 36 | 首頁 | person-29abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 37 | 確認頁面 | person-29abc654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 38 | 首頁 | person-30def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 39 | 首頁 | person-31ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 40 | 首頁 | person-32abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 41 | 首頁 | person-33ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 42 | 確認頁面 | person-33ghi456 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 43 | 首頁 | person-34abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 44 | 首頁 | person-35def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 45 | 首頁 | person-36ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 46 | 確認頁面 | person-36ghi789 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 47 | 首頁 | person-37abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 48 | 首頁 | person-38def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 49 | 首頁 | person-39ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 50 | 首頁 | person-40abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 51 | 確認頁面 | person-40abc654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 52 | 首頁 | person-41def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 53 | 首頁 | person-42ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 54 | 首頁 | person-43abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 55 | 首頁 | person-44def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 56 | 首頁 | person-45ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 57 | 首頁 | person-46abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 58 | 確認頁面 | person-46abc123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 59 | 首頁 | person-47def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 60 | 首頁 | person-48ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 61 | 首頁 | person-49abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 62 | 首頁 | person-50def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 63 | 首頁 | person-51ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 64 | 首頁 | person-52abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 65 | 確認頁面 | person-52abc789 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 66 | 首頁 | person-53abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 67 | 首頁 | person-54def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 68 | 首頁 | person-55ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 69 | 確認頁面 | person-55ghi987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 70 | 首頁 | person-56abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 71 | 首頁 | person-57def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 72 | 確認頁面 | person-57def123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 73 | 首頁 | person-58ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 74 | 首頁 | person-59abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 75 | 確認頁面 | person-59abc456 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 76 | 首頁 | person-60def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 77 | 首頁 | person-61ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 78 | 首頁 | person-62abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 79 | 確認頁面 | person-62abc789 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 80 | 首頁 | person-63def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 81 | 首頁 | person-64ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 82 | 首頁 | person-65abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 83 | 確認頁面 | person-65abc987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 84 | 首頁 | person-66def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 85 | 首頁 | person-67ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 86 | 首頁 | person-68abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 87 | 首頁 | person-69def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 88 | 首頁 | person-70ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 89 | 首頁 | person-71abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 90 | 確認頁面 | person-71abc321 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 91 | 首頁 | person-72def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 92 | 首頁 | person-73ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 93 | 首頁 | person-74abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 94 | 首頁 | person-75def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 95 | 首頁 | person-76ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 96 | 首頁 | person-77abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 97 | 確認頁面 | person-77abc456 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 98 | 首頁 | person-78def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 99 | 首頁 | person-79ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 100 | 首頁 | person-80abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 101 | 首頁 | person-81abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 102 | 確認頁面 | person-81abc987 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 103 | 首頁 | person-82def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 104 | 首頁 | person-83ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 105 | 首頁 | person-84abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 106 | 首頁 | person-85def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 107 | 確認頁面 | person-85def654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 108 | 首頁 | person-86ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 109 | 首頁 | person-87abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 110 | 首頁 | person-88ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 111 | 首頁 | person-89abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 112 | 確認頁面 | person-89abc789 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 113 | 首頁 | person-90def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 114 | 首頁 | person-91ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 115 | 首頁 | person-92abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 116 | 確認頁面 | person-92abc987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 117 | 首頁 | person-93def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 118 | 首頁 | person-94ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 119 | 首頁 | person-95abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 120 | 首頁 | person-96def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 121 | 確認頁面 | person-96def654 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 122 | 首頁 | person-97ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 123 | 首頁 | person-98abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 124 | 首頁 | person-99def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 125 | 首頁 | person-100ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 126 | 首頁 | person-101abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 127 | 首頁 | person-102def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 128 | 確認頁面 | person-102def123 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 129 | 首頁 | person-103ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 130 | 首頁 | person-104abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 131 | 首頁 | person-105def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 132 | 首頁 | person-106ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 133 | 首頁 | person-107abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 134 | 首頁 | person-108abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 135 | 確認頁面 | person-108abc987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 136 | 首頁 | person-109def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 137 | 首頁 | person-110ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 138 | 確認頁面 | person-110ghi987 |  |  |  |
| 2024-07-18T19:15:39+00:00 | 139 | 首頁 | person-111def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 140 | 首頁 | person-112def987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 141 | 確認頁面 | person-112def987 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 142 | 首頁 | person-113ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 143 | 首頁 | person-114abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 144 | 首頁 | person-115def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 145 | 確認頁面 | person-115def654 |  | 1 | 159.25 |
| 2024-07-18T19:15:39+00:00 | 146 | 首頁 | person-116ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 147 | 首頁 | person-117abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 148 | 首頁 | person-118def321 | def321 |  |  |
| 2024-07-18T19:15:39+00:00 | 149 | 確認頁面 | person-118def321 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 150 | 首頁 | person-119ghi321 | ghi321 |  |  |
| 2024-07-18T19:15:39+00:00 | 151 | 首頁 | person-120abc123 | abc123 |  |  |
| 2024-07-18T19:15:39+00:00 | 152 | 首頁 | person-121def123 | def123 |  |  |
| 2024-07-18T19:15:39+00:00 | 153 | 首頁 | person-122ghi123 | ghi123 |  |  |
| 2024-07-18T19:15:39+00:00 | 154 | 首頁 | person-123abc456 | abc456 |  |  |
| 2024-07-18T19:15:39+00:00 | 155 | 首頁 | person-124def456 | def456 |  |  |
| 2024-07-18T19:15:39+00:00 | 156 | 確認頁面 | person-124def456 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 157 | 首頁 | person-125ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 158 | 首頁 | person-126abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 159 | 首頁 | person-127abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 160 | 首頁 | person-128def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 161 | 首頁 | person-129ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 162 | 首頁 | person-130abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 163 | 確認頁面 | person-130abc654 |  | 1 | 149.25 |
| 2024-07-18T19:15:39+00:00 | 164 | 首頁 | person-131def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 165 | 首頁 | person-132ghi654 | ghi654 |  |  |
| 2024-07-18T19:15:39+00:00 | 166 | 首頁 | person-133abc321 | abc321 |  |  |
| 2024-07-18T19:15:39+00:00 | 167 | 首頁 | person-134ghi456 | ghi456 |  |  |
| 2024-07-18T19:15:39+00:00 | 168 | 確認頁面 | person-134ghi456 |  | 1 | 139.25 |
| 2024-07-18T19:15:39+00:00 | 169 | 首頁 | person-135abc789 | abc789 |  |  |
| 2024-07-18T19:15:39+00:00 | 170 | 首頁 | person-136def789 | def789 |  |  |
| 2024-07-18T19:15:39+00:00 | 171 | 首頁 | person-137ghi789 | ghi789 |  |  |
| 2024-07-18T19:15:39+00:00 | 172 | 首頁 | person-138abc987 | abc987 |  |  |
| 2024-07-18T19:15:39+00:00 | 173 | 確認頁面 | person-138abc987 |  | 1 | 124.25 |
| 2024-07-18T19:15:39+00:00 | 174 | 首頁 | person-139def987 | def987 |  |  |
| 2024-07-18T19:15:39+00:00 | 175 | 首頁 | person-140ghi987 | ghi987 |  |  |
| 2024-07-18T19:15:39+00:00 | 176 | 首頁 | person-141abc654 | abc654 |  |  |
| 2024-07-18T19:15:39+00:00 | 177 | 首頁 | person-142def654 | def654 |  |  |
| 2024-07-18T19:15:39+00:00 | 178 | 確認頁面 | person-142def654 |  | 1 | 174.25 |
| 2024-07-18T19:15:39+00:00 | 179 | 首頁 | person-143ghi654 | ghi654 |  |  |

[！[資料下載](/help/assets/icons/DataDownload.svg)](./assets/event-data.csv)

+++

+++ 查詢資料

查詢資料可在範例查詢資料集中使用。 範例資料如下所示：

| _id | tracking_code | ad_group | campaign_name |
|---|---|---|---|
| 1 | abc123 | abc-adgroup | 123行銷活動 |
| 2 | def123 | def-adgroup | 123行銷活動 |
| 3 | ghi123 | ghi-adgroup | 123行銷活動 |
| 4 | abc456 | abc-adgroup | 456行銷活動 |
| 5 | def456 | def-adgroup | 456行銷活動 |
| 6 | ghi456 | ghi-adgroup | 456行銷活動 |
| 7 | abc789 | abc-adgroup | 789行銷活動 |
| 8 | def789 | def-adgroup | 789行銷活動 |
| 9 | ghi789 | ghi-adgroup | 789行銷活動 |
| 10 | abc987 | abc-adgroup | 987行銷活動 |
| 11 | def987 | def-adgroup | 987行銷活動 |
| 12 | ghi987 | ghi-adgroup | 987行銷活動 |
| 13 | abc654 | abc-adgroup | 654行銷活動 |
| 14 | def654 | def-adgroup | 654行銷活動 |
| 15 | ghi654 | ghi-adgroup | 654行銷活動 |
| 16 | abc321 | abc-adgroup | 321行銷活動 |
| 17 | def321 | def-adgroup | 321行銷活動 |
| 18 | ghi321 | ghi-adgroup | 321行銷活動 |

[！[資料下載](/help/assets/icons/DataDownload.svg)](./assets/lookup-data.csv)
+++

>[!INFO]
>
>未提供為事件和查詢資料設定結構描述和資料集的更多詳細資料。 此設定假定為常識，並遵循與查詢資料相同的步驟。
>


### 摘要結構描述

摘要資料需要Experience Platform中的摘要結構。 摘要結構描述是以XDM摘要量度作為基底類別的結構描述。

若要在Experience Platform中建立摘要結構：

1. 選取&#x200B;**[!UICONTROL Experience Platform]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 從左側邊欄選取&#x200B;**[!UICONTROL 結構描述]**。
1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 建立結構描述]**。
1. 在&#x200B;**[!UICONTROL 建立結構描述]**&#x200B;對話方塊中選取&#x200B;**[!UICONTROL 手動]**。 然後使用&#x200B;**[!UICONTROL 選取]**&#x200B;以繼續。
1. 在&#x200B;**[!UICONTROL 結構描述]** > **[!UICONTROL 建立結構描述]**&#x200B;精靈的&#x200B;**[!UICONTROL 選取類別]**&#x200B;步驟中，從&#x200B;**[!UICONTROL 選取此結構描述的基類別]**&#x200B;選項中選取&#x200B;**[!UICONTROL 其他]**。
1. 從清單中選取&#x200B;**[!UICONTROL XDM摘要量度]** （或使用![搜尋](/help/assets/icons/Search.svg)欄位來搜尋），然後選取&#x200B;**[!UICONTROL 下一步]**。
1. 在&#x200B;**[!UICONTROL 結構描述]** > **[!UICONTROL 建立結構描述]**&#x200B;精靈的&#x200B;**[!UICONTROL 名稱和檢閱]**&#x200B;步驟中，輸入&#x200B;**[!UICONTROL 結構描述顯示名稱]**，例如`Example Summary Data Schema`和選用的說明。 選取&#x200B;**[!UICONTROL 完成]**&#x200B;以完成此步驟。

系統會顯示基本摘要綱要的結構，並準備好使用摘要資料的欄位來擴充結構。 您可以使用欄位群組將欄位新增到結構描述。

新增包含範例資料欄位的欄位群組：

1. 選取![欄位群組](/help/assets/icons/AddCircle.svg)中的&#x200B;**[!UICONTROL AddCircle]** **[!UICONTROL Add]**。
1. 在&#x200B;**[!UICONTROL 新增欄位群組]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 建立新欄位群組]**。
1. 輸入欄位群組的&#x200B;**[!UICONTROL 顯示名稱]**，例如`Example Summary Data`。 選擇性地提供說明。
1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。
1. 回到架構結構使用者介面。 在&#x200B;**[!UICONTROL 欄位群組]**&#x200B;中選取新的&#x200B;**[!UICONTROL 範例摘要資料]**。
1. 選取結構描述名稱![範例摘要資料結構描述](/help/assets/icons/AddCircle.svg)旁的&#x200B;**[!UICONTROL AddCircle]**。 會開啟&#x200B;**[!UICONTROL 欄位屬性]**&#x200B;面板，讓您新增欄位的詳細資料。
   1. 輸入&#x200B;**[!UICONTROL 欄位名稱]**： `campaign_id`
   1. 輸入&#x200B;**[!UICONTROL 顯示名稱]**： `campaign_id`
   1. 從&#x200B;**[!UICONTROL 選取資料型別]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 型別]**： **[!UICONTROL 字串]**
   1. 確定已選取&#x200B;**[!UICONTROL 指派給]** **[!UICONTROL 欄位群組]**，並從下拉式選單中選取&#x200B;**[!UICONTROL 範例摘要資料]**。
   1. 向下捲動至底部，並選取&#x200B;**[!UICONTROL 套用]**。
1. 對摘要資料的其他欄位重複上一步驟。 如需正確值，請參閱下表。

   | 欄位名稱 | 顯示名稱 | 類型 | 欄位群組 |
   |---|---|---|---|
   | `ad_group` | `ad_group` | 字串 | 範例摘要資料 |
   | `campaign_name` | `campaign_name` | 字串 | 範例摘要資料 |
   | `cost` | `cost` | 雙精度浮點數 | 範例摘要資料 |
   | `impression` | `impression` | 整數 | 範例摘要資料 |
   | `network` | `network` | 字串 | 範例摘要資料 |

1. 若要將您的&#x200B;**[!UICONTROL 範例摘要資料]**&#x200B;欄位群組儲存為結構描述的一部分，請選取&#x200B;**[!UICONTROL 儲存]**。 成功儲存結構時，您會看到一則確認訊息。

您現在已定義結構，詳細說明摘要資料的模型。 類似於以下專案。

![範例摘要資料結構描述](../assets/example-summary-schema.png)





### 摘要資料集

若要將摘要資料儲存在Experience Platform中，您必須先建立資料集，然後將摘要資料上傳至資料集。

若要建立資料集：

1. 選取&#x200B;**[!UICONTROL Experience Platform]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 從左側邊欄選取&#x200B;**[!UICONTROL 資料集]**。
1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 建立資料集]**。
1. 在&#x200B;**[!UICONTROL 資料集]** > **[!UICONTROL 建立資料集]**&#x200B;畫面中，選取&#x200B;**[!UICONTROL 從結構描述建立資料集]**。
1. 在&#x200B;**[!UICONTROL 工作流程]** > **[!UICONTROL 從結構描述]**&#x200B;精靈建立資料集&#x200B;**[!UICONTROL 選取結構描述]**&#x200B;步驟中，![搜尋](/help/assets/icons/Search.svg)並選取您的&#x200B;**[!UICONTROL 範例摘要資料結構描述]**。
1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
1. 在&#x200B;**[!UICONTROL 工作流程]** > **[!UICONTROL 從結構描述建立資料集]**&#x200B;精靈的&#x200B;**[!UICONTROL 設定資料集]**&#x200B;步驟中：
   1. 輸入資料集的&#x200B;**[!UICONTROL 名稱]**，例如： `Example Summary Data Dataset`。 選擇性地提供說明。
   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

您會看到一個顯示新資料集詳細資訊的畫面。

若要將範例資料上傳至此資料集：

1. 選取&#x200B;**[!UICONTROL Experience Platform]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 從左側邊欄選取&#x200B;**[!UICONTROL 工作流程]**。
   1. 從&#x200B;**[!UICONTROL 工作流程]**&#x200B;畫面中的&#x200B;**[!UICONTROL 資料擷取]**&#x200B;選項中選取&#x200B;**[!UICONTROL 將CSV對應至XDM結構描述]**。
   1. 從&#x200B;**[!UICONTROL 將CSV對應至XDM結構描述]**&#x200B;面板中選取&#x200B;**[!UICONTROL 啟動]**。
1. 在&#x200B;**[!UICONTROL 工作流程]** > **[!UICONTROL 將CSV對應至XDM結構描述]**&#x200B;精靈的&#x200B;**[!UICONTROL 資料流詳細資料]**&#x200B;步驟中：
   1. 為&#x200B;**[!UICONTROL 目標資料集]**&#x200B;選取&#x200B;**[!UICONTROL 現有的資料集]**。
   1. 從下拉式功能表中選取&#x200B;**[!UICONTROL 範例摘要資料集]**。
   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
1. 在&#x200B;**[!UICONTROL 工作流程]** > **[!UICONTROL 將CSV對應至XDM結構描述]**&#x200B;精靈的&#x200B;**[!UICONTROL 選取資料]**&#x200B;步驟中：
   1. 將含有CSV格式摘要資料的檔案拖放到&#x200B;**[!UICONTROL 拖放檔案]**。 或者，使用&#x200B;**[!UICONTROL 選擇檔案]**&#x200B;來選取您的檔案。
   1. 請確定&#x200B;**[!UICONTROL 資料格式]**&#x200B;和&#x200B;**[!UICONTROL 分隔符號]**&#x200B;確實具有您範例資料的正確值。 例如，**[!UICONTROL 已分隔]**&#x200B;為&#x200B;**[!UICONTROL 資料格式]**，而&#x200B;**[!UICONTROL ，]**&#x200B;為&#x200B;**[!UICONTROL 分隔符號]**。
   1. 摘要資料的範例（10筆記錄）會顯示在&#x200B;**[!UICONTROL 範例資料]**&#x200B;中。
   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
1. 在&#x200B;**[!UICONTROL 工作流程]** > **[!UICONTROL 將CSV對應至XDM結構描述]**&#x200B;精靈的&#x200B;**[!UICONTROL 對應]**步驟中：
   ![範例資料集對應](../assets/example-dataset-mapping.png)
   1. 檢查&#x200B;**[!UICONTROL Source資料]**&#x200B;的所有資料欄位是否正確對應到結構描述中對應的&#x200B;**[!UICONTROL 目標欄位]**。 對於範例資料，不會報告錯誤，因為您明確命名了結構描述中的欄位，類似於範例資料中的欄位名稱。 否則，您可以使用此畫面來更正對應。
   1. 您可以選擇選取![齒輪](/help/assets/icons/Gear.svg) **[!UICONTROL 驗證]**&#x200B;以（再次）驗證資料。
   1. 您可以選擇選取![預覽](/help/assets/icons/Preview.svg) **[!UICONTROL 預覽資料]**&#x200B;以開啟對話方塊，在資料集載入資料後，預覽資料。
   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

在&#x200B;**[!UICONTROL 來源]** > **[!UICONTROL 資料流 — XX/XX/XXXX， XX:XX XX]**&#x200B;中，會顯示您上傳的狀態。 重新整理以檢視上傳的更新。 成功後，範例資料會載入到Experience Platform中。




## 連線

若要在Customer Journey Analytics中使用範例資料，請建立包含Experience Platform範例摘要資料集的連線。


1. 選取&#x200B;**[!UICONTROL Customer Journey Analytics]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 在頂端功能表中選取&#x200B;**[!UICONTROL 連線]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取「**[!UICONTROL 建立新連線]**」。
1. 在&#x200B;**[!UICONTROL 連線]** > **[!UICONTROL 未命名的連線]**&#x200B;中：
   1. 輸入&#x200B;**[!UICONTROL 連線名稱]**，例如`Example Connection Using Summary Data`。
   1. 從沙箱下拉式選單中選取沙箱，其中包含您建立的資料集和您要包含的其他資料集。
   1. 從&#x200B;**[!UICONTROL 每日事件平均數量]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 小於100萬]**。
   1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。
   1. 在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;精靈的&#x200B;**[!UICONTROL 選取資料集]**&#x200B;步驟中：
      1. 搜尋![搜尋](/help/assets/icons/Search.svg)並選取&#x200B;**[!UICONTROL 範例摘要資料集]**、**[!UICONTROL 範例事件資料集]**&#x200B;和&#x200B;**[!UICONTROL 範例查詢資料集]**。
      1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
   1. 在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;精靈的&#x200B;**[!UICONTROL 資料集設定]**&#x200B;步驟中：

      1. 對於&#x200B;**[!UICONTROL 範例事件資料集]**：

         1. 確認&#x200B;**[!UICONTROL 人員ID]** (`person_id`)和&#x200B;**[!UICONTROL 時間戳記]**&#x200B;的選取專案正確。
         1. 從&#x200B;**[!UICONTROL 資料來源型別]**&#x200B;選取&#x200B;**[!UICONTROL 網頁資料]**。
         1. 啟用&#x200B;**[!UICONTROL 匯入所有新資料]**。
         1. 啟用&#x200B;**[!UICONTROL 回填所有現有資料]**。

      1. 針對&#x200B;**[!UICONTROL 範例查詢資料集]**：

         1. 選取&#x200B;**[!UICONTROL tracking_code]**&#x200B;作為&#x200B;**[!UICONTROL Key]**，選取&#x200B;**[!UICONTROL tracking_code （事件資料集）]**&#x200B;作為&#x200B;**[!UICONTROL Matching]**&#x200B;索引鍵。
         1. 從&#x200B;**[!UICONTROL 資料來源型別]**&#x200B;選取&#x200B;**[!UICONTROL 網頁資料]**。
         1. 啟用&#x200B;**[!UICONTROL 匯入所有新資料]**。
         1. 啟用&#x200B;**[!UICONTROL 回填所有現有資料]**。

      1. 對於&#x200B;**[!UICONTROL 範例摘要資料集]**：

         1. 確認&#x200B;**[!UICONTROL 時間戳記]**&#x200B;和&#x200B;**[!UICONTROL 時區]**&#x200B;的選取專案正確。
         1. 啟用&#x200B;**[!UICONTROL 匯入所有新資料]**。
         1. 啟用&#x200B;**[!UICONTROL 回填所有現有資料]**。

      1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

1. 在&#x200B;**[!UICONTROL 連線]** > **[!UICONTROL 使用摘要資料的連線範例]**&#x200B;連線畫面中，選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存連線。

來自資料集的資料新增到Customer Journey Analytics，這可能需要幾個小時。 因此，在繼續之前，請耐心等待。

一段時間後，請確認資料集中的資料已正確載入Customer Journey Analytics。

1. 選取&#x200B;**[!UICONTROL Customer Journey Analytics]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 在頂端功能表中選取&#x200B;**[!UICONTROL 連線]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取您的連線，例如&#x200B;**[!UICONTROL 使用摘要資料的連線範例]**。
1. 在&#x200B;**[!UICONTROL 連線]** > **[!UICONTROL 使用摘要資料的範例連線]**&#x200B;詳細資料中選取適當的日期範圍。
   1. 選取![行事曆](/help/assets/icons/Calendar.svg)，然後選取&#x200B;**[!UICONTROL 最近7天]**。
   1. 選取&#x200B;**[!UICONTROL 「套用」]**。

在&#x200B;**[!UICONTROL 資料集]**&#x200B;的清單中，**[!UICONTROL 新增的記錄]**&#x200B;欄中的值應該會確認來自資料集的資料現在已成為Customer Journey Analytics的一部分。

![摘要資料的連線範例](../assets/example-connection-summary-data.png)

## 資料視圖

為確保您可以在Workspace中報告正確的資料，您想要建立包含相關量度和維度的資料檢視。

1. 選取&#x200B;**[!UICONTROL Customer Journey Analytics]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取&#x200B;**[!UICONTROL 「建立新的資料檢視」]**。
1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;中，瀏覽精靈畫面來設定您的資料檢視。
   1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;的&#x200B;**[!UICONTROL 設定]**&#x200B;步驟中：
      1. 從&#x200B;**[!UICONTROL 設定]**&#x200B;選取您的連線 | **[!UICONTROL 連線]**。 例如，**[!UICONTROL 使用摘要資料的連線範例]**。
      1. 輸入資料檢視的&#x200B;**[!UICONTROL 名稱]**，例如`Example Data View Using Summary Data`。
      1. 保留所有其他設定。
      1. 選取&#x200B;**[!UICONTROL 「儲存並繼續」]**。
   1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;的&#x200B;**[!UICONTROL 元件]**&#x200B;步驟中> **[!UICONTROL 使用摘要資料的範例資料檢視]**：
      1. 將下列元件新增至「維度和量度」清單。 請注意，為了清楚起見，元件名稱會從預設名稱修改而來，在元件面板（右側）的&#x200B;**[!UICONTROL 元件設定]**&#x200B;中使用&#x200B;**[!UICONTROL 元件名稱]**。

         **量度**

         | 元件名稱 | 資料集 | 結構描述資料類型 | 結構描述路徑 |
         |---|---|---|---|
         | 成本 | 範例摘要資料集 | 雙精度浮點數 | *_tenant*.cost |
         | 曝光數 | 範例摘要資料集 | 整數 | *_tenant*.impression |
         | 訂購 | 範例事件資料集 | 整數 | *_tenant*.orders |
         | 收入 | 範例事件資料集 | 雙精度浮點數 | *_tenant*.revenue_amount |

         **Dimensions**

         | 元件名稱 | 資料集 | 結構描述資料類型 | 結構描述路徑 |
         |---|---|---|---|
         | 廣告群組（查詢） | 範例查詢資料集 | 字串 | *_tenant*.ad_group |
         | 廣告群組（摘要） | 範例摘要資料集 | 字串 | *_tenant*.ad_group |
         | 行銷活動ID | 範例摘要資料集 | 字串 | *_tenant*.campaign_id |
         | 促銷活動名稱（查詢） | 範例查詢資料集 | 字串 | *_tenant*.campaign_name |
         | 行銷活動名稱（摘要） | 範例摘要資料集 | 字串 | *_tenant*.campaign_name |
         | 網路 | 範例摘要資料集 | 字串 | *_tenant*.network |
         | 頁面名稱 | 範例事件資料集 | 字串 | *_tenant*.page_name |
         | 人員 ID | 範例事件資料集 | 字串 | *_tenant*.person_id |
         | 追蹤程式碼（事件） | 範例事件資料集 | 字串 | *_tenant*.tracking_code |
         | 追蹤代碼（查詢） | 範例查詢資料集 | 字串 | *_tenant*.tracking_code |

      1. 在&#x200B;**[!UICONTROL 維度]**&#x200B;清單中選取&#x200B;**[!UICONTROL 追蹤代碼（事件）]**&#x200B;維度。 在元件面板中：

         ![追蹤程式碼摘要資料](../assets/tracking-code-summary-data.png)
         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要資料群組]**。
         1. 啟用「**[!UICONTROL 建立分組]**」。
         1. 從&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 促銷活動ID]**。 此步驟可確保正確組合事件資料和摘要資料以用於報告。
         1. 您可以選擇啟用&#x200B;**[!UICONTROL 隱藏報告]**。 [!UICONTROL 隱藏在報表中]可確保選取的維度（[!UICONTROL 促銷活動ID]）隱藏在Analysis Workspace和其他Customer Journey Analytics報表工具中。 如果已啟用此選項，您可以驗證選項：
            1. 在&#x200B;**[!UICONTROL 維度]**&#x200B;清單中選取&#x200B;**[!UICONTROL 促銷活動ID]**&#x200B;維度。
            1. 您注意到&#x200B;**[!UICONTROL 元件設定]**&#x200B;中的&#x200B;**[!UICONTROL 隱藏報表中的元件]**&#x200B;現在已自動啟用。

      1. 建立新的衍生欄位，例如`Campaign Name (Lookup Derived Field)`，以確保您可以使用範例查詢資料集中的促銷活動名稱（查詢）維度在Workspace中報告。

         行銷活動名稱![的](../aa-data/../assets/summary-derived-field.png)衍生欄位

         1. 選取&#x200B;**[!UICONTROL 值]**&#x200B;的&#x200B;**[!UICONTROL campaign_id]**。
         1. 從&#x200B;**[!UICONTROL 查詢資料集]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 範例查詢資料集]**。
         1. 從&#x200B;**[!UICONTROL 比對索引鍵]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL tracking_code]**。
         1. 從&#x200B;**[!UICONTROL 要傳回的值]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL campaign_name]**。
         1. 選取「**[!UICONTROL 儲存]**」。

      1. 將新建立的衍生欄位&#x200B;**[!UICONTROL 促銷活動名稱（查閱衍生欄位）]**&#x200B;新增至&#x200B;**[!UICONTROL 維度]**&#x200B;元件清單。

      1. 在&#x200B;**[!UICONTROL 維度]**&#x200B;清單中選取&#x200B;**[!UICONTROL 促銷活動名稱（查閱）]**&#x200B;維度。 在元件面板中：

         ![衍生欄位摘要資料群組](../assets/derived-field-summary-data-group.png)

         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要資料群組]**。
         1. 啟用「**[!UICONTROL 建立分組]**」。
         1. 從&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 促銷活動名稱（查詢衍生欄位）]**。 此步驟可確保範例查詢資料集中的行銷活動名稱（查詢）可安全地用於報告中(請參閱[Workspace](#workspace))。

      1. 從&#x200B;**[!UICONTROL 度量]**&#x200B;清單中選取&#x200B;**[!UICONTROL 收入]**&#x200B;度量。 在元件面板中：

         ![收入摘要資料](../assets/revenue-summary-data.png)
         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 歸因]**。
            1. 從![歸因模型](/help/assets/icons/AttributeLastTouch.svg)下拉式功能表中選取&#x200B;**[!UICONTROL AttributeLastTouch]** **[!UICONTROL 上次接觸]**。
            1. 從&#x200B;**[!UICONTROL 回顧視窗]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 30天]**。
         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **格式**。
            1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 貨幣]**。
            1. 從&#x200B;**[!UICONTROL 小數位數]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 2]**。

      1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;清單中選取&#x200B;**[!UICONTROL 訂單]**&#x200B;量度。 在元件面板中：

         ![訂單摘要資料](../assets/orders-summary-data.png)
         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 歸因]**。
            1. 從![歸因模型](/help/assets/icons/AttributeLastTouch.svg)下拉式功能表中選取&#x200B;**[!UICONTROL AttributeLastTouch]** **[!UICONTROL 上次接觸]**。
            1. 從&#x200B;**[!UICONTROL 回顧視窗]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 30天]**。
         1. 展開![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 格式]**。
            1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 十進位]**。
            1. 從&#x200B;**[!UICONTROL ▲將上升趨勢顯示為]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 良好（綠色）]**。

      1. 選取&#x200B;**[!UICONTROL 「儲存並繼續」]**。

   1. 在&#x200B;**[!UICONTROL 資料檢視]**&#x200B;的&#x200B;**[!UICONTROL 設定]**&#x200B;步驟中：
      1. 將所有設定保留為其預設值。
      1. 選取&#x200B;**[!UICONTROL 儲存並完成。]**

您現在已設定資料檢視，以正確報告摘要資料。


## Workspace

若要回報您的摘要資料，請在Analysis Workspace中建立新專案。

1. 選取&#x200B;**[!UICONTROL Customer Journey Analytics]**，從   ![應用程式](/help/assets/icons/Apps.svg)   應用程式切換器。
1. 從頂端功能表選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取&#x200B;**[!UICONTROL 「建立專案」]**。
1. 從包含建立空白Workspace專案的選項的對話方塊中選取&#x200B;**[!UICONTROL 空白Workspace專案]**。
1. 選取「**[!UICONTROL 建立]**」。

您看到包含[!UICONTROL 自由格式]面板的空白畫布，其中包含空白的[!UICONTROL 自由格式表格]。

1. 確保為面板選取的資料檢視是指包含摘要資料設定的資料檢視。 例如，**[!UICONTROL 使用摘要資料的資料檢視範例。]**
1. 請確認日期範圍對您要報告的資料有效。 例如： **[!UICONTROL 最近2個整月]**。
1. 從&#x200B;**[!UICONTROL 維度]**&#x200B;拖曳&#x200B;**[!UICONTROL 追蹤代碼（事件）]**，並將維度拖放到空的自由格式表格上。
1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳&#x200B;**[!UICONTROL 訂單]**，並將量度拖放至&#x200B;**[!UICONTROL 事件]**&#x200B;欄，以取代自由表格中的該欄。
1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳&#x200B;**[!UICONTROL 收入]**，並放置量度，以新增為自由表格的其他欄。
1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳&#x200B;**[!UICONTROL 曝光次數（摘要）]**，並放置量度，以新增為自由表格中的額外欄。
1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳&#x200B;**[!UICONTROL 成本（摘要）]**，並放置量度，以新增為自由表格中的額外欄。
1. 若要儲存您的專案，請選取&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 儲存]**，然後為您的專案提供名稱。 例如，`Example Project Using Summary Data`。

您想要使用報告摘要資料的強大功能，並報告每次曝光成本和廣告投資報酬率(ROAS)。 若要針對這些量度製作報表，您必須建立兩個計算量度。

1. 選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 計算量度]**。
1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;以新增新的計算量度。
   1. 指定`Cost per Impression`名稱&#x200B;**[!UICONTROL 的]**。
   1. 選取&#x200B;**[!UICONTROL 格式]**&#x200B;的&#x200B;**[!UICONTROL 貨幣]**。
   1. 指定`4`小數位數&#x200B;**[!UICONTROL 的]**。
   1. 使用![事件](/help/assets/icons/Event.svg) **[!UICONTROL 成本（摘要）]** **[!UICONTROL ÷]** **[!UICONTROL 曝光數（摘要）]**&#x200B;做為&#x200B;**[!UICONTROL 定義]**。
   1. 選取「**[!UICONTROL 儲存]**」。
1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Add]**&#x200B;以新增另一個新計算量度。
   1. 指定`Return on Ad Spend`名稱&#x200B;**[!UICONTROL 的]**。
   1. 選取&#x200B;**[!UICONTROL 格式]**&#x200B;的&#x200B;**[!UICONTROL 貨幣]**。
   1. 選取`2`小數位數&#x200B;**[!UICONTROL 的]**。
   1. 使用![事件](/help/assets/icons/Event.svg) **[!UICONTROL 收入（上次接觸） | 30天)]** **[!UICONTROL −]** ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 成本（摘要）]**&#x200B;為&#x200B;**[!UICONTROL 定義]**。
   1. 選取「**[!UICONTROL 儲存]**」。

將計算量度新增至報表。

1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳![每次曝光成本](/help/assets/icons/Calculator.svg) **[!UICONTROL 電腦]**，並放置量度以作為額外欄新增至自由表格。
   1. 選取![設定](/help/assets/icons/Setting.svg)資料行設定。
      1. 停用&#x200B;**[!UICONTROL 百分比]**。
1. 從&#x200B;**[!UICONTROL 量度]**&#x200B;拖曳![廣告支出回訪](/help/assets/icons/Calculator.svg) **[!UICONTROL 電腦]**，並放置量度以作為額外欄新增至自由表格。
   1. 選取![設定](/help/assets/icons/Setting.svg)資料行設定。
      1. 停用&#x200B;**[!UICONTROL 百分比]**。
      1. 啟用&#x200B;**[!UICONTROL 條件式格式]**。
         1. 選取&#x200B;**[!UICONTROL 自動產生的]**。
         1. 選取偏好的&#x200B;**[!UICONTROL 條件式格式化調色盤]**。
   1. 選取「**[!UICONTROL 儲存]**」，即可儲存您的專案。

如果要報告促銷活動名稱而非追蹤代碼（事件），請執行以下步驟：

1. 複製&#x200B;**[!UICONTROL 摘要資料報表]**&#x200B;自由表格視覺效果。
1. 將複製的視覺效果重新命名為`Summary Data Report (using Campaign Name)`。
1. 將![Switch](/help/assets/icons/Switch.svg)的&#x200B;**[!UICONTROL 追蹤代碼（事件）]**&#x200B;維度取代為&#x200B;**[!UICONTROL 促銷活動名稱（查閱）]**&#x200B;維度。

因為您建立的衍生欄位，以及促銷活動名稱（查詢）的摘要資料群組元件設定，所以您可以在促銷活動名稱（查詢）上正確報告。 檢視[資料檢視](#data-view)。

您的最終專案看起來應該類似以下所示。

![使用摘要資料的專案範例，顯示摘要資料面板和摘要資料報告](../assets/summary-workspace.png)


>[!MORELIKETHIS]
>
>[摘要資料](/help/data-views/summary-data.md)
>[摘要資料群組元件設定](/help/data-views/component-settings/summary-data-group.md)
