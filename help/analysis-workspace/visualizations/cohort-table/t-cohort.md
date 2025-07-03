---
description: 瞭解如何在Analysis Workspace中建立及設定同類群組表格，並執行同類群組分析報表。
keywords: Analysis Workspace
title: 設定同類群組表格
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 85%

---

# 設定同類群組表格

若要建立並設定[!UICONTROL 同類群組表格]：

1. 新增 ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同類群組表]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 按照下表的定義，對「**[!UICONTROL 包含條件]**」、「**[!UICONTROL 回傳條件]**」、「**[!UICONTROL 同類群組類型]**」和「**[!UICONTROL 設定]**」進行定義。

   ![設定同類群組表格](assets/cohort-configure.png)

   | 元素 | 說明 |
   |--- |--- |
   | **[!UICONTROL 包含條件]** | 您可以套用最多 10 個包含區段和最多 3 個包含量度。此量度指定使用者屬於哪個同類群組。例如，如果包含量度為「訂購」，則只有在同類群組分析的時間範圍內下訂單的使用者，才會包含在初始同類群組中。<br>量度間的預設運算子為「和」，但您可以將其變更為「或」。此外，您也可以為這些量度新增數值區段。 例如：`Sessions >= 1`、</br> |
   | **[!UICONTROL 回訪標準]** | 您可以套用最多 10 個回訪區段和最多 3 個回訪量度。該量度指出已保留使用者 (保留率) 或未保留使用者 (流失率)。例如，如果返回量度是「視訊檢視」，則只有在後續時段 (在將他們新增至同類群組後) 檢視視訊的使用者才會表示為保留。可以量化保留的另一個量度是「工作階段」。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 容器&#x200B;]** | 根據預設，同類群組分析會與「人員」容器繫結。 如果支援Workspace專案的帳戶式連線中有更多個人以外的容器可用，您可以從&#x200B;**[!UICONTROL 容器]**&#x200B;下拉式選單中選取其他容器以進行同類群組分析。 |
   | **[!UICONTROL 詳細程度]** | 日、週、月、季或年的時間詳細程度。 |
   | **[!UICONTROL 類型]** | **[!UICONTROL 保留率]** (預設)：**[!UICONTROL 保留率]**&#x200B;保留率同類群組會衡量一段時間中，人員同類群組回訪您網站的程度。保留同類群組為標準同類群組，表示返回和重複使用者行為。[!UICONTROL 保留率]同類群組在表格中以綠色表示。<br>**[!UICONTROL 流失率&#x200B;]**：**[!UICONTROL &#x200B;流失率&#x200B;]**(也稱為「減少」或「流失」) 同類群組會衡量一段時間中，您網站的人員同類群組流失情況。流失率和保留率相反：`Churn = 1 - Retention`。[!UICONTROL 流失率]透過顯示客戶未回訪的頻率，非常適合用來衡量黏著度和銷售機會。您可以使用流失率來分析並找出重點區域，瞭解可能需要關注哪些同類群組區段？ [!UICONTROL 流失率]同類群組在表格中以紅色表示 (類似於&#x200B;**[!UICONTROL &#x200B;流量&#x200B;]**&#x200B;視覺效果中的流失)。</br> |
   | **[!UICONTROL 設定]** | **[!UICONTROL 滾動式計算]**：根據上一欄計算保留率或流失率，而非根據「包含」欄 (預設)。[!UICONTROL 滾動式計算]會變更「回訪」期間的計算方法。一般計算會找出符合「回訪」標準，且屬於包含時段的使用者。無論他們是否屬於前一時段的同類群組。相對地，[!UICONTROL 滾動式計算]會找出符合「回訪」標準、且屬於先前時段的使用者。因此，[!UICONTROL 滾動式計算]區段並彙集在各時段持續符合「回訪」標準的使用者。 [!UICONTROL 回訪]標準會套用至選取時段之前的各個時段。</br><br>**[!UICONTROL 延遲表格&#x200B;]**：[!UICONTROL 延遲表格]會衡量包含事件發生前後的經過時間。[!UICONTROL 延遲表格]非常適合用於事前/事後分析。例如，您即將推出一款產品或啟動行銷活動，並且想要追蹤啟動前後的行為。[!UICONTROL 延遲表格]並排顯示前後行為，以查看直接影響。[!UICONTROL 延遲表格]的包含前儲存格，是根據在包含時段符合[!UICONTROL 包含]標準，且在包含時段前符合[!UICONTROL 回訪]標準的使用者來計算的。請注意，[!UICONTROL 延遲表格]和[!UICONTROL 自訂維度同類群組表格]無法同時使用。</br><br>**[!UICONTROL 自訂維度同類群組]**: 根據選取維度建立同類群組，而非根據以時間為主的同類群組 (預設)。許多客戶希望能透過時間以外的其他方法分析其同類群組，而新的「自訂維度同類群組」功能，可靈活地根據客戶選擇的維度建置同類群組。使用維度 (例如行銷管道、行銷活動、產品、頁面、區域或其他維度) 顯示保留率在不同維度值的變化。[!UICONTROL 自訂維度]同類群組區段定義只會將維度項目套用為包含時段的一部分，而非回訪定義的一部分。</br><br>選擇「[!UICONTROL 自訂維度同類群組]」選項後，您可以將任何需要的維度拖放至放置區。新增維度可讓您比較同一時段中類似的維度項目。例如，您可以並排比較城市、產品和促銷活動等的績效。同類群組表格會傳回您的前 14 個熱門維度項目。不過，您可以使用![區段](/help/assets/icons/Filter.svg)區段來僅顯示想要的維度專案。 [!UICONTROL 自訂維度同類群組]無法與[!UICONTROL 延遲表格]功能搭配使用。</br> |

1. 按一下「**[!UICONTROL 建置]**」。
1. 若要重新設定[!UICONTROL 同類群組表格]，請選取「![編輯](/help/assets/icons/Edit.svg)」。

1. （選用）從選取專案建立區段或對象。

   選取儲存格 (連續或非連續)，然後按一下滑鼠右鍵 >**[!UICONTROL 「從選取項目建立區段」]**。

   ![建立區段或對象](assets/retention-createfilter.png)

1. 在「[區段產生器](/help/components/segments/seg-builder.md)」中進一步編輯區段，然後按一下「**[!UICONTROL 儲存]**」。

   已儲存的區段可用於 [!UICONTROL Analysis Workspace] 中的[!UICONTROL 區段]面板。

## 設定

您可以定義[!UICONTROL 同類群組表格]的特定設定。

1. 請選取「![設定](/help/assets/icons/Setting.svg)」，以調整[!UICONTROL 同類群組表格] 設定。

   | 設定 | 說明 |
   |---|---|
   | **僅顯示百分比** | 移除數值並僅顯示百分比。 |
   | **將百分比四捨五入到最接近的整數** | 將百分比四捨五入為最接近的整數，而非顯示小數值。 |
   | **顯示平均百分比列** | 在表格頂端插入新列，然後在每個欄中加入平均值。 |


>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[視覺效果設定](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[視覺化內容選單](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

