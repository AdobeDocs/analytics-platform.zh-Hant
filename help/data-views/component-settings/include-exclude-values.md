---
title: 包含/排除值元件設定
description: 根據其值有條件地包含或排除維度項目。
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: ht
source-wordcount: '356'
ht-degree: 100%

---

# 包含/排除值元件設定 {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="包含排除值"
>abstract="篩選量度以僅對符合特定條件的值進行計數。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="包含排除值"
>abstract="縮小維度而僅包含符合特定條件的值。包含和排除會在報告中的配置和劃分前執行。判斷指定的區段邏輯是否區分大小寫。"

<!-- markdownlint-enable MD034 -->

包含排除值允許您建立依賴於維度項目值的規則。不符合您設定的條件的值在 Analysis Workspace 中會被視為不曾存在過，儘管資料仍然存在於基礎資料集中。

![資料檢視視窗重點顯示「包括排除值」](../assets/include-exclude.png)

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 設定包含/排除值] | 允許您啟用資料包含在資料檢視中的條件的核取方塊。 |
| [!UICONTROL 區分大小寫] | 在字串結構描述資料類型上可見。預設為開。此設定僅適用於「[!UICONTROL 包含/排除值]」邏輯，不適用於結果值。它允許您指定規則是否區分大小寫。 |
| [!UICONTROL 符合] | 可讓您指定在歸因和劃分之前，考慮要以哪些值產生報告 (例如，僅使用包含片語「error」的值)。您可以指定「**[!UICONTROL 如果滿足所有標準]**」或「**[!UICONTROL 如果滿足任何標準]**」。使用空格分隔每個值。 |
| [!UICONTROL 標準] | 可讓您指定應套用至特定區段的符合邏輯。<ul><li>**字串**：[!UICONTROL 包含片語]、[!UICONTROL 包含任何詞語]、[!UICONTROL 包含所有詞語]、[!UICONTROL 不包含任何詞語]、[!UICONTROL 不包含片語]、[!UICONTROL 等於]、[!UICONTROL 不等於]、[!UICONTROL 開頭為]、[!UICONTROL 結尾為]</li><li>**Double/Integer**：[!UICONTROL 等於]、[!UICONTROL 不等於]、[!UICONTROL 大於]、[!UICONTROL 小於]、[!UICONTROL 大於或等於]、[!UICONTROL 小於或等於]</li><li>**日期**：[!UICONTROL 等於]、[!UICONTROL 不等於]、[!UICONTROL 晚於]、[!UICONTROL 等於]、[!UICONTROL 發生於]</li></ul> |
| [!UICONTROL 匹配操作數] | 可讓您指定應套用匹配運算子的匹配操作數。<ul><li>**字串**：文字欄位</li><li>**雙/整數**：文字欄位，其上／下箭頭代表數值</li><li>**日期**：日詳細程度選擇器 (日曆)</li><li>**日期時間**：日期和時間詳細程度選擇器</li></ul> |
| [!UICONTROL 新增規則] | 可讓您指定額外的匹配運算子和操作數。 |

{style="table-layout:auto"}
