---
description: 瞭解如何建立參與率量度。
title: 參與率量度
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
TQID: https://experienceleague.adobe.com/no7rAZUl25LTEPqwRyC7vY4XcottzPGRq-DCAR5ez54
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 9%

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
1. 在出現的快顯視窗中，選取「**[!UICONTROL 使用非預設歸因模型]**」以將該事件的[歸因模型](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)定義為&#x200B;**[!UICONTROL 參與率]**，並為[!UICONTROL 容器]選取&#x200B;**[!UICONTROL 工作階段]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以確認。


   ![資料行歸因模型快顯視窗，顯示選取為模型的參與率，以及選取做為回顧視窗的工作階段。](assets/participation-setup.png)

   **(Partipation|Session)**&#x200B;已新增至量度元件名稱。



1. 選取&#x200B;[!UICONTROL **儲存**]&#x200B;以儲存量度。
1. 在報表中使用計算量度。 例如，使用報表中的計算[!DNL Orders (Session Participation)]量度來顯示哪個客戶層促成（或參與）了包含訂單的工作階段。

   ![顯示客戶層級和訂單的自由格式表格。](assets/participation-pages-customer-tier.png)
