---
title: 引導式分析常見問題集
description: 有關引導式分析的常見問題。
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 2b1e0ce53016634e0cb32f9256fa48e02f2a5323
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 2%

---

# 引導式分析常見問題集

有關引導式分析的常見問題。

+++**如何布建我的組織以進行引導式分析？**

引導式分析是Customer Journey Analytics的付費附加元件。 如果您想要開始使用此附加元件，請聯絡您的Adobe客戶團隊。

+++

+++**使用引導式分析需要哪些實作變更？**

如果您目前已經使用Customer Journey Analytics，就不需要進行額外的實施變更。 引導式分析使用相同的 [資料檢視](../data-views/data-views.md) 和 [連線](../connections/overview.md) 作為其他CJA介面，例如 [Analysis Workspace](../analysis-workspace/home.md).

若要讓一般使用者在引導式分析上取得最大成功，建議您在Adobe Experience Platform中建立強大的事件結構描述和管理策略，並 [資料檢視](../data-views/data-views.md).

+++

+++**何時應使用引導式分析或Analysis Workspace？**

**引導式分析** 可協助使用者快速獲得高品質的深入分析。 對於產品團隊、希望以更自信的方式處理資料的使用者，甚至分析師而言，此功能都是深入分析的開端。

**[Analysis Workspace](../analysis-workspace/home.md)** 是一個更自由的空間，可讓您深入探究資料，以發掘更多深入見解。 對於熟悉資料且想深入瞭解資料的分析人員和進階使用者而言，此維度非常有用。

+++

+++**引導式分析和Analysis Workspace的術語有何不同？**

引導式分析使用的辭彙在產品團隊中更為常用。 在引導式分析與之間切換時，您可以參照此表格 [Analysis Workspace](../analysis-workspace/home.md).

| 引導式分析詞語 | Analysis Workspace詞語 |
| --- | --- |
| 事件 | 量度 |
| 使用者 | 人員 |
| 屬性 | 維度 |
| 值 | 維度項目 |
| 區段 | 篩選器 |

{style="table-layout:auto"}

+++

+++**如何進行引導式分析和Analysis Workspace方法報告有何不同？**

當 [Analysis Workspace](../analysis-workspace/home.md) 和引導式分析使用相同的基礎資料，每個工具讓您形成該資料查詢的方式不同。

* **Analysis Workspace是以維度為中心的體驗。** 表格通常包含維度列，而欄通常為量度。 篩選條件可同時套用至列和欄，以取得所需的資料。

* **引導式分析是以事件為中心的體驗。** 每個分析都從選取事件開始，然後可以新增維度和篩選器來調整該事件資料。

![結構](assets/structure.png)

請考量下列範例，其中您著重於網站首頁的相關資料。 團隊提出類似的問題，但分析方法可能不同。

* 典型的以維度為中心的Analysis Workspace方法是：「讓我們看看首頁，看看它收到多少頁面檢視。」

  ![Dimension置中](assets/dimension-centered.png)

* 典型的以事件為中心的引導式分析方法會是：「有多少使用者檢視過首頁？」

  ![以事件為中心](assets/event-centered.png)

+++
