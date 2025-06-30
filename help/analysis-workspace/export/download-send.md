---
description: 瞭解從Analysis Workspace專案下載資料的各種可能性。
title: 下載Analysis Workspace專案和資料
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 25%

---

# 下載專案和資料

您可以將Analysis Workspace專案和資料下載至本機裝置。 此下載檔案可以是複製資料、CSV （逗號分隔值資料）檔案或PDF （可攜式檔案格式）檔案。

* 如果您想要在下載的檔案中加入視覺效果，請選取PDF選項。
* 如果您只需要純文字資料，請選取CSV和複製的資料選項。

匯出Customer Journey Analytics資料的其他方法在[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)中說明。

## 下載為 CSV 或 PDF {#download-project}

![專案下拉式選單，下載 CSV 和下載 PDF 選項會醒目顯示。](assets/download-project.png)

將專案下載為PDF時，請考量下列事項：

* 由於專案會在Adobe伺服器上重新執行，以PDF格式呈現，因此下載作業可能需要幾分鐘的時間。 在瀏覽器中下載專案之前，請勿離開專案。  您可以在轉譯下載內容時繼續變更專案。 如果PDF的轉譯時間超過5分鐘，系統會提示您改為[傳送電子郵件給PDF](../curate-share/send-schedule-files.md)。
* 下載項目將呈現為單一頁面，而不套用任何分頁。
* PDF包含可在Analysis Workspace的瀏覽器頁面中看到的內容。 您必須自動調整自訂大小的視覺效果和面板大小，以免內容遭到截斷。 選取![調整大小](/help/assets/icons/Resize.svg)以自動調整自訂大小的視覺效果或面板的大小。
* 自由表格中的[超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)在下載的PDF中作為超連結。



若要將專案下載為PDF檔案：

1. 選取&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 下載PDF]**。
綠色長條圖，內含訊息![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 已要求您的下載。 請稍候。]**&#x200B;已顯示。

1. 只要您的下載準備就緒，就會出現綠色長條，內含訊息![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *專案名稱&#x200B;*PDF。]**出現。
選取**[!UICONTROL 下載]**以下載PDF。 PDF的顯示或下載方式取決於您用於處理PDF檔案的瀏覽器設定。


若要將專案下載為CSV檔案：

* 選取&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 下載CSV]**。 專案會直接下載至下載資料夾，此資料夾已設定為您瀏覽器設定的一部分。 檔案名稱由&#x200B;*專案名稱* - *報告套裝名稱* - *日期*&#x200B;組成，例如`Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`。

## 複製到剪貼簿 {#copy-data}

內容功能表中的&#x200B;**[!UICONTROL 複製到剪貼簿]**&#x200B;選項可讓您從Analysis Workspace快速複製資料，並將資料貼到協力廠商工具中。

* 如果您想要複製顯示的表格資料，請選取表格標頭，並從內容功能表選取&#x200B;**將資料複製到剪貼簿**。
* 如果您想要複製資料的子集，請在表格中選取專案，然後從內容功能表中選取&#x200B;**將選取專案複製到剪貼簿**。

>[!TIP]
>
>您可以使用快速鍵&#x200B;**_cmd + c_** (macOS)或&#x200B;**_ctrl + c_** (Windows)，將您的選取內容複製到剪貼簿。 然後使用&#x200B;**_cmd + v_** (macOS)或&#x200B;**_ctrl + v_** (Windows)貼上資料。


![「複製」選擇複製到剪貼簿選項。 ](assets/copy-clipboard.png){zoomable="yes"}

## 下載為 CSV {#download-data}

從快顯選單下載為CSV選項可讓您將資料表格或任何視覺效果的資料來源下載為CSV檔。

若要進行此步驟：

* 從任何表格或視覺效果的標題中，選取內容功能表中的&#x200B;**[!UICONTROL 將資料下載為CSV檔]**。 這樣會將表格中顯示的資料或視覺效果的基本資料來源下載為 CSV 檔。

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* 在表格中，從內容功能表選取&#x200B;**[!UICONTROL 將選取專案下載為CSV檔]**。 使用此選項只會下載選取內容，不會下載完整的顯示表格。

![下載資料為 CSV 選項。](assets/download-data-as-csv.png)

## 將項目下載為 CSV 檔 {#download-items}

如果您想要分析表格中超過400列的可見資料，請從表格標頭或任何一列的內容功能表中選取&#x200B;**以CSV格式下載專案(_Dimension名稱_)**。 此選項可針對選取的維度匯出多達 50,000 個維度項目 (根據表格排序)，並有套用的排序選項和篩選器。如果您從表格頂端選取此選項，會匯出表格中的第一個維度。

![將項目下載為 CSV (頁面) 選項。](assets/download-items-as-csv.png)

自由表格中不強制執行任何限制。 為確保最佳效能，建議在少於20欄的表格中使用此選項。

>[!TIP]
>
> 如果您的維度超出 50,000 個項目，請下載已套用不同排序量度的檔案或套用區段。例如，在某個下載中依「瀏覽數」進行遞減排序，並在第二個下載中依「瀏覽數」進行遞增排序。 此訣竅可幫助您擷取較冷門的項目。

您可以在專案中進行多工處理，甚至可以在下載進行中時，導覽至相同索引標籤中的新 Workspace 專案。 如果您開啟新的瀏覽器索引標籤，下載作業就會暫停。如果您完全離開 Workspace 或關閉瀏覽器索引標籤，下載作業就會取消。


### 已下載的項目檔案 {#items-file}

下列自由表格功能會套用至下載的檔案：

* 所有面板區段都會套用為篩選條件。
* 表格中所選維度&#x200B;**上方**&#x200B;的劃分會套用為每一欄上方的篩選條件。
* 表格中所選維度&#x200B;**下方**&#x200B;的劃分則會被移除。

![下載的.csv 檔案在 Excel 中開啟。](assets/download-items-file.png)

### 下載通知 {#notifications}

下載檔案時，您會看到下列通知：

* 已要求藍色&#x200B;**[!UICONTROL _資料表名稱&#x200B;_-_Dimension _.csv。_x _%完成]**，表示進度。 若要隨時取消下載，請選取&#x200B;**[!UICONTROL 取消下載]**。 若要關閉郵件，請選取![CrossSize100](/help/assets/icons/CrossSize100.svg)，這不會取消下載。
* 綠色&#x200B;**[!UICONTROL _資料表名稱&#x200B;_-_Dimension _.csv在檔案下載完成後已下載]**完成通知。 檔案會下載至為瀏覽器設定的下載資料夾。

如果您一次要求多項下載，您會收到通知，告知您每項額外下載要等到前一個下載完成時才會排入佇列。


## 下載敏感性資料 {#sensitive}

想像一下[資料治理原則](/help/data-views/data-governance.md)會防止資料下載。 而且會在您報告的資料檢視中開啟此原則。 因此，專案的任何下載(例如傳送電子郵件或共用PDF檔案時)都會對標示為敏感的資料欄位進行雜湊處理。 您仍可以在Analysis Workspace中分析這些欄位。 如果您嘗試透過電子郵件傳送專案或共用專案，PDF或CSV檔案中的敏感資料欄位會顯示為空白。

如果標示為敏感的資料欄位包含在資料檢視中，則從畫面選取和複製資料的選項會針對資料檢視中的所有資料受到限制。

## 常見問答 {#faq}

| 問題 | 回答 |
| --- | --- |
| 為什麼我下載的PDF只包含一個頁面？ | [下載PDF](#download-as-csv-or-pdf)功能無法將下載的PDF分頁。 |
| 我可以使用&#x200B;**[!UICONTROL 將專案下載為CSV檔]**&#x200B;選項匯出50,000個以上的專案嗎？ | 雖然每項下載最多可包含 50,000 個維度項目，您還是可以變更表格的排序，以擷取較冷門的項目，或是套用篩選條件來下載更明確的項目。 |
| 「**[!UICONTROL 複製視覺效果]**」有什麼作用？ | 不同於&#x200B;[!UICONTROL **將資料複製到剪貼簿**]&#x200B;或&#x200B;[!UICONTROL **將選取專案複製到剪貼簿**]，**[!UICONTROL 複製視覺效果]**&#x200B;內容功能表選項不是匯出選項。 此選項可讓您[複製視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)或[將面板](/help/analysis-workspace/c-panels/panels.md#context-menu)從Workspace中的某個位置複製到另一個位置。 例如，從某個面板複製到相同專案中的另一個面板，或從一個專案複製到另一個專案。 |
