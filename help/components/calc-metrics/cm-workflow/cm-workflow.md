---
description: 瞭解如何建立計算量度。
title: 建立計算量度
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 18%

---

# 建立計算量度

依預設，只有管理員可以建立計算量度。 使用者有權檢視計算量度，類似於使用者檢視其他元件的方式（例如區段、註解等）。

不過，管理員可以透過&#x200B;**[!UICONTROL Admin Console]**，將&#x200B;**[!UICONTROL 編輯CJA Workspace存取權]**&#x200B;中&#x200B;**[!UICONTROL 報告工具]**&#x200B;的[計算量度建立](/help/technotes/access-control.md#user-level-access)許可權授予使用者。


您可以透過下列方式建立計算量度：

![建立量度的方式](assets/create-metric.png)

* **A**. 在主介面中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;並選取&#x200B;**[!UICONTROL 計算量度]**。 從![計算量度](/help/assets/icons/AddCircle.svg)管理員[!UICONTROL **[!UICONTROL 選取]**]AddCircle[Add](/help/components/calc-metrics/cm-workflow/cm-manager.md)。
* **B**. 在Workspace專案中，從「元件」左側面板選取![事件](/help/assets/icons/Add.svg) ![量度](/help/assets/icons/Event.svg)的&#x200B;**新增**。
* **C**. 在Workspace專案中，從量度欄標題的內容功能表中，選取「**[!UICONTROL 從選取專案建立量度]**」。 您可以從子功能表中選取函式，或選取&#x200B;**[!UICONTROL 在計算量度產生器中開啟]**。 <br/>如果您選取函式，計算量度會定義為僅限專案的量度。 當您稍後透過[元件資訊](/help/components/use-components-in-workspace.md#component-info)快顯視窗編輯此量度時，會在[計算量度產生器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中看到通知。
* **D**. 在Workspace專案中，從功能表選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 建立量度]**。
* **E**。 在Workspace專案中，使用捷徑&#x200B;**[!UICONTROL shift+cmd+c]** (macOS)或&#x200B;**[!UICONTROL shift+ctrl+c]** (Windows)。

若要定義新的計算量度，請使用[計算量度產生器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。


## 工作流程

在建立計算量度之前，請仔細考量下列工作流程：

| 工作流程工作 | 說明 |
| --- | --- |
| 計畫計算量度 | 尤其是針對即將正式核准的量度，規劃可概述哪些計算量度將會廣泛使用以及將如何定義。 |
| [建置](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)計算量度 | 建立和編輯計算量度與進階計算量度，以用於 [!DNL Customer Journey Analytics] 元件。 |
| [標籤](cm-tagging.md)計算量度 | 標記計算量度以方便進行組織和共用。請參閱如何規劃和指派標記來進行簡易與進階的搜尋及組織。 |
| [核准](cm-approving.md)計算量度 | 核准計算量度可讓它們成為遵循標準。 |
| 使用計算量度 | 在您的專案中使用計算量度。 |
| [共用](cm-sharing.md)個計算量度 | 與其他個人、群組或組織共用您的計算量度。 |
| [篩選器](cm-filter.md)計算量度 | 依標籤、擁有者和其他篩選器（「全部顯示」、「我的」、「已共用給我」、「我的最愛」和「已核准」）來篩選計算量度。 |
| 將計算量度標示為[我的最愛](cm-finding.md) | 要組織量度以方便使用，將量度標記為我的最愛是另一種方法。 |

