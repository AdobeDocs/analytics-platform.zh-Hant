---
title: 範圍元件設定
description: 設定元件在母體總計報表中的範圍設定方式。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
source-git-commit: a4f7eef26a019f4f8a716f44d49985290b135112
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 4%

---


# 範圍元件設定 {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="範圍"
>abstract="決定元件在報告中使用時的範圍界定。 您可以選取事件型、設定檔型或總計型。"

量度元件的範圍會決定該元件在報表中的使用方式。

| 範圍 | 說明 |
|---|---|
| 以事件為基礎 | 量度元件的範圍以事件為基礎。 |
| 以設定檔為基礎 | 量度元件的範圍以設定檔為基礎。 在報告中使用元件時，日期範圍會從設定檔資料傳回母體，無論套用至面板的日期範圍為何。 日期篩選器和日期範圍比較不會影響此量度的報表。 |
| 以總數為基礎 | 量度元件的範圍以設定檔和事件為基礎。 當報告中使用元件時，無論套用至面板的日期範圍為何，量度都會從您的設定檔和事件資料傳回母體。 日期篩選器和日期範圍比較不會影響此量度的報表。 |

