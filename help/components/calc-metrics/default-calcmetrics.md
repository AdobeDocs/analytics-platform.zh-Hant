---
description: Adobe提供您能使用的各種計算量度。 此頁面列出這些量度及其預期用途。
title: 計算量度範本
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: d37734ae415722fc609715868c37a36f2becdbf6
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 8%

---

# 計算量度範本

Customer Journey Analytics提供下列計算量度範本，以涵蓋最常見的使用案例。 這些Adobe定義的計算量度由小型![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg)標誌識別。 若要快速篩選這些量度，請在[元件篩選器](/help/components/overview.md#filter)中選取![標籤](/help/assets/icons/Label.svg) **[!UICONTROL Adobe範本]**。

| 計算量度名稱 | 描述<br/>公式 |
|---------|----------|
| **[!UICONTROL 工作階段開始速率]** | 任何維度專案在工作階段的第一個事件發生百分比。<p>當您在[資料檢視](/help/data-views/create-dataview.md)中加入[!UICONTROL 工作階段開始] [標準元件](/help/data-views/component-reference.md)時，此計算量度會自動新增至Workspace。</p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **工作階段開始** ![分割](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **工作階段** **）** |
| 每個人&#x200B;**[!UICONTROL 逗留時間]** | 一個人在任何特定維度項目上的平均逗留時間。<p>當您在[資料檢視](/help/data-views/create-dataview.md)中加入[!UICONTROL 逗留時間（秒）] [標準元件](/help/data-views/component-reference.md)時，此計算量度會自動新增至Workspace。 篩選工作階段排除最後一個事件會套用至「人物」量度。 篩選器會排除資料集中每個工作階段的最後一個事件。 此排除可協助您分析導致事件或動作（例如購買或表單提交）的使用者行為，同時排除最終動作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **逗留時間（秒）** ![除](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除工作階段的最後一個事件（** ![事件](/help/assets/icons/Event.svg) **人員） )** |
| 每個人的&#x200B;**[!UICONTROL 個工作階段]** | 每人平均工作階段數。<p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **工作階段** ![分割](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **人員** **）** |
| 每個工作階段逗留時間&#x200B;**** | 一個人每工作階段在任何特定維度項目上的平均逗留時間。<p>當您在[資料檢視](/help/data-views/create-dataview.md)中加入[!UICONTROL 逗留時間（秒）] [標準元件](/help/data-views/component-reference.md)時，此計算量度會自動新增至Workspace。 「工作階段排除最後一個事件」篩選器會套用至「工作階段」量度。 篩選器會排除資料集中每個工作階段的最後一個事件。 此排除可協助您分析導致事件或動作（例如購買或表單提交）的使用者行為，同時排除最終動作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **逗留時間（秒）** ![除](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除工作階段的最後一個事件（** ![事件](/help/assets/icons/Event.svg) **工作階段） )** |
| **[!UICONTROL 工作階段結束率]** | 任何維度專案在工作階段的最後一個事件發生百分比。 <p>當您在[資料檢視](/help/data-views/create-dataview.md)中加入[!UICONTROL 工作階段結束] [標準元件](/help/data-views/component-reference.md)時，此計算量度會自動新增至Workspace。</p>摘要： **（** ![事件](/help/assets/icons/Event.svg) **工作階段結束** ![分割](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **工作階段** **）** |

{style="table-layout:auto"}
