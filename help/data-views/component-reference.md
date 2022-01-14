---
title: 標準元件參考
description: 您可以新增到任何資料檢視的所有標準元件的詳細資料和資訊。
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
source-git-commit: b4d2c564f9fc477212306dc022b4afc5ab92db97
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 92%

---

# 標準元件參考

CJA 中的大多數維度和量度都根據 Adobe Experience Platform 資料集中的結構描述元素。但是，無論您使用何種連線，都可以將多個元件新增到資料檢視中。

[!UICONTROL 標準元件]是不是從資料集結構欄位產生，而是從系統產生的元件。需要一些系統元件，以利 Analysis Workspace 的報告功能，而其他系統元件則是選用的。

![標準元件](assets/standard-components.png)

## 必要標準元件

依預設，這些必要的標準元件會新增至每個資料檢視。它們對於 Customer Journey Analytics 提供的報告功能至關重要。

| 元件名稱 | 維度或量度 | 附註 |
| --- | --- | --- |
| [!UICONTROL 人員] | 量度 | 根據[!UICONTROL 連線]中所指定的人員 ID。 |
| [!UICONTROL 工作階段] | 量度 | 根據資料檢視的工作階段設定。 |
| [!UICONTROL 事件] | 量度 | [!UICONTROL 連線]中所有事件資料集的列數。 |
| [!UICONTROL 分鐘] | 維度 | 指定事件發生的分鐘 (無條件捨去)。第一個維度項目是日期範圍中的第一分鐘，最後一個維度項目是日期範圍中的最後一分鐘。 |
| [!UICONTROL 小時] | 維度 | 指定事件發生的小時 (無條件捨去)。第一個維度項目是日期範圍中的第一小時，最後一個維度項目是日期範圍中的最後一小時。 |
| [!UICONTROL 日] | 維度 | 指定事件發生的天。第一個維度項目是日期範圍中的第一天，最後一個維度項目是日期範圍中的最後一天。 |
| [!UICONTROL 週] | 維度 | 指定量度發生的週。第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。 |
| [!UICONTROL 月] | 維度 | 指定量度發生的月。第一個維度項目是日期範圍中的第一個月，最後一個維度項目是日期範圍中的最後一個月。 |
| [!UICONTROL 季度] | 維度 | 指定量度發生的季。第一個維度項目是日期範圍中的第一季，最後一個維度項目是日期範圍中的最後一季。 |
| [!UICONTROL 年] | 維度 | 指定量度發生的年。第一個維度項目是日期範圍中的第一年，最後一個維度項目是日期範圍中最近的一年。 |

## 可選標準元件

可選的標準元件位於「**[!UICONTROL 資料檢視]** > **[!UICONTROL 編輯資料檢視]** > **[!UICONTROL 元件]** tab > **[!UICONTROL 標準元件]**」標籤下。

| 元件名稱 | 維度或量度 | 附註 和值 |
| --- | --- | --- |
| [!UICONTROL 上午/下午] | 時間分段維度 | 上午或下午 |
| [!UICONTROL 批次 ID]  | 維度 | 表示「[!UICONTROL 事件]」所屬的 Experience Platform 批次。 |
| [!UICONTROL 資料集 ID] | 維度 | 表示「[!UICONTROL 事件]」所屬的 Experience Platform 資料集。 |
| [!UICONTROL 日期] | 時間分段維度 | 1-31 |
| [!UICONTROL 星期] | 時間分段維度 | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| [!UICONTROL 一年當中的第幾天] | 時間分段維度 | 1-366 |
| [!UICONTROL 小時] | 時間分段維度 | 0-23 |
| [!UICONTROL  月份] | 時間分段維度 | 1月 — 12月 |
| [!UICONTROL 人員 ID] | 維度 | 在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。其中任何一個都可當作人員 ID 使用。範例包括 Cookie ID、彙整 ID、使用者 ID、追蹤代碼等。此 [!UICONTROL 人員ID] 維度是合併資料集並識別CJA中不重複訪客的基礎。 |
| [!UICONTROL 人員ID命名空間] | 維度 | 哪個ID類型 [!UICONTROL 人員ID] 包含。 範例： `email address`, `cookie ID`, `Analytics ID`、等 |
| [!UICONTROL 季別] | 時間分段維度 | 第 1 季、第 2 季、第 3 季、第 4 季 |
| [!UICONTROL 工作階段開始] | 量度 | 工作階段中第一個事件的事件數。當用於篩選定義時 (例如「[!UICONTROL 工作階段開始]存在」)，它只篩選到每個工作階段的第一個事件。 |
| [!UICONTROL 工作階段結束] | 量度 | 工作階段中最後一個事件的事件數。與[!UICONTROL 「工作階段開始」]類似，它也可用於篩選定義中，以篩選至每個工作階段的最後一個事件。 |
| [!UICONTROL 逗留時間 (秒)] | 量度 | 為維度加總兩個不同值之間的時間。 |
| [!UICONTROL 每個事件逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 事件]」值區。 |
| [!UICONTROL 每個工作階段逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 工作階段]」值區。 |
| [!UICONTROL 每人逗留時間] | 維度 | 將「[!UICONTROL 逗留時間]」量度儲存至「[!UICONTROL 人員]」值區。 |
| [!UICONTROL 週末]/[!UICONTROL 工作日] | 時間分段維度 | 週末或平日 |
