---
description: 瞭解如何使用資料摘要從Customer Journey Analytics匯出原始事件層級資料、檢閱先決條件，並尋找開始使用所需的文章。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: Customer Journey Analytics資料摘要概觀
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# 資料摘要概觀

{{release-limited-testing}}

資料摘要會從Customer Journey Analytics將原始事件層級資料匯出至雲端目的地。 您可以在Adobe以外的其他平台（例如資料倉儲）中使用此資料。

資料摘要是從資料檢視中的元件建置的。 您加入的每個維度和量度都會成為資料摘要中的欄，而資料檢視設定（例如持續性、衍生欄位和區段）會套用至資料。 檔案以Parquet格式傳送。

您可以建立下列型別的資料摘要：

* **即時摘要**：每小時或每天匯出目前和未來的資料。 每一次傳送都會在小時或一天結束後，且經過處理延遲後傳送。

* **回填摘要**：匯出過去日期範圍的歷史資料。

若要比較資料摘要與其他Customer Journey Analytics匯出方法（例如完整表格匯出），請參閱[Analytics產品比較](/help/getting-started/analytics-product-comparison.md)。

## 先決條件

在使用資料摘要之前，請確定您符合下列所有需求：

* 資料正在內嵌至Customer Journey Analytics，且已設定連線和[資料檢視](/help/data-views/create-dataview.md)。<!-- For more information, see Data ingestion overview - add link -->

* 您的帳戶是Customer Journey Analytics產品管理員，或屬於您要使用之資料檢視的產品設定檔，該設定檔具有&#x200B;[!UICONTROL **資料摘要**]&#x200B;許可權（在&#x200B;[!UICONTROL **資料檢視工具**]&#x200B;類別中）。 如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md)。<!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* 已為[!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]或[!DNL Azure SAS]設定雲端匯出帳戶和位置。 如需詳細資訊，請參閱[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)和[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)。

>[!TIP]
>
>由於資料檢視中元件的變更會影響使用此檢視的每個資料摘要，請考慮建立僅用於資料摘要的資料檢視。
>
>* **優點**：減少Analysis Workspace報告變更意外變更資料摘要輸出的風險。
>
>* **缺點**：您必須與其他資料檢視一起維護其他資料檢視。

## 開始使用

使用下列文章來規劃、移轉及建立您的資料摘要。

### 規劃您的資料摘要

* [比較Customer Journey Analytics和Adobe Analytics中的資料摘要](/help/components/exports/cja-data-feeds/df-comparison.md)：瞭解您先前使用Adobe Analytics資料摘要時功能與概念的差異。

* [瞭解資料摘要和Analysis Workspace之間的資料差異](/help/components/exports/cja-data-feeds/df-comparison-workspace.md)：瞭解資料摘要輸出可能與Analysis Workspace中的報表不符的原因。

* [資料摘要中的元件可用性](/help/components/exports/cja-data-feeds/df-components.md)：瞭解資料摘要中需要、不支援或限制哪些維度和量度。

### 從Adobe Analytics資料摘要移轉

1. [準備對應資料摘要欄](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md)：瞭解影響Adobe Analytics欄對應至Customer Journey Analytics方式的因素。

1. [將Adobe Analytics資料摘要資料行對應至Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)：尋找您要保留的每個Adobe Analytics資料行的相等專案Customer Journey Analytics。

### 建立及設定資料摘要

* [建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)：選擇元件、設定排程並設定傳送。

* [資料摘要中的分段](/help/components/exports/cja-data-feeds/df-segmentation.md)：套用區段以篩選資料摘要中的資料。

* [套用資料轉換](/help/components/exports/cja-data-feeds/df-data-transformations.md)：使用元件設定、衍生欄位或SQL轉換資料。

* [資料摘要中的子事件元件](/help/components/exports/cja-data-feeds/df-sub-event.md)：瞭解如何匯出陣列和地圖的元件，以及如何查詢它們。

