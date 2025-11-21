---
title: 在Customer Journey Analytics中分析Experience Platform受眾
description: 瞭解如何在Customer Journey Analytics中分析Experience Platform受眾。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---

# 在Customer Journey Analytics中分析Experience Platform受眾 {#analyze-audiences-RTCDP}

當對象資料可在Customer Journey Analytics中作為新維度使用時，您[建立對象分析設定](/help/connections/audience-analysis/audience-analysis-configure.md)後，就可以開始在Analysis Workspace中分析Experience Platform對象。

Customer Journey Analytics中有提供對象概觀範本。

如需有關如何存取對象概觀範本的資訊，請參閱[使用範本](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)中的[存取並執行範本](/help/analysis-workspace/templates/use-templates.md)。

對象概觀範本包含下列面板：

## 使用方式概觀面板

顯示與所選資料檢視相關聯之使用事件之所有對象的資料。 對象會籍資料每天從Experience Platform更新。 資料一律顯示為昨天，因此變更面板日期範圍導致資料不正確。

使用此面板中的表格以更清楚瞭解對象行為。 從選取的資料檢視中拖曳「對象說明」維度，並將其新增為劃分。 或使用任何其他互動維度（例如「頁面」、「動作」等）作為劃分。

## 熱門受眾來源面板

顯示建立對象的位置，不論是在RTCDP、Customer Journey Analytics中還是其他中。

使用此面板中的表格，更能瞭解對象來源可能影響其他因素的方式。 從選取的資料檢視中拖曳「對象名稱」維度，並將其新增為劃分。 或使用任何其他互動維度（例如「頁面」、「動作」等）作為劃分。

## 對象重疊面板

顯示與所選資料檢視相關聯之使用事件之所有對象的資料。 資料一律顯示為昨天，因此變更面板日期範圍導致資料不正確。

在此面板的表格中選取最多三個對象，以檢視它們在對應的文氏圖表中的重疊程度。

## 已退出觀眾使用情況

顯示已退出對象之資料，其中包含與所選資料檢視相關聯的使用事件。 資料一律顯示為昨天，因此變更面板日期範圍導致資料不正確。 「已退出的對象」是指具有使用事件之人員昨天離開或退出的對象。

使用此面板中的表格以更清楚瞭解對象行為。 從選取的資料檢視中拖曳現有的對象說明維度，並將其新增為劃分。 或使用任何其他互動維度或量度（例如「頁面」、「動作」等）作為劃分。

## 熱門退出對象來源面板

顯示原本建立退出受眾的位置，不論是在RTCDP、Customer Journey Analytics等中皆然。

使用此面板中的表格，更能瞭解對象來源可能影響其他因素的方式。 從選取的資料檢視中拖曳「退出對象名稱」維度，並將其新增為劃分。 或使用任何其他互動維度或量度（例如「頁面」、「動作」等）作為劃分。








