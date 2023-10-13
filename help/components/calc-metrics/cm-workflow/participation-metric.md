---
description: 使用計算量度產生器，任何人都能建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: d95d324350a2f8aa77032e7cac1c924d161d47ce
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 17%

---

# 建立「參與率」量度

本文說明如何建立量度，顯示選定維度（例如頁面檢視、行銷管道、應用程式版本）的個別值如何貢獻（或參與）包含訂單的工作階段。

這類資訊對於任何內容擁有者都相當實用。

>[!NOTE]
>
>具有其他歸因模型（例如參與率）的量度也可由管理員建立，作為的一部分 [資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 以下範例說明如何在工作區中，由任何具備計算量度產生器存取許可權的使用者建立量度。

1. 開始建立量度，如所述 [建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在計算量度產生器中，將量度命名為「參與率」或類似名稱
1. 將成功事件「訂單」拖曳至「定義」畫布。
1. 選取 ![齒輪](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 針對 [!DNL Orders] 量度。
1. 在出現的快顯視窗中，選取 **[!UICONTROL 使用非預設歸因模型]** 以定義 [歸因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) 的預設值 **[!UICONTROL 參與率]** 並選取 **[!UICONTROL 工作階段]** 針對 [!UICONTROL 回顧期間]. 選取 **[!UICONTROL 套用]** 以確認。

   在定義方塊中， ![事件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **訂購** 已更新至 ![事件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) **訂購（參與|工作階段）**.

   ![](assets/participation-setup.png)



1. 選取 [!UICONTROL **儲存**] 以儲存量度。
1. 在報表中使用計算量度。 以下計算量度用於報表中，以顯示哪些客戶層級對（或參與）包含訂單的工作階段有貢獻。

   ![](assets/participation-pages-customer-tier.png)

1. （選用）與組織中的其他使用者共用量度，如所述 [共用計算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
