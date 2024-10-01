---
title: 日期範圍總覽
description: 了解日期範圍以及您如何在報告中使用它們。
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 21%

---

# 日期範圍總覽

在Workspace專案中，您通常使用面板](/help/analysis-workspace/c-panels/panels.md#calendar)中的[行事曆來指定該面板中視覺效果的日期範圍。

日期範圍元件可讓您定義和覆寫面板的行事曆設定。

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## 使用日期範圍

您可以使用日期範圍元件來重新定義面板的行事曆。

或者，您也可以將自由表格中的日期範圍當做量度或維度使用。

![日期範圍使用狀況](/help/components/date-ranges/assets/date-ranges-usage.png)

- **量度**。 例如，比較特定量度兩個不同月份的維度。
- **Dimension**。 若要比較日期範圍維度中不同維度專案的量度。

>[!NOTE]
>
>當您在自由表格中使用日期範圍時，日期範圍會覆寫為自由表格所屬的面板指定的行事曆。
>

您可以使用日期範圍，就像[使用任何元件](/help/components/overview.md#analysis-workspace-components)一樣。 您從![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL 日期範圍]**&#x200B;元件面板拖曳日期範圍，並將元件放置在：

- **[!UICONTROL 行事曆]**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 將]**&#x200B;目前的行事曆組態取代為日期範圍。
- **量度資料行標題**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;量度、![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**日期範圍為量度，或使用日期範圍元件![篩選](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;篩選&#x200B;]**量度。
- **資料行標題** Dimension：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;目前的維度。 新維度現在是&#x200B;**[!UICONTROL 日期範圍]**。 一旦維度是日期範圍，您就可以將![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**額外的日期範圍作為維度專案。
- **Dimension專案**：您![劃分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 按日期範圍劃分]**&#x200B;特定維度專案。

您也可以直接在自由格式表格視覺效果中新增日期範圍欄：

1. 在量度欄中，從內容功能表選取：

   - **[!UICONTROL 新增時段資料行]**。 您可以選取以目前行事曆為基礎的建議選項，或建立[自訂日期範圍](#custom-date-ranges)。
   - **[!UICONTROL 比較時段]**。 您可以選取以目前行事曆為基礎的建議選項，或建立[自訂日期範圍](#custom-date-ranges)。

1. 系統會根據您的選取範圍，將其他日期範圍欄新增至自由表格。

## 預設日期範圍

Analysis Workspace提供數個預設日期範圍。


| 日 | 週 | 月 | 季 | 年 |
|---|---|---|---|---|
| 今天 | 本週 | 本月 | 本季 | 今年 |
| 昨天 | 本週 (不含今天) | 本月 (不含今天) | 本季 (不含今天) | 今年 (不含今天) |
| 2天前 | 2 週前 | 2個月前 |   |  |
| 3天前 | 3 週前 | 3個月前 |  | |
| 最近 7 天 | 上週 | 上個月 | 上一季 | 去年 |
| 最近 14 天 | 過去完整 2 週 | 過去2個月 | 過去完整 4 季 | |
| 最近 30 天 | 過去完整 3 週 | 過去3個月 | | |
| 最近 60 天 | 過去完整 4 週 | 過去6個月 | | |
| 最近 90 天 | 過去完整 12 週 | 過去12個月 | | |
| 過去完整 7 天 | 過去完整 52 週 | 過去13個月 | | |
| 過去完整 14 天 | | | | |
| 過去完整 30 天 | | | | |
| 過去完整 90 天 | | | | |

<table style="table-layout:fixed">

## 自訂日期範圍

您可以建立自己的自訂日期範圍。 請參閱[建立日期範圍](/help/components/date-ranges/create.md)，以瞭解各種可用來建立日期範圍的選項。 接著在[日期範圍產生器](create.md#date-range-builder)中建立、修改和儲存日期範圍。

您使用[日期範圍管理員](manage.md)來管理日期範圍。
