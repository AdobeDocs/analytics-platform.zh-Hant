---
title: 如何設定 Analysis Workspace 內的使用者偏好設定
description: 您可以設定使用者的一般和專案偏好設定。
feature: CJA Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
source-git-commit: bf067ca57564bad72640c6bb5eb1c376ad818d3e
workflow-type: tm+mt
source-wordcount: '3015'
ht-degree: 82%

---

# 使用者偏好設定

您可以管理您建立之所有新專案或面板之 Analysis Workspace 及其相關元件的設定。現有專案和面板不受影響。

## 更新偏好設定

1. 在 Customer Journey Analytics 中，前往&#x200B;[!UICONTROL **「專案」**]&#x200B;登陸頁面，然後選取&#x200B;[!UICONTROL **「偏好設定」**]。

   ![使用者偏好設定](assets/user-preferences.png)

1. 如需每個索引標籤上可用偏好設定的相關資訊，請繼續閱讀本文章的下列任一節：

   * [一般偏好設定](#general-preferences)

   * [專案偏好設定](#project-preferences)

   * [自由表格偏好設定](#freeform-table-preferences)

   * [視覺效果偏好設定](#visualizations-preferences)

## 一般偏好設定

一般偏好設定適用於瀏覽器中您的 CJA 體驗。

| 偏好設定 | 選項 |
| --- | --- |
| 登陸頁面 | 選擇存取 Adobe Analytics 時顯示為預設頁面的頁面： <ul><li>專案清單 (預設)</li><li>空白專案</li><li>特定專案(從清單中選取)</li></ul> |
| 顯示提示 | 在 Analysis Workspace 右下方區域的藍色框中顯示提示。 <p>此選項已預設啟用。</p> |
| 左側邊欄群組中顯示的元件 | 在左側邊欄的「元件」選單中，選取每個元件的顯示數量。 <p>如果選擇 0，則無法再從工作區的左側邊欄存取元件。</p><p>根據預設，會針對下列各項顯示 5 個元件：</p> <ul><li>維度</li><li>量度</li><li>篩選器</li><li>日期範圍</li></ul> <p>如需有關 Analysis Workspace 中元件的詳細資訊，請參閱[元件概觀](/help/components/overview.md)。</p> |

## 專案偏好設定

您可以為在 Analysis Workspace 中建立的所有新專案自訂專案偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

您也可以針對個別專案自訂其中某些相同偏好設定，如[專案概觀](/help/analysis-workspace/build-workspace-project/freeform-overview.md)。

按一下連結的偏好設定標題，以取得有關每個偏好設定的詳細資訊和內容。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **顯示** |  |  |
|  | [檢視密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hant) | 減少左側邊欄、自由表格和同類群組表格的垂直邊框間距，以選擇要在畫面上顯示多少內容。 <ul><li>精簡</li><li>舒適</li><li>展開 (預設)</li></ul> |
|  | [調色盤](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=zh-Hant) | 選取 Analysis Workspace 中使用的視覺效果調色盤。 <ul><li>Adobe 提供的調色盤 (預設)</li><li>條件式格式設定調色盤 </li><li>上/下浮動調色盤 (發散)<li>自訂界定的調色盤</li></ul> |
| **資料** |  |  |
|  | [報告套裝](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant?#report-suite) | 從表格和視覺效果衍生其資料的位置進行選擇。 <ul><li>最近使用 (預設)</li><li>從清單中選取的特定報告套裝</li></ul> |
|  | [行事曆](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant?#calendar) | 從以下清單中選取： <ul><li>Adobe 提供的範圍 (預設為「本月」)</li><li>自訂界定的範圍</li></ul> |
|  | [面板類型](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant) | <ul><li>自由形式 (預設)</li><li>空白</li><li>快速深入分析</li></ul> |
|  | 計算重複實例數 | 指定是否要將重複例項計入報告。例如，此設定 (啟動時) 會將多個連續頁面檢視視為同一個頁面的多次頁面檢視。關閉後，則會計為單次頁面檢視。 <p>**注意：**&#x200B;此設定只會影響特定量度 (例如單次頁面造訪次數)，不適用於「流量」或「流失」視覺效果。</p> |
|  | 數字格式 | <ul><li>1,000.00 (預設)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | CSV 分隔符號字元 | <ul><li>逗號 (預設)</li><li>分號</li><li>冒號</li><li>直立線符號</li><li>時段</li><li>空格</li><li>定位</li></ul> |
|  | 顯示註解 | 選取專案中是否顯示註解。如需註解的詳細資訊，請參閱[註解概觀](/help/components/annotations/overview.md)。 |


## 自由表格偏好設定

您可以為在 Analysis Workspace 中建立的所有新專案自訂自由表格偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

也可為個別表格自訂其中一些相同偏好設定。

按一下連結的區段標題，以取得有關可用偏好設定的詳細資訊和內容。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **表格** |  |  |
|  | 表格類型 | <ul><li>自由格式</li><li>表格產生器</li></ul> |
|  | 預設表格量度 | <ul><li>發生次數</li><li>不重複訪客</li><li>瀏覽</li></ul> |
|  | 預設表格維度 | 從分鐘、小時、日、週、月、季度或年中選擇。 |
|  | 統一日期 | 選取此選項，讓每一欄的日期與同一列中所有開始日期一致。 |
| **[欄](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** |  |  |
|  | 繞排標題文字 | 讓您自由表格中的標頭文字環繞，讓標頭變得更容易閱讀，表格也更便於分享。這項設定對 PDF 的轉譯還有較長名稱的量度來說，非常實用。預設啟用。 |
|  | 顯示總計 | 此總計通常等於[!UICONTROL 全部總量]或其一個小計。它反映的是在自由表格中套用的任何表格篩選條件，包括[!UICONTROL 「不包含任何項目」]選項。 |
|  | 顯示總計 | 此總計表示所選取的全部集合，有時候是指「報告套裝總計」。在面板層級或自由表格內套用區段時，這項總計會經過調整，藉此反映所有符合區段條件的點擊。具[靜態列](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md)的表格或劃分不支援全部總量。 |
|  | 顯示走勢圖 | 顯示或隱藏圖表底部的折線圖。隱藏時，圖例會變更為不再以視覺化方式參照線條。 |
|  | 數字 | 決定儲存格是否要顯示/隱藏量度數值。例如，如果量度為「頁面檢視」，則該數值為列項目的頁面檢視數量。 |
|  | 百分比 | 決定儲存格是否要顯示/隱藏量度百分比值。例如，如果量度為「頁面檢視」，則該百分比數值為欄頁面檢視總數除以列項目的頁面檢視次數。附註：為了比例更精確，我們可以顯示超過 100% 的數值。我們也將上限提高為 1000%，以確保欄位的寬度夠大。 |
|  | 顯示異常狀況 <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | 決定是否要在該欄的數值中執行異常偵測。 |
|  | 將零解讀為沒有值 | 針對含有 0 值的儲存格，決定顯示 0 或空白儲存格。如果您要查看某月的每日資料，而當月有部分天數尚未發生，這個方法就相當實用。若不想在未來的日期中顯示 0 值，則可選擇顯示空白儲存格。圖表也會採用此設定 (意即選取此設定後，若圖表含有 0 值，則不會顯示折線圖或長條圖)。 |
|  | 背景 | 決定儲存格是否要顯示/隱藏所有儲存格格式，包括橫條圖和條件式格式 <ul><li>橫條圖</li> 顯示橫條圖，當中呈現相對於欄總數的儲存格數值。 <li>條件式格式</li>如需條件式格式的詳細資訊，請參閱[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的「條件式格式」</ul> |
|  | 儲存格預覽 | 顯示目前已套用選定格式選項之各儲存格的呈現方式預覽。 |
| **[列](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** |  |  |
|  | 依位置劃分 | 如果您希望劃分保留在項目的位置，而非項目本身，請選取此選項。如需劃分的詳細資訊，請參閱[劃分維度](/help/components/dimensions/t-breakdown-fa.md)。 |
|  | 百分比計算 | <ul><li>欄</li><li>列</li></ul> |

## 視覺效果偏好設定

您可以為在 Analysis Workspace 中建立的所有新專案更新偏好設定。如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

也可為個別視覺效果自訂其中一些相同偏好設定。

按一下連結的區段標題，以取得有關可用偏好設定的詳細資訊和內容。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **一般預設值** |  |  |
|  | 百分比 | 以百分比顯示所有視覺效果的值。 |
|  | 可見圖例 | 可讓您隱藏所有視覺效果的詳細圖例文字。 |
|  | 限制項目數量上限 | 減少所有視覺效果的 X 軸項目數量。如果您有大型資料集，此功能會相當實用。 |
|  | 顯示雙軸 (適用時) | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，這項功能會很有用。 |
|  | 標準化 (適用時) | 強制量度為相同比例。當繪製的量度大小非常不同時，這項功能會很有用。 |
|  | 將 Y 軸固定於零 | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |
|  | 允許異常縮放 Y 軸 | 如果圖表中有多個量度，您必須將滑鼠移到每個異常值上方，才能查看該量度的信賴帶。為了讓視覺效果更清晰，異常偵測信賴區間不會自動縮放 Y 軸。此選項可讓信賴區間縮放視覺效果。 <p>如需詳細資訊，請參閱[在 Analysis Workspace 中檢視異常](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)。</p> |
| **[折線圖](/help/analysis-workspace/visualizations/line.md)** |  |  |
|  | 百分比 | 以百分比顯示線條視覺效果的值。 |
|  | 可見圖例 | 可讓您隱藏線條視覺效果的詳細圖例文字。 |
|  | 限制項目數量上限 | 減少線條視覺效果的 X 軸項目數量。如果您有大型資料集，此功能會相當實用。 |
|  | 顯示雙軸 (適用時) | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，這項功能會很有用。 |
|  | 標準化 (適用時) | 強制量度為相同比例。當繪製的量度大小非常不同時，這項功能會很有用。 |
|  | 顯示 x 軸 | 在折線圖上顯示 x 軸。 |
|  | 顯示 y 軸 | 在折線圖上顯示 y 軸。 |
|  | 固定 Y 軸 | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |
|  | 顯示最小值 | 覆蓋最小值標籤，以快速反白標示量度中的低谷。注意：最小值是從視覺效果中的可見資料點衍生而來，而非維度中的完整數值集。 |
|  | 顯示最大值 | 覆蓋最大值標籤，以快速反白標示量度中的尖峰。注意：最大值是從視覺效果中的可見資料點衍生而來，而非維度中的完整數值集。 |
|  | 顯示趨勢線 | 顯示迴歸或移動平均趨勢線至您的線圖序列。趨勢線有助於描繪出資料中更清晰的模式。 |
| **[同類群組](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** |  |  |
|  | 詳細程度 | 對於趨勢視覺效果，您可以變更時間詳細程度 (日、週、月、季或年)。這項變更也適用於資料來源表。 |
|  | 僅顯示百分比 | 移除數值並僅顯示百分比。 |
|  | 將百分比四捨五入到最接近的整數 | 將百分比四捨五入為最接近的整數，而非顯示小數值。 |
|  | 顯示平均百分比列 | 在表格頂端插入新列，然後在每個欄中加入平均值。 |
|  | 同類群組預覽 | 同類群組視覺效果中調色盤顯示方式的預覽。 |
|  | 同類群組調色盤 | 同類群組視覺效果中使用的調色盤。 |
| **[組合圖](/help/analysis-workspace/visualizations/combo-charts.md)** |  |  |
|  | 顯示 X 軸 | 在組合圖上顯示 x 軸。 |
|  | 顯示 Y 軸 | 在組合圖上顯示 y 軸。 |
|  | 在線上顯示節點 | 在組合圖中的線上顯示節點。 |
| **[關鍵量度摘要](/help/analysis-workspace/visualizations/key-metric.md)** |  |  |
|  | 摘要顯示類型 | <ul><li>強調百分比變化</li><li>強調數字值</li></ul> |
|  | 顯示走勢圖 | 顯示或隱藏圖表底部的折線圖。隱藏時，圖例會變更為不再以視覺化方式參照線條。 |
|  | 在走勢圖上顯示最大值和最小值 | 在主要和比較折線圖上顯示最小值和最大值. |
|  | 顯示比較 | 顯示比較資料。隱藏時，比較折線圖和摘要變更物件將會隱藏起來。 |
|  | 數字值選項 | 在&#x200B;[!UICONTROL **關鍵量度摘要**] 一節 <ul><li>顯示百分比變化</li><li>顯示原始差異</li>主要日期範圍與次要日期範圍中量度總值之間的原始差異</ul> |
| **[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** |  |  |
|  | 容器 | 可讓您切換瀏覽和訪客，分析訪客路徑。預設為「訪客」。這些設定可協助您了解訪客層級的訪客參與程度 (跨越造訪)，或是將分析限制在單一造訪。 <p>提供下列選項：</p> <ul><li>瀏覽</li><li>訪客</li></ul> |
| **[流量](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** |  |  |
|  | 容器 | 在&#x200B;[!UICONTROL **流量**]&#x200B;一節 <ul><li>瀏覽</li><li>訪客</li></ul> |
|  | 繞排標籤 | 一般而言，系統會截斷「流量」元素的標籤以節省螢幕空間，但您可勾選此方塊以完整顯示標籤。預設 = 未勾選。 |
|  | 包含重複例項 | 「流量」視覺效果是根據維度的例項而定。此設定可讓您選擇要包含或排除重複例項，如頁面重新載入次數。不過，無法從包含多值維度 (例如 listVars、listProps、s.product、銷售 eVars 等) 的「流量」視覺效果中移除重複項目。預設 = 未勾選。 |
|  | 顯示工具提示 | 決定將滑鼠游標暫留在流量視覺效果內的個別節點上時，是否顯示包含節點資料的工具提示。 |
|  | 欄數 | 決定您的流量圖中要有多少欄。 |
|  | 每欄展開的項目 | 每欄中想要多少項目。 |
| **堆疊圖** |  |  |
|  | 100% 堆疊 | 區域圖堆疊、橫條圖堆疊、水平橫條圖堆疊等視覺效果的這項設定，會將圖表轉變為「100％ 堆疊」視覺效果。 <p>如需詳細資訊，請參閱[長條圖和堆疊長條圖](/help/analysis-workspace/visualizations/bar.md)。</p> |
| **[長條圖](/help/analysis-workspace/visualizations/histogram.md)** |  |  |
|  | 貯體數 | 在視覺效果中選擇資料範圍 (貯體) 的數量。貯體的最大數量是 50。 <p>如需詳細資訊，請參閱[長條圖](/help/analysis-workspace/visualizations/histogram.md)。</p> |
|  | 計算方法 | 從下列選項中選擇： <ul><li>點擊</li><li>瀏覽</li><li>訪客</li></ul> <p>例如，搭配頁面檢視使用時，您可以選擇每個訪客的頁面檢視、造訪的頁面檢視，或每次點擊的頁面檢視。若為點擊，自由表格會將「發生次數」設為 Y 軸的量度。</p> |
| **[摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | 值 | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>百分比變更</li><li>原始差異</li></ul> |
|  | 百分比 | 以百分比顯示摘要變更視覺效果的值。 |
|  | 可見圖例 | 可讓您隱藏摘要變更視覺效果的詳細圖例文字。 |
| **[摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md)** |  |  |
|  | 百分比 | 以百分比顯示摘要數字視覺效果的值。 |
|  | 可見圖例 | 可讓您隱藏摘要數字視覺效果的詳細圖例文字。 |
|  | 摘要值依據 | 從最大值、最小值、平均值、中位數和總和中選擇。 |
|  | 縮簡值 | 在&#x200B;[!UICONTROL **摘要數字**] 一節 |
| **[樹狀圖](/help/analysis-workspace/visualizations/treemap.md)** |  |  |
|  | 百分比 | 以百分比顯示樹狀圖視覺效果的值。 |
|  | 限制項目數量上限 | 減少樹狀圖視覺效果的 X 軸項目數量。如果您有大型資料集，此功能會相當實用。 |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** |  |  |
|  | 可見圖例 | 可讓您隱藏 Venn 視覺效果的詳細圖例文字。 |
| **[散佈圖](/help/analysis-workspace/visualizations/scatterplot.md)** |  |  |
|  | 百分比 | 以百分比顯示散佈圖視覺效果的值。 |
|  | 可見圖例 | 讓您隱藏散佈圖視覺效果的詳細圖例文字。 |
|  | 限制項目數量上限 | 減少散佈圖視覺效果的 X 軸項目數量。如果您有大型資料集，此功能會相當實用。 |
|  | 將 y 軸固定於零 | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |

## 公司偏好設定

>[!AVAILABILITY]
>
>本節所述的「公用存取連結」功能正處於發行的「有限測試」階段，可能尚未在您的環境中使用。 當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

您可以更新適用於組織內所有使用者和專案的公司偏好設定。 如需如何存取這些偏好設定的相關資訊，請參閱[更新偏好設定](#update-preferences)。

| 區域 | 偏好設定 | 選項 |
| --- | --- | --- |
| **專案共用** |  |  |
|  | 僅允許與 Workspace 使用者共用 | <p>啟用此選項時：</p> <ul><li><p>「與任何人共用」選項會從「共用」功能表中移除。 這表示使用者無法再與組織中沒有Analysis Workspace帳戶的人員共用專案，如 [與任何人共用專案（不需登入）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [共用專案](/help/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>先前透過「與他人共用」共用選項而收到專案存取權的使用者，無法再存取專案。</p></li><p>**注意：** 如果啟用此選項（僅允許與工作區使用者共用），之後又停用（允許與任何人共用），先前透過「與任何人共用」共用選項收到專案存取權的使用者，不會自動重新取得專案存取權。 在此情況下，共用專案的使用者必須啟用 [!UICONTROL **連結處於活動狀態**] 與他人共用專案時可用的選項([!UICONTROL **共用**] > [!UICONTROL **與任何人共用**])，如中所述 [與任何人共用專案（不需登入）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [共用專案](/help/analysis-workspace/curate-share/share-projects.md).</p> |
|  | 需要 Experience Cloud 驗證 | <p>啟用後，Analysis Workspace中「與任何人共用」選項可供存取專案的使用者，必須使用其Experience Cloud憑證進行驗證。</p> <p>啟用此選項後，每當用戶使用「與任何人共用」共用選項共用項目時，「需要Experience Cloud驗證」選項就會在「共用」對話框中啟用，並且共用項目的用戶不能禁用該選項。 (如需使用者如何與他人共用專案的相關資訊，請參閱 [與任何人共用專案（不需登入）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [共用專案](/help/analysis-workspace/curate-share/share-projects.md).)</p> <p>啟用此選項時，請考量下列事項：</p><ul><li><p>啟用此選項後，先前與「與任何人共用」共用選項共用且未啟用「需要Experience Cloud驗證」選項的所有專案都會停用。</p></li> <li><p>如果啟用此選項(需要Experience Cloud驗證)，之後又停用（允許任何具有此連結的人存取專案），先前透過「與他人共用」共用選項而收到專案存取權的人，不會自動重新取得專案存取權。 在此情況下，共用專案的使用者必須啟用「連結作用中」選項，此選項可在與他人共用專案時使用([!UICONTROL **共用**] > [!UICONTROL **與任何人共用**] > [!UICONTROL **連結處於活動狀態**])，如中所述 [與任何人共用專案（不需登入）](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) in [共用專案](/help/analysis-workspace/curate-share/share-projects.md).</p></li> <li><p>只有在貴組織中實作了SSO時，才可使用此選項。 有關係統管理員如何為貴組織啟用SSO的資訊，請參見 [設定身分和單一登入](https://helpx.adobe.com/tw/enterprise/using/set-up-identity.html){target=_blank}.</p><p>如果已為貴組織設定SSO，請檢查主控台中是否已實作任何類型的自動帳戶建立。 通常，系統管理員會設定此設定，如 [啟用自動帳戶建立](https://helpx.adobe.com/enterprise/using/automatic-account-creation.html){target=_blank}.</p></li><li><p>如果貴組織所在的行業需要HIPAA法規遵從，則此選項將自動啟用，並且無法禁用。</p></li></ul> |

{style="table-layout:auto"}

## 還原預設偏好設定

您可以將所有使用者偏好設定還原為系統預設值。這不會影響「公司」標籤下的管理員偏好設定。

此動作無法復原。

1. 在Customer Journey Analytics中，選取 [!UICONTROL **元件**] **>** [!UICONTROL **偏好設定**].

   ![使用者偏好設定](assets/user-preferences.png)

1. 在右上角，選取&#x200B;**[!UICONTROL 「還原預設值」]**。

1. 出現提示時，選取&#x200B;**[!UICONTROL 「還原預設值」]**。

## [!UICONTROL 深色佈景主題]

如果您偏好將您的 Adobe Analytics 使用者介面設定為深色背景，您可切換至[!UICONTROL 深色佈景主題]。

1. 按一下右上方的「Experience Cloud」使用者圖示。

   ![dark-theme](assets/dark-theme.png)

1. 將&#x200B;**[!UICONTROL 深色佈景主題]**&#x200B;切換移動至右邊。

