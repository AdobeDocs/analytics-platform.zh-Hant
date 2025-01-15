---
title: 歸因面板
description: 如何使用和解讀 Analysis Workspace 中的歸因面板。
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: bf5853a1d23d6e648024016a64dc67d09da3fbb4
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 47%

---

# 歸因面板 {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="歸因"
>abstract="使用任何維度和轉換量度，快速比較和視覺化任何數量的歸因模型"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="歸因面板"
>abstract="使用任何維度和轉換量度，快速比較和視覺化任何數量的歸因模型。<br/><br/>**參數&#x200B;**<br/>**管道**<br/>&#x200B;屬性依據的維度。此維度可以是行銷管道、活動或任何其他維度。<br/>**模型**<br/>&#x200B;此模型可決定如何將積分指派給接觸點。<br/>**回顧視窗**<br/>&#x200B;此設定可決定套用至每個轉換的資料歸因期間。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*本文以&#x200B;**Customer Journey Analytics**記錄歸因面板。<br/>檢視此文章的&#x200B;**Adobe Analytics**版本的[歸因面板](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/attribution)。*

>[!ENDSHADEBOX]

建立比較各種歸因模型的分析時，**[!UICONTROL 歸因]**&#x200B;面板是可採用的簡單方式。面板提供專屬的工作區，供您使用和比較歸因模型。

Customer Journey Analytics 強化了歸因功能，讓您可以：

* 定義付費媒體以外的歸因：任何維度、量度、頻道或事件都可以套用至模型（例如內部搜尋），而不僅限於行銷活動。
* 不限次數使用歸因模型比較功能：動態比較任意數量的模型。
* 避免實施變更：透過報表時間處理功能和內容感知工作階段，可以建置客戶歷程內容並在執行階段套用。
* 建構與您的歸因狀況最相符的工作階段。
* 依篩選器劃分歸因：輕鬆比較行銷管道在任何重要篩選器中的效能（例如，新客戶與回頭客戶、產品X與產品Y、忠誠度或CLV）。
* 跨管道檢查和多點接觸分析：使用文氏圖表和直方圖，並計算歸因結果趨勢。
* 以視覺化方式分析關鍵行銷序列活動：透過多節點流量和流失視覺效果，以視覺效果方式探究帶來轉換的路徑。
* 建立計算量度：使用任何數量的歸因配置方法。

## 使用

若要使用&#x200B;**[!UICONTROL 歸因]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 歸因]**&#x200B;面板。 有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。

1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

### 面板輸入

您可以使用以下輸入設定來設定「歸因」面板：

1. 從&#x200B;**[!UICONTROL 管道]**&#x200B;新增您想要歸因的&#x200B;**[!UICONTROL 成功量度]**&#x200B;和維度。 其範例包括行銷管道或自訂維度，例如內部促銷。

   ![「歸因」面板視窗會顯示數個選取的維度和量度。](assets/attribution-panel.png)

1. 從&#x200B;**[!UICONTROL 包含的模型]**&#x200B;選取一或多個[歸因模型](#attribution-models)，並從&#x200B;**[!UICONTROL 回顧期間]**&#x200B;選取要用來比較的[回顧期間](#lookback-window)。

1. 選取&#x200B;**[!UICONTROL 建置]**&#x200B;以在面板中建置視覺效果。

### 面板輸出

**[!UICONTROL 歸因]**&#x200B;面板會傳回一組豐富的資料和視覺效果，用以比較所選維度和量度的歸因。

![比較所選量度和維度的「歸因」面板視覺效果。](assets/attr_panel_vizs.png)

### 歸因視覺效果

下列視覺效果是面板輸出的一部分。

* **量度總計**：在報告時間範圍內發生，且歸因到您選取之維度的轉換總數。
* **歸因比較長條圖**：以視覺效果方式比較所選維度中每個維度項目的歸因轉換。每個長條的顏色代表不同的歸因模型。
* **歸因比較表**：顯示與長條圖相同的資料，以表格的形式呈現。在此表格中選取不同的欄或列可篩選長條圖，以及面板中的其他數個視覺效果。表格的作用與Workspace中的其他自由表格相仿 — 讓您新增量度、篩選器或劃分等元件。
* **重疊圖表**：文氏圖表視覺效果，會顯示前三大維度專案，及其共同參與轉換的頻率。 例如，重疊的泡泡圖大小代表某人接觸到兩個維度專案時發生轉換的頻率。 選取相鄰自由表格中的其他列，可依據您的選取項目更新視覺效果。
* **效能詳細資料**：可視覺化比較最多三個歸因模型的散佈視覺效果。
* **趨勢效能**：顯示排名前面的維度項目的歸因轉換趨勢。選取相鄰自由表格中的其他列，可依據您的選取項目更新視覺效果。
* **流量**：可讓您檢視哪些頻道最常互動，以及在使用者歷程中的順序。

## 歸因模型

{{attribution-models-details}}

## 回顧視窗

{{attribution-lookback-window}}

>[!MORELIKETHIS]
>
> [Create a panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
