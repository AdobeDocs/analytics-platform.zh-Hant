---
title: 參與檢視
description: 了解功能參與的廣度與深度。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: 8a48ad3b-fa30-497e-8306-f8d881b1a335
source-git-commit: 670443a8caf6b71f49fc63a23b5328609864a9be
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 4%

---

# [!UICONTROL 參與] 檢視

此 **[!UICONTROL 參與]** 「檢視」可讓您深入瞭解功能的使用頻率及使用人數。 將數個功能相互比較時，此分析效果最佳。 瞭解您的核心、效能、一次性和可疑功能，有助於促進投資決策。

繪製於此視覺效果頂端的功能表示它們經常用於參與的使用者。 繪製於此視覺效果右側的功能表示這些功能已在您的作用中使用者中廣泛採用。 使用特徵的中位數水準分割圖形。 作用中使用者的中位數百分比會垂直分割圖表。 媒體會根據查詢中選取的事件進行計算，而非所有資料。

* 矩陣左上角的功能為 **power** 功能；這些功能並未廣泛採用，但經常由參與的使用者使用。
* 矩陣右上角的功能是您的 **高影響力** 功能；它們都被廣泛採用且經常使用。
* 矩陣左下角的功能為 **低影響** 功能；並未廣泛使用或經常使用。
* 矩陣右下方的功能是您的 **單次** 功能；它們被廣泛採用，但不常使用。

>[!VIDEO](https://video.tv.adobe.com/v/3429489/&learn=on)

## 使用案例

此檢視型別的使用案例包括：

* **依功能的參與**：您可以在參與和採用特定功能之間建立直接關聯。 瞭解哪些功能使用最多，有助於決定哪些功能需要進一步投資。
* **探索未充分利用的功能**：活躍使用者較少但使用率高的功能可能表示電源功能，該功能很有價值，但大眾不會發現或使用。 請考慮增強這些功能的可發現性，以便讓更多使用者運用這些功能。
* **改善熱門功能**：高活躍使用者但低使用量的功能可能表示某項功能請求量高但使用量不足。 這些情況提供機會，讓您的使用者進一步瞭解哪些改善會讓功能對他們來說更有價值。
* **建立以功能為基礎的區段**：以這種方式檢視功能使用情形，以提示其他分析機會。 為圖表上的任何點建立區段，以深入探究該使用者群組，並將這些學習內容套用至您的使用者參與策略。
* **功能採用A/B測試**：比較不同使用者群組間多個功能的使用情形。 在查詢邊欄中新增區段，以決定跨主要使用者群組的功能使用差異。

## 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 事件]**：您要測量的事件。每個事件代表指定功能的使用情形，並在矩陣中顯示為點。 您最多可以包含10個事件。 系統會根據選取的事件計算中位數。
* **[!UICONTROL 計為]**：您可以沿x軸測量每日、每週、每月或每季作用中使用者的平均百分比。 Y軸會根據x軸選取範圍自動調整每個使用者的平均時間。
* **[!UICONTROL 區段]**：您要測量的區段。每個選取的區段都會將圖表中的繪圖點數和表格中的列數加倍。 您最多可以包含三個區段。

>[!TIP]
>
>如果多個事件代表單一功能的使用情形，您可以衍生新事件來代表資料檢視中的功能。

## 圖表設定

此 [!UICONTROL 參與] 檢視提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 媒體]**：決定中間線的顯示位置以及繪製點與這些中間線的關聯方式。
   * **[!UICONTROL 標準]**：顯示使用量和參與度的絕對值。
   * **[!UICONTROL 已標準化]**：顯示每個中間值的相對變化。
* **[!UICONTROL 排名在前的事件覆蓋]**：根據公司和使用者造訪間隔和相關性（與查詢邊欄中的事件選擇器套用的相同演演算法），檢視事件和前20個事件的比較結果。

## 時間比較

{{apply-time-comparison}}

## 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要用來檢視趨勢資料的日期詳細程度。 此檢視型別處理 [!UICONTROL 間隔] 類似於 [!UICONTROL 計為] 在查詢邊欄中。 不支援每小時使用中的使用者。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。
