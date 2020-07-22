---
title: 演算法歸因
description: 演算法歸因模型的詳細資訊。
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 14%

---


# 演算法歸因

>[!NOTE]
>
>您正在檢視 Customer Journey Analytics 中 Analysis Workspace 的相關文件，其功能集與傳統 Adobe Analytics 中的 [Analysis Workspace 略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。[深入了解...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL 演算法歸因]** 目前正進行有限的測試。 如需詳 [細資訊，請參閱](https://docs.adobe.com/content/help/zh-Hant/analytics/landing/an-releases.html) 「Adobe Analytics功能發行」。

「分析工 [作區](models.md) 」中的「演算法歸因」模型與其他模型不同，因為它使用統計技術在報表或自由表格中的維度項目間分配評分。 和分析工作區中的所有其他歸因模型一樣，它可用於任何維度或度量，並支援無限制的分段和劃分，並將100%的轉換分發至表格中的維度（也稱為「分數」歸因）。

基於合作博弈論的Harsanyi Danyis算法用于歸因。 哈薩尼派息是對沙普利價值解（以諾貝爾經濟學獎得主勞埃德·沙普利命名）的概括，即在一場對結果貢獻不均的遊戲中，在玩家之間分配信用。

在高層面上，每個觸點的轉換信用的歸因計算將回顧窗口內的每個營銷觸點視為必須公平分配盈餘的玩家聯盟。 每個聯盟的盈餘分配是根據每個子聯盟（或先前參與的維度項目）先前建立的盈餘遞歸決定。 如需詳細資訊，請參閱John Harsanyi和Lloyd Shapley的原稿：

* 沙普利，勞埃德·S。 (1953)。 n人遊戲的值。 *對博弈論的貢獻，2(28)*,307-317.
* Harsanyi, John C. (1963)。 n人合作博弈的簡化談判模型。 *國際經濟回顧*,194-220年。

>[!NOTE]
>
>演算法歸因的結果只有在特定回顧視窗中存在多個觸點時，才會與其他模型不同。 無論歸因模型為何，單一觸點的轉換都能獲得100%的評分。
