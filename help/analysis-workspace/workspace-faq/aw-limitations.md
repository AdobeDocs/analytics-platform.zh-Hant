---
description: Adobe Analysis Workspace 及其相關元件的已知限制清單：
title: Analysis Workspace 的已知限制
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 當將篩選器用作表的行時，將禁用從選擇建立度量。 此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。
* [!UICONTROL 貢獻分析]_只能_&#x200B;在[!UICONTROL 每日]粒度下執行，無法針對[!UICONTROL 每小時]、[!UICONTROL 每週]等粒度的資料執行。

## 視覺效果

* 利用濾鏡的可視化效果，如 [!UICONTROL 放射性]。 [!UICONTROL 流]。 [!UICONTROL 隊列], [!UICONTROL 直方圖]，無法接受計算度量作為輸入。
* [!UICONTROL 流量]：「登入/退出」維度 (例如[!UICONTROL 「登入頁面」]) 無法用於「流量」。
* [!UICONTROL 同類群組]：非整數無法當作同類群組條件使用。

## 「元件」>「篩選器」

* 無法篩選某些度量和維，如 [!UICONTROL 具體值]。 [!UICONTROL 獨特訪問者]的子菜單。
* 在 [面板落點](/help/analysis-workspace/c-panels/panels.md) 將不顯示在「工作區」(Workspace)或「過濾器」(Filter)元件管理器的左滑軌中，除非它們被公開。 可以通過編輯篩選器和選擇 **[!UICONTROL 將此篩選器設為公共]**。

## 元件 > 計算量度

* 計算量度無法使用於特定視覺效果中。請參閱上方的「視覺效果」。
* 計算量度無法用於[!UICONTROL 「歸因」]面板，因為計算量度本身就可包含個別的歸因模型。
* 如果從工作區建立計算度量(而不是從 [!UICONTROL 元件>篩選器])。 例如 [!UICONTROL IP 位址]。

## 元件 > 日期範圍

* 自訂日期範圍不支援[!UICONTROL 「去年的今天」]、[!UICONTROL 「上個月的今天」]等。


## 元件 > 報表設定

* [!UICONTROL 「報表設定」]頁面上的某些設定並不適用。Analysis Workspace 僅會使用以下幾種位於底部的[!UICONTROL 「語言/貨幣/編碼」]設定：[!UICONTROL 「千位分隔符號」]、[!UICONTROL 「排程報表編碼」]和[!UICONTROL 「CSV 分隔符號字元」]。

## 歸因 IQ

* 有一組量度子集不受[!UICONTROL 歸因 IQ] 支援。如需完整清單，請參閱[歸因 IQ 常見問答](../attribution/faq.md)。
