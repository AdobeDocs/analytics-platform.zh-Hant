---
description: 顯示特定維度下一個或上一個維度項目的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 88%

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

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_ 中的下一個或上一個項目面板。<br/>_請參閱本文中 ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg)_&#x200B;**Adobe Analytics**&#x200B;版本的[下一個或上一個項目面板](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/panels/next-previous)_。_

>[!ENDSHADEBOX]

**[!UICONTROL 下一個或上一個項目]**&#x200B;面板包含許多表格和視覺效果，用於識別特定維度的下一個或上一個維度項目。例如，您可能想要探索客戶造訪首頁後最常造訪哪些頁面。

## 使用 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="容器"
>abstract="選取容器以確定查詢範圍。"

若要使用&#x200B;**[!UICONTROL 下一個或上一個項目]**&#x200B;面板：

1. 請建立&#x200B;**[!UICONTROL 下一個或上一個項目]**&#x200B;面板：有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入

您可以使用這些輸入設定，來設定[!UICONTROL 下一個或上一個項目]：

![下一個或上一個項目面板](assets/next-or-previous-item.png)

| 輸入 | 說明 |
| --- | --- |
| **[!UICONTROL 維度]** | 請選取您想要探索下一個或上一個項目的維度。 |
| **[!UICONTROL 維度項目]** | 請選取下一個/上一個查詢中心的特定維度項目。 |
| **[!UICONTROL 方向]** | 請指定您尋找[!UICONTROL 下一個]或[!UICONTROL 上一個]維度項目。 |
| **[!UICONTROL 容器]** | 選取容器，**[!UICONTROL 全域帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，**[!UICONTROL 帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，**[!UICONTROL 購買群組]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，**[!UICONTROL 機會]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，**[!UICONTROL 工作階段]**&#x200B;或&#x200B;**[!UICONTROL 人員]**，以決定您的查詢範圍。 |

{style="table-layout:auto"}

請選取「**[!UICONTROL 建置]**」以建置面板。

### 面板輸出

[!UICONTROL 下一個或上一個項目]面板會傳回一組豐富的資料和視覺效果，協助您更了解特定維度項目之後或之前的事件發生次數。


![下一個/上一個面板輸出](assets/next-or-previous-item-output.png)


| 視覺效果 | 說明 |
| --- | --- |
| **[!UICONTROL 橫條圖]** | 根據您選取的維度項目列出下一個 (或上一個) 項目。將游標停留在個別的條上，將會醒目提示自由格式表格中的對應項目。 |
| **[!UICONTROL 摘要數字]** | 目前月份 (迄今為止) 所有下一個或上一個維度項目顯示發生次數的高階摘要數字。 |
| **[!UICONTROL 自由格式表格]** | 根據您選取的維度項目以表格格式列出下一個 (或上一個) 項目。例如，在前往首頁或工作區頁面之後 (或之前)，哪些是人員造訪最受歡迎的頁面 (根據發生次數)。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[建立面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
