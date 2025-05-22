---
description: 了解關於厘度類型和歸因
title: 量度類型和歸因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 2d182004b12eb44f54ec9b4b5f63cb9072594aec
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 100%

---

# 量度類型和歸因

您可以在計算量度定義中為量度設定量度類型和[歸因模型](#attribution-models)。

1. 在量度元件中選取「![設定](/help/assets/icons/Setting.svg)」。
1. 在快顯對話框中：

   ![量度類型和歸因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 量度類型]**：

     | 量度類型 | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 如果某個公式由單一標準量度組成，則其顯示的資料將與其非計算量度相對應公式一樣。標準量度適合用來建立每個行項目專屬的計算量度。 <p>例如，![事件](/help/assets/icons/Event.svg) **[!UICONTROL 訂單]** ![除以](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段]**&#x200B;會採用該特定條列項目的訂單數，然後除以該特定條列項目的工作階段數。 |
     | **[!UICONTROL 總計]** | 使用適用於每個條列項目報告期間的&#x200B;**[!UICONTROL 總計]**。如果公式是由單一總計量度組成，則會在每個條列項目顯示相同總計。當您要建立與資料總計比較的計算量度時，適合使用總計量度。 <p>例如， ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 訂單]** ![除以](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段總計]**&#x200B;會顯示與所有工作階段比較的訂單比例，而不只是特定條列項目的工作階段數。在此範例中，您在計算量度中指定 ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段]**&#x200B;量度的&#x200B;**[!UICONTROL 總計]**，這會自動將其轉換為 ![事件](/help/assets/icons/Event.svg) **[!UICONTROL 工作階段總計]**。 |

   * 指定&#x200B;**[!UICONTROL 歸因]**。

      1. 您可以執行下列兩個動作中的一個:

         * 停用「**[!UICONTROL 使用非預設歸因模式]**」，以便使用預設欄歸因模型，也就是「上次接觸時間」且回顧期為 30 天。
         * 啟用「**[!UICONTROL 使用非預設歸因模型]**」。在「**[!UICONTROL 欄歸因模型]**」對話框。

            * 從歸因模型中選取「**[!UICONTROL 模型]**」。
            * 選取「**[!UICONTROL 回顧視窗]**」。如果您選取「**[!UICONTROL 自訂時間]**」，您可以&#x200B;**[!UICONTROL 分鐘]** (最多以&#x200B;**[!UICONTROL 季度]**) 來定義時段。請參閱「[回顧視窗](#lookback-window)」，了解更多資訊

      1. 請選取「**[!UICONTROL 套用]**」，以套用非預設歸因模型。選取「取消」，即可取消。

     如果您已定義非預設歸因模型，請選取「**[!UICONTROL 編輯]**」來修改選擇內容。

請參閱「[範例](#example)」，了解使用歸因模型和回顧視窗的範例。


## 歸因 {#attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非預設歸因模式"
>abstract="為所選的量度啟用非預設歸因模型。"


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="選取此量度的歸因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="上次接觸"
>abstract="100% 功勞歸於訪客看到的最後一個維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接觸"
>abstract="100% 功勞會歸於訪客看到的第一個維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="線性"
>abstract="功勞平均分佈在所有維度值上。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="參與率"
>abstract="100% 功勞歸於訪客看到的每個維度值。<br/>欄總計會出現浮報現象。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一次接觸"
>abstract="功勞僅給予與轉換同一事件中發生的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同一次接觸"
>abstract="功勞僅給予與轉換同一事件中發生的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="40% 功勞歸於第一個維度值，40% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲線"
>abstract="60% 功勞歸於最後一個維度值，20% 歸於第一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J 曲線"
>abstract="60% 功勞歸於最後一個維度值，20% 歸於第一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="60% 功勞歸於第一個維度值，20% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="反向 J"
>abstract="60% 功勞歸於第一個維度值，20% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="時間耗損"
>abstract="在時間上最接近轉換的維度值獲得最多功勞。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自訂"
>abstract="根據歸因加權定義您自己的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="自訂"
>abstract="根據歸因加權定義您自己的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="演算法"
>abstract="功勞是根據統計演算法動態決定的。"



{{attribution-models-details}}


### 回顧視窗 {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顧視窗"
>abstract="此設定可決定要為每個轉換套用的資料歸因期間。"

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### 歸因範例 {#attribution-example}

考量下列範例：

1. 9 月 15 日當天，某人透過付費搜尋廣告前往您的網站後離開。
1. 9 月 18 日當天，此人透過來自朋友的社交媒體連結再次造訪您的網站。對方在購物車中加入數個商品，但並未購買任何商品。
1. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

根據您的回顧期間和歸因模型，管道會獲得不同的評分。以下為幾個範例：

* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「工作階段回顧期間」**，歸因只會計入第三次造訪。在電子郵件和顯示廣告兩者之間，訪客優先接觸到電子郵件，因此電子郵件在這次 $50 美元的購買動作中有 100% 的評分。

* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「個人回顧期間」**，歸因會計入全部三次造訪。付費搜尋是第一次接觸，因此在這次 $50 美元的購買動作中有 100% 的評分。

* 如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「工作階段回顧期間」**，評分會由電子郵件和顯示廣告拆分，兩個管道各有 $25 美元的評分。如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告平分，每個管道在這次購買中各有 $12.50 的評分。

* 如果採用&#x200B;**「J 形」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分，

   * 60% 歸給顯示廣告，價值 $30 美元，
   * 20% 歸給付費搜尋，價值 $10 美元，
   * 剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。

* 如果採用&#x200B;**「時間耗損」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分。以預設的 7 天半衰期計算，結果如下：

   * 顯示廣告接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 電子郵件接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 社交媒體接觸點與轉換之間的間隔為六天。`2^(-6/7) = 0.552`
   * 付費搜尋接觸點與轉換之間的間隔為九天。`2^(-9/7) = 0.41`
   * 將這些值標準化會產生下列結果：

      * 顯示廣告：33.8%，價值 $16.88 美元
      * 電子郵件：33.8%，價值 $16.88 美元
      * 社交媒體：18.6%，價值 $9.32 美元
      * 付費搜尋：13.8%，價值 $6.92 美元

 如果評分屬於多個管道，則轉換事件數 (通常為整數) 將拆分。舉例來說，如果兩個管道對某個使用線性歸因模型的訂單都有貢獻，則兩個管道各會從該訂單中獲得 0.5 評分。這些部分量度在經過所有人的加總後，會四捨五入為最接近的整數，顯示於報表中。


>[!MORELIKETHIS]
>
>[歸因元件設定](/help/data-views/component-settings/attribution.md)
>[參與率量度](participation-metric.md)
>

