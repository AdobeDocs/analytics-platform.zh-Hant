---
title: 建立日期範圍
description: 選擇日期範圍，以便在報告中使用。
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '436'
ht-degree: 100%

---

# 建立日期範圍

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[了解更多...](/help/getting-started/cja-aa.md)

您可以使用下列兩種方法之一來建立自訂日期範圍：

* 按一下左邊日期範圍元件清單旁的 `+` 按扭，即可直接在 Workspace 專案中建立
* 在日期範圍管理器中建立

要在日期範圍管理器中建立日期範圍：

1. 使用您的 AdobeID 憑證登入 [analytics.adobe.com](https://analytics.adobe.com)。
1. 導覽至[!UICONTROL 元件] > [!UICONTROL 日期範圍]。
1. 按一下「[!UICONTROL 新增]」按鈕以開啟建立日期範圍的模型視窗。

## 建立日期範圍模型視窗

模型視窗有四個可編輯的欄位：

* **日期範圍**：您要為此元件設定的日期範圍。
* **標題**：您要用於此元件的名稱。標題用於 Workspace 專案。
* **說明**：您要為此元件設定的說明。按一下 ![i](../assets/i.png) 圖示即可看到說明。
* **標籤**：使用標籤來組織您的日期範圍。日期範圍可屬於多個標籤。

## 選擇日期範圍

在模型視窗中按一下日期範圍時，您有幾個選項：

* **日曆**： 選擇開始和結束日期。
* **使用遞延日期**：如果您希望日期範圍隨時間而變更，請勾選此方框。如果您希望日期範圍保持靜態，請勿勾選此方框。
* **選擇預設**：如果您想要 Adobe 根據預設提供的範圍來自訂日期範圍，請使用此下拉選單。當您選取預設集時，您可以進一步自訂日期範圍以符合您的需求。它不會影響 Adobe 提供的預設集。

## 遞延日期範圍

如果您想要遞延日期範圍，可以在日期範圍遞延時進行自訂。您可以控制開始和結束日期各自獨立遞延的時間。

* **當日期開始時**：選擇讓日期從一個時段的開頭開始、從一個時段結束時開始，或使用固定日期。
* **使用的時段**：選擇日期範圍遞延的頻率。您可以讓它每天、每週、每月、每季或每年都能遞延。
* **偏移**：選擇日期範圍的偏移。您可以增減其日數、週數、月數、季數或年數。

## 遞延日期範例

有些日期範圍可用於特定的報告。

年初至今：

```text
Start: Start of current year
End: End of current day
```

上週四至本週四：

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

會計年度 (例如，如果會計年度始於十二月)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
