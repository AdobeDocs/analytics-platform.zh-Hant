---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# CJA實驗小組統計計算：詳細資訊

本頁記錄了CJA實驗面板中使用的詳細統計計算。 面向技術用戶。


## 轉換率

轉換率或 **平**。 *μ<sub>ν</sub>* 每個變數 *ν* 在實驗中，定義為度量之和與分配給該度量的單位數之和的比率， *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="度量均值"></p>
此處，

- *Y<sub>我</sub>* 是每個單位的度量值 *我*，它已分配給給定變數 *ν*。
- 單位之和 *我* 取決於標準化指標的選擇。
   - 如果 *人物* 是標準化度量，每個單位都是唯一的人/個人資料。
   - 如果 *會話* 是標準化度量，每個單元都是唯一的會話。
   - 如果 *事件* 是標準化度量，每個單元是唯一事件。

通常，應選擇此規範化度量與您的獨立性單位相等，即，如果用戶在一個會話中的行為與他們在另一個會話中的行為無關，則會話是合理的規範化度量。

在需要時，使用樣本標準差，表達式


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="度量均值"></p>


## 提升度

變體之間的升降  *ν*，和控制項變數  *ν<sub>0</sub>* 是換算率中的相對「δ」，定義為
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="度量均值"></p>
兌換率如上文所界定者。


## 置信序列

雖然未顯示在「CJA實驗」面板中，但單個變體的置信度序列 *ν* 是Adobe所使用的統計方法的核心，此處定義(從 [沃德比史密斯等](https://doi.org/10.48550/arXiv.2103.06476))。

> 假設有人對估計目標參數感興趣 *ψ* （如實驗中變數的轉換率）。 然後，將「固定時間」置信區間(CIs)序列與時間一致置信區間(CS)序列的二分法總結如下：
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="度量均值"></p>

換句話說，對於正則置信區間，概率保證目標參數在值範圍內 *克勒<sub>t</sub>* 僅在一個固定值為 *n* ( *n* 是示例數)。 相反，對於置信序列，我們保證在所有時間/所有樣本大小的值 *t*，興趣參數的&quot;true&quot;值在界內 *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*。

這對線上測試有很深的影響：
- 當新資料可用時，CS可以根據需要更新。
- 實驗可以連續地被監控、自適應地停止或繼續。
- I類錯誤在所有停止時間（包括與資料相關的時間）都被控制。

Adobe使用漸近置信序列，該序列對於具有平均估計的個體變數 *μ* 有窗體

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="度量均值"></p>

執行:
- *N* 是該變數的單位數
- *σ* 是標準差的樣本估計值（以前定義）
- *α* 是I類錯誤（或誤覆蓋概率）的所需級別
- *ρ*<sup> 2</sup> 是一個常數，它調節CS最緊的樣本大小。 Adobe選擇了 *ρ*<sup> 2</sup> = 10<sup>-2.8</sup>這適用於線上實驗中看到的轉換率類型。


## 可信度

Adobe所用的置信度是「隨時有效」的置信度，通過求平均治療效果的置信度序列得到。

確切地說，我們注意到 *t* test兩個變數之間的均值差，在 *p*&#x200B;此test的 — value和均值差的置信區間。 比方說，任何時候 *p*-value可通過求平均處理效果估計器的（任何時間有效）置信序列來獲得：
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="度量均值"></p>

我們使用的估計是逆傾向加權(IPW)估計。 考慮 *N = N<sub>0</sub>* + *N<sub>1</sub>* 單位，每個單位的變型分配$i$，標籤為 *A<sub>我</sub>=0,1* 如果單位被分配給變型ν=0,1 如果用戶被賦予固定概率（傾向） *π<sub>0</sub>, (1-π<sub>0</sub>)*，其結果度量 *Y<sub>我</sub>*，則IPW估計器
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="度量均值"></p>

注意到 *f* 是影響函式，沃德比 — 史密斯等 表明該估計器的置信序列為：
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="度量均值"></p>

用經驗估計代替分配概率： *π<sub>0</sub> = N<sub>0</sub>/N*&#x200B;方差項可以用單個樣本均值估計表示  *μ<sub>{0,1}</sub>* 標準差估計，  *σ<sub>{0,1}</sub>* 為：

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="度量均值"></p>


回顧一個帶有test統計的常規假設test *z =(μ)<sub>1</sub> - μ<sub>0</sub>)/ σ<sub>p</sub>*,$p$值與置信區間之間有對應關係：

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="度量均值"></p>

何處 *Φ* 是標準常態分佈的累積分佈。 對於任何有效時間 *p*-values，給定上述平均治療效果的置信度序列，我們可以反轉這種關係：
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="度量均值"></p>

最後， **任何時間 *信心*** 是
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="度量均值"></p>


## 宣告實驗為結論性

對於雙臂實驗，CJA實驗面板顯示一條消息，說明實驗是 **結論** 當任何有效置信度超過95%時（即任何有效時間） *p*-value低於5%)。

當存在兩個以上變體時，應用Bonferonni校正。 為了進行 *K* 和單基線（對照）治療， *K-1* 獨立假設test。 Bonferonni修正意味著，如果在任何有效時間，則我們拒絕控制與給定變數具有相等均值的零假設 *p*-value低於閾值0.05/(K-1)。


## 最佳手臂

當實驗被確定時，顯示最佳效能臂。 這是具有最佳效能（最高平均或轉換率）的臂，在包括控制項的集合中，以及具有 *p*&#x200B;低於Bonferonni閾值的 — value。