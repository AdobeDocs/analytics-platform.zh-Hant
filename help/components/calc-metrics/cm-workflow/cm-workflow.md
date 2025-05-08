---
description: 瞭解如何建立計算量度。
title: 建立計算量度
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c183a5013cbc5ff3765cc4926a308d0c4563a097
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 44%

---

# 建立計算量度

依預設，只有管理員可以建立計算量度。 使用者有權檢視計算量度，類似於使用者檢視其他元件的方式（例如區段、註解等）。

不過，管理員可以透過[Admin Console](/help/technotes/access-control.md#user-level-access)，將&#x200B;**[!UICONTROL 編輯CJA Workspace存取權]**&#x200B;中&#x200B;**[!UICONTROL 報告工具]**&#x200B;的&#x200B;**[!UICONTROL 計算量度建立]**&#x200B;許可權授予使用者。


您可以透過下列方式建立計算量度：

![建立量度的方式](assets/create-metric.png)

* **A**. 在主介面中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;並選取&#x200B;**[!UICONTROL 計算量度]**。 從[[!UICONTROL 計算量度]管理員](/help/components/calc-metrics/cm-workflow/cm-manager.md)選取![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]。
* **B**. 在Workspace專案中，從「元件」左側面板選取![事件](/help/assets/icons/Event.svg) **量度**&#x200B;的![新增](/help/assets/icons/Add.svg)。
* **C**. 在Workspace專案中，從量度欄標題的內容功能表中，選取「**[!UICONTROL 從選取專案建立量度]**」。 您可以從子功能表中選取函式，或選取&#x200B;**[!UICONTROL 在計算量度產生器中開啟]**。 <br/>如果您選取函式，計算量度會定義為僅限專案的量度。 當您稍後透過[元件資訊](/help/components/use-components-in-workspace.md#component-info)快顯視窗編輯此量度時，會在[計算量度產生器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中看到通知。
* **D**. 在Workspace專案中，從功能表選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 建立量度]**。
* **E**。 在Workspace專案中，使用捷徑&#x200B;**[!UICONTROL shift+cmd+c]** (macOS)或&#x200B;**[!UICONTROL shift+ctrl+c]** (Windows)。

若要定義新的計算量度，請使用[計算量度產生器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。

瞭解建立計算量度的步驟。

| 工作流程工作 | 說明 |
| --- | --- |
| 規劃計算量度 | 對於要正式「核准」的量度來說，您尤其有必要先概述將廣泛使用的計算量度及其定義方式。 |
| [建立](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)計算量度 | 建立和編輯計算量度與進階計算量度，以用於 [!DNL Customer Journey Analytics] 元件。 |
| [&#128279;](cm-tagging.md)標記計算量度 | 標記計算量度以方便進行組織和共用。請參閱如何規劃和指派標記來進行簡易與進階的搜尋及組織。 |
| [&#128279;](cm-approving.md)核准計算量度 | 核准計算量度可讓它們成為遵循標準。 |
| 套用計算量度 | 您可從報表、量度選擇器 (若要存取，請按一下「[!UICONTROL 顯示量度]」) 直接套用量度。 |
| 篩選器計算量度 | 在量度選擇器中，按一下「[!UICONTROL 進階選擇]」並依標記、擁有者及其他篩選器 (全部顯示、我的、與我共用、我的最愛與已核准) 進行篩選。 |
| 將計算量度標示為[我的最愛](cm-finding.md) | 要組織量度以方便使用，將量度標記為我的最愛是另一種方法。 |

