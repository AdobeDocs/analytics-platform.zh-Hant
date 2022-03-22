---
title: 檢視註解
description: 如何在工作區中檢視註解。
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 998cc9e5f8d2ffd3964078dc389f55bb573063b9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 79%

---

# 檢視註解

>[!NOTE]
>
>此功能目前在有限測試中。

根據註解跨越一天還是跨越日期範圍，註解的體現方式略有不同。

## 在線圖或表格中檢視註解

| 日期 | 外觀 |
| --- | --- |
| **一天** | ![](assets/single-day.png)<p>當您將滑鼠停留在註解上時，您可以查看其詳細資料，您可以透過選取鋼筆圖示對其進行編輯，也可以將其刪除：<p> ![](assets/hover.png) |
| **日期範圍** | 圖示會變更，而且當滑鼠游標停留在圖示上方時，日期範圍就會出現。<p>![](assets/multi-day.png)<p>當您在折線圖上將其選取時，註解中繼資料隨即顯示，您可以對其進行編輯或將其刪除：![](assets/multi-hover.png)<p>在表格中，日期範圍內的每個日期都會出現圖示。<p>![](assets/multi-day-table.png) |
| **重疊註解** | 在有一個以上關聯註解的日期，圖示會以灰色顯示。<p>![](assets/grey.png)<p>當您將滑鼠停留在該灰色圖示上時，會顯示所有重疊的註解：<p>![](assets/overlap.png) |

## 在 .pdf 檔案中檢視註解

由於在 .pdf 檔案中滑鼠游標無法停留在圖示上方，此檔案 (在匯出後) 會在面板底部提供解釋說明。其範例如下：

![](assets/ann-pdf.png)

## 查看具有非趨勢資料的注釋

有時，注釋用非趨勢資料顯示，但與特定尺寸相關聯。 在此情況下，註解只會出現在右下角的摘要註解中。 其範例如下：

![](assets/non-date.png)

摘要圖表顯示在拐角中的所有可視化類型中，而不僅顯示在非趨勢的自由形式表和摘要數字中。 它也出現在可視化中，如 [!UICONTROL 甜甜圈]。 [!UICONTROL 流]。[!UICONTROL 放射性]。[!UICONTROL 隊列]等等。

![](assets/ann-summary.png)