---
description: 若要從 Analysis Workspace 下載資料，請複製該資料或使用 PDF 和 CSV 格式。
title: 下載 Customer Journey Analytics 檢視
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 9a15cb4d771892ff656fe72b8e53d890a3fd99f7
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 100%

---

# 下載 Customer Journey Analytics 檢視

您可以將 Customer Journey Analytics 資料下載到您的個人工作站。這可以是資料、CSV 或 PDF 形式。如果您希望下載的檔案中包含視覺效果，通常需優先使用 PDF。如果您只需要純文字資料，則更適合使用 CSV 和複製的資料。

還有匯出 Customer Journey Analytics 資料的其他方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)所述。

## 下載為 CSV 或 PDF {#download-project}

下載專案時，請考慮以下事項：

* 當您將專案下載為 CSV 或 PDF，且當您要求專案下載時可儲存或取消儲存該專案。但只有已儲存的專案才可以[排程](/help/analysis-workspace/export/t-schedule-report.md)。

* 下載專案為 PDF 時：
   * 下載項目可能需要幾分鐘的時間才能匯出，因為專案會先在 Adobe 伺服器上重新執行，然後才會以 PDF 格式呈現。 建議您在 PDF 下載到瀏覽器之前不要退出專案。 不過，您可以在等待時繼續變更專案。 如果呈現 PDF 需要 5 分鐘以上的時間，系統將提示您改為透過電子郵件發送。
   * 下載項目將呈現為單一頁面，而不套用任何分頁。
   * PDF 轉譯包含 Workspace 中頁面的內容。如果專案有自訂大小的視覺效果和面板，您必須將其變更為自動縮放 (右上角按鈕)，內容才不會遭截斷。
   * 自由格式表格內若有任何[超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)，在下載的 PDF 中都不能使用。

若要將專案匯出/下載為 CSV 或 PDF 檔案：

1. 視您想要下載的格式而定，執行下列任一動作：

   * **PDF：**&#x200B;選取「**[!UICONTROL 專案]** > **[!UICONTROL 下載 PDF]**」。

     如果您希望下載的檔案包含專案中所有顯示 (可見) 的表格和視覺效果，請選擇此選項。

   * **CSV：**&#x200B;選取「**[!UICONTROL 專案]** > **[!UICONTROL 下載 CSV]**」。

     如果您希望下載的檔案是純文字，請選擇此選項。

   ![專案下拉式選單，下載 CSV 和下載 PDF 選項會醒目顯示。](assets/download-project.png)

1. (視情況而定) 如果您選擇下載 PDF，則在專案準備好下載後會顯示一則訊息。選取「[!UICONTROL **下載**]」。

## 複製到剪貼簿 (快速鍵：Ctrl+C) {#copy-data}

按滑鼠右鍵選項「**[!UICONTROL 複製到剪貼簿]**」可讓您快速地複製 Workspace 中的 Customer Journey Analytics 資料，並將其貼上到協力廠商工具中。

* 如果您想要複製顯示的表格，請在表格標頭上按一下滑鼠右鍵，並選擇「**將資料複製到剪貼簿**」。
* 如果您想要複製一部分資料，請在表格中選進行取，然後按一下滑鼠右鍵 >「**將選取內容複製到剪貼簿**」。

>[!TIP]
>
>您可以使用快速鍵 `Ctrl+C` 將選取內容複製到剪貼簿，然後使用 `Ctrl+V` 將其貼上到協力廠商工具中。


![「複製」選擇複製到剪貼簿選項。 ](assets/copy-selection.png)

## 下載為 CSV {#download-data}

按滑鼠右鍵選項「**[!UICONTROL 將資料下載為 CSV 檔]**」可讓您將 Customer Journey Analytics 資料的表格或任何視覺效果的資料來源下載為 CSV 檔。

* 從任何表格的標頭或視覺效果，按一下滑鼠右鍵，然後選擇「**[!UICONTROL 將資料下載為 CSV 檔]**」。這樣會將表格中顯示的Customer Journey Analytics 資料或視覺效果的基本資料來源下載為 CSV 檔。

  >[!NOTE]
  >
  >  注意：地圖視覺效果不支援此選項。


* 在表格中按一下滑鼠右鍵，然後選擇「**[!UICONTROL 將選取內容下載為 CSV 檔]**」。使用此選項只會下載選取內容，不會下載完整的顯示表格。

![下載資料為 CSV 選項。](assets/download-data-viz.png)

## 將項目下載為 CSV 檔 {#download-items}

如果您想要分析的範圍超過表格中顯示的 400 列資料，請用滑鼠右鍵按一下表格標頭或任一列，然後選取「**將項目下載為 CSV 檔 (_維度名稱_)**」。此選項可針對選取的維度匯出多達 50,000 個維度項目 (根據表格排序)，並有套用的排序選項和篩選器。如果您從表格最上方選擇此選項，將會匯出表格中的第一個維度。 當自由表格中未實施任何限制時，建議您在小於 20 欄的表格中使用「下載」項目選項，以確保最佳效能。

>[!TIP]
>
> 如果您的維度超出 50,000 個項目，請下載已套用不同排序量度的檔案或套用區段。例如，在某個下載中依「瀏覽數」進行遞減排序，並在第二個下載中依「瀏覽數」進行遞增排序。 此訣竅可幫助您擷取較冷門的項目。

您可以在專案中進行多工處理，甚至可以在下載進行中時，導覽至相同索引標籤中的新 Workspace 專案。 如果您開啟新的瀏覽器索引標籤，下載作業就會暫停。如果您完全離開 Workspace 或關閉瀏覽器索引標籤，下載作業就會取消。

![將項目下載為 CSV (頁面) 選項。](assets/download-items.png)

### 已下載的項目檔案 {#items-file}

表格的特性將會套用到已下載的檔案，如下所示：

* 所有面板區段都會套用為篩選條件。
* 表格中所選維度&#x200B;**上方**&#x200B;的劃分會套用為每一欄上方的篩選條件。
* 表格中所選維度&#x200B;**下方**&#x200B;的劃分則會被移除。

在上述範例中，當下載頁面項目時，會將面板區段 (新訪客客戶) 和上方元件 (行銷管道 = 電子郵件) 套用為篩選條件，並從下載的 CSV 檔中移除下方元件 (行動裝置類型)。

![下載的.csv 檔案在 Excel 中開啟。](assets/downloaded-file.png)

### 下載通知 {#notifications}

在下載檔案時，您將會看到包含進度指示的告知性通知。 您隨時都可以按一下「**[!UICONTROL 取消下載]**」來取消下載作業。 關閉快顯通知&#x200B;**將不會**&#x200B;取消下載。

檔案完成時，您將會看到完成通知，而且檔案將會下載到您的瀏覽器。

如果您一次要求多項下載，您將會收到通知，告知您每項額外下載要等到前一個下載完成時才會排入佇列中。

![下載狀態通知會顯示完成百分比和取消下載連結。](assets/toast.png)

## 下載敏感性資料 {#sensitive}

如果在您報告的資料檢視中開啟&#x200B;**[!UICONTROL 強制下載]** [資料控管原則](/help/data-views/data-governance.md)，工作區專案的任何下載 (例如電子郵件或共用 PDF 檔案) 都會將標示為敏感的資料欄位進行雜湊處理。您仍可以對工作區中的這些欄位進行分析，但如果您嘗試寄電子郵件或共用專案，遭封鎖的欄位將在 .pdf 或 .csv 檔案中以空白形式出現。

如果在[!UICONTROL 資料檢視]中含有任何標示為敏感的資料欄位，則對於[!UICONTROL 資料檢視]中的所有資料，要從畫面選取和複製資料的選項將會受到限制。

## 常見問答 {#faq}

| 問題 | 回答 |
| --- | --- |
| 為什麼我下載的 PDF 是單頁的？ | Workspace 目前無法將下載的 PDF 分頁。 |
| 我可以使用「將項目下載為 CSV 檔」選項匯出超過 50,000 個項目嗎？ | 雖然每項下載最多可包含 50,000 個維度項目，您還是可以變更表格的排序，以擷取較冷門的項目，或是套用篩選條件來下載更明確的項目。 |
| 「**[!UICONTROL 複製視覺效果]**」有什麼作用？ | 與「[!UICONTROL **將資料複製到剪貼簿**]」或「[!UICONTROL **將選取內容複製到剪貼簿**]」不同的是，「**[!UICONTROL 複製視覺效果]**」按滑鼠右鍵選項並非匯出選項。它可讓您將 Workspace 中某個位置的視覺效果或面板複製到另一個位置。 例如，從某個面板複製到相同專案中的另一個面板，或是從某個專案複製到另一個專案。 [內部連結影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=zh-Hant) |
