---
title: 引導式分析常見問題集
description: 有關引導式分析的常見問題。
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: ht
source-wordcount: '434'
ht-degree: 100%

---

# 引導式分析常見問題集

有關引導式分析的常見問題。

+++**如何為我的組織佈建引導式分析？**

引導式分析是 Adobe Product Analytics 的一部分；而 Adobe Product Analytics 是 Customer Journey Analytics 的付費附加元件。如果您想開始使用此附加元件，請聯絡您的 Adobe 帳戶團隊。

+++

+++**使用引導式分析需要哪些實作變更？**

如果您現在已經在使用 Customer Journey Analytics，就無需進行額外的實作變更。引導式分析會使用與其他 CJA 介面相同的[資料視圖](../data-views/data-views.md)和[連線](../connections/overview.md)，例如 [Analysis Workspace](../analysis-workspace/home.md)。

為了讓您的一般使用者能夠透過引導式分析取得最大成功，建議您在 Adobe Experience Platform 和[資料視圖](../data-views/data-views.md)中製定穩健的事件綱要和管理策略。

+++

+++**何時應該使用引導式分析或 Analysis Workspace？**

**引導式分析**&#x200B;可以幫助使用者快速取得高品質的深入分析。對於產品團隊、希望更安心處理資料的使用者，甚至是分析師而言，它都相當實用，能夠取得先機進行更深入的分析。

**[Analysis Workspace](../analysis-workspace/home.md)** 是更自由形式的空間，可讓您進一步探討資料以找出更多深入分析。對於相當了解資料且想要深入探討的分析師和進階使用者而言，它非常實用。

+++

+++**引導式分析和 Analysis Workspace 之間的術語如何比較？**

引導式分析會使用產品團隊中較常用的字詞。在引導式分析和 [Analysis Workspace](../analysis-workspace/home.md) 之間切換時，您可以參考此表格。

| 引導式分析字詞 | Analysis Workspace 字詞 |
| --- | --- |
| 事件 | 量度 |
| 使用者 | 人員 |
| 屬性 | 維度 |
| 值 | 維度項目 |
| 區段 | 篩選器 |

{style="table-layout:auto"}

+++

+++**引導式分析和 Analysis Workspace 處理報告的方式有哪些差異？**

雖然 [Analysis Workspace](../analysis-workspace/home.md) 和引導式分析使用相同的基礎資料，各個工具支援您形成該資料查詢的方式依然有所不同。

* **Analysis Workspace 是以維度為中心的體驗。**&#x200B;表格通常由維度列組成，而欄通常是量度。可以在列和欄中套用篩選器，以獲得所需的資料。

* **引導式分析是以事件和使用者為中心的體驗。**&#x200B;每次分析都是從選取事件開始，之後可以新增維度和篩選器來縮小該事件資料的範圍。

![Analysis Workspace 和引導式分析視圖](assets/structure.png){style="border:1px solid gray"}

請考慮以下範例，其中請將重點放在有關網站首頁的資料。團隊會詢問類似的問題，但分析方法可能會不同。

* 以維度為中心的典型 Analysis Workspace 方法會是：「我們來看看首頁，了解它收到了多少頁面瀏覽次數。」

  ![以維度為中心](assets/dimension-centered.png){style="border:1px solid gray"}

* 以事件和使用者為中心的典型引導式分析方法會：「有多少使用者造訪過我們的首頁？」

  ![以事件為中心](assets/event-centered.png){style="border:1px solid gray"}

+++
