---
description: 您可以複製Analysis Workspace的資料，或以PDF和CSV格式下載資料。
title: 下載 PDF 或 CSV 檔案
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 12%

---


# 下載 PDF 或 CSV 檔案

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

從Analysis Workspace匯出資料有幾種不同的方式，這取決於您要在工具外部分析的資料集以及需要接收資訊的人員。 匯出的資料可以是複製資料、CSV或PDF檔案的形式。 如果您想要將視覺化內容包含在檔案中，通常偏好使用PDF，而如果您只想要純文字資料，則偏好使用CSV（或複製的資料）。

## 將專案下載為CSV或PDF {#download-project}

您可以前往「**[!UICONTROL 專案>下載為PDF（或CSV）]**」下載完整專案。 下載的檔案包含專案中所有顯示的（可見）表格和視覺化。 如果您想要將視覺化內容包含在檔案中，通常偏好使用PDF，而如果您只想要純文字資料，則偏好使用CSV。

![](assets/download-project.png)

對於專案下載，請記住：

* 當您要求下載專案時，可以儲存或儲存專案。 但是，只有儲存的專案可以是[scheduled](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html)。
* 在瀏覽器中下載的PDF可能需要幾分鐘的時間才能匯出，因為專案會在Adobe伺服器上重新執行，然後再以PDF格式轉譯。 建議您在 PDF 下載到瀏覽器之前不要退出專案。不過，您可以在等待時繼續變更專案。如果PDF的轉譯時間超過5分鐘，則會提示您以電子郵件傳送。
* PDF下載會呈現為單一頁面，不會套用分頁。
* 當專案轉譯為PDF時，我們會轉譯頁面上的內容。 如果專案有自訂視覺效果和面板，您必須將其變更為自動縮放 (右上角按鈕)，內容才不會遭截斷。

## 將資料複製到剪貼簿(熱鍵：Ctrl+C){#copy-data}

按一下右鍵選項&#x200B;**[!UICONTROL 複製到剪貼簿]**&#x200B;可讓您快速從工作區複製資料並將其貼上到其他位置。

* 如果要複製顯示的表，請按一下右鍵表標題並選擇&#x200B;**將資料複製到剪貼簿**。
* 如果要複製資料子集，請在表中進行選擇，然後按一下右鍵> **將選擇複製到剪貼簿**。

此外，熱鍵`Ctrl+C`會將您的選擇複製到剪貼簿。 複製後，您可以進入另一個工具並貼上資訊（或按`Ctrl+V`）。

![](assets/copy-selection.png)

## 將資料下載為 CSV 檔 {#download-data}

右鍵按一下選項&#x200B;**[!UICONTROL 「以CSV格式下載資料」可讓您下載資料表格或任何視覺化的CSV格式資料來源。]**

* 在任何表格或視覺化的標題中，以滑鼠右鍵按一下「以CSV格式下載資料」。 ****&#x200B;如此會下載表格或基礎資料來源中顯示的資料，以供視覺化為CSV。 注意：地圖視覺化不支援此選項。
* 如果在表格中做出選擇，則選項會顯示「將選擇下載為CSV ]**」。**[!UICONTROL &#x200B;與顯示的完整表格相比，只有選擇內容會使用此選項下載。

![](assets/download-data-viz.png)

## 將項目下載為 CSV 檔 {#download-items}

如果要分析表中超過400行的可見資料，請按一下右鍵表標題或任何行，然後選擇&#x200B;**將項目下載為CSV(Dimension名)**。 此選項最多可針對選取的維度匯出50,000個維度項目（根據表格排序），並套用篩選和區段。 如果從表頂部選擇此選項，則將導出表中的第一個維。 雖然自由表格中不會強制限制，但建議在少於20欄的表格中使用「下載項目」選項，以確保最佳效能。

>[!TIP]
>
> 如果您的維度超過50,000個項目，請下載套用不同排序度量的檔案或套用篩選。 例如，在一次下載中依瀏覽次序排序，然後在第二次下載中依瀏覽次序排序。 此提示可協助您擷取長尾項目。

您可以在專案中執行多項工作，甚至在下載進行中時，在同一標籤中導覽至新的工作區專案。 如果您開啟新的瀏覽器標籤，下載將會暫停。 如果您完全離開工作區或關閉瀏覽器標籤，下載將會取消。

![](assets/download-items.png)

### 下載的項目檔案

表格的功能將應用於下載的檔案，如下所示：

* 所有面板區段都會套用為濾鏡。
* 表格中所選維度的上方&#x200B;**劃分會套用為每欄上方的篩選。**
* 在&#x200B;**下方的劃分會移除表格中選取的維度。**

在上述範例中，頁面項目會隨面板區段（新訪客客戶）和上述元件（行銷渠道=電子郵件）一起下載，並套用為篩選器，而下列元件（行動裝置類型）則會從下載的CSV中移除。

![](assets/downloaded-file.png)

### 下載通知

當檔案下載時，您會看到進度的資訊性通知。 您隨時可以按一下&#x200B;**[!UICONTROL 取消下載]**&#x200B;來取消下載。 關閉吐司&#x200B;**將不會**&#x200B;取消下載。

檔案完成後，您會看到完成通知，檔案將會下載至您的瀏覽器。

如果您一次要求多個下載，您會收到通知，告知每個額外的下載都會佇列等候，直到先前的下載完成為止。

![](assets/toast.png)

## 常見問題集 {#faq}

| 問題 | 回答 |
| --- | --- |
| 我下載的PDF為何只有一頁？ | 工作區目前不會將下載的PDF分頁。 |
| 我可以使用「以CSV格式下載項目」選項匯出超過50,000個項目嗎？ | 雖然每次下載最多可包含50,000個維度項目，但您可以變更表格的類型，以擷取較長的尾部項目，或套用篩選來下載更多特定項目。 |
| **[!UICONTROL 複製視覺化]**&#x200B;的功能為何？ | **[!UICONTROL 複製]** 視覺化不是匯出選項。它可讓您將視覺化或面板從工作區的某個位置複製到另一個位置。 例如，在同一個專案中，從一個面板移至另一個面板，或從一個專案移至另一個專案。 [內部連結視訊](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |

