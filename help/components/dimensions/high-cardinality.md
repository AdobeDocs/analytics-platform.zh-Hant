---
title: 高基數維度
description: 說明Customer Journey Analytics如何處理具有許多唯一值的維度。
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 7%

---

# 高基數維度

使用包含許多唯一值的維度時，產生的報表可能包含太多要顯示或計算的唯一維度專案。 移除最不重要的維度專案，即可截斷結果。 這些最佳化是為了維護專案和產品效能而完成的。

當您請求含有太多唯一值的報表時，Analysis Workspace會在維度標題中顯示指標，指出並非所有維度專案都會納入。 例如，**[!UICONTROL 列：超過22,343,156]**&#x200B;的1-50列。 **[!UICONTROL 大於]**&#x200B;的關鍵字指出已將某些最佳化套用到報表，以傳回最重要的維度專案。

![Workspace中的自由格式表格顯示「超過」關鍵字，可顯示1-50個超過22,343,156](assets/high-cardinality.png)

## 決定要顯示哪些維度專案

Customer Journey Analytics會在執行報表時處理報表，將合併的資料集分發到多台伺服器。 每個處理伺服器的資料依人員ID分組，這表示單一處理伺服器包含給定人員的所有資料。 伺服器一旦完成處理，就會將其處理資料的子集交給彙總器伺服器。 所有已處理資料的子集都以工作區報表的形式合併並傳回。

如果任何個別伺服器處理的資料超過唯一臨界值，它會在傳回處理的資料子集之前截斷結果。 截斷的維度專案是根據用於排序的量度來決定。

如果排序量度是計算量度，伺服器會使用計算量度內的量度，以決定要截斷的維度專案。 由於計算量度可包含數個重要性不一的量度，因此結果可能會較不準確。 例如，在計算「每人收入」時，系統會在進行劃分前，傳回收入總額和人數總計。 因此，每個個別處理伺服器都會選擇移除哪些專案，而不知道它們的結果如何影響整體排序。

雖然高基數報表中可能遺漏某些個別維度專案，但欄總計是準確的，且不會根據截斷的資料。 計算量度中的「相異計數」函式也不受截斷的維度專案影響。

## 高基數維度的最佳做法

適應高基數維度的最佳方式是限制報表處理的維度專案數。 由於所有報表在請求時都會處理，因此您可以調整報表引數以立即獲得結果。 Adobe建議對高基數維度進行下列任何最佳化：

* 使用[區段](/help/components/segments/seg-create.md)。 區段在每個伺服器處理資料子集時套用。
* 使用搜尋。 從搜尋字詞中排除的Dimension專案會從報表結果中移除，因此您更有可能看到所需的維度專案。
* 使用查詢資料集維度。 查詢資料集維度結合了事件資料集維度項目，這會限制傳回的唯一值數量。
* 在資料檢視管理員中使用[包含/排除](/help/data-views/component-settings/include-exclude-values.md)元件設定。
* 縮短請求的日期範圍。 如果許多唯一值隨著時間累積，縮短Workspace報表的日期範圍會限制伺服器要處理的唯一值數量。
* 請考慮使用[完整表格匯出](/help/analysis-workspace/export/export-cloud.md)來傳回表格的所有列。
