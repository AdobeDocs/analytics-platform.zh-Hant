---
title: 建立日期範圍
description: 建立日期範圍以用於報告。
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 10%

---


# 建立日期範圍

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

您可以使用下列兩種方法之一來建立自訂日期範圍：

* 按一下左側日期範圍元件清單旁的「`+`」按鈕，即可直接在工作區專案中
* 在日期範圍管理員中

要在日期範圍管理器中建立日期範圍，請執行以下操作：

1. 使用您的AdobeID認證登入[analytics.adobe.com](https://analytics.adobe.com)。
1. 導覽至「[!UICONTROL 元件] > [!UICONTROL 日期範圍]」。
1. 按一下「新增」按鈕，以開啟建立日期範圍的模式視窗。

## 建立日期範圍模式視窗

模型窗口包含四個可編輯的欄位：

* **日期範圍**:您要此元件的日期範圍。
* **標題**:您要用於此元件的名稱。標題用於工作區專案。
* **說明**:您需要此元件的說明。按一下![i](../assets/i.png)表徵圖時將顯示說明。
* **標籤**:使用標籤來組織您的日期範圍。日期範圍可屬於多個標籤。

## 選擇日期範圍

在模式視窗中按一下日期範圍時，您有幾個選項：

* **日曆**:選擇開始和結束日期。
* **使用遞延日期**:如果您希望日期範圍隨時間而變更，請勾選此方塊。如果您希望日期範圍保持靜態，請勿勾選此方塊。
* **選擇預設**:如果您想要根據預設的Adobe選件範圍來自訂日期範圍，請使用此下拉式清單。當您選取預設集時，您可以進一步自訂日期範圍以符合您的需求。 它不會影響Adobe提供的預設集。

## 滾動日期範圍

如果您想要滾動日期範圍，可以在滾動日期範圍時進行自定義。 您可以控制開始和結束日期彼此獨立進行的時間。

* **日期開始時**:選擇日期是從時段的開始、時段的結束開始，還是使用固定日期。
* **使用的時段**:選擇日期範圍的滾動頻率。您可以讓它每天、每週、每月、每季或每年都能捲動。
* **偏移**:選擇日期範圍的偏移。您可以新增或減去日、周、月、季或年。

## 滾動日期示例

某些日期範圍在某些報表中很實用。

年初至今：

```text
Start: Start of current year
End: End of current day
```

上星期四到本星期四：

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

會計年度（例如，如果會計年度從12月開始）

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
