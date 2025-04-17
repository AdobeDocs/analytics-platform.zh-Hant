---
title: 將Quantum量度摩擦事件新增至Customer Journey Analytics
description: 使用Quantum Metric中收集的摩擦事件，在Customer Journey Analytics中增加深入分析。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# 將Quantum量度摩擦事件新增至Customer Journey Analytics

Quantum Metric會收集頁面載入緩慢、頁面載入錯誤、範圍點選等摩擦事件。 這些事件可以傳遞到Customer Journey Analytics中，作為使用者歷程中的補充事件。 有了這項合併資料，您就能更清楚瞭解摩擦對下游量度的影響。

## 必要條件:

此使用案例有兩個需求：

* 您必須有權使用Quantum量度的&#x200B;**Dev Ops**&#x200B;套件。
* 您必須使用Adobe Experience Platform資料彙集中的標籤。

## 步驟1：使用量度標籤擴充功能擷取摩擦事件

Quantum Metric CSM團隊可以協助您決定要新增的正確結構描述元素，並指示您修改實作，以收集所需的資料以用於Customer Journey Analytics。 如需詳細資訊，請聯絡您的Quantum Metric客戶成功案例經理。

最終，您將會想要開始追蹤欄位中的摩擦事件名稱。

## 步驟2：確認包含的資料集欄位

確認連線中的資料集現在在所需資料集中具有Quantum量度工作階段ID。

## 步驟3：將一或多個維度和量度新增至Customer Journey Analytics中的資料檢視

編輯您現有的資料檢視，將工作階段ID新增為Customer Journey Analytics中的可用維度。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。
1. 選取所需的現有資料檢視。
1. 在左側找到「量子量度」摩擦事件欄位清單，並將其拖曳至量度中央區域。
1. 在右窗格中，將[包含/排除值](/help/data-views/component-settings/include-exclude-values.md)設定設定為您要追蹤的所需摩擦事件。 您可以將多個摩擦事件新增至相同量度以組合這些事件。 您也可以將另一個摩擦事件欄位拖曳到量度區域，以作為單獨的量度追蹤其他摩擦事件。
1. 建立所有需要的維度和量度後，按一下&#x200B;**[!UICONTROL 儲存]**。

## 步驟4：將維度和量度與Analysis Workspace中的其餘資料搭配使用

有了量度摩擦事件資料會與您的其他訪客資料一起收集，您就可以完全依照在Customer Journey Analytics中使用任何其他維度或量度的方式使用這些資料。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取現有專案，或建立專案。
1. 建立[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 將所需的維度和量度拖曳至Workspace畫布以進行分析。

可能的分析想法包括：

* 趨勢摩擦事件資料隨時間變化
* 在流失或漏斗視覺效果中，將Customer Journey Analytics事件新增為部分步驟，並將Quantum量度摩擦事件新增為其他步驟。 此報表可讓您檢視訪客最常遇到問題的位置。
* 為體驗摩擦事件的訪客建立並套用篩選器，以進行更深入的分析
