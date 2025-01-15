---
description: 使用「摘要編號」和「摘要變更」視覺效果來顯示專案中的重要資料點。
title: 摘要數字和摘要變更
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: f8abf388e0cb1e2e2eb9ff69fed2c542a26dcd66
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 47%

---

# 摘要數字和摘要變更

## 摘要數字 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要數字"
>abstract="建立顯示總計和小計的視覺效果。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*本文以![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**記錄摘要編號和摘要變更視覺效果。<br/>檢視此文章的![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics**版本的[摘要編號和摘要變更](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change)。*

>[!ENDSHADEBOX]


使用![摘要](/help/assets/icons/123.svg) **[!UICONTROL 摘要數字]**&#x200B;視覺效果來強調專案中重要的大數字。 此視覺效果的運作方式如下，使用相關聯的資料來源：

* 如果未選取儲存格，則會選取該欄的總計。
* 如果選取單一儲存格，則會顯示該儲存格的摘要。
* 如果選取多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會挑選欄中第一個儲存格的值。

![摘要數字視覺效果](asses/../assets/summary-number.png)

視覺效果設定中有提供特定摘要數字選項。

| 選項 | 定義 |
|--- |--- |
| **[!UICONTROL 縮簡值]** | 選取&#x200B;**[!UICONTROL Abbreviate value]**&#x200B;以智慧地縮簡數字值。 選取時，輸入數字以定義縮寫金額。 例如：<br/><table><tr><td>**原始值**</td><td>**縮寫值**</td><td>**結果**</td></tr><tr><td>12,011,141.25美元</td><td>未選取</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`0`</td><td align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td> 已選取，設定為`1`</td><td  align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`2`</td><td align="right">1201萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`3`</td><td align="right">1201.1萬美元</td></tr></table> |
| **[!UICONTROL 值摘要依據]** | 選擇此選項即可顯示一系列資料的最大值、最小值、平均值、中間值或總和。 |

## 摘要變更 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="摘要變更"
>abstract="建立顯示兩個數字之間的差異 (變化) 的視覺效果"

<!-- markdownlint-enable MD034 -->


使用![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 摘要變更]**&#x200B;視覺效果來顯示兩個數字間的差異（變更）。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

此視覺效果的運作方式如下：

* 如果未選取儲存格，則會比較欄中前兩個儲存格的值。
* 如果選取一個儲存格，由於與自身比較儲存格的值，因此會顯示 0。
* 如果選取兩個儲存格，會取第一個選取的儲存格為分子，第二個選取的儲存格為分母。
* 如果選取超過兩個儲存格，僅會比較前兩個選取的儲存格。
* 如果選取某個範圍中的儲存格，會比較該範圍第一個與最後一個選取的儲存格。
* 如果選取欄，會就第一個值的本身進行比較，顯示變更為 0。


![摘要變更視覺效果顯示兩個數字間的差異。s](assets/summary-change.png)


作為視覺效果設定的一部分，可以使用特定的&#x200B;**[!UICONTROL 摘要變更選項]**。

| 選項 | 定義 |
|--- |--- |
| **[!UICONTROL 顯示百分比變更]** | 顯示2個數字之間的百分比變化。 |
| **[!UICONTROL 顯示原始差異]** | 顯示2個數字之間的原始差異。 您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
| **[!UICONTROL 縮簡值]** | 選取&#x200B;**[!UICONTROL Abbreviate value]**&#x200B;以智慧地縮簡變更的值。 選取時，輸入數字以定義縮寫金額。 例如：<br/><table><tr><td>**原始值**</td><td>**縮寫值**</td><td>**結果**</td></tr><tr><td>12,011,141.25美元</td><td>未選取</td><td  align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`0`</td><td align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td> 已選取，設定為`1`</td><td  align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`2`</td><td align="right">1201萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為`3`</td><td align="right">1201.1萬美元</td></tr></table> |

>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
