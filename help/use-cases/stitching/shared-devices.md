---
title: 共用裝置
description: 說明如何使用拼接和其他技術處理共用裝置。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d94f6d6b592b2ddecfa0b1024b9ae045b3c3ce11
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 6%

---


# 共用裝置

本文提供有關共用裝置的內容、如何使用拼接處理及緩解來自共用裝置的資料，以及瞭解使用查詢服務在您的資料中暴露共用裝置。

## 什麼是共用裝置？

共用裝置是指由超過一個使用者使用的裝置。 常見的案例是平板電腦之類的裝置、資訊站中使用的裝置或呼叫中心代理程式共用的電腦裝置。

當兩個人使用同一部裝置且都進行購買時，範例事件資料可能如下所示：

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 |
|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | 1234 | |
| 2023-05-12 12:02 | 產品頁面 | 1234 | |
| 2023-05-12 12:03 | 訂購成功 | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | 產品頁面 | 1234 | |
| 2023-05-12 12:08 | 訂購成功 | 1234 | <cassidy@a.com> |

訂單成功（購買）事件會將資料準確地指派給正確的電子郵件。 此指派如何影響您的分析，取決於您執行分析的方式：

- 以裝置為中心的方法：使用裝置ID執行的分析。 使用此方法時，分析中會包含已驗證和未驗證的資料。 不過，此方法無法進行更多以人為本的分析。
- 以人為中心的方法：使用電子郵件地址或其他人員識別碼執行的分析。 使用此方法時，分析中只會包含已驗證的事件。 此方法無法完整呈現客戶歷程，包括贏取

## 改善以人為中心的分析

若要改善共用裝置以人為中心的分析，您有兩個選擇：您可以使用拼接，或實施ECID重設功能。 以下各節將更詳細地討論這兩種方法。

### 拼接

拼接過程解決了以人為本方法的缺點。 拼接會將選取的人員識別碼（在範例資料中，即電子郵件）新增至不存在該識別碼的事件。 拼接運用裝置ID和人員ID之間的對應，確保分析時可同時使用已驗證和未驗證的流量，並保持以人為中心。 如需詳細資訊，請參閱[拼接](/help/stitching/overview.md)。

拼接可以使用上次驗證歸因或裝置分割歸因來歸因共用裝置資料。 不過，透過ECID重設進行的實作變更也可以處理共用裝置。


#### 上次驗證歸因

上次驗證會將共用裝置中的所有未知活動，歸因於上次驗證的使用者。 上次驗證用於Audience Manager，且是即時客戶資料設定檔使用案例的偏好方法。 Experience PlatformIdentity服務會根據上次驗證歸因建立圖表，因此會用於圖表式拚接。 如需詳細資訊，請參閱[身分圖表連結規則總覽](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview)。

在拼接中使用上次驗證歸因時，拼接ID會解析，如下表所示。

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 | 拼接的 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | 產品頁面 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:03 | 訂購成功 | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | 產品頁面 | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 訂購成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 首頁 | 1234 | | <cassidy@a.com> |


#### 裝置分割

裝置分割會將共用裝置的匿名活動歸因於最接近匿名活動的使用者。 裝置分割目前用於依欄位彙整。 裝置分割是分析使用案例的偏好方法，因為裝置分割會將未驗證和已驗證活動的評分給予最接近的已知人員。 裝置分割目前用於依欄位彙整。

在拼接中使用裝置分割歸因時，拼接ID會解析，如下表所示。

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 | 拼接的 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 產品頁面 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 訂購成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 產品頁面 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | 訂購成功 | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 首頁 | 1234 | | <cassidy@a.com> |


### ECID重設

顧名思義，ECID重設會在預先決定的觸發條件（大多數情況下是登入或登出事件）上重設ECID的功能。 透過此實作，單一裝置在每次觸發預先決定的觸發器時都會取得新的ECID。 基本上，此重設會強制裝置從資料的角度反複變成&#x200B;*新裝置*。 ECID重設也有助於防止共用裝置出現在資料中。 您不需要其他演演算法，但您有責任實施ECID重設訊號，作為Adobe資料收集實施的一部分。


使用ECID重設時，會解析彙整ID，如下表所示。

| 時間戳記 | 頁面名稱 | 裝置ID | 電子郵件 | 拼接的 ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | 首頁 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | 產品頁面 | 1234 | | <ryan@a.com> |
| 2023-05-12 12:03 | 訂購成功 | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | 產品頁面 | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | 訂購成功 | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | 首頁 | 5678 | | <cassidy@a.com> |

## 共用裝置曝光

請考慮數個因素，以正確瞭解共用裝置在您的組織中的普及程度。 此外，瞭解來自共用裝置的事件整體貢獻，有助於您瞭解對用於分析的整體事件資料的影響。

若要瞭解共用裝置的曝光度，您可以考慮執行下列查詢。

1. 瞭解共用的裝置數量。 您可以使用查詢來計算擁有兩個以上與裝置ID相關聯之人員ID的裝置ID。 範例查詢可能如下所示：

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


2. 對於透過第一次查詢而得到的共用裝置，您需要瞭解可將總事件中的多少個事件歸因於這些共用裝置。 此歸因可讓您更清楚瞭解共用裝置對資料的影響，以及執行分析時的影響。 範例查詢可能如下所示：

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

3. 對於歸因於共用裝置的事件（第二個查詢的結果），您需要瞭解其中有多少事件沒有人員ID。 若未指定，共用的裝置事件中有多少是匿名事件。 最後，您選取用來改善資料品質的演演算法（上次驗證、裝置分割、ECID重設）確實會影響這些匿名共用裝置事件。 範例查詢可能如下所示：

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

4. 最後，您想要瞭解每位客戶因事件錯誤分類而遇到的曝光度。 若要取得此曝光度，您必須針對每個共用裝置計算與事件總數相關的匿名事件百分比。 範例查詢可能如下所示：

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


