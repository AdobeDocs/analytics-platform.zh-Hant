---
title: 摘要資料群組元件設定
description: 詳細資訊以及如何設定資料集的維度，以確保您可以正確報告摘要資料。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 17%

---

# [!UICONTROL 摘要資料群組]元件設定 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_summarydatagroup"
>title="摘要資料群組"
>abstract="摘要資料群組會在分組中的所有維度之間建立關聯，並用於將摘要資料集中的維度與其他維度合併以進行報告。"

<!-- markdownlint-enable MD034 -->


摘要資料群組會在分組中的所有維度之間建立關聯，並用於將摘要資料集中的維度與其他維度合併以進行報告。

![摘要資料群組元件設定](/help/data-views/assets/summary-data-group.png)

若要建立維度群組：

1. 選取維度。
1. 選取![V形](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要資料群組]**。
1. 啟用&#x200B;**[!UICONTROL 建立群組]**。
1. 從&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉式清單中選取一個維度，您想要將它與第一個步驟中選取的維度群組。 請注意，下拉式清單中只會顯示您已新增至資料檢視的維度。
1. 選擇性地啟用&#x200B;**[!UICONTROL 在報表中隱藏]**，以隱藏報表中的群組維度。 啟用此選項與針對群組維度個別設定&#x200B;**[!UICONTROL 隱藏報表]**&#x200B;類似。 如需詳細資訊，請參閱[元件設定](overview.md)。
1. 若要新增其他維度到群組，請選取![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增維度到群組]**。<br/>您最多可以新增9個維度，因為摘要資料群組的限製為10個維度。

## 相同的元件設定

群組維度時，您必須確保群組內每個維度的[!UICONTROL 子字串]、[!UICONTROL 行為（小寫）]和[!UICONTROL 包含排除值]設定相同。 否則，群組的每個維度可能會在群組之前傳回不同的結果。
例如：

1. 您已為`campaign_code` （摘要資料的一部分）和`tracking_code` （事件資料的一部分）建立摘要資料群組。
1. 您已將[!UICONTROL 行為（小寫）]套用至`campaign_code`，但未套用至`tracking_code`維度。

`tracking_code`中的值可能會顯示為`campaign_code`以外的值。

>[!IMPORTANT]
>
>確保您僅從一個維度對維度進行分組，而不套用來自多個維度的分組。 例如，如果您透過將`campaign_name`維度新增到`tracking_code`維度來建立群組，請不要也為`campaign_name`維度建立群組。
>
