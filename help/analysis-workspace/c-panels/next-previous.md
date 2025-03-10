---
description: 顯示特定維度的下一個或上一個維度專案的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 28%

---

# 下一個或上一個項目面板 {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="下一個或上一個項目"
>abstract="建立一個面板來了解人們來自的前一個維度或人們前往的下一個維度。"

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="下一個或上一個項目"
>abstract="分析訪客之前最常來自什麼地方或接下來最常造訪什麼地方。指定用於視覺效果的維度、維度項目、方向和容器。"



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文記錄了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_&#x200B;中的下一個或上一個專案面板。<br/>_檢視此文章的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[下一個或上一個專案面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous)。_

>[!ENDSHADEBOX]

**[!UICONTROL 下一個或上一個專案]**&#x200B;面板包含許多表格和視覺效果，可識別特定維度的下一個或上一個維度專案。 例如，您可能會想要探索客戶在造訪首頁後最常前往哪些頁面。

## 使用 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="容器"
>abstract="選取容器以確定查詢範圍。"

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
