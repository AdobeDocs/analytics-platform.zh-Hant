---
description: Adobe 提供各種您可使用的計算量度。此頁面列出這些量度及其預期用途。
title: 計算量度範本
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 85%

---

# 計算量度範本

Customer Journey Analytics提供下列計算量度範本，以涵蓋最常見的使用案例。 這些 Adobe 定義的計算量度是透過一個小的 ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) 標誌來識別。若要快速篩選這些量度，請在![元件篩選器](/help/assets/icons/Label.svg)中選取&#x200B;**[!UICONTROL 標籤]** [Adobe範本](/help/components/overview.md#filter)。

| 計算量度名稱 | 說明<br/>公式 |
|---------|----------|
| **[!UICONTROL 工作階段開始率]** | 在第一個工作階段事件發生的任何維度項目百分比。<p>當您將「[!UICONTROL 工作階段開始]」[標準元件](/help/data-views/component-reference.md)納入您的[資料檢視](/help/data-views/create-dataview.md)時，此計算量度會自動新增至 Workspace。</p>摘要：**(** ![事件](/help/assets/icons/Event.svg) **工作階段開始** ![劃分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **工作階段** **)** |
| **[!UICONTROL 每人花費的時間]** | 一個人在任何特定維度項目上的平均逗留時間。<p>當您將「[!UICONTROL 花費時間 (秒)]」[標準元件](/help/data-views/component-reference.md)納入您的[資料檢視](/help/data-views/create-dataview.md)時，此計算量度會自動新增至 Workspace。區段排除工作階段的最後一個事件會套用至「人員」量度。 區段會排除資料集中每個工作階段的最後一個事件。 此排除可協助您分析導致某個事件或動作 (例如購買或表單提交) 的使用者行為，同時排除最終動作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **花費的時間 (秒)** ![劃分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除最後工作階段事件 (** ![事件](/help/assets/icons/Event.svg) **人員 ) )** |
| **[!UICONTROL 每人工作階段數]** | 每個人平均工作階段數量。<p>摘要：**(** ![事件](/help/assets/icons/Event.svg) **工作階段** ![劃分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **人員** **)** |
| **[!UICONTROL 每個工作階段花費的時間]** | 一個人每工作階段在任何特定維度項目上的平均逗留時間。<p>當您將「[!UICONTROL 花費時間 (秒)]」[標準元件](/help/data-views/component-reference.md)納入您的[資料檢視](/help/data-views/create-dataview.md)時，此計算量度會自動新增至 Workspace。「工作階段排除最後一個事件」區段會套用至「工作階段」量度。 區段會排除資料集中每個工作階段的最後一個事件。 此排除可協助您分析導致某個事件或動作 (例如購買或表單提交) 的使用者行為，同時排除最終動作本身。</p>摘要： **(** ![事件](/help/assets/icons/Event.svg) **花費的時間 (秒)** ![劃分](/help/assets/icons/Divide.svg) ![分段](/help/assets/icons/Segmentation.svg) **排除最後工作階段事件 (** ![事件](/help/assets/icons/Event.svg) **工作階段 ) )** |
| **[!UICONTROL 工作階段結束率]** | 在工作階段的最後事件發生任何維度項目的百分比。 <p>當您將「[!UICONTROL 工作階段結束]」[標準元件](/help/data-views/component-reference.md)納入您的[資料檢視](/help/data-views/create-dataview.md)時，此計算量度會自動新增至 Workspace。</p>摘要：**(** ![事件](/help/assets/icons/Event.svg) **工作階段結束** ![劃分](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **工作階段** **)** |
| **[!UICONTROL 網頁工作階段]** | 網站上發生的工作階段數量。 |
| **[!UICONTROL 意見調查完成率]** | 人們在意見調查開始後完成意見調查的比率。 |
| **[!UICONTROL 多管道工作階段比率]** | 包含多個管道 (例如網路流量和行動流量) 的工作階段與僅包含單一管道的工作階段相比的比例。 |
| **[!UICONTROL 多管道人員比率]** | 參與多個管道的人數與僅參與單一管道的人數相比的比例。 |
| **[!UICONTROL 行動應用程式工作階段]** | 行動應用程式上發生的工作階段數量。 |
| **[!UICONTROL 網路+應用程式跨管道工作階段]** | 發生的工作階段數量 (包括網路流量和行動流量)。 |
| **[!UICONTROL 通話成本]** | 呼叫中心通話的總成本。<!-- <p>Summary: Call length</p> --> |
| **[!UICONTROL 平均通話時長]** | 撥打呼叫中心的通話的平均時長。 |
| **[!UICONTROL 每次通話的平均成本]** | 撥打呼叫中心的通話的平均成本。 |
| **[!UICONTROL 平均電話意見調查分數]** | 有關撥打呼叫中心的通話的平均意見調查分數。 |

{style="table-layout:auto"}
