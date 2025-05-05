---
description: 有了計算量度產生器，任何人都能建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 65eafd65358d9370b452338ce1036e59b3c69d1a
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# 參與率量度

參與率量度可用來量化某個維度的個別值（例如「頁面檢視」）對包含特定量度（例如「訂購」）的工作階段的貢獻或參與程度。

>[!NOTE]
>
>管理員可以使用非預設歸因模型（例如參與率）建立量度，作為[資料檢視](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/data-views)的一部分。 如需詳細資訊，請參閱[歸因元件設定](../../../data-views/component-settings/attribution.md)。

下列步驟顯示任何具有[建立計算量度許可權](/help/technotes//access-control.md#user-level-access)的使用者如何建立參與率量度。

1. [建立計算量度](cm-workflow.md)，並在[計算量度產生器](cm-build-metrics.md)中命名量度`Participation`或類似名稱。
1. 將包含成功事件的量度（例如[!DNL Orders]）拖曳至[!UICONTROL **[!UICONTROL 定義]**]區域。
1. 選取量度的![齒輪](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。
1. 在出現的快顯視窗中，選取「**[!UICONTROL 使用非預設歸因模型]**」以將該事件的[歸因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)定義為&#x200B;**[!UICONTROL 參與率]**，並選取[!UICONTROL 回顧期間]的&#x200B;**[!UICONTROL 工作階段]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以確認。


   ![資料行歸因模型快顯視窗，顯示選取為模型的參與率，以及選取做為回顧視窗的工作階段。](assets/participation-setup.png)

   **(Partipation|Session)**&#x200B;已新增至量度元件名稱。



1. 選取&#x200B;[!UICONTROL **儲存**]&#x200B;以儲存量度。
1. 在報表中使用計算量度。 例如，使用報表中的計算[!DNL Orders (Session Participation)]量度來顯示哪個客戶層促成（或參與）了包含訂單的工作階段。

   ![顯示客戶層級和訂單的自由格式表格。](assets/participation-pages-customer-tier.png)
