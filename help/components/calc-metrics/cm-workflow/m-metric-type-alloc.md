---
description: 瞭解量度型別和歸因
title: 量度型別和歸因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 39%

---

# 量度型別和歸因

您可以為計算量度定義中的量度設定量度型別和[歸因模型](#attribution-models)。

1. 在量度元件中選取![設定](/help/assets/icons/Setting.svg)。
1. 在快顯對話方塊中：

   ![量度型別和歸因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 量度型別]**：

     | 量度類型 | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 如果公式包含單一標準量度，它會顯示與其相對的非計算量度相同的資料。 標準量度可用來建立個別條列專案專屬的計算量度。 <p>例如，![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**&#x200B;會接受特定條列專案的訂單，然後除以該特定條列專案的工作階段數目。 |
     | **[!UICONTROL 總計]** | 在每個行專案中的報告期間使用&#x200B;**[!UICONTROL 總計]**。 如果公式包含單一「總量」量度，則計算量度會在每個行專案上顯示相同的「總量」數字。 如果您想要建立計算量度來與總資料進行比較，「總量」量度就十分實用。 <p>例如，![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段總數]**&#x200B;會顯示所有工作階段的訂單比例，而不只是特定條列專案的工作階段比例。 在此範例中，您為計算量度中的![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段]**&#x200B;量度指定&#x200B;**[!UICONTROL 總量]**，這會自動將其轉換為![事件](/help/assets/icons/Event.svg) **[!UICONTROL 總工作階段]**。 |

   * 指定&#x200B;**[!UICONTROL 歸因]**。

      1. 您可以：

         * 停用&#x200B;**[!UICONTROL 使用非預設歸因模型]**，以使用回顧期間為30天的預設資料行歸因模型（即「上次接觸」）。
         * 啟用&#x200B;**[!UICONTROL 使用非預設歸因模型]**。 在&#x200B;**[!UICONTROL 資料行歸因模型]**&#x200B;對話方塊中，

            * 從歸因模型中選取&#x200B;**[!UICONTROL 模型]**。
            * 選取&#x200B;**[!UICONTROL 回顧期間]**。 如果您選取&#x200B;**[!UICONTROL 自訂時間]**，則可以以&#x200B;**[!UICONTROL 分鐘]**&#x200B;定義時間段，最多&#x200B;**[!UICONTROL 季]**。 如需詳細資訊，請參閱[回顧期間](#lookback-window)

      1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用非預設歸因模型。 選取「取消」以取消。

     如果您已定義非預設歸因模型，請選取&#x200B;**[!UICONTROL 編輯]**&#x200B;以修改選取範圍。

請參閱[範例](#example)以取得使用歸因模型和回顧期間的範例。


## 歸因 {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非預設歸因模式"
>abstract="為所選的量度啟用非預設歸因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="選取此量度的歸因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lasttouch"
>title="上次接觸"
>abstract="100% 功勞歸於訪客看到的最後一個維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_firsttouch"
>title="首次接觸"
>abstract="100% 功勞會歸於訪客看到的第一個維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_linear"
>title="線性"
>abstract="功勞平均分佈在所有維度值上。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_participation"
>title="參與率"
>abstract="100% 功勞歸於訪客看到的每個維度值。<br/>欄總計會出現浮報現象。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_sametouch"
>title="同一次接觸"
>abstract="功勞僅給予與轉換同一事件中發生的維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="40% 功勞歸於第一個維度值，40% 歸於最後一個維度值，20% 則分配到中間的維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_jcurve"
>title="J 曲線"
>abstract="60% 功勞歸於最後一個維度值，20% 歸於第一個維度值，20% 則分配到中間的維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="60% 功勞歸於第一個維度值，20% 歸於最後一個維度值，20% 則分配到中間的維度值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_timedecay"
>title="時間耗損"
>abstract="在時間上最接近轉換的維度值獲得最多功勞。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_custom"
>title="自訂"
>abstract="根據歸因加權定義您自己的位置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_algorithmic"
>title="演算法"
>abstract="功勞是根據統計演算法動態決定的。"

<!-- markdownlint-enable MD034 -->


{{attribution-models-details}}


### 回顧視窗 {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_calculatedmetrics_attribution_lookbackwindow"
>title="回顧視窗"
>abstract="此設定可決定要為每個轉換套用的資料歸因期間。"

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### 歸因範例 {#attribution-example}

考量下列範例：

1. 9月15日當天，有人透過付費搜尋廣告進入您的網站後離開。
1. 9月18日當天，該人透過朋友的社群媒體連結再次造訪您的網站。 對方在購物車中加入數個商品，但並未購買任何商品。
1. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

根據您的回顧期間和歸因模型，管道會獲得不同的評分。以下是一些範例：

* 使用&#x200B;**首次接觸**&#x200B;和&#x200B;**工作階段回顧期間**，歸因只會計入第三次造訪。 在電子郵件和顯示廣告兩者之間，訪客優先接觸到電子郵件，因此電子郵件在這次 $50 美元的購買動作中有 100% 的評分。

* 使用&#x200B;**首次接觸**&#x200B;和&#x200B;**人員回顧期間**，歸因會計入全部三次造訪。 付費搜尋是第一次接觸，因此在這次 $50 美元的購買動作中有 100% 的評分。

* 使用&#x200B;**線性**&#x200B;和&#x200B;**工作階段回顧期間**，評分會由電子郵件和顯示廣告平分。 這兩個管道各有$25美元的評分。
使用**線性**&#x200B;和&#x200B;**人員回顧期間**，評分會由搜尋付費、社群媒體、電子郵件和顯示廣告平分， 每個管道在這次購買中各有 $12.50 的評分。

* 使用&#x200B;**J形**&#x200B;和&#x200B;**個人回顧期間**，評分會由搜尋付費、社群媒體、電子郵件和顯示廣告平分。

   * 60% 歸給顯示廣告，價值 $30 美元，
   * 20% 歸給付費搜尋，價值 $10 美元，
   * 剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。

* 使用&#x200B;**時間耗損**&#x200B;和&#x200B;**人員回顧期間**，評分會由付費搜尋、社交、電子郵件和顯示廣告平分。 以預設的 7 天半衰期計算，結果如下：

   * 顯示廣告接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 電子郵件接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 社交接觸點與轉換之間的間隔為六天。`2^(-6/7) = 0.552`
   * 付費搜尋接觸點與轉換之間的間隔為九天。`2^(-9/7) = 0.41`
   * 將這些值標準化會產生下列結果：

      * 顯示廣告：33.8%，價值 $16.88 美元
      * 電子郵件：33.8%，價值 $16.88 美元
      * 社交媒體：18.6%，價值 $9.32 美元
      * 付費搜尋：13.8%，價值 $6.92 美元

如果評分屬於多個管道，則通常具有整數的轉換事件會被除。 例如，如果兩個管道對使用線性歸因模型的訂單都有貢獻，則兩個管道會分別獲得該訂單的0.5倍。 這些部分量度會在所有人員之間加總，然後舍入至最接近的整數以用於報表。


>[!MORELIKETHIS]
>
>[歸因元件設定](/help/data-views/component-settings/attribution.md)
>[參與率量度](participation-metric.md)
>

