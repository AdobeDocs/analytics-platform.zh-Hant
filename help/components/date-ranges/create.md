---
title: 建立日期範圍
description: 選擇日期範圍，以便在報告中使用。
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 97%

---

# 建立日期範圍


任何人都可以建立自訂日期範圍。您可以透過以下方式建立日期範圍：

![建立附註](assets/create-date-range.png)

* **A**：在主介面中選取「**[!UICONTROL 元件]**」，然後選取「**[!UICONTROL 日期範圍]**」。從[[!UICONTROL 日期範圍]管理員](/help/components/date-ranges/manage.md)中選取 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]**。
* **B**：在工作區專案內，從視覺效果的內容選單中選取「**[!UICONTROL 自訂日期範圍至此日期範圍]**」。
* **C**：在 Workspace 專案內，從選單中選取「**[!UICONTROL 元件]**」，然後選取「**[!UICONTROL 建立日期範圍]**」。
* **D**：在 Workspace 專案內，使用快速鍵 **[!UICONTROL Ctrl+Shift+d]** (Windows) 或 **[!UICONTROL Shift+Command+d]** (macOS)。
* **E**：在工作區專案內，從元件左側面板![行事曆](/help/assets/icons/Calendar.svg)**日期範圍**&#x200B;中選取「![新增](/help/assets/icons/Add.svg)」。
* **F**：在支援的視覺效果，例如折線視覺效果中，從資料點的內容選單中選取「**[!UICONTROL 註解選取]**」。

您可以使用[[!UICONTROL 日期範圍產生器]](#annotation-builder)來定義註解。

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 日期範圍產生器 {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="結束時間"
>abstract="結束時間始終會包含 59 秒。"

<!-- markdownlint-enable MD034 -->




 **[!UICONTROL 新日期範圍]**&#x200B;或&#x200B;**[!UICONTROL 編輯日期範圍]**&#x200B;對話框是用來建立新的日期範圍或編輯現有日期範圍。

![註解詳細資料視窗，顯示下一節說明的欄位和選項。](assets/edit-date-range.png)


1. 為日期範圍指定&#x200B;**[!UICONTROL 標題]**。例如，**[!UICONTROL 每個季度]**。
1. 另外，要註明&#x200B;**[!UICONTROL 說明]**。
1. 透過建立或套用一個或多個&#x200B;**[!UICONTROL 標記]**&#x200B;來整理區段。開始輸入內容以尋找您可以選取的現有標記。或按一下 **[!UICONTROL ENTER]** 以新增新標記。選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標記。 |
1. 首先選取開始日期，然後選取結束日期來選取&#x200B;**[!UICONTROL 日期範圍]**。或者，您也可以從&#x200B;[!UICONTROL *選取預設集*]&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 預設集]**。

1. 或者，選取&#x200B;**[!UICONTROL 顯示進階設定]**&#x200B;以進行：

   * 指定&#x200B;**[!UICONTROL 開始時間]**&#x200B;和&#x200B;**[!UICONTROL 結束時間]** (預設值 `12:00 AM` (`0:00`) 和 `11:59 PM` (`23:59`) 除外)。結束時間始終會包含 59 秒。對於涵蓋很多天的日期範圍，則開始時間適用於日期範圍的第一天，而結束時間則適用於日期範圍的最後一天。使用 **[!UICONTROL (重設時間值)]** 將開始和結束時間重設為預設值。
   * **[!UICONTROL 使用遞延日期]**。如果啟用，預設的日期範圍，例如&#x200B;**[!UICONTROL 前 7 個整天]**&#x200B;會隨著目前日期和時間的進展而動態更新。如果停用，此類預設集一旦套用就不會更新。

     您可以選取括號中的文字 (例如&#x200B;**[!UICONTROL 固定開始 - 每個季度遞延]**) 以延長面板並指定&#x200B;**[!UICONTROL 開始]**&#x200B;和&#x200B;**[!UICONTROL 結束]**&#x200B;的詳細資訊。

     ![遞延日期](assets/rolliing-dates.png)

      1. 選取&#x200B;**[!UICONTROL 開始於]**、**[!UICONTROL 結束於]**，或&#x200B;**[!UICONTROL 固定日期]**。
      1. 當您已選取&#x200B;**[!UICONTROL 開始於]**&#x200B;或&#x200B;**[!UICONTROL 結束於]**，您可以建置完整的運算式。例如： ******[!UICONTROL 本季]****[!UICONTROL 結束減去]** `20` **[!UICONTROL 天]**。為運算式的個別部分選擇適當的值。
         * 選取目前的值。例如&#x200B;**[!UICONTROL 目前季度]**。
         * 選取一個值進行其他計算。例如， **[!UICONTROL 減去]**。
         * 當您指定其他計算時，請指定一個值。例如，`20`。
         * 當您已指定其他計算時，請選取用於計算的時段。例如， **[!UICONTROL 天]**。

     選取&#x200B;**[!UICONTROL 隱藏詳細資訊]**&#x200B;以隱藏遞延日期計算的詳細資訊。

1. 選取：
   * **[!UICONTROL 儲存]**&#x200B;以儲存日期範圍。
   * **[!UICONTROL 另存新檔]**&#x200B;以儲存日期範圍的副本。
   * **[!UICONTROL 取消]**&#x200B;以取消對日期範圍所做的任何變更，或取消新日期範圍的建立。


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->
