---
title: 演算法歸因
description: 瞭解演演算法歸因模型的詳細資料。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
TQID: https://experienceleague.adobe.com/t9MaGZioEVgtaMgoTpemXlvulgaDFo-XBtM6-G8562Q
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# 演算法歸因

Analysis Workspace 中的演算法[歸因模型](models.md)與其他模型不同，因為此模型使用統計技術將評分分配給報表或自由格式表格中的各個維度項目。 和Analysis Workspace中的所有其他歸因模型一樣，演演算法歸因也可用於任何維度或量度。 演演算法歸因支援無限制的分段和劃分，並將100%的轉換分送給表格中的一或多個維度（也稱為「細節」歸因）。

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

用於歸因的演算法以合作賽局理論中的 Harsanyi 利益為基礎。 Harsanyi Dividend是Shapley值解法（以諾貝爾經濟學獎獲得者Lloyd Shapley命名）的泛論，用於分配玩家之間的評分，對結果的貢獻不相等。

概言之，在為每個接觸點計算轉換評分的歸因時，會將回顧期間內的每個行銷接觸點視為玩家聯盟。 對於這個玩家聯盟，盈餘必須公平分配。 每個聯盟的盈餘分配則由每個子聯盟先前遞回建立的盈餘決定。

如需詳細資訊，請參閱John Harsanyi和Lloyd Shapley的原稿：

* 夏普利，勞埃德 (1953). A value for n-person games。 *Contributions to the Theory of Games, 2(28)*, 307-317。
* 夏仙怡，約翰 (1963). A simplified bargaining model for the n-person cooperative game。 *International Economic Review 4(2)*, 194-220。

>[!NOTE]
>
>只有在給定回顧期間內多個接觸點存在時，演算法歸因的結果才會與其他模型不同。 無論歸因模型為何，單一接觸點的轉換都會獲得 100% 的評分。
