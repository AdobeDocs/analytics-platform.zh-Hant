---
description: 瞭解如何編輯欄設定以設定欄格式，部分可設為條件式。
title: 欄設定
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 49b165c4dfec99ff1c65d4aacf4a5ffbe65d4004
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 74%

---

# [!UICONTROL 欄設定]

[!UICONTROL 欄設定]可供設定欄的格式，部分可設為條件式。

在此檢視有關列和欄設定的影片：

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## 編輯[!UICONTROL 「欄設定」]  {#edit-column-settings}

若要存取[!UICONTROL 欄設定]，請拖曳自由表格至專案，然後按一下欄標題中的設定圖示![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。

<img src="./assets/column-settings.png" alt="顯示「總計」儲存格、「表格」儲存格和「表格」儲存格預覽的「欄」設定。" width="50%" />

您可以同時編輯&#x200B;**多欄**&#x200B;的設定。只要選取多個欄，然後在任一欄中按一下設定圖示。您所做的任何變更都會套用在所有欄，以及您在其中選定的儲存格。

| 元素 | 說明 |
| --- | --- |
| 數字 | 決定儲存格是否要顯示/隱藏量度數值。例如，如果量度為「頁面檢視」，則該數值為列項目的頁面檢視數量。 |
| 百分比 | 決定儲存格是否要顯示/隱藏量度百分比值。例如，如果量度為「頁面檢視」，則該百分比數值為欄頁面檢視總數除以列項目的頁面檢視次數。附註：為了比例更精確，我們可以顯示超過 100% 的數值。我們也將上限提高為 1000%，以確保欄位的寬度夠大。 |
| 顯示異常狀況 | 決定是否要在該欄的數值中執行異常偵測。 |
| 顯示預測 | 決定此欄位是否顯示預測值。 |
| 繞排標頭文字 | 讓您自由表格中的標頭文字環繞，讓標頭變得更容易閱讀，表格也更便於分享。這項設定對 PDF 的轉譯還有較長名稱的量度來說，非常實用。預設啟用。 |
| 將零解讀為沒有值 | 針對含有 0 值的儲存格，決定顯示 0 或空白儲存格。如果您要查看某月的每日資料，而當月有部分天數尚未發生，這個方法就相當實用。若不想在未來的日期中顯示 0 值，則可選擇顯示空白儲存格。圖表也會採用此設定 (意即選取此設定後，若圖表含有 0 值，則不會顯示折線圖或長條圖)。 |
| 背景 | 決定儲存格是否要顯示/隱藏所有儲存格格式，包括長條圖和條件式格式。 |
| 長條圖 | 顯示橫條圖，當中呈現相對於欄總數的儲存格數值。 |
| 條件式格式 | 請參閱以下小節。 |
| 表格儲存格預覽 | 顯示目前已套用選定格式選項之各儲存格的呈現方式預覽。 |

## 條件式格式 {#conditional-formatting}

條件式格式會將格式套用至您可定義的上限、中點和下限。除非選取「自訂」限制，否則系統也會在資料劃分時自動在自由表格中套用顏色等條件式格式。

<img src="./assets/conditional-formatting.png" alt="已選取「自訂」的「條件式」格式選項" width="50%" />

| 元素 | 說明 |
| --- | --- |
| 條件式格式 | 將您選擇的預配置顏色集應用到單元格。 根據您選取的 4 種可用色彩配置中的哪一種，高值、中點值和低值會分配不同的顏色。 <br>取代表格中的維度會重設條件式格式限制。取代量度會重新計算該欄的限制 (其中量度位在 X 軸，維度位在 Y 軸)。 |
| 使用百分比限制 | 變更限制範圍，從絕對值改為以百分比為基礎.此設定適用於僅有百分比的量度 (例如反彈率)，以及含有計數和百分比的量度 (例如頁面檢視)。 |
| 自動產生 | 根據資料自動計算上/中/下限。上限是此欄中的最大值。下限是最小值，而中點是上限和下限的平均。 |
| 自訂 | 手動對齊上/中/下限。這可提供由您決定欄的值是好、中等或壞的彈性。 |
| 條件式格式設定調色盤 | 從 4 個可用色彩配置中，選擇要將哪一個用於條件式格式。 |

## 使用非預設歸因模式 {#attribution}

允許您覆寫[資料檢視](/help/data-views/component-settings/attribution.md)中設定的預設歸因模型。

>[!NOTE]
>
>將元件的歸因更新為非預設歸因模型時，請考量下列事項：
>
>* **在具有&#x200B;*單一維度*：**&#x200B;的報表中使用元件時，如果使用非預設歸因模型，元件的歸因會忽略配置模型。
>
>* **在具有&#x200B;*多個維度的報表中使用元件時*：**&#x200B;使用非預設歸因模型時，元件的歸因會保留配置模型。
>
>   只有在[將資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)時，才能使用多個維度。
>
> 如需配置的詳細資訊，請參閱[持續性元件設定](/help/data-views/component-settings/persistence.md)。

若要對Analysis Workspace中的量度使用非預設歸因模型：

1. 按一下「自由格式表格」欄中量度上的「設定」（齒輪）圖示。

   ![醒目提示「資料設定」選項的欄設定選項：使用非預設歸因模式。](assets/attribution-checkbox.png)

2. 在&#x200B;**[!UICONTROL 資料設定]**&#x200B;底下，勾選&#x200B;**[!UICONTROL 使用非預設歸因模式]**。如需不同歸因模式的詳細資訊，請參閱[歸因模式](/help/data-views/component-settings/attribution.md)。

   ![顯示線性選取的資料行歸因模型選項。](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [管理資料來源](/help/analysis-workspace/visualizations/t-sync-visualization.md)
