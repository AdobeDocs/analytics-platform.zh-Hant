---
description: 使用「摘要數字」和「摘要變更」視覺效果來呈現專案中的重要資料點。
title: 摘要數字和摘要變更
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 639c3d3c349615078c76f8806bcd5bb458b0f6f2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 69%

---

# 摘要數字和變更

>[!BEGINSHADEBOX]

_本文記錄了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的摘要數字和摘要變更視覺效果。_<br/>_請參閱本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 版本的[摘要數字和摘要變更](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change)。_

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [摘要數字和摘要變更視覺效果](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]

## 摘要數字 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="摘要數字"
>abstract="建立顯示總計和小計的視覺效果。"

<!-- markdownlint-enable MD034 -->

使用![摘要化](/help/assets/icons/123.svg)**[!UICONTROL 摘要數字]**&#x200B;視覺效果可強調專案中重要的大數字。 此視覺效果使用關聯資料來源，其行為方式如下：

* 如果未選取儲存格，則選取欄的總計。
* 如果選取了單一儲存格，它會顯示該儲存格的摘要。
* 如果選取了多個儲存格，則會顯示第一個選取的儲存格。
* 如果選取欄，則會選取欄中的第一個儲存格值。

![摘要數字視覺效果](asses/../assets/summary-number.png)

作為視覺效果設定的一部分，可使用特定摘要數字選項。

| 選項 | 定義 |
|--- |--- |
| **[!UICONTROL 縮簡值]** | 請選取「**[!UICONTROL 縮簡值]**」以智慧的方式縮簡數值。選取後，請輸入一個數字來定義縮簡的總數。例如：<br/><table><tr><td>**原始值**</td><td>**縮簡值**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選取</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `0`</td><td align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td> 已選取，設定為 `1`</td><td  align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `2`</td><td align="right">$12,010,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `3`</td><td align="right">$12,011,000</td></tr></table> |
| **[!UICONTROL 值摘要依據]** | 選擇此選項即可顯示一系列資料的最大值、最小值、平均值、中間值或總和。 |

## 摘要變更 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="摘要變更"
>abstract="建立顯示兩個數字之間的差異 (變化) 的視覺效果"

<!-- markdownlint-enable MD034 -->


使用 ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 摘要變更]**&#x200B;視覺效果可顯示兩個數字間的差異 (變更)。<!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) option.
-->

此視覺效果的運作方式如下：

* 如果未選取任何儲存格，則會比較欄中的前兩個儲存格值。
* 如果選取一個儲存格，則會顯示0，因為它會將儲存格值與本身做比較。
* 如果選取了兩個儲存格，則會將第一個選取的儲存格視為分子，將第二個儲存格視為分母。
* 如果選取兩個以上的儲存格，則只會考慮前兩個儲存格進行比較。
* 如果選取了儲存格範圍，則會比較第一個儲存格和範圍中最後選取的儲存格。
* 如果選取該欄，則會比較第一個值與本身，其顯示為0的變更。


![摘要變更視覺效果顯示兩個數字間的差異 (變更)](assets/summary-change.png)


作為視覺效果設定的一部分，可使用特定&#x200B;**[!UICONTROL 摘要變更選項]**。

| 選項 | 定義 |
|--- |--- |
| **[!UICONTROL 顯示百分比變更]** | 顯示 2 個數字之間的百分比變化。 |
| **[!UICONTROL 顯示原始差異]** | 顯示 2 個數字之間的原始差異。您也可以縮簡值，使用此選項顯示最多小數點後 3 位。 |
| **[!UICONTROL 縮簡值]** | 請選取「**[!UICONTROL 縮簡值]**」以智慧的方式縮減變更的值。選取後，請輸入一個數字來定義縮簡的總數。例如：<br/><table><tr><td>**原始值**</td><td>**縮簡值**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選取</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `0`</td><td align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td> 已選取，設定為 `1`</td><td  align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `2`</td><td align="right">$12,010,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 `3`</td><td align="right">$12,011,000</td></tr></table> |

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[視覺化內容選單](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
