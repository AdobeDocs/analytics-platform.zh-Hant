---
description: 顯示特定維度的下一個或上一個維度專案的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 36%

---

# 下一個或上一個項目面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="下一個或上一個項目"
>abstract="建立一個面板來了解人們來自的前一個維度或人們前往的下一個維度。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="下一個或上一個項目"
>abstract="分析訪客之前最常來自什麼地方或接下來最常造訪什麼地方。<br/><br/>**維度**：選取維度。例如，**頁面**。<br/>**維度項目**：選取特定維度項目。例如，**首頁**。<br/>**方向**：選取「**下一個**」可查看緊接在所選維度項目之後的維度項目。選取「**上一個**」以查看您所選維度項目之前的維度項目。<br/>**容器**：選取「**工作階段**」以查看同一工作階段中的下一個/上一個維度項目，或選取「**人員**」查看同一個人的下一個/上一個維度項目。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*本文會記錄&#x200B;**Customer Journey Analytics**中的下一個或上一個專案面板。 檢視此文章的&#x200B;**Adobe Analytics**版本的[下一個或上一個專案面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous)。*

>[!ENDSHADEBOX]

**[!UICONTROL 下一個或上一個專案]**&#x200B;面板包含許多表格和視覺效果，可識別特定維度的下一個或上一個維度專案。 例如，您可能會想要探索客戶在造訪首頁後最常前往哪些頁面。

## 使用

若要使用&#x200B;**[!UICONTROL 下一個或上一個專案]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 下一個或上一個專案]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

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
| **[!UICONTROL 自由格式表格]** | 根據您選取的維度專案，以表格格式列出下一個（或上一個）專案。 例如，在首頁或Workspace頁面之後（或之前），人們最常前往的頁面（依發生次數而定）。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
