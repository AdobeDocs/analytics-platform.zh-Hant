---
description: 使用日曆和資料範圍來指定 Analysis Workspace 中的日期範圍。
title: 日期範圍概觀
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 100%

---

# 日期範圍概觀

在 Workspace 專案中，您通常會使用[面板中的行事曆](/help/analysis-workspace/c-panels/panels.md#calendar)來指定該面板中視覺效果的日期範圍。

日期範圍元件可讓您定義和覆蓋面板的行事曆設定。

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/3445840?captions=chi_hant&format=jpeg)

{{videoaa}}
+++

-->

## 使用日期範圍

您可以使用日期範圍元件來重新定義面板的行事曆。

或者，您可以使用自由格式表格中的日期範圍作為量度或維度。

![日期範圍使用](/help/components/date-ranges/assets/date-ranges-usage.png)

- **量度**。 例如，比較兩個不同月份特定量度的維度。
- **維度**。 比較日期範圍維度上的不同維度項目量度。

>[!NOTE]
>
>當您在自由格式表中使用日期範圍時，日期範圍會覆寫自由格式表格所屬面板指定的行事曆。
>

使用日期範圍的方式與[使用任何元件](/help/components/overview.md#analysis-workspace-components)的方式一樣。您從![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL 日期範圍]** 元件面板將日期範圍拖曳到：

- **[!UICONTROL 行事曆]**：您使用日期範圍![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;目前的行事曆設定。
- **量度欄標題**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;量度，![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**日期範圍作為量度，或使用日期範圍元件來![篩選](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;篩選&#x200B;]**量度。
- **維度欄標題**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;目前的維度。現在的新維度是&#x200B;**[!UICONTROL 日期範圍]**。只要維度是日期範圍，您就可以![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**其他日期範圍作為維度項目。
- **維度項目**：您可依日期範圍![劃分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 劃分]**&#x200B;特定維度項目。

您也可以直接在自由格式表格視覺效果中新增日期範圍欄：

1. 在量度欄中，從內容選單中選取：

   - **[!UICONTROL 新增時段欄]**。您可以在根據目前行事曆的建議選項中選取，或建立[自訂日期範圍](#custom-date-ranges)。
   - **[!UICONTROL 比較時段]**。 您可以在根據目前行事曆的建議選項中選取，或建立[自訂日期範圍](#custom-date-ranges)。

1. 根據您的選擇，額外的日期範圍欄將會新增至自由格式表格中。

## 預設日期範圍

Analysis Workspace 提供許多預設的日期範圍。


| 日 | 週 | 月 | 季 | 年 |
|---|---|---|---|---|
| 今天 | 本週 | 本月 | 本季度 | 今年 |
| 昨天 | 本週 (不含今天) | 本月 (不含今天) | 本季 (不含今天) | 今年 (不含今天) |
| 2 天前 | 2 週前 | 2 個月前 |   |  |
| 3 天前 | 3 週前 | 3 個月前 |  | |
| 最近 7 天 | 上週 | 上個月 | 上一季 | 去年 |
| 最近 14 天 | 過去完整 2 週 | 過去 2 個月整 | 過去完整 4 季 | |
| 最近 30 天 | 過去完整 3 週 | 過去 3 個月整 | | |
| 最近 60 天 | 過去完整 4 週 | 過去 6 個月整 | | |
| 最近 90 天 | 過去完整 12 週 | 過去 12 個月整 | | |
| 過去完整 7 天 | 過去完整 52 週 | 過去 13 個月整 | | |
| 過去完整 14 天 | | | | |
| 過去完整 30 天 | | | | |
| 過去完整 90 天 | | | | |

<table style="table-layout:fixed">

## 自訂日期範圍

您可以建立專屬的自訂日期範圍。有關建立日期範圍時可使用的各種選項，請參閱[建立日期範圍](/help/components/date-ranges/create.md)。然後，您可以在[日期範圍產生器](create.md#date-range-builder)中建立、修改和儲存日期範圍。

您可以使用[日期範圍管理器](manage.md)來管理日期範圍。
