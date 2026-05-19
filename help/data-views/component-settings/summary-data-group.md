---
title: 摘要資料群組元件設定
description: 詳細資訊以及如何設定資料集中的維度，以確保您可以正確報告摘要資料。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
autotag-review: '2026-05-19T09:00:37.763Z'
TQID: 'https://experienceleague.adobe.com/t1TH-tkHBNCfmC8hgk-IntYmYdRrS0enf2YEyRExCo4'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 89%

---

# [!UICONTROL 摘要資料群組]元件設定 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="摘要資料群組"
>abstract="摘要資料群組會在分組中的所有維度之間建立關聯，並用於將摘要資料集中的維度與其他維度合併以進行報告。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="在報告中隱藏"
>abstract="選取此選項將啟用該維度的「**[!UICONTROL 在報告中隱藏元件]**」，並阻止元件顯示在 Analysis Workspace 和其他 Customer Journey Analytics 報告工具中。"

<!-- markdownlint-enable MD034 -->



摘要資料群組會在分組中的所有維度之間建立關聯，並用於將摘要資料集中的維度與其他維度合併以進行報告。

![摘要資料群組元件設定](/help/data-views/assets/summary-data-group.png)

若要建立維度群組：

1. 選取維度。
1. 選取「![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 摘要資料群組]**」。
1. 啟用「**[!UICONTROL 建立分組]**」。
1. 從&#x200B;**[!UICONTROL Dimension]**&#x200B;下拉式功能表中選取您想要在第一步驟與所選維度分組的維度。 請注意，只有您已新增至資料檢視的維度才能從下拉式功能表中使用。
1. 或者，啟用「**[!UICONTROL 在報告中隱藏]**」，以隱藏報告中的分組維度。 啟用此選項與在分組維度上單獨設定「**[!UICONTROL 在報告中隱藏]**」類似。 如需詳細資訊，請參閱=[元件設定](overview.md)」。
1. 或者，若要為分組新增更多維度，請選取「![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增維度至群組]**」。<br/>最多可以新增九個維度，因為摘要資料群組的限制是十個維度。

## 相同元件設定

將維度分組時，您必須確保群組所屬每個維度的「[!UICONTROL 子字串]」、「[!UICONTROL 行為 (小寫)]」和「[!UICONTROL 包含排除值]」等設定相同。 否則，在分組之前，群組的每個維度可能會傳回不同的結果。
例如：

1. 您已經為 `campaign_code` (摘要資料一部分) 和 `tracking_code` (您的事件資料一部份) 建立一個摘要資料群組。
1. 您已套用 [!UICONTROL 行為 (小寫)] 至 `campaign_code`，但未套用至 `tracking_code` 維度。

`tracking_code` 中的值可能會顯示為與 `campaign_code` 不同的值。

>[!IMPORTANT]
>
>確保您只從一個維度進行維度分組，而不是從多個維度分組。 例如，如果您是透過新增 `campaign_name` 維度至 `tracking_code` 維度來建立分組，不要同時為 `campaign_name` 維度建立分組。
>
