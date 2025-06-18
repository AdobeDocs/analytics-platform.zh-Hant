---
title: 歸因元件設定
description: 允許您為量度設定預設歸因。
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 93%

---

# 歸因元件設定 {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="歸因"
>abstract="設定套用至報告中量度的預設歸因模型。"

<!-- markdownlint-enable MD034 -->


歸因可讓您自訂維度項目如何獲得成功事件的貢獻度。

![資料檢視視窗會醒目顯示「設定歸因」選項](../assets/attribution-settings.png)

例如：

1. 您的網站有人按一下您其中一個產品頁面的付費搜尋連結。他們將產品新增至他們的購物車，但並未購買。
2. 第二天，他們在社群媒體上看到了一位朋友的貼文。他們可按一下連結，然後完成購買。

在某些報告中，您可能想要將訂單歸因於「付費」搜尋。在其他報告中，則可能會將訂單歸因至「社交」。歸因可讓您控制報表的這個方面。

## 設定元件的預設歸因模型

您可以透過更新資料檢視中的量度設定，為特定量度設定預設歸因模型。這樣做可在 Analysis Workspace 中使用量度的任何時候覆寫量度的歸因模型。

>[!NOTE]
>
>啟用量度歸因時，請考慮以下事項：
>
>* **當使用報告中&#x200B;*單一維度的元件*：**&#x200B;使用非預設歸因模型時，此元件歸因會忽略配置模式。
>
>* **當使用報告中&#x200B;*多個維度的元件*：**&#x200B;使用非預設歸因模型時，此元件歸因會保留配置模式。
>
>   只有[將資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md) 時才有多個維度可使用。
>
> 有關配置的更多資訊，請參閱「[持續性元件設定](/help/data-views/component-settings/persistence.md)」。

若要更新元件的預設歸因模型：

1. 前往包含您要更新其預設歸因模型的元件資料視圖。

1. 選取元件，然後展開畫面右側的&#x200B;**[!UICONTROL 歸因]**&#x200B;區段。

   ![資料檢視視窗會醒目顯示「設定歸因」選項](../assets/attribution-settings.png)

1. 選取&#x200B;[!UICONTROL **設定歸因**]，然後選取[歸因模型](#attribution-models)、[容器](#container)和[回顧](#lookback-window)視窗。



1. 選取&#x200B;[!UICONTROL **「儲存並繼續」**]。

>[!TIP]
>
>如果您的組織要求某個量度具有多個歸因設定，您可以執行以下操作之一：
>
> * 複製資料檢視中的量度，含每個所需的歸因設定。您可在資料檢視中多次包含相同的量度，並為每個量度提供不同的設定。確保善適當地標示每個量度，以便分析師在產生報告時了解這些量度之間的差異。
>
> * 覆蓋 Analysis Workspace 中的量度。在量度的[資料欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中，選取「**[!UICONTROL 使用非預設歸因模型]**」以變更該特定報告的量度歸因模型和回顧期間。

## 歸因模型 {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="模型"
>abstract="選取此量度的歸因模型。"

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## 容器

{{attribution-container}}

## 回顧視窗

{{attribution-lookback-window}}

## 範例

{{attribution-example}}
