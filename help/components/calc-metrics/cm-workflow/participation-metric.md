---
description: 使用計算量度產生器，任何人都能建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 5%

---

# 建立參與率量度

本文說明如何建立參與率量度。 參與率量度會顯示某個維度的個別值（例如「頁面檢視」、「行銷管道」）如何貢獻或參與包含特定量度（例如「訂單」）的作業。

這類資訊對於任何內容擁有者都相當實用。

>[!NOTE]
>
>管理員也可以建立其他歸因模型（例如參與率）的量度，作為[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html)的一部分。 如需詳細資訊，請參閱[歸因元件設定](../../../data-views/component-settings/attribution.md)。<br/>以下範例說明如何由任何有權存取Workspace中的計算量度產生器的使用者建立參與率量度。


1. 開始建立量度，如[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。
1. 在計算量度產生器中，將量度命名為`Participation`或類似名稱。
1. 將包含成功事件的量度（例如[!DNL Orders]）拖曳至[!UICONTROL 定義]畫布。
1. 選取量度的![齒輪](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。
1. 在出現的快顯視窗中，選取「**[!UICONTROL 使用非預設歸因模型]**」以將該事件的[歸因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)定義為&#x200B;**[!UICONTROL 參與率]**，並選取[!UICONTROL 回顧期間]的&#x200B;**[!UICONTROL 工作階段]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以確認。

   在「定義」方塊中，已將&#x200B;**(Partipation|Session)**&#x200B;附加至其名稱以更新選取的量度。

   ![資料行歸因模型快顯視窗，顯示選取為模型的參與率，以及選取做為回顧視窗的工作階段。](assets/participation-setup.png)



1. 選取&#x200B;[!UICONTROL **儲存**]&#x200B;以儲存量度。
1. 在報表中使用計算量度。 例如，使用報表中的計算[!DNL Orders (Session Participation)]量度（如步驟5中所定義）來顯示哪個客戶層促成（或參與）了包含訂單的工作階段。

   ![顯示客戶層級和訂單的自由格式表格。](assets/participation-pages-customer-tier.png)

1. （選用）如[共用計算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md)中所述，與組織中的其他使用者共用量度。
