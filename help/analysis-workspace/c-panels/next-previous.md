---
description: 顯示特定維度的下一個或上一個維度專案的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 下一個或上一個項目面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="下一個或上一個專案"
>abstract="建立面板來瞭解人員來自的先前維度或前往的下一個維度。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="巢狀內嵌或上一個專案"
>abstract="分析訪客先前來自或前往下一個的最常見位置。<br/><br/>**Dimension**：選取維度。 例如&#x200B;**頁面**。<br/>**Dimension專案**：選取特定的維度專案。 例如&#x200B;**首頁**。<br/>**方向**：選取&#x200B;**下一步**，可緊接在您選取的維度專案後面檢視維度專案。 選取&#x200B;**上一步**，以檢視通往您所選維度專案的維度專案。<br/>**容器**：選取「**工作階段**」可檢視相同工作階段中的下一個/上一個維度專案，或選取「**人員**」可檢視相同人員的下一個/上一個維度專案。"

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 下一個或上一個專案]**&#x200B;面板包含許多表格和視覺效果，可識別特定維度的下一個或上一個維度專案。 例如，您可能會想要探索客戶在造訪首頁後最常前往哪些頁面。

## 使用

若要使用&#x200B;**[!UICONTROL 下一個或上一個專案]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 下一個或上一個專案]**&#x200B;面板。 如需如何建立面板的詳細資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入

您可以使用這些輸入設定來設定[!UICONTROL 下一個或上一個專案]面板：

![下一個或上一個專案面板](assets/next-or-previous-item.png)

| 輸入 | 說明 |
| --- | --- |
| **[!UICONTROL 維度]** | 選取您要探索下一個或上一個專案的維度。 |
| **[!UICONTROL 維度項目]** | 選取下次/上次查詢中心的特定維度專案。 |
| **[!UICONTROL 方向]** | 指定您要尋找[!UICONTROL Next]或[!UICONTROL Previous]維度專案。 |
| **[!UICONTROL 容器]** | 選取容器[!UICONTROL 工作階段]或[!UICONTROL 人員] （預設），以決定查詢的範圍。 |

{style="table-layout:auto"}

選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置面板。

### 面板輸出

[!UICONTROL 下一個或上一個專案]面板會傳回一組豐富的資料和視覺效果，協助您更清楚瞭解特定維度專案之後或之前的情形。


![下一個/上一個面板輸出](assets/next-or-previous-item-output.png)


| 視覺效果 | 說明 |
| --- | --- |
| **[!UICONTROL 橫條圖]** | 根據您選取的維度專案列出下一個（或上一個）專案。 將滑鼠懸停在個別長條上，會醒目顯示自由格式表格中的對應專案。 |
| **[!UICONTROL 摘要數字]** | 目前月份（到目前為止）所有下一個或上一個維度專案發生次數的高層級摘要數字。 |
| **[!UICONTROL 自由表格]** | 根據您選取的維度專案，以表格格式列出下一個（或上一個）專案。 例如，在首頁或Workspace頁面之後（或之前），人們最常前往的頁面（依發生次數而定）。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[建立面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>