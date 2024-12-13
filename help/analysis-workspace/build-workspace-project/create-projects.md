---
description: 了解如何在 Analysis Workspace 中建立專案
title: 建立專案
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 100%

---

# 建立專案 {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/><br/>注意，此設定不適用於「流程」或「流失」視覺效果。"

<!-- markdownlint-enable MD034 -->


Analysis Workspace 中的[專案](/help/analysis-workspace/build-workspace-project/freeform-overview.md)讓您建立和檢視關鍵業務分析。這些分析可以與組織內部或外部的利害關係人共用。

1. 在 Customer Journey Analytics 中，選取 **[!UICONTROL Workspace]**。

1. 在左側面板中選取&#x200B;**[!UICONTROL 專案]**，然後選取&#x200B;**[!UICONTROL 建立專案]**。

1. 選取&#x200B;**空白 Workspace 專案**，以使用瀏覽器建立您的 Workspace 專案。

   請參閱[空白行動計分卡](/help/mobile-app/curator.md)，以了解更多關於如何建立行動記分卡專案的資訊，且您可以使用行動應用程式與其他利害關係人共用專案。有關可用於建立引導式分析專案之各種選項的詳細資訊，請參閱[引導式分析](/help/guided-analysis/overview.md)。

1. 選取&#x200B;[!UICONTROL **建立**]。


現在您已經建立空白 Workspace 專案，請確保您熟悉 [Analysis Workspace](/help/analysis-workspace/home.md) 使用者介面。確認後，即可建置您的專案。若要進行此步驟：

![Example project](assets/example-project.png)

* 新增[面板](/help/analysis-workspace/c-panels/panels.md)至您的專案。例如，**[!DNL Example Panel]**➊。

* 新增[視覺化呈現](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)至您的面板。例如：
   * **[!DNL Line Graph]** [折線圖](/help/analysis-workspace/visualizations/line.md)視覺化呈現➋
   * **[!DNL Countries]** [自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)視覺化呈現➌
* 新增[元件](/help/components/overview.md)至您的視覺效果。例如：
   * **[!DNL Store Country]** [維度](/help/components/dimensions/overview.md)➍
   * **[!DNL People]** [量度](/help/components/apply-create-metrics.md)➎
   * **[!DNL Avg Order Value]** [計算量度](/help/components/calc-metrics/calc-metr-overview.md)➏
   * **[!DNL Mobile App Sessions]** [篩選器](/help/components/filters/filters-overview.md)➐
   * **[!DNL Last Month]** [日期範圍](/help/components/date-ranges/overview.md)➑
   * **[!DNL Example]** [註解](/help/components/annotations/overview.md)➒


## 專案資訊和設定 {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/>注意，此設定不適用於「流程」或「流失」視覺效果。"

<!-- markdownlint-enable MD034 -->


專案資訊和設定可提供目前使用中專案的專案層級資訊。

![The Project Info &amp; Settings window.](./assets/projectinfo.png)

設定包括：

| 設定 | 說明 |
|---|---|
| 專案名稱 | 提供給專案的名稱。按兩下名稱即可進行編輯。 |
| 所有者 | 專案所有者名稱 |
| 修改時間 | 上次修改專案的日期。 |
| 標記 | 列出為了方便分類而套用至專案的所有標籤。 |
| 說明 | 說明可用於釐清專案的用途。按兩下說明即可進行編輯。 |
| 計算重複實例數 | 指定是否要將重複實例計入報告中。注意，此設定不適用於「流程」或「流失」視覺化呈現。 |
| 顯示註解 | 指定是否顯示此專案的註解。 |
| [專案調色盤](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 您可以變更用於 Workspace 的分類調色盤，其方式為選擇已針對色盲人士最佳化的立即可用調色盤或指定您的自訂調色盤。此功能會影響工作區中的許多項目，包括大部分的視覺效果。 |
| [檢視密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 可減少左側面板、自由格式表格和同類群組表格的垂直邊框間距，讓您在畫面上查看更多資料。 |



