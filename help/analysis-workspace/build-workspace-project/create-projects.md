---
description: 了解如何在 Analysis Workspace 中建立專案
title: 建立專案
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 45%

---

# 建立專案 {#create-projects}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_countrepeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/><br/>注意，此設定不適用於「流量」或「流失」視覺效果。"

<!-- markdownlint-enable MD034 -->


Analysis Workspace中的[專案](/help/analysis-workspace/build-workspace-project/freeform-overview.md)可讓您建立和檢視關鍵業務分析。  這些分析可與組織內部或外部的利害關係人分享。

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL Workspace]**。

1. 在左側面板中選取&#x200B;**[!UICONTROL 專案]**，然後選取&#x200B;**[!UICONTROL 建立專案]**。

1. 選取&#x200B;**空白Workspace專案**&#x200B;以使用瀏覽器建立您的Workspace專案。

   請參閱[空白行動計分卡](/help/mobile-app/curator.md)，以取得有關如何建立行動計分卡專案的詳細資訊，而您可使用行動應用程式與其他利害關係人共用。 請參閱[引導分析](/help/guided-analysis/overview.md)，以取得建立引導分析專案的各種可用選項的詳細資訊。

1. 選取「[!UICONTROL **建立**]」。


現在您已建立空白Workspace專案，請務必熟悉[Analysis Workspace](/help/analysis-workspace/home.md)使用者介面。 一旦完成，您就可以建置專案。 若要這麼做：

![範例專案](assets/example-project.png)

* 新增[面板](/help/analysis-workspace/c-panels/panels.md)至您的專案。 例如，**[!DNL Example Panel]**➊。

* 新增[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)至您的面板。 例如：
   * **[!DNL Line Graph]** [線](/help/analysis-workspace/visualizations/line.md)視覺效果➋
   * **[!DNL Countries]** [自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)視覺效果➌
* 新增[元件](/help/components/overview.md)至您的視覺效果。 例如：
   * **[!DNL Store Country]** [維度](/help/components/dimensions/overview.md)➍
   * **[!DNL People]** [量度](/help/components/apply-create-metrics.md)➎
   * **[!DNL Avg Order Value]** [計算量度](/help/components/calc-metrics/calc-metr-overview.md)➏
   * **[!DNL Mobile App Sessions]** [篩選器](/help/components/filters/filters-overview.md)➐
   * **[!DNL Last Month]** [日期範圍](/help/components/date-ranges/overview.md)➑
   * **[!DNL Example]** [註解](/help/components/annotations/overview.md)➒


## 專案資訊和設定 {#project-info-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_project_repeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/>注意，此設定不適用於「流量」或「流失」視覺效果。"

<!-- markdownlint-enable MD034 -->


專案設定提供目前使用中專案的專案層級資訊。

![專案資訊和設定視窗。](./assets/projectinfo.png)

設定包括：

| 設定 | 說明 |
|---|---|
| 專案名稱 | 提供給專案的名稱。按兩下名稱即可進行編輯。 |
| 所有者 | 專案所有者名稱 |
| 修改時間 | 上次修改專案的日期。 |
| 標記 | 列出為了方便分類而套用至專案的所有標籤。 |
| 說明 | 說明可用於釐清專案的用途。按兩下說明即可進行編輯。 |
| 計算重複執行個體數 | 指定是否要將重複例項計入報表中。 注意，此設定不適用於「流量」或「流失」視覺效果。 |
| 顯示註解 | 指定是否顯示此專案的註解。 |
| [專案調色盤](/help/analysis-workspace/build-workspace-project/color-palettes.md) | 您可以變更用於 Workspace 的分類調色盤，其方式為選擇已針對色盲人士最佳化的立即可用調色盤或指定您的自訂調色盤。此功能會影響工作區中的許多項目，包括大部分的視覺效果。 |
| [檢視密度](/help/analysis-workspace/build-workspace-project/view-density.md) | 可減少左側面板、自由表格和同類群組表格的垂直邊框間距，讓您在畫面上檢視更多資料。 |



