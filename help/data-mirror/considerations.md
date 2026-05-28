---
title: Data Mirror考量事項
description: 瞭解當您想要在Data Warehouse原生解決方案和Customer Journey Analytics之間同步資料時，需要考慮的其他事項。
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
autotag-review: '2026-05-19T06:55:09.938Z'
TQID: 'https://experienceleague.adobe.com/uZjXZUKUMeXLxxpTRrkCZrPsGhxseSxOtJ9X0ZjG5wU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: df1ab1af7757ef012b4c233e6206ee6c6cde6686
workflow-type: tm+mt
source-wordcount: 889
ht-degree: 1%

---

# Experience Platform Data Mirror考量事項

本文介紹設定Data Mirror資料集時應考量的因素。

## 新增資料行至來源資料表

在啟用CDC的資料映象資料集中，將新欄新增到來源表格時，該變更可能會觸發所有現有列的更新。 這些更新會透過CDC以變更形式處理，CDC會：

* 從進度角度來看，其行為可能像完全表格重寫。
* 可能會導致擷取數量大幅增加，進而導致更新超過您的擷取許可權。

來源表格中資料行的建議策略：

* 請確認一開始已定義所有相關欄。
* 對應您一開始可能認為需要的每個欄。

如果要新增欄，根據是否需要追溯回填，有兩個選項：

* 回溯回填：

   * 移除目前的資料集。
   * 使用更新的欄再次設定聯結器。

  這可確保資料回填的效率更高、更及時。

* 無回溯回填：

   * 在來源表格中新增欄。
   * 在目標資料集結構描述中新增欄。
   * 更新對應以包含從來源表格到目標資料集的新欄位（欄）。

此策略：

* 避免之後昂貴的結構描述演化（新增欄時的大量更新）。
* 保持變更磁碟區比稍後新增或修改資料行時更可預測。
* 有助於限制外部資料庫端的潛在計算成本，因為資料倉儲可能會將新欄解譯為所有列的更新。


## Privacy Service

由於隱私權請求與資料的結構不同，因此非關聯式結構描述目前處理隱私權請求的方式必須相同，才會發生隱私權請求。

從外部關聯式架構映象的資料會成為Adobe生態系統的一部分，並可在整個生態系統內共用，例如透過Customer Journey Analytics Audience Publishing。 提交隱私權請求可確保在Adobe生態系統中，正確處理身分和相關資料。

因此，隱私權請求不應僅限於映象的資料集，也應涉及外部資料庫中來源資料的更新。

## 衛生行為

衛生服務在&#x200B;*主要身分*&#x200B;上運作，但映象的外部資料庫中的資料表有&#x200B;*主要金鑰*，而非主要身分。

主要身分和主要金鑰之間差異的後果是，衛生刪除無法直接對這些關聯式表格執行。 因此，您必須：

* 在資料倉儲解決方案中，刪除其來源表格中的資料，並確保刪除作業透過CDC （或手動變更欄）進行。
* 針對任何包含身分資訊的下游XDM型資料集（例如：Customer Journey Analytics檢視、Real-Time Customer Data Platform資料集、Adobe Journey Optimizer特定資料集等），將衛生和隱私權請求提交至Adobe。

主要身分和主要金鑰之間的差異引入了共同責任模式：

* 出現身分時，Adobe會處理衛生。
* 作為客戶，您有責任將來源資料庫中自己的衛生程式與提交給Adobe的衛生請求進行對應。

## 治理差異

在XDM [結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)和基礎概念（例如[欄位群組](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#field-group)）中，欄位群組中定義的[欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition#field)會將其標籤傳播到使用該欄位群組的所有資料集。 例如，欄位群組`identities`中的電子郵件欄位`emailID`在所有使用欄位群組`identities`的資料集中標籤為相同。

在關聯式結構描述中，欄名稱是獨立的。 資料表`customers`中名為`email`的資料行與資料表`prospects`中名為`email`的資料行獨立且不同。 此行為表示標籤（例如DULE使用標籤、原則）必須個別套用至映象資料集中的欄位。 根據上述範例，您需要將標籤同時套用至`customers`資料集中的`email`欄位和`prospects`資料集中的`email`欄位。

治理差異的影響如下：

* 更多手動控管和設定功能適合客戶使用。
* 您可能需要明確的指引，因此您不會認為透過欄位群組進行一次性標籤足以進行適當治理。

## 拼接

關聯式結構描述在結合時有下列考量事項：

* 部分支援圖表式拚接。 無法針對設定檔/為圖表貢獻內容啟用關聯式結構描述。
* 完全支援欄位式拚接。


## 系統鍵和欄位

下列考量事項適用於系統金鑰和欄位：

* 主索引鍵、版本描述項和時間戳記描述項必須是關聯式XDM結構描述中的根層級欄位。 在內嵌期間使用[欄位對應](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)以支援此需求。
* 您可以在[對應階段](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/dataflow/databases#map-data-fields-to-an-xdm-schema)期間省略適當的來源欄位。

## 映象資料的批次大小

對於任何已設定為連線一部分的映象資料集，您必須確保每個要為映象資料集擷取資料的批次不會超過100GB。 如需詳細資訊，請參閱批次擷取的[護欄](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/guardrails#guardrails-for-batch-ingestion){target="_blank"}。
