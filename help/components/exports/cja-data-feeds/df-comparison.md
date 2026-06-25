---
description: 瞭解如何比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: 比較Customer Journey Analytics和Adobe Analytics中的資料摘要功能
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 8c577ff8508f15944ced77aaf20b692c911fdd3e
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 2%

---

# 比較Customer Journey Analytics和Adobe Analytics中的資料摘要

Customer Journey Analytics和Adobe Analytics中的資料摘要可讓您將原始資料匯出至協力廠商平台。 如果您先前在Adobe Analytics中使用過資料摘要，請使用下列資訊來瞭解可用功能和概念的差異：

| **概念和組態選項** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **資料輸入**<br/>&#x200B;可以收集並包含在資料摘要中的資料型別。 | 支援跨管道資料輸入，包括網路資料、客服中心資料、銷售點資料等。 | 主要支援網頁和行動資料輸入。 其他資料型別（例如客服中心或銷售點資料）可透過資料來源擷取，但處理能力非常有限。 |
| **資料處理**<br/>&#x200B;資料會根據您使用的產品，以不同的階段處理。 | 資料在&#x200B;**報告時間**&#x200B;處理，因此許多報告功能可用於變更歷史資料，例如拼接、衍生欄位和分段。 | 資料會在&#x200B;**收集時間**&#x200B;處理，因此處理規則和VISTA規則等報表功能不會影響歷史資料。 |
| **傳遞頻率**<br/>&#x200B;決定資料摘要的傳送頻率以及摘要中包含的時間範圍。 | **每日** （資料檢視時區的午夜至午夜）或&#x200B;**每小時**。 | **每日** （報告套裝時區的午夜至午夜）或&#x200B;**每小時**。 可以使用15分鐘摘要，但預設無法使用。 |
| **延遲送達點選**<br/>&#x200B;時間戳記屬於先前的傳遞頻率期間，但在該期間過後送達的點選。 <p>例如，延遲送達點選可能來自在離線時緩衝事件並在其重新連線時傳送這些事件的行動應用程式。</p> | **處理延遲**&#x200B;設定會控制系統在頻率視窗關閉之後多久才會觸發匯出，為延遲的資料分配額外的到達時間。 | 透過&#x200B;**延遲送達點選**&#x200B;組態選項，可以&#x200B;**包含或排除**&#x200B;延遲送達點選。 <p>**回顧視窗**&#x200B;設定可控制系統要包含延遲資料的回溯時間。</p> |
| **順序錯亂的點選**<br/>&#x200B;時間戳記不符合其接收順序的點選。 | 由於Customer Journey Analytics同時接受串流和批次資料，因此無法保證指定人員的事件會依時間戳記順序到達。 Customer Journey Analytics會依報告時每人時間戳記重新排序資料。 <p>**處理延遲**&#x200B;設定可提供更多時間讓批次資料在匯出前到達，有助於減少資料摘要輸出中的順序錯亂事件。 不保證傳送中的事件排序。</p><p>**重要**：您的資料摘要資料的最終消費者必須能夠處理每人不正確的時間戳記，因為不保證資料摘要傳遞中的點選順序不會改變。</p> | Adobe Analytics要求資料在收集時依每個訪客的順序送達，但不保證資料摘要傳送中的點選排序。</p> |
| **回填視窗**<br/>&#x200B;匯出兩個過去日期之間的歷史資料。 | 僅限於連線的滾動資料時間視窗。 | 限製為報表套裝資料保留限制：預設為&#x200B;**25個月**。 |
| **Segmentation** | 區段可透過資料檢視區段和/或摘要特定區段套用至資料摘要。 | 無法套用區段。 |
| **拼接** | 支援。 啟用跨裝置身分解析，將跨裝置的事件連結至單一人員。 | 不支援。 拼接資料無法透過Adobe Analytics資料摘要匯出。 |
| **結構描述**<br/>&#x200B;資料摘要結構描述會決定哪些資料行可以包含在資料摘要中。 | 資料摘要結構描述是以資料檢視設定為基礎。  可包含在資料摘要結構描述中的元件，是資料檢視設定中可用元件的子集。</p> | 約1,100個以上變數的預先定義靜態清單。 許多資料行會匯出為&#x200B;**前置與後置處理的資料對** （例如，`eVar1` / `post_eVar1`），這佔資料行計數的大部分。 |
| **查閱**<br/>&#x200B;動態查閱可讓您在資料摘要中接收其他查閱檔案（否則無法使用）。 | 不需要，因為查閱和分類都是直接在資料檢視中組織的維度。 當您在資料檢視中將查閱或分類組織為維度時，解析的值會在Parquet輸出中顯示為規則欄，與事件資料內嵌，而不是作為單獨的參考檔案。 | 用於將資料摘要欄中的數字與實際值比對。 專用於特定專案集（瀏覽器、作業系統、行動裝置，而且會套用為資料摘要隨附的個別檔案）。 |
| **工作階段定義**<br/> <!--(could be included in the data processing section instead)--> | 已在資料檢視中定義。 | 已在集合時定義。 |
| **計算量度**<br/> | 未提供 | 未提供 |
| **持續性模型** | 彈性。 來自資料檢視的持續性設定（配置和到期日）在產生摘要時套用至報告時間。 支援資料檢視中可用的所有配置設定： **原始**、**最近**、**全部**、**最先已知**&#x200B;和&#x200B;**最後已知**。 | 只表示&#x200B;**最近（上次接觸）**&#x200B;和&#x200B;**原始值（首次接觸）**&#x200B;歸因模型。 線性配置的處理與上次接觸相同。 |
| **輸出檔案格式** | Parquet<p>原生支援複雜的巢狀和結構化資料。 產品清單會以結構化陣列/巢狀物件來表示。 </p><p>需要Parquet感知工具才能讀取，例如BigQuery、Snowflake或Apache Spark。</p> | TSV<p>平坦、人類看得懂的列。 不原生支援結構化資料；複雜欄位（例如產品清單）必須編碼為需要自訂剖析邏輯的專有分隔字串。</p> |
| **傳送目的地** | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform。 | Amazon S3、Azure RBAC、Azure SAS、Google Cloud Platform。 也支援&#x200B;**SFTP**。 |

{style="table-layout:auto"}

<!-- Is this useful info to accompany the table? Not sure... **Hits**<br/>  | Only Hit 5 is in the data feed window. However, because the reporting window also includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window.<p>Hits are reordered in the data feed according to their timestamp, as follows: Hit 3, Hit 4, Hit 5.</p> | Only Hit 5 is in the data feed window. However, because a lookback is configured and it includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window. (If a lookback was not configured, only Hit 5 would be included in the data feed.) <p>Hits are shown in the data feed in the order they were received, as follows: Hit 4, Hit 3, Hit 5.</p> -->

<!-- Is all of this info redundant?  **Late-arriving hits**<br/> (If you send us data that is out of order per person would be if you are setting the timestamp. You can set the timestamp in 2 ways: you can have Adobe set the timestamp, based on when we received the data. Or you can set it yourself. If you're setting the timestamps and you sending us data that is out of order, it messes things up in AA. In AA, data needs to come in order per visitor. We need the right order of events. But in CJA, it doesn't matter what timestamps are on the data. CJA doesn't assign a timestamp to a hit. That is done upstream. CJA reorders the data once it arrives, so that everything is in the proper time sequence. Then we can do the report-time processing. That means you can have both streaming data and batch data. It doesn't matter. At the time it arrives, we reorder it and it becomes in order per person as a result. So in CJA we'll give you all the data we received in the last day or hour, but it's limited to the beginning of the reporting window. Most likely a huge chunk of the data you get in a day or hour belongs to that day or hour. If all you did was batch data from a call center, then that is what you would get out. In CJA, data can come in and it doesn't matter when it came in. So the data feed ustomer has to be able to handle this on their side. So wherever they're putting the data, it needs to handle the fact that timestamps could potentially be all over the place. This might be a challenge for some customers. They need to know this. Needs to be able to handle out of order data per person. It doesn't matter across people. ) Hits that should have been included in a previous data feed, but for some reason they arrived late (such as through timestamped hits or data sources). <p>These late-arriving hits are included in the current data feed at the time they arrive, even though their timestamps are within a previous data feed window. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file that is sent.</p>  | Late-arriving hits that occur within the **[!UICONTROL Reporting window]** are always included. <p>The lookback window for these late-arriving hits is controlled through the **[!UICONTROL Reporting window]** configuration option.</p><p>Hits are automatically reordered based on timestamps; original values are persisted (no change feed).</p> | Can be included or excluded. Configurable with the **[!UICONTROL Late-arriving hits]** configuration option.<p>The lookback window for these hits is configured through the **[!UICONTROL Lookback window]** configuration option that is available for this specific purpose.</p><p>Hits are shown in the order in which they are received; they are not reordered according to timestamp.</p>   -->
