---
description: 使用關鍵量度摘要視覺效果，比較兩個時間軸的量度成效。
title: 關鍵量度摘要
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: e4107e2f795b9beb7aa2802aa7ea646be6733212
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 37%

---

# 關鍵量度摘要 {#key-metric-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="關鍵量度摘要"
>abstract="建立折線圖、摘要變更和摘要數字圖表組合的視覺效果。使用此視覺效果來比較兩個時段之間重要量度的趨勢。"

<!-- markdownlint-enable MD034 -->

![關鍵量度](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 關鍵量度摘要]**&#x200B;視覺化可讓您檢視一項重要的量度在單一時間範圍內的趨勢分析。 也能讓您比較兩個時間範圍內的量度成效。它提供多個視覺效果合併成單一視覺效果的優勢。

* **[!UICONTROL 線]**&#x200B;視覺效果顯示主要和比較日期範圍的趨勢分析

* **[!UICONTROL 摘要百分比變更]**&#x200B;顯示主要和比較日期範圍之間的量度增減

* 量度目前的總值 ([!UICONTROL **摘要數字**])

## 使用案例

此視覺效果處理各種常見的使用案例，包括：

* 分析嘗試了解本月創造的商機跟去年同一時間範圍相比之下的表現。

* 行銷人員探索特定本月與上個月之間銷售機會的銷售機會開發變化。

* 高階主管想要了解本季與上一季之間的新預約變化。

## 使用

1. 新增![關鍵量度](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 關鍵量度摘要]**&#x200B;視覺效果。 請參閱[將視覺效果新增至面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 選取&#x200B;**[!UICONTROL 量度]**、**[!UICONTROL 主要日期範圍]**、**[!UICONTROL 比較日期範圍]** （選用）和&#x200B;**[!UICONTROL 篩選器]** （選用），以設定視覺效果：

   ![關鍵量度組態顯示量度、主要日期範圍、比較日期範圍和區段的選項。](assets/key-metrics-config.png)

   | 選項 | 說明 |
   | --- | --- |
   | **[!UICONTROL 量度]** | 選取想要檢查的量度。支援所有量度。 |
   | **[!UICONTROL 主要日期範圍]** | 任意形狀表格目前的日期範圍。<p>從資料檢視中的任何可用日期範圍中選擇。</p> <p>如果您想要使用與視覺效果所在面板相同的日期範圍，請選擇&#x200B;[!UICONTROL **面板日期範圍**]。</p> |
   | **[!UICONTROL 比較日期範圍]** | 您要與主要日期範圍比較的日期範圍。 |
   | **[!UICONTROL 篩選器（選擇性）]** | 您對此摘要感興趣的任何篩選器。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >當&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位設定為&#x200B;[!UICONTROL **面板日期範圍**]&#x200B;時，根據您選擇的&#x200B;**[!UICONTROL 比較日期範圍]**&#x200B;選項是相對於主要日期範圍還是固定，**[!UICONTROL 比較日期範圍]**&#x200B;可以自動更新。
   >
   >* **相對：**&#x200B;如果&#x200B;**[!UICONTROL 比較日期範圍]**&#x200B;欄位設定為相對於主要日期範圍的選項（例如&#x200B;[!UICONTROL **Previous day**]、[!UICONTROL **Same day last week**]、[!UICONTROL **Same day 4 weeks about**]&#x200B;等等），則&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位的任何更新都會導致&#x200B;**[!UICONTROL 比較日期範圍]**&#x200B;自動更新為緊接面板日期範圍之後的期間。
   >* **固定：**&#x200B;如果&#x200B;[!UICONTROL **比較日期範圍**]&#x200B;欄位設定為固定的日期範圍（例如&#x200B;**2023年2月3日**），則對&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位或面板日期範圍所做的變更不會影響&#x200B;[!UICONTROL **比較日期範圍**]。 但是，面板日期範圍的任何更新都會導致&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;自動更新。

1. 選取「**[!UICONTROL 建立]**」。

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

關鍵量度摘要的輸出如下所示：

![顯示量度、摘要變更、摘要數字和折線圖的關鍵量度輸出。](assets/key-metrics.png)

檢視輸出時，請考量下列事項：

* **[!UICONTROL 上一期]**&#x200B;線圖（一律以灰色顯示）對應於設定步驟中的&#x200B;**[!UICONTROL 比較日期範圍]**。

* 如果未在設定期間指定比較日期範圍，或在視覺效果設定中隱藏日期比較範圍，僅會顯示主要日期範圍的線圖。摘要變更已隱藏。

* 您可以從此處將指標停留在線圖上，以查看個別天數的統計資料：


## 設定

建立視覺效果後，您可以編輯原始設定。

1. 在視覺效果頂端選取「![編輯](/help/assets/icons/Edit.svg)」**[!UICONTROL 設定視覺效果]**。

   系統會將您帶回原始設定對話方塊。

1. 依偏好變更設定。 選取&#x200B;**[!UICONTROL 重設]**&#x200B;以重設目前的設定。 選取&#x200B;**[!UICONTROL 建置]**&#x200B;以重建視覺效果。

## 設定

在視覺效果設定中，可以使用特定的關鍵量度摘要設定。

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 強調百分比變化]** | 在視覺效果中心，以顯著粗體顯示摘要變更 |
| **[!UICONTROL 強調數字值]** | 在視覺效果中心，以顯著粗體顯示摘要數字 |
| **[!UICONTROL 可見圖例]** | 顯示或隱藏視覺效果底部的圖例 |
| **[!UICONTROL 顯示註解]** | 顯示或隱藏管理員新增的註解 |
| **[!UICONTROL 隱藏標題]** | 隱藏視覺效果的標題。 |
| **[!UICONTROL 百分比]** | 以百分比而非數字顯示視覺效果。 |
| **[!UICONTROL 顯示趨勢線]** | 在視覺效果中顯示趨勢線。 |
| **[!UICONTROL 在趨勢線上顯示最大值和最小值]** | 在主要和比較折線圖上顯示或隱藏最小值和最大值 |
| **[!UICONTROL 顯示比較百分比與趨勢線]** | 顯示或隱藏比較資料。隱藏時，比較折線圖和摘要變更物件會隱藏起來。 |
| **[!UICONTROL 顯示總數]** | 顯示或隱藏摘要數字 |
| **[!UICONTROL 顯示原始差異]** | 顯示主要日期範圍與次要日期範圍中量度總值之間的原始差異 |
| **[!UICONTROL 縮簡值]** | 選取&#x200B;**[!UICONTROL Abbreviate value]**&#x200B;以智慧地縮簡數字值。 選取時，輸入數字以定義縮寫金額。 例如：<br/><table><tr><td>**原始值**</td><td>**縮寫**</td><td>**結果**</td></tr><tr><td>12,011,141.25美元</td><td>未選取</td><td align="right">12,011,141.25美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設為1</td><td align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為2</td><td align="right">1200萬美元</td></tr><tr><td>12,011,141.25美元</td><td>已選取，設定為2</td><td align="right">1201.1萬美元</td></tr><tr><td>12,011,141.25美元</td><td>選取，設為3</td><td align="right">1201.1萬美元</td></tr></table> |

## 編輯視覺效果

建置視覺效果後，您仍可編輯原始的設定。

1. 按一下視覺效果右上角的鉛筆圖示（設定齒輪圖示旁）。

   ![視覺效果編輯圖示](assets/edit-icon.png)

   現在您會返回原始設定檢視。

1. 依偏好變更量度、主要日期範圍、比較日期範圍或篩選。

>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
