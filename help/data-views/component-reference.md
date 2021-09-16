---
title: 標準元件參考
description: 您可以新增至任何資料檢視之所有標準元件的詳細資訊。
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 57%

---


# 標準元件參考

CJA中的大部分維度和量度都以Adobe Experience Platform資料集的結構元素為基礎。 不過，無論您使用何種連線，都有數個元件可新增至資料檢視。

[!UICONTROL 標準元件]是不是從資料集結構欄位產生，而是從系統產生的元件。需要一些系統元件才能加速Analysis Workspace中的報告功能，其他系統元件則為選用。

![標準元件](assets/standard-components.png)

## 必要的標準元件

依預設，這些必要的標準元件會新增至每個資料檢視。這對Customer Journey Analytics提供的報表功能至關重要。

| 元件名稱 | 維度或量度 | 附註 |
| --- | --- | --- |
| [!UICONTROL 人員] | 量度 | 根據[!UICONTROL Connection]中指定的人員ID。 |
| [!UICONTROL 工作階段] | 量度 | 根據資料檢視的工作階段設定。 |
| [!UICONTROL 事件] | 量度 | [!UICONTROL Connection]中所有事件資料集的列數。 |
| [!UICONTROL 分鐘] | 維度 | 指定事件發生的分鐘（無條件捨去）。 第一個維度項目是日期範圍中的第一分鐘，最後一個維度項目是日期範圍中的最後一分鐘。 |
| [!UICONTROL 小時] | 維度 | 指定事件發生的小時（無條件捨去）。 第一個維度項目是日期範圍中的第一小時，最後一個維度項目是日期範圍中的最後一小時。 |
| [!UICONTROL 日] | 維度 | 特定事件發生的當天。 第一個維度項目是日期範圍中的第一天，最後一個維度項目是日期範圍中的最後一天。 |
| [!UICONTROL 週] | 維度 | 特定事件發生的周。 第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。 |
| [!UICONTROL 月] | 維度 | 特定事件發生的月份。 第一個維度項目是日期範圍中的第一個月，最後一個維度項目是日期範圍中的最後一個月。 |
| [!UICONTROL 季度] | 維度 | 特定事件發生的季度。 第一個維度項目是日期範圍中的第一季，最後一個維度項目是日期範圍中的最後一季。 |
| [!UICONTROL 年] | 維度 | 特定事件發生的年份。 第一個維度項目是日期範圍中的第一年，最後一個維度項目是日期範圍中最近的一年。 |

## 可選標準元件

可選標準元件位於&#x200B;**[!UICONTROL 資料視圖]** > **[!UICONTROL 編輯資料視圖]** > **[!UICONTROL 元件]**&#x200B;頁簽> **[!UICONTROL 標準元件]**&#x200B;頁簽下。

| 元件名稱 | 維度或量度 | 附註 |
| --- | --- | --- |
| [!UICONTROL 工作階段開始] | 量度 | 作為工作階段第一個事件的事件數。 當用於篩選定義時 (例如「[!UICONTROL 工作階段開始]存在」)，它只篩選到每個工作階段的第一個事件。 |
| [!UICONTROL 工作階段結束] | 量度 | 作為工作階段最後一個事件的事件數。 與[!UICONTROL 「工作階段開始」]類似，它也可用於篩選定義中，以篩選至每個工作階段的最後一個事件。 |
| [!UICONTROL 逗留時間 (秒)] | 量度 | 一個維度的兩個不同值之間時間的總和。 |
| [!UICONTROL 每個事件逗留時間] | 維度 | 將[!UICONTROL 逗留時間]量度貯體至[!UICONTROL Event]貯體。 |
| [!UICONTROL 每個工作階段逗留時間] | 維度 | 將[!UICONTROL 逗留時間]量度貯體至[!UICONTROL 工作階段]貯體。 |
| [!UICONTROL 每人逗留時間] | 維度 | 將[!UICONTROL 逗留時間]量度貯體至[!UICONTROL Person]貯體。 |
| [!UICONTROL 批次 ID]  | 維度 | 表示「[!UICONTROL 事件]」所屬的 Experience Platform 批次。 |
| [!UICONTROL 資料集 ID] | 維度 | 表示「[!UICONTROL 事件]」所屬的 Experience Platform 資料集。 |
