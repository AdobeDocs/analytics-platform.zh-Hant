---
description: 瞭解Analysis Workspace中自由格式表格的總計計算方式。
title: 總計
feature: Visualizations
exl-id: ba14b88c-44c2-45f6-b68f-f5c1263a89dd
role: User
TQID: https://experienceleague.adobe.com/BoH9J-fL9UxPG4wId9-GU7muMNR10aeWe0BBd1NQOjo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 502
ht-degree: 88%

---

# 總計 {#workspace-totals}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_grandtotal"
>title="總量"
>abstract="具靜態列的表格或劃分不支援全部總計。"


在自由格式表格中，每個劃分層級都會顯示總列數，當中會顯示兩個總計數字：

![自由格式表格醒目顯示總計和表格總計。](assets/total-row.png)

* **[!UICONTROL 資料表總計]** ➊ — 此總計通常等於[!UICONTROL 總計]或是其子集。 總計反映的是在自由格式表格中套用的任何表格區段，包括[!UICONTROL 不包含任何項目]選項。
* **[!UICONTROL 總計]** （**[!UICONTROL 個，共]**&#x200B;個&#x200B;*數字*） ➋ — 此總計代表已收集的所有事件。 在面板層級或自由格式表格內套用區段時，這項總計會經過調整，藉以反映所有符合區段條件的事件。




## 顯示總計

![「設定」](/help/assets/icons/Setting.svg)**[!UICONTROL 「欄設定」]**&#x200B;下方有「**[!UICONTROL 顯示總計]**」和「**[!UICONTROL 顯示總量]**」選項。 如果未選中這些設定，總數將從表格中刪除，在總數不合理情況下可能必須這樣做。


在包含[靜態列](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)的自由格式表格中，總計的行為會不同。 並使用![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 資料列設定]**&#x200B;來控制和。

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 顯示目前行數的總和作為總數]** | 顯示表格中的客戶端行數總和。 此總和&#x200B;**不會**&#x200B;刪除如工作階段或人數等重複量度。 |
| **[!UICONTROL 顯示總量]** | 顯示伺服器端總數。 此總和會刪除如工作階段或人數等重複量度。 |

請參閱「[自由格式表格中的動態與靜態維度項目](column-row-settings/manual-vs-dynamic-rows.md)」。


## 常見問題集

| 問題 | 回答 |
|---|---|
| 灰色欄的百分比以哪些「*總計*」為依據？ | 這項「*總計*」取決於「**[!UICONTROL 列設定]**」中的「**[!UICONTROL 百分比]**」設定選取項目：<ul><li>依欄計算百分比 - 此為預設設定。 百分比是以「表格總計」為依據。</li><li>依列計算百分比 - 百分比是以「總量」為依據。</li></ul> |
| **[!UICONTROL 「包含「沒有值」」]**&#x200B;設定對總計會有何影響？ | 如果取消勾選「**[!UICONTROL 包含「無值」]**」設定，「**[!UICONTROL 無值]**」列會從表格和「表格總計」中移除，且這種情形會持續在任何使用「[*總計*」量度類型的計算量度中生效](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)。 |
| 如果在自由格式表格套用自訂表格區段，區段是否會採計我的所有計算量度和條件式格式？ | 目前不會。 會採計&#x200B;**[!UICONTROL 包含「無值」]**，但自訂表格區段不會影響以下項目：<ul><li>條件式格式使用的欄最大值 / 最小值範圍會檢查所有資料。</li><li>使用「**[!UICONTROL 總量]**」量度類型的計算量度 。</li><li>內含的函數可計算自由格式表格中所有列的計算量度：「欄加總」、「欄最大值」、「欄最小值」、「計數」、「平均值」、「中位數」、「百分位數」、「四分位數」、「列計數」、「標準差」、「變數」、「累積」、「累積平均值」、「迴歸變數」、「T 分數」、「T 檢定」、「Z 分數」和「Z 檢定」。</li></ul> |
| 在計算量度中，**[!UICONTROL 「總量」]**&#x200B;量度類型會反映什麼？ | **[!UICONTROL 總量]**&#x200B;只會持續參考&#x200B;**[!UICONTROL 總量]**，不會反映套用至表格或&#x200B;**[!UICONTROL 表格總計]**&#x200B;的區段。 |
| 如果資料經由自由格式表格複製貼上或透過 CSV 下載，系統會顯示哪項總計？ | 總列數只會反映「**[!UICONTROL 表格總計]**，並遵從欄的「**[!UICONTROL 顯示總計]**」設定。 |
