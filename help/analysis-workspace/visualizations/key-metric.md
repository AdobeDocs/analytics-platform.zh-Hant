---
description: 使用關鍵量度摘要視覺效果，比較兩個時間軸的量度成效。
title: 關鍵量度摘要
feature: Visualizations
role: User, Admin
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 85%

---

# 關鍵量度摘要

The [!UICONTROL 關鍵量度摘要]視覺效果可讓您查看一項重要的量度在單一時間範圍內的趨勢分析。也能讓您比較兩個時間範圍內的量度成效。它提供多個視覺效果合併成單一視覺效果的優勢。

* **[!UICONTROL 線段]**&#x200B;視覺效果會顯示主要和比較日期範圍的趨勢分析

* **[!UICONTROL 摘要百分比變更]**&#x200B;會顯示主要和比較日期範圍之間的量度增減

* 量度目前的總值 ([!UICONTROL **摘要數字**])

## 使用案例

此視覺效果處理各種常見的使用案例，包括：

* 分析嘗試了解本月創造的商機跟去年同一時間範圍相比之下的表現。

* 行銷人員探索特定本月與上個月之間銷售機會的銷售機會開發變化。

* 高階主管想要了解本季與上一季之間的新預約變化。

## 設定關鍵量度摘要

1. 從左側邊欄的「**[!UICONTROL 視覺效果]**」選單，將&#x200B;**[!UICONTROL 關鍵量度摘要]**&#x200B;視覺效果拖曳至面板。

1. 選取量度、主要日期範圍、比較日期範圍及篩選器（如有需要），以設定視覺效果：

   ![顯示量度、主要日期範圍、比較日期範圍和區段選項的關鍵量度設定。](assets/key-metric-config.png)

   | 組態設定 | 定義 |
   | --- | --- |
   | **[!UICONTROL 量度]** | 選取想要檢查的量度。支援所有量度。 |
   | **[!UICONTROL 主要日期範圍]** | 任意形狀表格目前的日期範圍。 |
   | **[!UICONTROL 比較日期範圍]** | 您要與主要日期範圍進行比較的日期範圍。 |
   | **[!UICONTROL 篩選器 (選擇性)]** | 您對此摘要特別感興趣的任何篩選器。 |

   {style="table-layout:auto"}

1. 按一下&#x200B;**[!UICONTROL 「建置」]**。

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

## 檢視輸出

![顯示量度、摘要變更、摘要編號和折線圖的關鍵量度輸出。](assets/key-metric-output.png)

請注意：

* **[!UICONTROL 前一期]**&#x200B;線圖 (總是以灰色顯示) 對應於設定步驟中的&#x200B;**[!UICONTROL 比較日期範圍]**。

* 如果未在設定期間指定比較日期範圍，或在視覺效果設定中隱藏日期比較範圍，僅會顯示主要日期範圍的線圖。將會隱藏摘要變更。

* 您可以從此處將指標停留在線圖上，以查看個別天數的統計資料：

![造訪統計資料](assets/key-metric-output2.png)

## 視覺效果設定

關鍵量度摘要提供多種彈性設定，以為重要量度提供更佳的報告和溝通。您可以透過視覺效果右上角的齒輪圖示存取設定。

![顯示「摘要」顯示型別、一般和顯示選項的關鍵量度摘要設定。](assets/key-metric-settings.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 強調百分比變化]** | 在視覺效果中心，以顯著粗體顯示摘要變更 |
| **[!UICONTROL 強調數字值]** | 在視覺效果中心，以顯著粗體顯示摘要數字 |
| **[!UICONTROL 可見圖例]** | 顯示或隱藏視覺效果底部的圖例 |
| **[!UICONTROL 顯示註解]** | 顯示或隱藏管理員新增的註解 |
| **[!UICONTROL 顯示走勢圖]** | 顯示或隱藏圖表底部的折線圖。隱藏時，圖例將會變更，以不再參考線條 |
| **[!UICONTROL 在走勢圖上顯示最小值和最大值]** | 在主要和比較折線圖上顯示或隱藏最小值和最大值 |
| **[!UICONTROL 顯示比較]** | 顯示或隱藏比較資料。隱藏時，比較折線圖和摘要變更物件將會隱藏起來。 |
| **[!UICONTROL 顯示總數]** | 顯示或隱藏摘要數字 |
| **[!UICONTROL 顯示原始差異]** | 顯示主要日期範圍與次要日期範圍中量度總值之間的原始差異 |
| **[!UICONTROL 縮簡值]** | 縮簡數字值，以簡化傳達的見解 (例如 20,000 -> 20K) |

## 編輯視覺效果

建置視覺效果後，您仍可編輯原始的設定。

1. 按一下視覺效果右上角的鉛筆圖示 (設定齒輪圖示旁)。

   ![視覺效果編輯圖示](assets/edit-icon.png)

   現在您會返回原始設定檢視。

1. 依偏好變更量度、主要日期範圍、比較日期範圍或篩選。
