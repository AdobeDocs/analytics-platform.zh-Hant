---
description: Adobe提供您能使用的各種計算量度。 此頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 27%

---

# 預設計算量度

Customer Journey Analytics提供下列計算量度，以涵蓋最常見的使用案例：

| 計算量度名稱 | 說明 | 公式 |
|---------|----------|---------|
| 工作階段開始率 | 任何維度專案在工作階段的第一個事件發生百分比。<p>當您納入以下專案時，此計算量度會自動新增至工作區 `[Session Starts]` [標準元件](/help/data-views/component-reference.md) 在您的 [資料檢視](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| 每人逗留時間 | 一個人在任何特定維度項目上的平均逗留時間。<p>當您納入以下專案時，此計算量度會自動新增至工作區 `[Time Spent (seconds)]` [標準元件](/help/data-views/component-reference.md) 在您的 [資料檢視](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| 每人工作階段數 | 每人平均工作階段數。 | `[Sessions] / [Users]` |
| 每工作階段逗留時間 | 一個人每工作階段在任何特定維度項目上的平均逗留時間。<p>當您納入以下專案時，此計算量度會自動新增至工作區 `[Time Spent (seconds)]` [標準元件](/help/data-views/component-reference.md) 在您的 [資料檢視](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| 工作階段結束率 | 任何維度專案在工作階段的最後一個事件發生百分比。 <p>當您納入以下專案時，此計算量度會自動新增至工作區 `[Session Ends]` [標準元件](/help/data-views/component-reference.md) 在您的 [資料檢視](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
