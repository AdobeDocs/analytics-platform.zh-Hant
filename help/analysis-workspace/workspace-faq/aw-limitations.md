---
description: Adobe Analysis Workspace 及其相關元件的已知限制清單：
title: Analysis Workspace 的已知限制
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: a69f9eef39c0eceee1964a3b8741b7538b218ece
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 88%

---

# Analysis Workspace 的已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 篩選器在表格中設為列時，「從選取項目建立量度」功能會遭停用。此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。
* [!UICONTROL 貢獻分析]_只能_&#x200B;在[!UICONTROL 每日]粒度下執行，無法針對[!UICONTROL 每小時]、[!UICONTROL 每週]等粒度的資料執行。

## 視覺效果

* 運用[!UICONTROL 「流失」]、[!UICONTROL 「流量」]、[!UICONTROL 「同類群組」]、[!UICONTROL 「長條圖」]等篩選器的視覺效果，無法將計算量度設為輸入項目。
* [!UICONTROL 流量]：「登入/退出」維度 (例如[!UICONTROL 「登入頁面」]) 無法用於「流量」。
* [!UICONTROL 同類群組]：非整數無法當作同類群組條件使用。

## 元件 > 篩選器

* [!UICONTROL 「發生次數」]、[!UICONTROL 「不重複訪客」]等特定量度和維度無法進行篩選。
* 在 [面板放置區](/help/analysis-workspace/c-panels/panels.md) 是快速篩選的類型。 除非將它們設為公用，否則它們不會顯示在Workspace的左側邊欄或「篩選器」元件管理員中。 如需詳細資訊，請參閱 [快速篩選](/help/components/filters/quick-filters.md).

## 元件 > 計算量度

* 計算量度無法使用於特定視覺效果中。請參閱上方的「視覺效果」。
* 計算量度無法用於[!UICONTROL 「歸因」]面板，因為計算量度本身就可包含個別的歸因模型。
* 如果從 Workspace 中建立計算量度，而非經由[!UICONTROL 「元件 > 篩選器」]建立，則某些元件和運算子將無法使用。 例如 [!UICONTROL IP 位址]。

## 元件 > 日期範圍

* 自訂日期範圍不支援[!UICONTROL 「去年的今天」]、[!UICONTROL 「上個月的今天」]等。


## 元件 > 報表設定

* [!UICONTROL 「報表設定」]頁面上的某些設定並不適用。Analysis Workspace 僅會使用以下幾種位於底部的[!UICONTROL 「語言/貨幣/編碼」]設定：[!UICONTROL 「千位分隔符號」]、[!UICONTROL 「排程報表編碼」]和[!UICONTROL 「CSV 分隔符號字元」]。

