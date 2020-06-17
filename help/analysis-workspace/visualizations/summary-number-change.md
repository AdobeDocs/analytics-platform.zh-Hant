---
description: 'null'
title: 摘要數字和摘要變更
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 92%

---


# 摘要數字和摘要變更

>[!NOTE] 您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

## 摘要數字視覺效果

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

![](assets/summary-number.png)

## 摘要變更視覺效果

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。
* 摘要變更的綠紅顏色可以透過以下方式控制：
   * [自訂事件極性](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/success-events/success-event.html)。
   * 計算量度的[「將向上趨勢顯示為」](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)選項。

## 摘要變更設定 {#section_2581AC0107634FB4990AB8347E5897AA}

按一下視覺效果旁的齒輪圖示以設定「摘要」設定：

| 設定 | 定義 |
|--- |--- |
| 百分比 | 使用百分比而非原始數據。 |
| 可見圖例 | 顯示所使用的量度。 |
| 摘要數字選項：縮略值 | 您可以選擇 0 到 3 當作小數來表示縮略值。 |
| 摘要變更選項：顯示百分比變化 | 以百分比顯示 2 個數字之間的變化。 |
| 摘要變更選項：顯示原始差異 | 顯示 2 個數字之間的原始差異。 |
