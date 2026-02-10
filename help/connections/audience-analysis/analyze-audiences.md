---
title: 在Customer Journey Analytics中分析Experience Platform受眾
description: 瞭解如何在Customer Journey Analytics中分析Experience Platform受眾。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# 在Customer Journey Analytics中分析Experience Platform受眾 {#analyze-audiences-RTCDP}

在您[建立對象分析設定](/help/connections/audience-analysis/audience-analysis-configure.md)後，對象資料會在您設定要建立對象的資料檢視中成為新的維度。 如果您有許可權存取新增了對象分析維度的資料檢視，您可以在Analysis Workspace中的任何地方使用新的對象維度。

## 使用對象概觀範本

Customer Journey Analytics中有提供對象概觀範本。

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

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

## 退出對象使用面板

顯示已退出對象之資料，其中包含與所選資料檢視相關聯的使用事件。 資料一律顯示為昨天，因此變更面板日期範圍導致資料不正確。 「已退出的對象」是指具有使用事件之人員昨天離開或退出的對象。

使用此面板中的表格以更清楚瞭解對象行為。 從選取的資料檢視中拖曳「退出對象說明」維度，並將其新增為劃分。 或使用任何其他互動維度或量度（例如「頁面」、「動作」等）作為劃分。

## 熱門退出對象來源面板

顯示原本建立退出受眾的位置，不論是在RTCDP、Customer Journey Analytics等中皆然。

使用此面板中的表格，更能瞭解對象來源可能影響其他因素的方式。 從選取的資料檢視中拖曳「退出對象名稱」維度，並將其新增為劃分。 或使用任何其他互動維度或量度（例如「頁面」、「動作」等）作為劃分。
