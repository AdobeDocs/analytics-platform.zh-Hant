---
title: AAID、ECID、AACUSTOMID 和 Analytics 來源連接器
description: 瞭解 Analytics 來源連接器如何處理 Adobe Analytics 身分識別欄位。
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
role: User
source-git-commit: 5c5f276711f39abb1b3f3b955ad99e17cb0ac09c
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 96%

---

# AAID、ECID、AACUSTOMID 和 Analytics 來源連接器

Adobe Analytics 資料包含多個身分識別欄位。[Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant) 會對三個重要的身分識別欄位進行特殊處理：AAID、ECID、AACUSTOMID。

## AAID

Adobe Analytics ID (AAID) 是 Adobe Analytics 中的主要裝置識別碼，並且保證存在於透過 Analytics 來源連接器傳遞的每個事件中。AAID 有時稱為「舊版分析 ID」或 `s_vi`Cookie ID。但是，即使 `s_vi`Cookie 不存在，也會建立 AAID。AAID 由 [Adobe Analytics 資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant#columns%2C-descriptions%2C-and-data-types)中的 `post_visid_high/post_visid_low` 資料行表示。

在 Analytics 來源連接器中，AAID 將轉換為 `HEX(post_visid_high) + "-" + HEX(post_visid_low)`。指定事件的 AAID 欄位包含單一身分識別，該身分識別可能是 [Analytics ID 作業順序](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html)中所述的幾種類型之一。 (在整個報告套裝中，AAID 可能包含跨事件的多種類型。 每個事件的型別都顯示在Analytics資料摘要的`post_visid_type`欄中。) 另請參閱： [資料行參考](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html)。

## ECID

ECID (Experience Cloud ID)，有時也稱為 MCID (Marketing Cloud ID)，是一個單獨的裝置識別碼欄位，在使用 [Experience Cloud 身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hant) 執行 Analytics 時填入到 Adobe Analytics 中。ECID 由 Adobe Analytics 資料摘要中的 `mcvisid` 資料行表示。

如果事件中存在 ECID，則 AAID 可能會以 ECID 為基礎，具體取決於是否設定了 Analytics [寬限期](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html)。另請參閱：[Analytics 與 Experience Cloud ID 要求](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html)。

## AACUSTOMID

AACUSTOMID 是一個單獨的識別碼欄位，根據 Analytics 執行中 `s.VisitorID` 變數的使用情況在 Adobe Analytics 中填入。AACUSTOMID 由 Adobe Analytics 資料摘要中的 `cust_visid` 資料行表示。如果 AACUSTOMID 存在，則 AAID 將以 AACUSTOMID 為基礎。(AACUSTOMID 比上述作業順序定義的其它識別碼更有效率。)

## Analytics 來源連接器如何處理這些身分識別

Analytics 來源連接器將這些身分識別以 XDM 形式傳遞到 Adobe Experience Platform，如下所示：

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

這些欄位不會標記為身分識別。 而是將相同的身分識別作為索引鍵/值組複製到 XDM 的 **_identityMap_** 中，如下所示：

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

&lt;> 方括弧中的項目表示實際值出現的地方。

在 identityMap 中：

* 如果 ECID 存在，則將其標記為事件的主要身分識別。請注意，在這種情況下，AAID 可能會以上述 ECID 為基礎。
否則，AAID 將標記為事件的主要身分識別。
* AACUSTOMID 永遠不會標記為事件的主要 ID。但是，如果 AACUSTOMID 存在，則 AAID 會以上述 AACUSTOMID 為基礎。

當身分識別複製到 `identityMap` 時，同一事件上也會設定 `endUserIDs._experience.mcid.namespace.code`：

* 如果存在 AAID，則 `endUserIDs._experience.aaid.namespace.code` 設定為「AAID」。
* 如果存在 ECID，則 `endUserIDs._experience.mcid.namespace.code` 設定為「ECID」。
* 如果存在 AACUSTOMID，則 `endUserIDs._experience.aacustomid.namespace.code` 設定為「AACUSTOMID」。

## Customer Journey Analytics 和主要 ID

就 Customer Journey Analytics 而言，只有在您決定將主要 ID 當做人員 ID 時，主要 ID 的定義才重要。然而，這並不具有強制性。 您可以選擇其他身分識別資料行作為人員 ID。
