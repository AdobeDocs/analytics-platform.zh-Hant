---
title: 引導式分析概述
description: 分析Customer Journey Analytics中資料的方法，可讓產品團隊快速獲得高品質的深入分析。 也稱為Product Analytics。
keywords: 產品分析
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '1360'
ht-degree: 2%

---

# 引導式分析概述

引導式分析可讓使用者透過引導式工作流程(以Customer Journey Analytics的跨管道資料為基礎)，針對客戶歷程提供高品質的資料和深入分析。 從行銷到產品的跨職能團隊可以即時連線，以使用和瞭解這些報表。

>[!NOTE]
>
> 引導式分析目前僅能作為Adobe Product Analytics的一部分提供，這是Customer Journey Analytics的付費附加元件。 如果您的組織想要開始使用這組功能，請聯絡您的Adobe客戶團隊。

引導式分析類似於Analysis Workspace和行動計分卡，使用來自 [資料檢視](../data-views/data-views.md)，會透過參照Adobe Experience Platform中的資料 [連線](../connections/overview.md). 在引導式分析中建立的許多報表，皆可順暢地傳輸至Analysis Workspace以供進一步研究。

下列引導式分析檢視可供使用：

| 分析類型 | 檢視類型 | 說明 |
| --- | --- | --- |
| [!UICONTROL 漏斗] | [摩擦](types/friction.md) | 比較步驟之間的轉換率。 |
| [!UICONTROL 漏斗] | [轉換趨勢](types/conversion-trends.md) | 追蹤轉換率在一段時間內的變化。 |
| [!UICONTROL 影響] | [版本](types/release.md) | 比較發行前後的相同期間效能。 |
| [!UICONTROL 影響] | [首次使用](types/first-use.md) | 測量首次功能使用對關鍵指標的影響。 |
| [!UICONTROL 保留] | [保留率](types/retention-rates.md) | 衡量使用者持續的回訪習慣。 |
| [!UICONTROL 趨勢] | [使用狀況](types/usage.md) | 測量一段時間內的使用者參與。 |
| [!UICONTROL 趨勢] | [頻率](types/frequency.md) | 透過使用頻率測量參與度。 |
| [!UICONTROL 使用者成長] | [作用中](types/active.md) | 識別新人、保留人、回訪者或休眠者。 |
| [!UICONTROL 使用者成長] | [淨增長](types/net-growth.md) | 您正在獲得還是失去使用者? |
| [!UICONTROL 使用者資料流] | [時間表](types/timeline.md) | 探索工作階段活動中的模式。 |

{style="table-layout:auto"}

## 存取

如果您的組織已針對引導式分析進行布建，您可以從Customer Journey Analytics首頁存取它。

1. 按一下 **[!UICONTROL 引導式分析]** 從首頁，直接前往 [使用趨勢檢視](types/usage.md).

   ![登陸頁面圖磚](assets/landing-page-tile.png){style="border:1px solid gray"}

1. 按一下 **[!UICONTROL 新建]** 檢視不同的檢視選項，並為您的分析選擇不同的起點。

   ![建立新強制回應視窗](assets/create-new-modal.png){style="border:1px solid gray"}

如果貴組織尚未布建引導式分析，請聯絡您的Adobe客戶團隊。

## 介面

引導式分析的介面會遵循問與答格式。 在查詢邊欄中形成您的問題，然後透過書面分析、圖表和表格獲得答案。 然後您可以透過檢視型別和視覺效果設定來詢問下一個問題。

引導式分析使用下列UI元素：

| 介面預覽 | UI 元素 | 說明 |
| --- | --- | --- |
| ![查詢邊欄](assets/query-rail.png){style="border:1px solid gray"} | 查詢邊欄 | 設定您的「問題」，即選取構成分析的所需元件（事件、屬性和區段）。 以下選項適用於所有檢視型別，其他設定則適用於每個檢視。 <ul><li>**分析選擇器**：可讓您切換至新分析型別的下拉式清單。 您的查詢選取範圍會維持在新的分析型別允許的限制內。</li><li>**檢視選擇器**：下拉式清單，可讓您針對您形成的查詢切換至新檢視（「回答」）。 您的查詢選取項會維持在新的檢視型別所允許的限制內。</li><li>**活動**：您要測量的事件。 每個檢視型別都會強制實施您可設定的事件數限制。</li><li>**篩選器**：使用 ![篩選](assets/filter.png) 圖示加以劃分，依特定屬性來縮小。 選取屬性時，兩個標準篩選條件(例如 [!UICONTROL 等於]， [!UICONTROL 包含]，或 [!UICONTROL 結尾為])和前1000個屬性值可供使用。</li><li>**計為**：您要套用至所選事件的計數方法。</li><li>**區段**：您要測量的區段。 每個檢視型別都會對可設定的區段數實施不同的限制。</li></ul> |
| ![圖表](assets/chart.png){style="border:1px solid gray"} | 圖表 | 根據您從查詢邊欄和設定輸入的資料，針對傳回的資料視覺效果。 您看到的視覺效果取決於圖表上方的檢視和設定。 此圖表也包含： <ul><li>**工具提示**：將游標停留在任何圖表資料點上，就會顯示包含更多資訊的工具提示。</li><li>**圖例**：將游標停留在圖表圖例序列上可檢視可用定義、聚焦於該序列，並暫時隱藏其他序列。 按一下圖例以隱藏數列。</li><li>**註解**：適用 [註解](../components/annotations/overview.md) 在視覺效果和圖例之間可見。 它會顯示為 ![註解圖示](assets/annotation.png) 圖示中設定的顏色。 顯示一段時間內資料的檢視型別位置 ![註解圖示](assets/annotation.png) 圖示加以搜尋。 若檢視型別未顯示一段時間的資料，則會顯示 ![註解圖示](assets/annotation.png) 圖示加以顯示。</li><li>**點按動作**：以滑鼠左鍵按一下任何資料點，公開可用的後續動作。 選項包括 **儲存區段**.</li></ul> |
| ![表格](assets/table.png){style="border:1px solid gray"} | 表格 | 根據您從查詢邊欄和設定輸入的資料傳回的表格表示法。 表格中的欄取決於圖表上方的檢視型別。 此表格也包含： <ul><li>**點按動作**：切換以隱藏或顯示圖表數列 ![顯示隱藏圖示](assets/hide-in-chart.png) 圖示加以填入。 按一下 **[!UICONTROL 更多]** 功能表。 選項包括 **儲存區段**.</li></ul> |
| ![視覺效果設定](assets/visualization-settings.png){style="border:1px solid gray"} | 視覺效果設定 | 圖表上方的選項可讓您詢問下一個問題，並自訂圖表和表格傳回資料的方式。 以下選項適用於所有檢視型別，其他設定則適用於每個檢視。 <ul><li>**圖表設定**：微調圖表和表格顯示的內容。 可用的選項取決於選取的檢視。</li><li>**日期範圍**：日曆選擇器，可讓您決定分析的日期範圍。 您也可以選取趨勢檢視的間隔，例如每日、每週或每月。</li><li>**Insights**：內容深入解析取決於您檢視的分析。 您可以使用箭頭來定位以取得其他見解，或使用右上角的燈泡圖示來顯示或隱藏這些見解。</li></ul> |
| ![選單](assets/menu.png){style="border:1px solid gray"} | 選單 | 引導式分析右上角的命令，可為您的分析提供總體動作。<ul><li>**資料檢視選擇器**：變更分析使用的資料檢視。 當您變更資料檢視時，查詢邊欄中的可用元件也會變更。</li><li>**複製連結**：將分析的連結複製到剪貼簿。 共用前會提示您儲存。</li><li>**共用**：開啟共用強制回應視窗，其中包含其他可共用給個別使用者或群組的選項。 共用前會提示您儲存。</li><li>**儲存**：儲存分析。 如果您要儲存新的分析，會出現一個強制回應視窗，要求輸入名稱和說明。</li><li>**另存為**：將分析與目前分析分開儲存，並建立副本。 系統會顯示一個強制回應視窗，要求您提供新的名稱和說明。</li><li>**在工作區中開啟**：在Analysis Workspace中重新建立目前的引導式分析。 Workspace專案是在新標籤中建立，以防止在引導式分析中工作時發生中斷。 它是分析的副本，在開啟後不會與原始引導分析保持同步。 當您想要將資料移交分析團隊或深入瞭解引導式分析所允許的資料時，請使用此命令。</li><li>**複製到剪貼簿**：將圖表圖形複製到剪貼簿，以貼到其他應用程式中。 查詢邊欄和表格未包含在圖形中。</li><li>**下載PNG**：將圖表圖形下載為 `.png`. 查詢邊欄和表格未包含在圖形中。</li><li>**下載CSV**：將表格資料下載為 `.csv`. 查詢邊欄和圖表未包含在檔案中。</li></ul> |

{style="table-layout:auto"}

## 佈建

引導式分析屬於Adobe Product Analytics的一部分，是Customer Journey Analytics的付費附加元件。 如果您的組織想要開始使用這組功能，請聯絡您的Adobe客戶團隊。

您的組織布建為使用引導式分析後，產品設定檔管理員可以在Adobe Admin Console中新增或移除對分析的存取權。

1. 登入 [Adobe Admin Console](https://adminconsole.adobe.com).
1. 選取 **[!UICONTROL Customer Journey Analytics]** 在產品清單中。
1. 針對您要編輯的許可權，選取所需的產品設定檔。
1. 按一下 **[!UICONTROL 許可權]** 標籤，然後按一下 **[!UICONTROL 編輯]** 在 [!UICONTROL 報告工具].
1. 按一下旁的加號圖示 **[!UICONTROL 引導式分析存取]** 在清單中 [!UICONTROL 可用的許可權專案]，這會將其新增至 [!UICONTROL 包含的許可權專案].
1. 按一下「**[!UICONTROL 儲存]**」。

>[!TIP]
>
>有些管理員偏好啟用引導式分析，也偏好停用Analysis Workspace以供新使用者Customer Journey Analytics。 這些使用者熟悉產品和您的組織資料後，您就可以啟用Analysis Workspace的存取權。
