---
title: 引導式分析常見問題集
description: 有關引導式分析的常見問題。
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: d5208a28c9efd6c31ecbfc6ff6b4e44a52f396e8
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# 引導式分析常見問題集

{{release-limited-testing}}

有關引導式分析的常見問題。

+++**引導式分析是否可供所有人使用？**

否；引導式分析是Customer Journey Analytics的付費附加元件。 如果您想要開始使用此附加元件，請聯絡您的Adobe客戶團隊。

+++

+++**使用引導式分析需要哪些實作變更？**

如果您已在Customer Journey Analytics中使用Analysis Workspace，則不需要進行額外的實作變更。 引導式分析使用與Analysis Workspace相同的資料檢視和連線。 對於所有Customer Journey Analytics（包括引導式分析），上線和使用任何專案型別的程式都是相同的。

+++

+++**在「引導式」分析內外辭彙如何相互關聯？**

引導式分析使用產品分析產業中較常使用的術語。 在引導式分析和Analysis Workspace之間切換時，您可以參考此表格。

| 引導式分析詞語 | Analysis Workspace詞語 |
| --- | --- |
| 事件 | 量度 |
| 屬性 | 維度 |
| 值 | 維度項目 |
| 區段 | 篩選器 |

{style="table-layout:auto"}

+++

+++**Analysis Workspace和引導式分析方法的報告方式有何差異？**

雖然Analysis Workspace和引導式分析使用相同的基礎資料，但每個工具查詢該資料的方式不同。

**Analysis Workspace是以維度為中心的體驗。** 表格通常包含維度專案列，而欄通常是量度。 您可以將篩選器套用至任一專案，以取得所需的資料。

![工作區結構](assets/workspace-structure.png)

**引導式分析是以事件為中心的體驗。** 視覺效果著重於事件，使用維度和篩選器來補充該資料。

![引導式分析結構](assets/guided-analysis-structure.png)

請考量下列範例，其中您著重於網站首頁的相關資料。 團隊提出類似的問題，但分析方法可能不同。

* 典型的以維度為中心的Analysis Workspace方法是，「首頁收到多少次頁面檢視？」

  ![Dimension置中](assets/dimension-centered.png)

* 典型的以事件為中心的引導式分析方法會是：「有多少使用者檢視過首頁？」

  ![以事件為中心](assets/event-centered.png)

這些陳述會說明實現相同報告的兩種不同方法，具體取決於您的事件管理策略。

+++
