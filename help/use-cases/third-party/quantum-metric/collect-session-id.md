---
title: 在Customer Journey Analytics中收集量度工作階段ID
description: 修改您的實作以包含工作階段ID，以便在Customer Journey Analytics中加以分析。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# 在Customer Journey Analytics中收集量度工作階段ID

某些使用案例，例如[繫結量子量度工作階段重播](tie-session-replays.md)或[使用量子量度熱度圖](heatmap.md)，需要您修改實作以收集量子量度工作階段識別碼。 本頁面概述成功將資料帶入現有實作的程式。

## 必要條件:

這些步驟假設您使用Adobe Experience Platform資料彙集中的標籤。 如果您的組織未使用標籤，您可以將這些資料收集方法調整為手動Web SDK實施。

如需詳細資訊，請參閱[Quantum量度標籤延伸功能](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)檔案。

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

## 步驟2：確認包含的資料集欄位

確認連線中的資料集現在在所需資料集中具有Quantum量度工作階段ID。

## 步驟3：將Quantum量度工作階段ID新增為可用維度

編輯您現有的資料檢視，將工作階段ID新增為Customer Journey Analytics中的可用維度。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取所需的現有資料檢視。
1. 在左側找到「量度工作階段ID」欄位清單，並將其拖曳至中央的維度區域。
1. 在右窗格中，將[持續性](/help/data-views/component-settings/persistence.md)設定設為&#39;Session&#39;。
1. 按一下「**[!UICONTROL 儲存]**」。


