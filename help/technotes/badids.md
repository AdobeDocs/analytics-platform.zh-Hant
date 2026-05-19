---
title: Customer Journey Analytics錯誤ID
description: 瞭解Customer Journey Analytics中的錯誤ID (BAVID)。 瞭解如何識別資料中的不良ID、其影響報告的原因，以及如何調查和解決連線中的不良ID暴露。
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 4f71fbf2-290b-4076-b2ad-b086c2b854d9
autotag-review: '2026-05-19T06:53:00.572Z'
TQID: 'https://experienceleague.adobe.com/6vut30l-BSIxhTK96Tt3BG01q-rjHagcmer0WZ2GL-c'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 632
ht-degree: 2%

---

# 異常 ID

本文提供不良ID的相關內容，並說明如何使用查詢服務，偵測資料中是否有不良ID或發生不良事件的風險。


>[!INFO]
>
>錯誤的ID在Customer Journey Analytics介面中也被稱為BAVID （源自[Analytics BAVID](https://experienceleague.adobe.com/zh-hant/docs/experience-cloud-kcs/kbarticles/ka-16444)）。
>

## 定義

在Customer Journey Analytics中，做為連線中定義的所有資料的一部分，錯誤ID是一個識別碼：

* ，並使用源自的特定ID值
   * 來自人員ID欄位（非拼接資料集）、**或**
   * 永久性ID或人員ID欄位（已啟用拼接的資料集）中的資料，

  **和**
* 在一個月內對連線資料中的超過100萬(1,000,000)個事件負責（針對連線中的所有資料集計算）。

當ID值標示為錯誤ID時，連線資料中任何包含該ID值的未來事件都會遭到捨棄，而不會顯示在報表中。

### 範例

ID錯誤情況的範例是，您在人員ID欄位中有自訂或預留位置值（例如，匿名流量為`undefined`）。 對於啟用拼接的資料集，這種情況對報表資料的影響甚至可能更大，因為拼接品質最有可能受到影響。 若要解決此問題，您可能需要清除並重新啟用拚接設定，包括刪除連線中資料集的歷史資料。


## 量度

Customer Journey Analytics連線介面會在介面的數個位置提供&#x200B;**[!UICONTROL 錯誤的ID]**&#x200B;量度資訊。

* 在&#x200B;**[!UICONTROL 檢查略過的詳細資料]**&#x200B;對話方塊中，您可以看到&#x200B;**[!UICONTROL 錯誤的ID]** （或&#x200B;**[!UICONTROL BAVID]**）為略過記錄的可能原因。 在連線的[詳細資訊畫面](/help/connections/create-connection.md)中，使用&#x200B;**[!UICONTROL 略過的記錄]**&#x200B;下方的&#x200B;**[!UICONTROL 檢查詳細資料]** （如果有的話）。
* 針對已啟用拼接的資料集，[**[!UICONTROL 資料集預覽]**](/help/stitching/use-stitching-ui.md#bad-ids)會將&#x200B;**[!UICONTROL 錯誤的ID]**&#x200B;顯示為&#x200B;**[!UICONTROL 拼接量度]**&#x200B;的一部分。 此量度可協助您識別可能的Bad ID案例。 但是，請注意，此量度的計算基礎是一組有限的資料。

請參考[錯誤的ID暴露](#bad-ids-exposure)，協助您識別您計畫在連線中使用的資料集是否存在錯誤的ID （無論是否啟用拼接）。


## 曝光

若要調查特定資料集欄位的錯誤ID暴露情形，請考慮在Experience Platform查詢服務中執行以下查詢。 檢查前幾個傳回的ID值，看看是否有適用的ID錯誤。 請注意，[錯誤的ID定義](#definition)會考慮連線中的所有資料集。


### 識別欄位中的錯誤ID （風險）

您可以使用Experience Platform查詢來協助識別欄位中發生錯誤ID的潛在風險。

以下查詢會從欄位傳回前20個ID值。 依事件總數降序排列。 以及在特定間隔內（例如過去30天內）偵測到每個值的位置。

針對您要分析的特定人員ID欄位執行此查詢。 對於需要拼接的資料集，您也可以對永久ID欄位執行查詢。

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

在查詢中，根據您調查錯誤ID的欄位型別取代`INSERT FIELD HERE`：

* `full.field.path.from.XDM.schema` （適用於XDM結構描述中定義的字串欄位）
* `identityMap['namespace_value'][0].id` （針對`identityMap`中以`namespace_value`定義的欄位）

檢查結果以檢視是否有問題的ID值。 例如自訂或預留位置值，或高發生次數的值，在連線資料層級上一個月內會或可能接近100萬。
即使您的實作仍處於開發階段，一旦設定穩定並準備好投入生產，您也應評估存在錯誤ID的風險。
