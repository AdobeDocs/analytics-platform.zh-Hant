---
title: 在Customer Journey Analytics中收集量度工作階段ID
description: 修改您的實作以包含工作階段ID，以便在Customer Journey Analytics中加以分析。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: d71f39d25c52b0389d0441f238cb5b1809986b2d
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# 在Customer Journey Analytics中收集量度工作階段ID

某些使用案例，例如[繫結量子量度工作階段重播](tie-session-replays.md)或[使用量子量度熱度圖](heatmap.md)，需要您修改實作以收集量子量度工作階段識別碼。 本頁面概述成功將資料帶入現有實作的程式。

這些步驟假設您使用Adobe Experience Platform資料彙集中的標籤。 如果您的組織未使用標籤，您可以將這些資料收集方法調整為手動Web SDK實施。

## 步驟1：使用量度標籤擴充功能擷取量度工作階段ID

請依照下列步驟，將Quantum量度工作階段ID附加至您傳送至Adobe Experience Platform的資料。

1. 在標籤UI中使用Quantum Metric擴充功能傳送資料給Quantum Metric。
1. 建立四個資料元素：
   1. 從名為`QuantumMetricSessionID`的Quantum量度的Cookie擷取Quantum量度工作階段ID的機制
   1. 從`localStorage`中擷取Quantum量度工作階段ID的專案。 有時此資料元素的載入速度，會比在其他資料元素中設定的Cookie更快。
   1. 使用資料元素助理或自訂JavaScript從`localStorage`資料元素擷取`s`節點。
   1. 使用邏輯來先尋找Cookie資料元素，然後將其傳回XDM物件路徑（如果找到的話）的路徑。 如果未定義，請嘗試在擷取的`localStorage`物件資料元素中檢視。
1. 將最終的Quantum量度工作階段ID資料元素傳送至在每個事件中傳送的XDM物件。

>[!NOTE]
>有時Web SDK的執行速度會比Quantum Metric程式碼更快。 在這些情況下，工作階段ID會在後續點選時傳送。 如果訪客跳出，則系統不會收集這些例項的工作階段ID。

如需詳細資訊，請參閱[Quantum量度標籤延伸功能](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)檔案。

## 步驟2：確認包含的資料集欄位

確認連線中的資料集現在在所需資料集中具有Quantum量度工作階段ID。

## 步驟3：將Quantum量度工作階段ID新增為可用維度

編輯您現有的資料檢視，將工作階段ID新增為Customer Journey Analytics中的可用維度。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]**。
1. 選取所需的現有資料檢視。
1. 在左側找到「量度工作階段ID」欄位清單，並將其拖曳至中央的維度區域。
1. 在右窗格中，將[持續性](/help/data-views/component-settings/persistence.md)設定設為&#39;Session&#39;。
1. 按一下「**[!UICONTROL 儲存]**」。

## 步驟4：設定Workspace以容納工作階段ID維度

在Workspace中建立自由表格，並進行設定，以便工作階段ID值直接連結至Quantum Metric。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取現有專案，或建立專案。
1. 建立[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 將「工作階段ID」維度拖曳至Workspace畫布。
1. 以滑鼠右鍵按一下維度資料行標題，然後選取&#x200B;**[!UICONTROL 為所有維度專案建立超連結]**。
1. 選取&#x200B;**[!UICONTROL 建立自訂URL]**。
1. 貼上下列URL結構：

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 按一下「**[!UICONTROL 建立]**」。

每個工作階段ID現在都是可點按的連結。 這些連結會帶您前往新標籤中的Quantum Metric，讓您更詳細地分析該特定工作階段。 如需新增超連結至Analysis Workspace維度專案的詳細資訊，請參閱[在自由格式表格中建立超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。
