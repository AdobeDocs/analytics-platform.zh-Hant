---
description: 瞭解如何編輯欄設定以設定欄格式，部分可設為條件式。
title: 欄設定
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: a62ac798da9d66fa3d88262ef7d04aa4bf6a3303
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 21%

---

# [!UICONTROL 欄設定]

[!UICONTROL 欄設定]可讓您設定欄格式，部分可設為條件式。

+++ 觀看此功能的示範影片。

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

{{videoaa}}

+++

若要存取[!UICONTROL 欄設定]，請在欄標題中選取![欄設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。

![欄設定](assets/column-settings.png)


您可以一次編輯多個欄的設定。 選取多個資料行，並在選取的任一資料行中選取![設定](/help/assets/icons/Setting.svg)。 您所做的任何變更都會套用至所有已選取儲存格的欄。

| 選項 | 說明 |
| --- | --- |
| **[!UICONTROL 顯示總計]** | 顯示欄的使用者端總和。 此總計&#x200B;**不會**&#x200B;刪除重複量度，例如工作階段或人員。 |
| **[!UICONTROL 顯示總計]** | 顯示欄的伺服器端總和。 「總量」會去除重複量度，例如工作階段或人員。 |
| **[!UICONTROL 顯示走勢圖]** | 在欄標題顯示折線圖。 |
| **[!UICONTROL 數字]** | 決定儲存格是否要顯示/隱藏量度的數值。 例如，如果量度為「頁面檢視」，則該數值為列項目的頁面檢視數量。 |
| **[!UICONTROL 百分比]** | 決定儲存格是否要顯示/隱藏量度的百分比值。 例如，如果量度是「頁面檢視」，則百分比值是列專案的頁面檢視次數除以欄的頁面檢視總次數。  注意：百分比大於100%可確保準確。 上限上限可以移動到1,000%，以防止欄寬變得太大。 |
| **[!UICONTROL 顯示異常]** | 判斷此欄中的值是否執行異常偵測。 |
| **[!UICONTROL 顯示預測]** | 決定此欄位中是否顯示預測值。 |
| **[!UICONTROL 繞排標頭文字]** | 自由表格中的標題文字環繞，讓標題變得更容易閱讀，表格也更便於分享。 包裝對於PDF轉譯和名稱較長的量度相當實用。 預設啟用。 |
| **[!UICONTROL 將零解讀為沒有值]** | 決定針對含有0值的儲存格，顯示0或空白儲存格。 當您檢視一個月中每一天的資料，並且某些天是未來時，這種詮釋會很有用。  若不想在未來的日期中顯示0值，則顯示空白儲存格。 圖表也會遵循此設定（也就是說，圖表不會顯示含有0值的線或長條）。 |
| **[!UICONTROL 背景]** | 決定儲存格是否要顯示/隱藏所有儲存格格式，包括長條圖和條件式格式。 |
| **[!UICONTROL 長條圖]** | 顯示橫條圖，代表相對於欄總數的儲存格值。 |
| **[!UICONTROL 條件式格式]** | 使用條件式格式。 請參閱下方的[區段](#conditional-formatting)。 |
| **[!UICONTROL 表格儲存格預覽]** | 每個儲存格的顯示方式預覽，其中已套用目前選取的格式選項。 |
| **[!UICONTROL 使用非預設歸因模式]** | 使用非預設歸因模型。 請參閱下方的[區段](#use-non-default-attribution-model)。 |

## 條件式格式 {#conditional-formatting}

條件式格式會將格式套用至您可定義的上限、中點和下限。除非選取[!UICONTROL 自訂]限制，否則系統也會在資料劃分時自動在自由表格中套用條件式格式。

![條件式格式](./assets/conditional-formatting.png)

| 條件式格式選項 | 說明 |
| --- | --- |
| **[!UICONTROL 使用百分比限制]** | 變更限制範圍，從絕對值改為以百分比為基礎.百分比限制範圍適用於完全以百分比為基礎的量度（例如反彈率），以及含有計數和百分比的量度（例如頁面檢視）。 |
| **[!UICONTROL 自動產生]** | 根據資料自動計算上/中/下限。上限是此欄中的最大值。下限是最小值，而中點是上限和下限的平均。 |
| **[!UICONTROL 自訂]** | 手動指派&#x200B;**[!UICONTROL 上限]**、**[!UICONTROL 中點]**&#x200B;和&#x200B;**[!UICONTROL 下限]**。 限制可讓您靈活地判斷欄的值是好、中等或壞值。 |
| **[!UICONTROL 條件式格式調色盤]** | 將預先設定的色彩集套用至儲存格。 根據您選取的四種可用色彩配置中，不同的顏色會指定給高值、中點值和低值。 <br>取代表格中的維度會重設條件式格式限制。取代量度會重新計算該欄的限制 (其中量度位在 X 軸，維度位在 Y 軸)。 |

## 使用非預設歸因模式 {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel"
>title="使用非預設歸因模式"
>abstract="為選取的欄啟用非預設歸因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="使用非預設歸因模式"
>abstract="此量度無法使用非預設歸因模型。"

<!-- markdownlint-enable MD034 -->



您可以覆寫在[資料檢視](/help/data-views/component-settings/attribution.md)中設定的預設歸因模型。

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

1. 選取&#x200B;**[!UICONTROL 使用非預設歸因模型]**。 如果已選取，請使用&#x200B;**[!UICONTROL 編輯]**&#x200B;來編輯歸因模型。 或取消選取以返回預設歸因模型。

   ![醒目提示「資料設定」選項的欄設定選項：使用非預設歸因模式。](assets/attribution-checkbox.png)

2. 在&#x200B;**[!UICONTROL 資料行歸因模型]**&#x200B;中，選取&#x200B;**[!UICONTROL 模型]**&#x200B;和&#x200B;**[!UICONTROL 回顧視窗]**。 回顧期間會決定每次轉換要套用的資料歸因期間。

   ![顯示線性選取的資料行歸因模型選項。](assets/attribution-select.png)


### 歸因模型

{{attribution-models-details}}

### 回顧視窗

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [管理資料來源](/help/analysis-workspace/visualizations/t-sync-visualization.md)
