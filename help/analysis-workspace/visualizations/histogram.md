---
description: 長條圖類似於橫條圖，但前者將數字分組為範圍 (貯體)。
title: 長條圖
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 100%

---

# 長條圖

長條圖類似於橫條圖，但前者將數字分組為範圍 (貯體)。Analytics 會自動將數字分組至範圍貯體，但您可以在[進階設定](#section_09D774C584864D4CA6B5672DC2927477)中變更設定。

## 建立長條圖 {#section_74647707CC984A1CB6D3097F43A30B45}

若要建立長條圖：

1. 按一下左側邊欄中的&#x200B;**[!UICONTROL 「視覺效果」]**。
1. 將&#x200B;**[!UICONTROL 「長條圖」]**&#x200B;拖曳至面板。
1. 選擇要拖曳至長條圖視覺效果的量度並按一下&#x200B;**[!UICONTROL 「建立」]**。

![](assets/histogram.png)

>[!NOTE]
>
>長條圖僅支援標準量度，不支援計算量度。

這裡我們使用了每個不重複訪客的頁面檢視次數量度。第一個 (最左邊) 貯體對應至每個不重複訪客 1 次頁面檢視、第二個貯體對應至 2 次頁面檢視，以此類推。

![](assets/histogram2.png)

## 進階設定 {#section_09D774C584864D4CA6B5672DC2927477}

若要調整長條圖設定，請按一下右上角的「設定」(「齒輪」) 圖示。您可以修改的設定如下：

| 長條圖設定 | 用途 |
|---|---|
| 起始貯體 | 決定長條圖開始使用的貯體。「1」是預設值。您可設定從 0 開始的數字，一直到無限大 (無負數)。 |
| 量度貯體 | 可讓您增加/減少資料範圍 (貯體) 的數目。貯體的最大數量是 50。 |
| 量度貯體大小 | 可讓您設定每個貯體的大小。例如，您可將貯體大小從 1 次頁面檢視變更為 2 次頁面檢視。 |
| 計算方法 | 可讓您選擇[訪客](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html)、[造訪](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html)或點擊類型。 例如，每次造訪的頁面檢視數、每個訪客的頁面檢視數，或每次點擊的頁面檢視數。若為點擊，自由表格會將「發生次數」設為 Y 軸的量度。 |

<!--Russ or Meike - Check Hit Type link above. -->

**範例**：

* 起始貯體：1、量度貯體：5、量度貯體大小：2 會產生這個長條圖：1-2、3-4、5-6、7-8、9-10。
* 起始貯體：0、量度貯體：3、量度貯體大小：5 會產生這個長條圖：0-4、5-9、10-14

## 檢視和編輯長條圖資料 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

若要檢視或變更長條圖的資料來源，請按一下長條圖標頭旁的點，前往「**[!UICONTROL 資料來源設定]** > **[!UICONTROL 顯示資料來源]**」。

![](assets/manage-data-source.png)

此表格中顯示的預先建立篩選器是內部篩選器，不會顯示在篩選器選取器中。 按一下篩選器名稱旁的「i」圖示，然後按一下&#x200B;**[!UICONTROL 「設為公用」]**，將該篩選器設為公用。

![](assets/prebuilt_segments.png)

若想探索管理自由資料表及其他視覺效果的其他方法，例如進行資料劃分，請前往[此處](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hant)。
