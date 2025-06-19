---
description: 了解關於厘度類型和歸因
title: 量度類型和歸因
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 304b8d85767d89ee60a6fb37a128194f60ca89d4
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 91%

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

            * 從[歸因模型](#attribution-models)中選取&#x200B;**[!UICONTROL 模型]**。
            * 從[容器](#container)選項中選取&#x200B;**[!UICONTROL 容器]**。
            * 從[回顧期間](#lookback-window)選項中選取&#x200B;**[!UICONTROL 回顧期間]**。 如果您選取&#x200B;**[!UICONTROL 自訂時間]**，則可以以&#x200B;**[!UICONTROL 分鐘]**&#x200B;定義時間段，最多&#x200B;**[!UICONTROL 季]**。

      1. 請選取「**[!UICONTROL 套用]**」，以套用非預設歸因模型。選取「取消」，即可取消。

     如果您已定義非預設歸因模型，請選取「**[!UICONTROL 編輯]**」來修改選擇內容。

如需使用歸因模型、容器和回顧視窗的範例，請參閱[範例](#example)。


## 歸因模型 {#attribution-models}

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


## 容器 {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="容器"
>abstract="選取容器以設定所需的歸因範圍。"

{{attribution-container}}


## 回顧視窗 {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顧視窗"
>abstract="此設定可決定要為每個轉換套用的資料歸因期間。"

{{attribution-lookback-window}}




## 範例

{{attribution-example}}

>[!MORELIKETHIS]
>
>[歸因元件設定](/help/data-views/component-settings/attribution.md)
>&#x200B;>[參與率量度](participation-metric.md)
>

