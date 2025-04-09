---
title: 量度重複資料刪除元件設定
description: 僅計算報告中量度的第一次出現。
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: af88be97f303095129177b2132c6711c648cea34
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 82%

---

# 量度重複資料刪除元件設定 {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="量度重複資料刪除"
>abstract="設定量度，僅對非重複出現的值進行計數。"

<!-- markdownlint-enable MD034 -->


量度重複資料刪除允許您將量度設定為僅對值進行非重複計數。

![量度重複資料刪除](../assets/metric-deduplication.png)

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 量度重複資料刪除] | 允許您啟用量度重複資料刪除的核取方塊。預設為停用。 |
| [!UICONTROL 重複資料刪除範圍] | 可讓您決定唯一檢查追溯到多遠。<br/>**[!UICONTROL 全域帳戶&#x200B;]**：僅計算報表時段中第一個量度發生次數。<br/>**[!UICONTROL 帳戶]**：僅計算報表時段中第一個量度發生次數。<br/>**[!UICONTROL 機會&#x200B;]**：僅計算報告時段中第一個量度發生次數。<br/>**[!UICONTROL 購買群組]**：僅計算報表時段中第一個量度發生次數。<br/>**[!UICONTROL 人員&#x200B;]**：僅計算報表時段中第一個量度發生次數。<br>**[!UICONTROL 工作階段]**：僅計算工作階段的第一個量度發生次數。<br> |
| [!UICONTROL 重複資料刪除 ID] | 不是在量度本身上套用重複資料刪除，而是允許您根據維度套用重複資料刪除。對於購買 ID 之類的維度套用重複資料刪除很有價值。 |
| [!UICONTROL 要保留的值] | <ul><li>**保留第一個執行個體**：在量度的第一個執行個體是有效的情況下使用。最常見的可能是購買確認。即使有人在無意間重新載入頁面，而且我們得到另一個購買確認的執行個體，初始事件仍有效。</li><li>**保留最後一個執行個體**：如果收集最後一個執行個體較有意義，請用此選項。範例：有人更新了自己的線上個人檔案。針對每個工作階段中的更新，我們只想計入其中之一。但是，他們可能會在工作階段期間多次更新他們的檔案。如果我們保留第一個執行個體，則可能會有與事件無關的活動。在這種情況下，保留最後一個執行個體更有意義。</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>_人員_ 範圍內的重複資料刪除會根據 UTC 時間的完整月份進行評估。如果某些執行個體發生在完整月份內但在報告日期之外，部分月份的報告視窗可能不會顯示所有第一個或最後一個執行個體。
