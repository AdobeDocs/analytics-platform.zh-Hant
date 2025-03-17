---
title: 繫結量子量度工作階段重播至Customer Journey Analytics中的資料
description: 連結量度工作階段會重播CJA資料，以便更清楚瞭解「內容」背後的「原因」。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 94dad68426a08ffa34ded7905567fbea307b1de4
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# 繫結量子量度工作階段重播至Customer Journey Analytics中的資料

連結Quantum量度工作階段重播與CJA資料，可讓客戶更瞭解「內容」背後的「原因」。  Workspace可用來探索摩擦的工作階段，然後您可以按一下超連結的工作階段ID，以探索「量度」中的工作階段重播。  此資料可讓您檢視工作階段中的行為，並更瞭解促使消費者發生摩擦的因素。  透過與CJA繫結的工作階段重播，您可以擷取有關您體驗中客戶行為的關鍵內容。

## 先決條件

此使用案例需要您將量子量度的工作階段ID與其餘實施一起收集。 請參閱[在Customer Journey Analytics](collect-session-id.md)中收集量度工作階段ID，瞭解如何修改您的實作。

## 步驟1：設定Workspace以容納工作階段ID維度

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

## 步驟2從Customer Journey Analytics檢視工作階段

使用可點按連結建立Workspace報表後，您就可以在Customer Journey Analytics中使用篩選器，識別可在Quantum量度中進一步分析的有趣工作階段。
此表格會傳回該區段中的所有工作階段，您可以按一下其中的任何工作階段，進一步探索QM。  若要進一步瞭解Quantum量度工作階段重播，請前往[https://www.quantummetric.com/platform/session-replay](https://www.quantummetric.com/platform/session-replay)

