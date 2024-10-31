---
title: 共用裝置
description: 說明如何使用拼接和其他技術處理共用裝置。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: c0dae5f1255a986df5ab2551aabdf1bd0727e949
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 6%

---

# 共用裝置

本文提供共用裝置上的內容、如何使用[拼接](/help/stitching/overview.md)處理及緩解來自共用裝置的資料，以及使用查詢服務瞭解資料中的共用裝置曝光度。

## 什麼是共用裝置？

共用裝置是指由超過一個使用者使用的裝置。 常見的案例是平板電腦之類的裝置、資訊站中使用的裝置或呼叫中心代理程式共用的電腦裝置。

當兩個人使用同一部裝置且都進行購買時，範例事件資料可能如下所示：

| 事件 | 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | 首頁 | `1234` | |
| 2 | 2023-05-12 12:02 | 產品頁面 | `1234` | |
| 3 | 2023-05-12 12:03 | 訂購成功 | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | 產品頁面 | `1234` | |
| 5 | 2023-05-12 12:08 | 訂購成功 | `1234` | `cassidy@a.com` |

如表所示，一旦在事件3和5上執行驗證，裝置id和人員id之間就會開始形成連結。 若要瞭解任何行銷活動對個人層級的影響，這些未驗證事件必須歸因到正確的人員。

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## 改善以人為中心的分析

彙整程式會將選取的人員識別碼（在範例資料中為電子郵件）新增至不存在該識別碼的事件，以解決此歸因問題。 拼接運用裝置ID和人員ID之間的對應，確保分析時可同時使用已驗證和未驗證的流量，並保持以人為中心。 如需詳細資訊，請參閱[拼接](/help/stitching/overview.md)。

拼接可以使用上次驗證歸因或裝置分割歸因來歸因共用裝置資料。 所有嘗試將未驗證事件拼接給已知使用者的行為都是非決定性的。


### 上次驗證歸因

上次驗證會將共用裝置中的所有未知活動，歸因於上次驗證的使用者。 Experience PlatformIdentity服務會根據上次驗證歸因建立圖表，因此會用於圖表式拚接。 如需詳細資訊，請參閱[身分圖表連結規則總覽](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview)。

彙整使用上次驗證歸因時，彙整ID會解決問題，如下表所示。

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 | 拼接的 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | 產品頁面 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | 訂購成功 | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | 產品頁面 | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | 訂購成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 首頁 | `1234` | | `cassidy@a.com` |


### 裝置分割

裝置分割會將共用裝置的匿名活動歸因於最接近匿名活動的使用者。 裝置分割是分析使用案例的偏好方法，因為裝置分割會將未驗證和已驗證活動的評分給予最接近的已知人員。 裝置分割目前用於依欄位彙整。

在拼接中使用裝置分割歸因時，拼接ID會解析，如下表所示。

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 | 拼接的 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | 產品頁面 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | 訂購成功 | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | 產品頁面 | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | 訂購成功 | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | 首頁 | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## 共用裝置曝光

請考慮數個因素，以正確瞭解共用裝置在您的組織中的普及程度。 此外，瞭解來自共用裝置的事件整體貢獻，有助於您瞭解對用於分析的整體事件資料的影響。

若要瞭解共用裝置的曝光度，您可以考慮執行下列查詢。

1. **識別共用裝置**

   若要瞭解共用的裝置數，請執行查詢，以計算與兩個或多個相關聯之人員ID的裝置ID。 這有助於識別多人使用的裝置。

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **事件歸因至共用裝置**

   針對已識別的共用裝置，決定總計中有多少事件可歸因於這些裝置。 此歸因可讓您深入瞭解共用裝置對您資料的影響，以及對於分析的影響。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **識別共用裝置上的匿名事件**

   在歸因於共用裝置的事件中，找出多少沒有人員ID，以表示匿名事件。 您選擇用來增強資料品質的演演算法（例如last-auth、device-split或ECID-reset）會影響這些匿名事件。

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **根據事件錯誤分類計算曝光率**

   最後，評估每位客戶因事件分類錯誤而可能面臨的曝光率。 計算每個共用裝置的匿名事件佔事件總數的百分比。 這有助於瞭解對客戶資料正確性的潛在影響。

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
