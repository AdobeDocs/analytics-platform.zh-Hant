---
description: 使用交談摘要視覺效果來摘要交談。
title: 對話摘要
feature: Visualizations
role: User
hide: true
source-git-commit: ccaa957e79fba24292316c7447be786f57f03493
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 19%
---
# 對話摘要 {#conversation-summaries}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_button"
>title="對話摘要"
>abstract="建立視覺化圖表來總結已篩選的對話群組。"

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_panel"
>title="對話摘要"
>abstract="總結已篩選的對話群組。 控制摘要的長度。 查看客戶的代表性引述，以驗證所擷取訊號的準確性。 選取報價以開啟完整的交談重播。"


![摘要](/help/assets/icons/Summarize.svg) **[!UICONTROL 交談摘要]**&#x200B;視覺效果可讓您摘要經過篩選的交談群組。

當您將視覺效果設定為包含子主題時，視覺效果會顯示所選量度的摘要（例如「交談」），並顯示子主題或逐字註釋。


## 建立及設定 {#conversation-summaries-create-configure}

>[!CONTEXTUALHELP]
>id="workspace_conversationsummaries_attribution"
>title="交談摘要歸因"
>abstract="為所選的量度啟用非預設歸因模型。"

若要建立及設定&#x200B;**[!UICONTROL 交談摘要]**&#x200B;視覺效果：

1. 新增![摘要](/help/assets/icons/Summarize.svg) **[!UICONTROL 交談摘要]**&#x200B;視覺效果。 請參閱[新增視覺效果至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 在&#x200B;**[!UICONTROL 交談摘要]**&#x200B;視覺效果設定中：

   1. 選取&#x200B;**[!UICONTROL 量度]**。 例如： **[!UICONTROL 交談]**。
   1. 如果您想要在Metrix上設定[歸因](/help/analysis-workspace/attribution/models.md)，請選取&#x200B;**[!UICONTROL 設定歸因]**，然後選取&#x200B;**[!UICONTROL 模型]**、**[!UICONTROL 容器]**&#x200B;和&#x200B;**[!UICONTROL 回顧視窗]**。
   1. 您可以選擇將區段套用至視覺效果。 從&#x200B;**[!UICONTROL 區段]**&#x200B;下拉式功能表中選取區段。

1. 選取&#x200B;**[!UICONTROL 建置]**&#x200B;以建置視覺效果。 選取&#x200B;**[!UICONTROL 重設]**&#x200B;將組態值重設為預設值。 選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消設定。

若要重新設定&#x200B;**[!UICONTROL 交談摘要]**&#x200B;視覺效果，請選取&#x200B;**[!UICONTROL 量度： _量度_]**&#x200B;或&#x200B;**[!UICONTROL 量度：_量度_]**&#x200B;旁的![編輯](/help/assets/icons/Edit.svg) | **[!UICONTROL 區段： _區段_]**。

## 使用

若要使用視覺效果：

>[!BEGINTABS]

>[!TAB 子主題]

![子主題](assets/conversation-summaries-subtopics.png)

>[!TAB 逐字註解]

![逐字註解](assets/conversation-summaries-verbatimcomments.png)

>[!ENDTABS]

* 如果您有[包含的子主題](#settings)，請選取&#x200B;**[!UICONTROL 子主題]**&#x200B;以顯示子主題，或選取&#x200B;**[!UICONTROL 逐字註解]**&#x200B;以顯示逐字註解。
* 當您已選取&#x200B;**[!UICONTROL 逐字註解]**&#x200B;時，請選取![FileSearch](/help/assets/icons/FileSearch.svg)以針對逐字註解所屬的特定交談開啟新的[**[!UICONTROL 交談檢閱]**](./conversation-review.md)視覺效果。

## 設定

下列特定的[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)可供使用。

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 摘要長度]** | 指定摘要的長度。 您可以選取&#x200B;**[!UICONTROL 短]**&#x200B;或&#x200B;**[!UICONTROL 長]**。 |
| **[!UICONTROL 包含子主題]** | 選取&#x200B;**[!UICONTROL 包含子主題]**&#x200B;以在視覺效果中顯示子主題。 使用&#x200B;**[!UICONTROL 最大子主題數目]**&#x200B;來設定要顯示的子主題數目上限。 |
