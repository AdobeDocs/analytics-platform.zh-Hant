---
description: 使用計算量度產生器，任何人都能建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d55df4ea2086278a243af51b698a9822a9a04e04
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 32%

---

# 建立「參與率」量度

下列資訊說明如何建立量度，顯示哪些頁面促成（或參與）包含訂單的工作階段。

這類資訊對於任何內容擁有者都相當實用。

>[!NOTE]
>
>具有其他歸因模型（例如參與率）的量度也可由管理員建立，作為的一部分 [資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 以下範例說明如何在工作區中，由任何具備計算量度產生器存取許可權的使用者建立量度。

1. 開始建立量度，如所述 [建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在計算量度產生器中，將量度命名為「參與率」或類似名稱
1. 將成功事件「訂單」拖曳至「定義」畫布。
1. 在[設定](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)齒輪底下將該事件的&#x200B;**[!UICONTROL 歸因模型]**&#x200B;變更為&#x200B;**[!UICONTROL 參與率]**。選取 **[!UICONTROL 工作階段]** 回顧。 定義應該看起來類似下列：

   ![](assets/participation.png)

1. 選取 [!UICONTROL **儲存**] 以儲存量度。
1. 在&#x200B;**[!UICONTROL 頁面]**&#x200B;報表中使用計算量度。

   ![](assets/participation-pages.png)

1. （選用）與組織中的其他使用者共用量度，如所述 [共用計算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
