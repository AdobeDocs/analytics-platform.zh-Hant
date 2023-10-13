---
description: 使用計算量度產生器，任何人都能建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: e7019722871dfac60408748aa183ca6d76f4993a
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 6%

---

# 建立參與率量度

本文說明如何建立參與率量度。 參與率量度會顯示某個維度的個別值（例如「頁面檢視」、「行銷管道」）如何貢獻或參與包含特定量度（例如「訂單」）的作業。

這類資訊對於任何內容擁有者都相當實用。

>[!NOTE]
>
>具有其他歸因模型（例如參與率）的量度也可由管理員建立，作為的一部分 [資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html). 另請參閱 [歸因元件設定](../../../data-views/component-settings/attribution.md) 以取得更多詳細資料。<br/>以下範例說明在工作區中，有權存取計算量度產生器的任何使用者如何建立參與率量度。


1. 開始建立量度，如所述 [建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 在計算量度產生器中，為量度命名 `Participation` 或類似專案。
1. 例如，拖曳包含成功事件的量度 [!DNL Orders]，移入 [!UICONTROL 定義] 畫布。
1. 選取 ![齒輪](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) 用於量度。
1. 在出現的快顯視窗中，選取 **[!UICONTROL 使用非預設歸因模型]** 以定義 [歸因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md) 的預設值 **[!UICONTROL 參與率]** 並選取 **[!UICONTROL 工作階段]** 針對 [!UICONTROL 回顧期間]. 選取 **[!UICONTROL 套用]** 以確認。

   在「定義」方塊中，會透過附加來更新選取的量度  **（參與|工作階段）** 至其名稱。

   ![](assets/participation-setup.png)



1. 選取 [!UICONTROL **儲存**] 以儲存量度。
1. 在報表中使用計算量度。 例如，使用計算的 [!DNL Orders (Session Participation)] 量度（如步驟5中所定義），用於顯示哪個客戶層促成（或參與）了包含訂單的工作階段。

   ![](assets/participation-pages-customer-tier.png)

1. （選用）與組織中的其他使用者共用量度，如所述 [共用計算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md).
