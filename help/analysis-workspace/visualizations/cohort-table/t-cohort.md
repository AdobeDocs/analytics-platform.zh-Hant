---
description: 在Analysis Workspace中建立同類群組表格並執行同類群組分析。
keywords: Analysis Workspace
title: 設定同類群組表格
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: b38e9052618f7326cd5ea22b6cda8b96624a3f84
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 34%

---

# 設定同類群組表格

若要建立及設定[!UICONTROL 同類群組表格]：

1. 新增![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表格]**&#x200B;視覺效果。 請參閱[將視覺效果新增至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 按照下表的定義，對&#x200B;**[!UICONTROL 「包含條件」]**、**[!UICONTROL 「回傳條件」]**、**[!UICONTROL 「同類群組類型」]**&#x200B;和&#x200B;**[!UICONTROL 「設定」]**&#x200B;設定定義。

   ![設定同類群組表格](assets/cohort-configure.png)

   | 元素 | 說明 |
   |--- |--- |
   | **[!UICONTROL 包含條件]** |  您可以套用最多 10 個包含篩選器和最多 3 個包含量度。 此量度會指定使用者所屬的同類群組。 例如，如果包含量度是「訂單」，則只有在同類群組分析的時間範圍內下訂單的使用者，才會包含在初始同類群組中。<br>量度間的預設運算子為「和」，但您可以將其變更為「或」。此外，您也可以為這些量度新增數值篩選條件。例如： `Sessions >= 1`.</br> |
   | **[!UICONTROL 傳回條件]** | 您可以套用最多 10 個回訪篩選器和最多 3 個回訪量度。 該量度指出已保留使用者 (保留率) 或未保留使用者 (流失率)。例如，如果傳回量度是「視訊檢視」，則後續時段內（加入同類群組的時段後）檢視視訊的使用者，只會顯示為「保留」。 另一個量化保留的量度是「工作階段」。 |
   | **[!UICONTROL 詳細程度]** | 日、週、月、季或年的時間詳細程度。 |
   | **[!UICONTROL 類型]** | **[!UICONTROL 保留率]** （預設）： **[!UICONTROL 保留率]**&#x200B;同類群組可衡量一段時間中，同類群組回訪您網站的程度。 保留率同類群組是標準同類群組，可指出回訪和重複的使用者行為。 綠色表示表格中的[!UICONTROL 保留率]同類群組。<br>**[!UICONTROL 流失率&#x200B;]**：**[!UICONTROL &#x200B;流失率&#x200B;]**（也稱為流失率或流失率）同類群組會衡量一段時間中，您網站的同類群組流失程度。 流失率與保留率相反： `Churn = 1 - Retention`。 [!UICONTROL 流失率會向您顯示客戶未回訪的頻率，非常適合用來衡量黏著度及商機。]您可以使用流失率來分析並找出重點區域，了解可能需要關注哪些同類群組篩選器。 紅色表示表格中的[!UICONTROL 流失率]同類群組（類似於**[!UICONTROL &#x200B;流量&#x200B;]**視覺效果中的流失）。</br> |
   | **[!UICONTROL 設定]** | **[!UICONTROL 滾動式計算]**：根據上一欄計算保留率或流失率，而非根據「包含」欄（預設）。 [!UICONTROL 「滾動式計算」會變更「回訪」期間的計算方法。]一般計算會找出符合回訪標準且屬於包含期間的使用者。 無論他們是否在先前時段的同類群組中。 相對地，[!UICONTROL 滾動式計算]會找出符合「回訪」標準、且屬於先前時段的使用者。因此，[!UICONTROL 滾動式計算]會篩選並彙集在各時段持續符合「回訪」標準的使用者。[!UICONTROL Return]條件會套用至所選期間之前的每個期間。 </br><br>**[!UICONTROL 延時表格&#x200B;]**： [!UICONTROL 延時表格]會測量包含事件發生前後的經過時間。 [!UICONTROL 延時表格]非常適合用於事前/事後分析。 例如，您有即將推出的產品或行銷活動，且您想要追蹤行銷活動前後的行為。 [!UICONTROL 延時表格]會並排顯示事前和事後的行為，以檢視直接影響。 [!UICONTROL 延時表格]中的包含前儲存格，會計算在包含時段符合[!UICONTROL 包含]條件，然後在包含時段之前的時段符合[!UICONTROL 回訪]條件的使用者。 請注意，[!UICONTROL 延遲資料表]和[!UICONTROL 自訂維度同類群組]不能一起使用。</br><br>**[!UICONTROL 自訂維度同類群組]**：根據選取的維度建立同類群組，而非根據以時間為主的同類群組（預設）。 許多客戶希望能透過時間以外的其他方法分析其同類群組，而新的「自訂維度同類群組」功能，可靈活地根據客戶選擇的維度建立同類群組。 使用行銷管道、行銷活動、產品、頁面、地區等維度，說明保留率在不同維度值的變化。 [!UICONTROL 自訂維度]同類群組篩選器定義只會將維度項目套用為包含時段的一部分，而非回訪定義的一部分。 </br><br>選擇[!UICONTROL 自訂維度同類群組]選項後，您可以將任何需要的維度拖放至拖放區域。 新增維度可讓您比較相同時段內的類似維度專案。 例如，您可以並排比較城市效能、產品、行銷活動等。 同類群組表格會傳回前14個維度專案。 不過，您可以使用![篩選器](/help/assets/icons/Filter.svg)篩選器，只顯示想要的維度專案。 [!UICONTROL 自訂維度同類群組]無法搭配[!UICONTROL 延遲資料表]功能使用。</br> |

1. 按一下&#x200B;**[!UICONTROL 建置]**。
1. 若要重新設定[!UICONTROL 同類群組表格]，請選取![編輯](/help/assets/icons/Edit.svg)。

1. （選用）從選取專案建立篩選條件或對象。

   選取儲存格 (連續或非連續)，然後按一下滑鼠右鍵 >**[!UICONTROL 「從選取項目建立篩選器」。]**.

   ![建立篩選器或對象](assets/retention-createfilter.png)

1. 在[篩選產生器](/help/components/filters/filter-builder.md)中，進一步編輯篩選，然後按一下&#x200B;**[!UICONTROL 儲存]**。

   已儲存的篩選器可用於 [!UICONTROL Analysis Workspace] 中的[!UICONTROL 篩選器]面板。

## 設定

您可以定義[!UICONTROL 同類群組表格]的特定設定。

1. 選取![設定](/help/assets/icons/Setting.svg)以調整[!UICONTROL 同類群組表格]設定。

   | 設定 | 說明 |
   |---|---|
   | **僅顯示百分比** | 移除數值並僅顯示百分比。 |
   | **將百分比四捨五入到最接近的整數** | 將百分比四捨五入為最接近的整數，而非顯示小數值。 |
   | **顯示平均百分比列** | 在表格頂端插入新列，然後在每個欄中加入平均值。 |


>[!MORELIKETHIS]
>
>[將視覺效果新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺效果內容功能表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

