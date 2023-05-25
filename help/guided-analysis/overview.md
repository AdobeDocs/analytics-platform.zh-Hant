---
title: 引導式分析概述
description: 分析Customer Journey Analytics中資料的方法，可讓產品團隊輕鬆產生報告和見解。
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# 引導式分析概述

{{release-limited-testing}}

引導式分析是一種報告格式，可讓產品團隊快速自助滿足其資料需求，以便他們可以做出更多資料導向的產品決策。 跨職能團隊可以即時連線，以使用和瞭解這些報表。

引導式分析報表類似於Analysis Workspace和行動計分卡，使用來自 [資料檢視](../data-views/data-views.md)，會透過參照Adobe Experience Platform中的資料 [連線](../connections/overview.md). 在「引導式分析」中建立的所有報表均可順暢地傳輸至Analysis Workspace以供進一步研究。

引導式分析報告目前具有三種分析型別： [漏斗](analysis-types/funnel.md)， [趨勢](analysis-types/trends.md)、和 [使用者成長](analysis-types/user-growth.md). 這些分析型別各有多種檢視型別，可為每個報表提供額外的深入分析。

## 布建

引導式分析是Customer Journey Analytics的付費附加元件。 如果您的組織想要開始使用此功能，請聯絡您的Adobe客戶團隊。

## 介面

引導式分析的介面（無論分析型別為何）包含下列主要UI元素：

1. **查詢邊欄**：使用左側的這個邊欄來建置您的分析。
1. **圖表**：選取所需事件、人員或步驟後，圖表會顯示在右側，以視覺化呈現資料。
1. **表格**：圖表下方的表格，顯示視覺效果中使用的數字。
1. **設定和深入分析**：圖表上方的多個UI元素，可讓您自訂傳回的資料。

[UI熒幕擷圖]

引導式分析包含下列介面部分：

| 介面預覽 | UI 元素 | 說明 |
| --- | --- | --- |
| [查詢邊欄的熒幕擷圖] | 查詢邊欄 | 設定組成報表的所需元件。 不同的分析型別會共用數個查詢選項；如果兩個分析型別共用查詢選項，則會在切換分析型別時延續。 另請參閱 [分析型別](analysis-types/overview.md) 有關每個個別分析型別的查詢選項的更多資訊。 |
| [圖表熒幕擷圖] | 圖表 | 根據您從查詢邊欄和設定輸入的資料，傳回資料的視覺效果。 您看到的視覺效果取決於圖表上方的檢視型別。 可用的檢視型別取決於 [分析型別](analysis-types/overview.md) 查詢邊欄上方。 |
| [表格的熒幕擷圖] | 表格 | 根據您從查詢邊欄和設定輸入的資料傳回的表格表示法。 表格中的欄取決於圖表上方的檢視型別。 可用的檢視型別取決於 [分析型別](analysis-types/overview.md) 查詢邊欄上方。 |
| [設定熒幕擷圖] | 設定 | 圖表上方有數個選項，可讓您自訂圖表和表格傳回資料的方式。<ul><li>**檢視型別**：下拉式選擇器，可讓您顯示指定資料 [分析型別](analysis-types/overview.md) 以不同的方式進行。 每個分析型別至少有兩個檢視型別。</li><li>**圖表設定**：微調圖表外觀以及要使用的事件。 可用的選項取決於所選的檢視型別。</li><li>**日期範圍**：日曆選擇器，可讓您決定報表的日期範圍。 有些分析型別也允許間隔，例如每日、每週或每月。</li><li>**深入分析**：根據您檢視的報表提供內容分析。 您可以使用右上角的燈泡圖示來顯示或隱藏這些深入分析。</li></ul> |
| [分析功能表的熒幕擷圖] | 「分析」功能表 | 「引導式分析」右上角的命令，提供總體動作。<ul><li>**資料檢視選擇器**：變更此分析使用的資料檢視。 當您變更資料檢視時，查詢邊欄中的可用元件也會變更。</li><li>**儲存**：儲存分析。 如果您要儲存新的分析，會出現一個要求名稱和說明的強制回應視窗。</li><li>**另存為**：將分析與目前分析分開儲存，並建立副本。 會出現一個強制回應視窗，要求新的名稱和說明。</li><li>**在工作區中開啟**：在Analysis Workspace中重新建立目前的引導式分析。 Workspace專案是在新索引標籤中建立，以防止在引導式分析中工作時發生中斷。 當引導式分析無法提供您所需的彈性或特定深入分析時，請使用此命令。 例如，您希望 [趨勢](analysis-types/trends.md) 一個區段使用工作階段，另一個區段使用人員的報告。</li><li>**下載PNG**：將圖表圖形下載為 `.png`. 查詢邊欄和表格不包含在圖形中。</li><li>**下載SVG**：將圖表圖形下載為 `.svg`. 查詢邊欄和表格不包含在圖形中。</li></ul> |

{style="table-layout:auto"}

## 權限

Adobe計畫在未來提供引導式分析的特定許可權。

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
