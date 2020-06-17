---
description: 列設定依您拖放至表格中的元件而異。
title: 列設定
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# 列設定

>[!NOTE] 您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

列設定依您拖放至表格中的元件而異。

您也可以使用[表格中的按右鍵動作](/help/analysis-workspace/visualizations/freeform-table.md)來管理選取的列。

若要存取表格列設定，按一下維度、區段、量度、時段旁的設定圖示，或按以下各項之中的劃分：

![](assets/row-settings.png)

| 列設定 | 說明 |
|--- |--- |
| 日期比較 | 對齊各欄日期，讓所有開始日期在同一列。當您選擇對齊日期，例如，在 2016 年 10 月和 9 月的月對月比較中，左欄將從 10 月 1 日開始，右欄將從 9 月 1 日開始.<br>預設為停用。 |
| 百分比 | 「按列計算百分比」可強制自由格式表格跨列計算儲存格百分比，而非整欄計算。此設定在計算趨勢百分比時特別實用。<br>使用「視覺化」圖示時，此功能會預設為啟用。 |
| 欄總計 | 僅選取有限數目的項目時，這些設定只會在 [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL 將目前的列數加總顯示為總計]** - 這個選項會顯示表格中的用戶端列數加總，因此總計&#x200B;**不會**&#x200B;刪除「造訪次數」或「訪客人數」等重複量度。</li><li>**[!UICONTROL 顯示總量]** - 這個選項會顯示伺服器端的加總，因此總計會刪除「造訪次數」或「訪客人數」等重複量度。</li></ul> |
| 劃分 | **[!UICONTROL 依位置劃分]**：您可以根據自由格式表格中的固定位置執行劃分。例如，您可以指定一律劃分前七列。<br>(在舊版中，資料劃分中的值清單為「鎖定」。這樣的設定如舉例說名，在您執行依「頁面」劃分「日期」時，會得到所選日期範圍內前 50 個頁面的清單。如果儲存該報表，並在一個月後執行，前 50 頁可能會有所變更。然而，Analysis Workspace 會使用原始劃分的結果，並傳回相同的頁面，但以當前月份為日期範圍。)<br>若要依固定位置執行劃分：1.劃分表格中的一些列。2. 找到您要固定位置的表格列，按一下旁邊的設定 (齒輪) 圖示。3. 勾選「依位置劃分」旁的核取方塊。4. 變更排序順序或日期範圍，並注意劃分現在已繫結至該列的位置，而不是程式碼寫定的列。<br>預設為停用。 |