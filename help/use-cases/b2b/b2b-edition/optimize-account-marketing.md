---
title: 最佳化帳戶行銷
description: 瞭解如何使用Customer Journey Analytics B2B edition最佳化帳戶行銷。
solution: Customer Journey Analytics
feature: Use Cases
role: User
badgePremium: label="B2B Edition"
exl-id: d5e44546-ea82-42eb-98df-19d51c71e9be
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 1%

---

# 將帳戶行銷最佳化

有效的帳戶式行銷需要帳戶層級對購買歷程有深入的瞭解。 因此，您可以決定最具影響力的行銷活動，以推動交易完成。

針對此瞭解，您要分析及探索：

* 行銷影響：

   * 橫跨行銷活動、管道和內容。
   * 在帳戶內購買群組時，

* 銷售管道進度。
* 追加銷售和交叉銷售機會。
* 客戶帳戶健康情況。


Customer Journey Analytics B2B edition可協助您最佳化帳戶行銷。 如需範例，請參閱下列各節。


## 以帳戶為基礎的行銷參與

您想要找出哪些體驗（線上和離線體驗）在推動已關閉機會方面最具影響力。

使用[歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)視覺效果來對應帳戶、商機、購買群組、行銷活動和管道之間的每個互動，以深入瞭解帳戶行銷中的運作方式以及您可以改善的地方。

歷程畫布視覺效果可協助您：

* 檢視完整劇本。 例如，您可以顯示&#x200B;*特定*&#x200B;高價值帳戶的詳細路徑，或包含所有已知線上和離線互動的購買群組。
* 將關鍵里程碑之前或之後的關鍵時刻內容化（例如：行銷合格潛在客戶觸發程式或機會建立）。
* 透過視覺效果在特定帳戶上的互動歷史記錄，支援銷售人員。 這類視覺效果可啟用相關的交談。

### 範例

您想要以視覺效果呈現從潛在客戶表單到已關閉成功的歷程。

1. [建立並設定歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)視覺效果。
1. 將&#x200B;**[!UICONTROL 帳戶]**&#x200B;設定為&#x200B;**[!UICONTROL 主要量度]**。
1. 請確定您選取&#x200B;**[!UICONTROL 帳戶]**&#x200B;做為&#x200B;**[!UICONTROL 歷程畫布容器]**。

   ![B2B使用案例 — 最佳化帳戶行銷 — 歷程畫布 — 設定](assets/b2b-uc-optimize-marketing-journey-canvas-config.png)

1. 選取「**[!UICONTROL 建置]**」。
1. 將節點拖放到畫布上並連線節點，以說明帳戶歷程。 例如：從&#x200B;**[!UICONTROL 潛在客戶表單：步驟1]**&#x200B;表單到&#x200B;**[!UICONTROL Opp。 已建立]**。

   ![B2B使用案例 — 最佳化帳戶行銷 — 歷程畫布](assets/b2b-uc-optimize-marketing-journey-canvas.png)


## 同類群組區段

您想要識別重要的買家群組，以便針對其他管道（例如付費媒體、電子郵件、社交）啟用這些買家群組。

使用[同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)視覺效果，根據共用的起點(例如市場資格(MQL)潛在客戶日期)，將B2B實體（帳戶、商機、購買群組）分組。 並在後續階段或里程碑中追蹤每個實體在一段時間內的進度。

同類群組表格視覺效果可協助您：

* 分析客戶或商機同類群組在幾週或幾個月內達成關鍵里程碑（例如：從行銷合格銷售機會晉升為銷售合格銷售機會）的速度。
* 識別某些同類群組（依區段、促銷活動來源、購買群組型別）在銷售週期中的移動速度是否比其他同類群組更快。
* 評估策略性方案（例如：行銷活動）是否與後續同類群組的較短推進時間表相關。

### 範例

您想要檢視每月已關閉商機的同類群組。

1. [建立並設定同類群組表格](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)視覺效果。
1. 使用&#x200B;**[!UICONTROL 已建立的商機]**&#x200B;做為&#x200B;**[!UICONTROL 包含條件]**&#x200B;量度。 選取&#x200B;**[!UICONTROL >=]**&#x200B;作為運運算元，並輸入值`1`。
1. 使用&#x200B;**[!UICONTROL Closed-Won]**&#x200B;作為&#x200B;**[!UICONTROL 傳回條件]**&#x200B;量度。 選取&#x200B;**[!UICONTROL >=]**&#x200B;作為運運算元，並輸入值`1`。
1. 選取&#x200B;**[!UICONTROL 機會]**&#x200B;作為容器。

   ![B2B使用案例 — 同類群組區段 — 同類群組表格 — 設定](assets/b2b-uc-optimize-marketing-cohort-table-config.png)

1. 選取&#x200B;**[!UICONTROL 組建]**。 如需同類群組表格的範例，請參閱下文。

   ![B2B使用案例 — 同類群組區段 — 同類群組表格](assets/b2b-uc-optimize-marketing-cohort-table.png)


## 面對面活動

您想要報告多個面對面事件中的參與帳戶和檢視活動。 因此，您可以分析和最佳化面對面活動出席的影響。

[流量](/help/analysis-workspace/visualizations/c-flow/flow.md)視覺效果可讓您視覺化路徑使用者，現在也可視覺化帳戶或購買群組、隨著時間而在互動或階段之間進行的路徑。

流量視覺效果可協助您：

* 識別B2B實體所周遊的接觸點最頻繁的順序（例如：從&#x200B;*網站造訪*&#x200B;到&#x200B;*白皮書下載*&#x200B;到&#x200B;*示範要求*）。
* 以視覺效果呈現帳戶或購買群組如何以非線性方式導覽（例如：回圈、略過階段或採取未預期的路線）。
* 專注於關鍵互動（例如：示範請求）之前或之後的流程，以瞭解哪些因素促成互動或互動後會採取哪些動作。

### 範例

您想要將對MQL （行銷合格銷售機會）產生的影響視覺化。

1. [建立並設定流量](/help/analysis-workspace/visualizations/c-flow/create-flow.md)視覺效果。
1. 選取&#x200B;**[!UICONTROL End with]**&#x200B;的&#x200B;**[!UICONTROL MQL合格]**。
1. 選取&#x200B;**[!UICONTROL 路徑維度]**&#x200B;的&#x200B;**[!UICONTROL 內容型別]**。
1. 選取&#x200B;**[!UICONTROL 顯示進階設定]**。
1. 為`5`欄數&#x200B;**[!UICONTROL 輸入]**。
1. 為&#x200B;**[!UICONTROL 流量容器]**&#x200B;選取&#x200B;**[!UICONTROL 帳戶]**。

   ![B2B使用案例 — 個人事件 — 流程設定](assets/b2b-uc-optimize-marketing-flow-config.png)

1. 選取「**[!UICONTROL 建置]**」。

   ![B2B使用案例 — 個人事件 — 流程設定](assets/b2b-uc-optimize-marketing-flow.png)
