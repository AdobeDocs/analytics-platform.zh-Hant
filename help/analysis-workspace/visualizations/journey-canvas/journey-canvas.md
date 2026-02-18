---
description: 了解如何在 Analysis Workspace 中使用歷程畫布。
title: 歷程畫布概觀
feature: Visualizations
role: User
exl-id: be03c3b2-8faf-47b8-b3ab-e953202bf488
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1996'
ht-degree: 100%

---

# 歷程畫布概觀 {#journey-canvas-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_button"
>title="歷程畫布"
>abstract="顯示人們如何完成或退出一系列接觸點。用於具有多個進入點和路徑的歷程，或用來分析在 Journey Optimizer 中建立的歷程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_panel"
>title="歷程畫布"
>abstract="分析人們如何完成或退出定義的歷程。建立由節點和箭頭組成的彈性圖表來表示事件、維度項目和區段的任何組合，藉以建置使用者歷程分析。拖曳畫布上的節點，重新排列歷程的事件和條件。當您這樣做時，資料會隨之更新。<br/><br/>擁有 Adobe Journey Optimizer 存取權的客戶可以分析現有的 Journey Optimizer 歷程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_button"
>title="歷程畫布"
>abstract="顯示人們如何完成或退出一系列接觸點。用於具有多個進入點和路徑的歷程，或用來分析在 Journey Optimizer 中建立的歷程。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="journeycanvas_panel"
>title="歷程畫布"
>abstract="分析人們如何完成或退出定義的歷程。建立由節點和箭頭組成的彈性圖表來表示事件、維度項目和區段的任何組合，藉以建置使用者歷程分析。拖曳畫布上的節點，重新排列歷程的事件和條件。當您這樣做時，資料會隨之更新。<br/><br/>擁有 Adobe Journey Optimizer 存取權的客戶可以分析現有的 Journey Optimizer 歷程。"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 中的歷程畫布視覺效果。<br/>**Adobe Analytics** 中沒有相等的視覺效果。_

>[!ENDSHADEBOX]

您可以利用歷程畫布視覺化圖表，針對您提供給使用者和客戶的歷程進行分析並獲取深入洞察。此視覺效果允許您從頭開始定義歷程或從 Journey Optimizer 中查看歷程，然後查看人們如何離開 (流失) 或繼續 (流過) 歷程。

您可以使用事件、維度項目、區段和日期範圍的任意組合來建立歷程節點，藉以[建置使用者歷程分析](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。連接節點以建立歷程流程，並包含多條路徑和決策點。拖曳動畫布上的節點，以重新排列歷程的事件和條件。當您進行變更時，資料會即時更新。

[節點已連接](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#logic-when-connecting-nodes)作為「最終路徑」，這表示只要訪客最後從一個節點移動到另一個節點，就會被計算在內，而不管 2 個節點之間發生什麼事件。使用者沿著路徑移動所分配的時間由容器設定來決定。

![歷程畫布](assets/journey-canvas.png)

## 主要功能

歷程畫布視覺效果的主要功能包括：

* 考慮最複雜的使用者歷程下，流失和流過的深入分析。

* 對應和視覺化使用者歷程各個入口點、節點和路徑的畫布。

* 透過拖放互動將元件新增至畫布，並重新定位現有節點。

* 在歷程畫布內建立使用者歷程分析，或根據 Journey Optimizer 歷程自動建立分析。

## 潛在的洞察

歷程畫布會為最複雜的歷程提供可操作洞察。

### 轉換率最高的路徑 {#conversion-rate-caption}

歷程畫布中最突出的洞察顯示為畫布最上方的標題。

此標題總結歷程中哪條路徑的轉換率最高。

當歷程包含多個起始節點時，標題如下所示：

![歷程畫布洞察標題](assets/journey-canvas-caption.png)

當歷程包含單一起始節點時，標題如下所示：

![歷程畫布洞察標題單一起始節點](assets/journey-canvas-caption-singlestart.png)

解釋此標題時，請考慮以下幾點：

* _路徑_&#x200B;是定義為透過箭頭連接到終止節點的起始節點，並且之間連接任意數量的節點。

* 轉換率的計算取決於歷程的類型 (歷程包含的起始節點和終點節點的數量，以及二者之間的路徑是否相交)。

  下表描述如何根據歷程類型計算轉換率：

  | 歷程類型 | 轉換率計算 | 範例 |
  |---------|----------|---------|
  | **單一起始節點和單一結束節點** | 轉換率的計算方式是將結束節點的數量除以起始節點的數量。 | ![有多個起始點但匯集至一個共同節點的歷程](assets/journey-canvas-single-path.png) |
  | **單一起始節點和多個結束節點** | 轉換率的計算方法是找出數量最高的結束節點，然後將該數量除以起始節點的數量。 | ![有多個起始點但匯集至一個共同節點的歷程](assets/journey-canvas-singlestart-multiend.png) |
  | **多個獨立路徑，每個路徑包含一個起始節點和一個結束節點** | 轉換率的計算方式是將結束節點的數量除以起始節點的數量。標題內有轉換率最高的路徑說明。 | ![有多個起始點但匯集至一個共同節點的歷程](assets/journey-canvas-multi-start-separate.png) |
  | **多個起始節點，且歷程的任何一點會匯集一個共同節點** | 轉換率的計算方法是找出數量最高的結束節點，然後將該數量除以數量最低的起始節點數量。 | ![有多個起始點但匯集至一個共同節點的歷程](assets/journey-canvas-multi-start-converge.png) |

### 流過、流失及其他

以下是歷程畫布可幫助提供其他洞察的一些範例。您可以選擇這些洞察是否依據後者來進行：資料檢視中的所有人、開始歷程的所有人或來自歷程上一個節點的所有人。

#### 流過

* 完成歷程 (到達結束節點) 的人數和百分比

* 到達歷程中特定節點的人數和百分比

* 在歷程中特定節點之後或之前最常見的步驟

#### 流失

* 歷程中最常出現中途退出的節點 (從未到達任何接下來的節點)

#### 每個節點更多資料

* 在歷程任何節點上新增劃分維度，以查看該特定節點的其他資料

## 在歷程畫布、流失或流量視覺效果之間作選擇

歷程畫布視覺效果與[流失視覺效果](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)和[流量視覺效果](/help/analysis-workspace/visualizations/c-flow/flow.md)有相似之處，但也有重要的差異。

### 了解差異性

<!-- Information in this snippet is shared between Journey canvas, Fallout, and Flow visualization docs -->

{{journey-visualization-comparisons}}

### 何時使用歷程畫布

歷程畫布對以下方面至關重要：

* 對有多個入口點和路徑的歷程進行流失分析。

* 有多個入口點和路徑的非線性歷程，且其中有預先定義的頁面序列。

* 根據預先定義歷程進行的探索性臨時分析。

* 需要主要量度的分析，但工作階段、人員或發生次數除外。

* 對源自 Adob&#x200B;&#x200B;e Journey Optimizer 的歷程進行更深入的分析。

使用[上面表格](#understand-the-differences)來了解歷程畫布、流失和流量視覺效果之間的差異。

## 分析 Journey Optimizer 歷程

>[!NOTE]
>
>如果您的組織無法存取 Journey Optimizer，您仍然可以[在歷程畫布中建立分析](#build-analyses-in-customer-journey-analytics)。

在歷程畫布中分析 Journey Optimizer 歷程，可以提供人們如何與歷程互動的可操作的洞察。

當您在歷程畫布中分析 Journey Optimizer 歷程時，該歷程將以與 Journey Optimizer 中相同的順序、序列和結構來顯示。如果您在歷程畫布中對歷程進行大幅變更，[變更將不再從 Journey Optimizer 進行同步](#synchronization-between-journey-optimizer-and-journey-canvas)。

### 使用歷程畫布分析 Journey Optimizer 歷程的好處

歷程畫布提供在 Journey Optimizer 無法實現的徹底深入分析。

使用歷程畫布分析在 Journey Optimizer 中建立的歷程，有多種好處：

* 使用任何 Customer Journey Analytics 維度、量度、區段或日期範圍來建立事件。

  在 Journey Optimizer 中，技術使用者必須先建立事件，然後才能將其新增至歷程。

* 根據您建立的自訂節點來建立客群 (啟動 Customer Journey Analytics 客群建立器)。

  在 Journey Optimizer 中，您只能為預先定義的活動建立客群。

* 分析流過和流失

* 以任何維度劃分事件

* 合併事件

* 連接事件

* 重新命名與刪除事件

* 更多

### Journey Optimizer 與歷程畫布之間的同步

請思考以下行為來了解 Journey Optimizer 和歷程畫布之間的同步：

* **資料同步僅是單向的**

  在歷程畫布中建立 Journey Optimizer 歷程分析後，資料只會朝一個方向同步，即從 Journey Optimizer 到歷程畫布。這表示在歷程畫布中對歷程進行的變更絕不會反映在 Journey Optimizer 中。

* **在歷程畫布中修改歷程會使同步停下**

  [唯有當歷程畫布中未進行大幅修改時](#differences-after-modifying-a-journey-in-journey-canvas)，對 Journey Optimizer 內歷程所做的變更才會同步到歷程畫布。在歷程畫布中修改歷程後，您在 Journey Optimizer 中對歷程所做的任何變更都不會反映在歷程畫布中。若要查看歷程畫布中反映的變更，您可以刪除[歷程畫布中的歷程並重新建立](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

* **若要使用「與任何人共用」連結，於 Journey Optimizer 中進行變更後，需要將專案儲存在 Customer Journey Analytics 中**

  使用「與任何人共用」連結時，於專案儲存在 Customer Journey Analytics 中以前，Journey Optimizer 內所做的變更不會反映在歷程畫布中。

  如需有關「與任何人共用」連結的詳細資訊，請參閱[共用專案](/help/analysis-workspace/curate-share/share-projects.md)中的[與任何人共用專案 (無需登入)](/help/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required)。

### 在歷程畫布中修改歷程後的差異 {#differences-after-modifying}

在歷程畫布中修改 Journey Optimizer 歷程後，資料處理、可用功能和同步行為可能會改變。

如果您在歷程畫布中對 Journey Optimizer 歷程進行大幅修改，資料處理、可用功能和同步行為可能會改變。大幅修改包括以下任何一項：

* 新增或刪除節點

* 新增或刪除節點之間的箭頭

* 變更節點上的元件

如果您在歷程畫布中對 Journey Optimizer 歷程進行其他變更，例如拖曳節點或新增劃分，則以下部分說明的差異不適用。

>[!NOTE]
>
>若要將歷程恢復到原始狀態，您可以在歷程畫布中進行第一次變更，然後按 Ctrl+z。或者，您可以刪除[歷程畫布中的歷程並重新建立](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)

#### 資料處理差異

在歷程畫布中修改 Journey Optimizer 歷程後，如果您的歷程包含具有非預設歸因模型的量度，您可能會注意到資料發生變化。

這是因為與 Journey Optimizer 不同，歷程畫布允許您在一次歷程中應用多個維度。此功能表示[量度歸因](/help/data-views/component-settings/attribution.md)不受支援。

#### 功能差異

在歷程畫布中修改 Journey Optimizer 歷程後，[!UICONTROL **箭頭設定**]&#x200B;下拉選單欄位內的選項會發生變化，取決於您的修改內容。如需更多資訊，請參閱「[設定進行](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)」。

「[!UICONTROL **節點類型**]」欄位僅適用於 Journey Optimizer。在歷程畫布中查看 Journey Optimizer 歷程時無法使用此功能，無論您是否在歷程畫布中對歷程進行修改。

#### 同步差異

只有在歷程畫布中的歷程保持不變時，對 Journey Optimizer 中的歷程進行的變更才會同步到歷程畫布。

在歷程畫布中修改 Journey Optimizer 歷程後，您在 Journey Optimizer 中對歷程所做的任何變更都不會反映在歷程畫布中。若要查看歷程畫布中反映的變更，您可以刪除[歷程畫布中的歷程並重新建立](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。

### Journey Optimizer 與 Customer Journey Analytics 之間的專業術語差異

某些用語在 Journey Optimizer 中具有某種含義，而在 Customer Journey Analytics 中則具有其他含義。使用歷程畫布時，會使用 Customer Journey Analytics 用語。

| 詞語 | 歷程畫布 | Journey Optimizer |
|---------|----------|---------|
| **事件** | Customer Journey Analytics 中提供的多個標準量度之一。此量度會計入營收、訂閱或產生的潛在客戶等類。 | 觸發個人化歷程的活動類別，例如線上購買。 |

### 在歷程畫布中分析 Journey Optimizer 歷程

有關在歷程畫布中分析 Journey Optimizer 歷程的資訊，請參閱「[設定歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)」。

## 在歷程畫布中建立分析

您可以在歷程畫布中建立以 Analysis Workspace 中適用任何維度或量度的分析。或者，您可以分析在 Journey Optimizer 中建立的歷程。如需更多資訊，請參閱「[設定歷程畫布視覺效果](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)」。


>[!MORELIKETHIS]
>
> * [Adobe Customer Journey Analytics 歷程畫布視覺效果指南](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/a-guide-to-journey-canvas-visualization-in-adobe-customer/ba-p/737857)

