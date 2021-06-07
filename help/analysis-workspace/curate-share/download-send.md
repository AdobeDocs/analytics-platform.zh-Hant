---
description: 您可以複製Analysis Workspace中的資料，或以PDF和CSV格式下載資料。
title: 下載 PDF 或 CSV 檔案
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 10%

---

# 下載 PDF 或 CSV 檔案

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant)。[深入了解...](/help/getting-started/cja-aa.md)

您可以透過數種不同的方式從Analysis Workspace匯出資料，端視您要在工具外部分析的資料集，以及需要接收資訊的人員而定。 匯出的資料可以是複製資料、CSV或PDF檔案的形式。 如果您想要將視覺效果納入檔案中，通常偏好使用PDF，而如果只想要純文字資料，則偏好使用CSV（或複製資料）。

## 將專案下載為CSV或PDF {#download-project}

您可以前往「**[!UICONTROL 專案>以PDF格式（或以CSV格式）下載完整專案」]**。 下載的檔案包含專案中所有顯示（可見）的表格和視覺效果。 如果您想要將視覺效果納入檔案中，通常會偏好使用PDF；如果只想要純文字資料，則偏好使用CSV。

![](assets/download-project.png)

若是專案下載項目，請記住：

* 當您要求下載專案時，可以儲存或儲存專案。 不過，只有儲存的專案可以是[scheduled](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html)。
* 在瀏覽器中下載的PDF可能需要幾分鐘的時間才能匯出，因為專案會在Adobe伺服器上重新執行，然後才會以PDF格式轉譯。 建議您在 PDF 下載到瀏覽器之前不要退出專案。不過，您可以在等待時繼續變更專案。如果PDF的轉譯時間超過5分鐘，系統會提示您以電子郵件傳送。
* PDF下載會呈現為單一頁面，不套用分頁。
* 將專案轉譯為PDF時，我們會轉譯頁面上的內容。 如果專案有自訂視覺效果和面板，您必須將其變更為自動縮放 (右上角按鈕)，內容才不會遭截斷。

## 將資料複製到剪貼簿(熱鍵：Ctrl+C){#copy-data}

按一下右鍵選項&#x200B;**[!UICONTROL 複製到剪貼簿]**&#x200B;可讓您快速從工作區複製資料並貼到其他位置。

* 如果要複製顯示的表，請按一下右鍵表頭，然後選擇&#x200B;**將資料複製到剪貼簿**。
* 如果要複製資料的子集，請在表中進行選擇，然後按一下右鍵> **將選擇複製到剪貼簿**。

此外，熱鍵`Ctrl+C`將您的選擇複製到剪貼簿。 複製後，您可以前往其他工具並貼上資訊（或點擊`Ctrl+V`）。

![](assets/copy-selection.png)

## 將資料下載為 CSV 檔 {#download-data}

按一下滑鼠右鍵選項&#x200B;**[!UICONTROL 以CSV格式下載資料]**&#x200B;可讓您下載資料表或任何以CSV格式顯示之視覺效果的資料來源。

* 在任何表格或視覺效果的標題中按一下滑鼠右鍵&#x200B;**[!UICONTROL 以CSV格式下載資料]**。 如此會將顯示的資料下載至表格或CSV格式的視覺效果基礎資料來源。 注意：地圖視覺效果不支援此選項。
* 如果已在表格中選取，選項會顯示「**[!UICONTROL 以CSV格式下載選取項目」。]**&#x200B;只下載帶有此選項的選項，而不是顯示的完整表。

![](assets/download-data-viz.png)

## 將項目下載為 CSV 檔 {#download-items}

如果要分析表中400行以上可見的資料，請按一下右鍵表頭或任何行，然後選擇&#x200B;**以CSV格式下載項目(Dimension名稱)**。 此選項最多會針對選取的維度匯出50,000個維度項目（根據表格排序），並套用篩選器和篩選器。 如果您從表格頂端選取此選項，則會匯出表格中的第一個維度。 雖然自由表格中不會強制執行任何限制，但建議在少於20欄的表格中使用「下載項目」選項，以確保提供最佳效能。

>[!TIP]
>
> 如果您的維度超過50,000個項目，請下載套用不同排序量度的檔案或套用篩選器。 例如，在一次下載中依瀏覽次數遞減排序，在第二次下載中依瀏覽次數遞增排序。 此提示可協助您擷取長尾項目。

您可以在專案內執行多項工作，甚至在下載進行中時，在相同索引標籤中導覽至新的Analysis Workspace專案。 如果您開啟新的瀏覽器標籤，下載會暫停。 如果您完全離開工作區或關閉瀏覽器標籤，下載將取消。

![](assets/download-items.png)

### 下載的項目檔案

表格的功能會套用至下載的檔案，如下所示：

* 所有面板篩選器都會套用為篩選器。
* 表格中所選維度的上方&#x200B;**劃分會套用為每欄上方的篩選器。**
* 表格中所選維度的下方&#x200B;**劃分會遭移除。**

在上述範例中，頁面項目會以面板篩選器（新訪客客戶）和上方元件（行銷管道=電子郵件）的形式套用為篩選器，而下方元件（行動裝置類型）則會從下載的CSV中移除。

![](assets/downloaded-file.png)

### 下載通知

當檔案下載時，您會看到提供資訊的進度通知。 您隨時可以按一下&#x200B;**[!UICONTROL 取消下載]**&#x200B;取消下載。 關閉toast **不會**&#x200B;取消下載。

檔案完成後，您會看到完成通知，檔案會下載至您的瀏覽器。

如果您一次要求多個下載項目，您會收到通知，通知每個額外的下載項目都會排入佇列，直到先前的下載完成為止。

![](assets/toast.png)

## 常見問題集 {#faq}

| 問題 | 回答 |
| --- | --- |
| 為什麼下載的PDF為一頁？ | Workspace目前不會為下載的PDF分頁。 |
| 我可以透過「以CSV格式下載項目」選項匯出超過50,000個項目嗎？ | 雖然每個下載最多可包含50,000個維度項目，但您可以變更表格的排序以擷取較長的尾部項目，或套用篩選器以下載更多特定項目。 |
| **[!UICONTROL 複製視覺效果]**&#x200B;有何功能？ | **[!UICONTROL 複製]** 視覺效果不是匯出選項。它可讓您將視覺效果或面板從工作區的某個位置複製到另一個位置。 例如，在同一個專案中，從一個面板切換至另一個面板，或從一個專案切換至另一個專案。 [內部連結影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
