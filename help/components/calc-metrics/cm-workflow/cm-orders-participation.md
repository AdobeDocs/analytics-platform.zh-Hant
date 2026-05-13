---
description: 說明如何建立量度，顯示哪些行銷管道協助推動訂單。
title: 建立更複雜的計算量度
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# 建立更複雜的計算量度

本文會說明一個更複雜的計算量度範例。 此計算量度會顯示哪些行銷管道協助推動訂單。 此型別的計算量度可適用於任何維度或成功事件。

1. 開始建立計算量度，如[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。

1. 在計算量度產生器中，將量度命名為`Assisted Online Orders`或類似名稱。

1. 從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件中選取&#x200B;**[!UICONTROL 線上訂單]**&#x200B;量度，並將量度拖曳至&#x200B;**[!UICONTROL 定義]**&#x200B;區域。

   1. 選取量度的![設定](/help/assets/icons/Setting.svg)。
   1. 請選取「**[!UICONTROL 使用非預設歸因模型]**」。
   1. 調整&#x200B;**[!UICONTROL 欄歸因模型]**&#x200B;中的歸因模型。
      1. 選取&#x200B;**[!UICONTROL 模型]**&#x200B;的&#x200B;**[!UICONTROL 自訂]**。 將&#x200B;**[!UICONTROL 入門者]**&#x200B;設定為`0`，**[!UICONTROL 播放器]**&#x200B;設定為`100`，以及&#x200B;**[!UICONTROL 更靠近]**&#x200B;設定為`0`。
      1. 選取&#x200B;**[!UICONTROL 容器]**&#x200B;的&#x200B;**[!UICONTROL 訪客]**。
      1. 選取&#x200B;**[!UICONTROL 回顧期間]**&#x200B;的&#x200B;**[!UICONTROL 30天]**。

      1. 選取&#x200B;**[!UICONTROL 「套用」]**。

      ![資料行歸因模型](assets/complex-calculated-metric.png)

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存計算量度。

若要使用計算量度：

1. 在Analysis Workspace中，使用&#x200B;**[!UICONTROL 行銷管道]**&#x200B;維度、**[!UICONTROL 線上訂單]**&#x200B;以及您新的&#x200B;**[!UICONTROL 輔助線上訂單]**&#x200B;量度來建立自由表格。

   ![行銷管道輔助線上訂單](assets/marketing-channel-assists.png)

1. （選用）如[共用計算量度](/help/components/calc-metrics/cm-workflow/cm-sharing.md)中所述，與組織中的其他使用者共用量度。

這是分辨哪些行銷管道協助促進訂單的簡單方法。 或者，您也可以從自由表格選取任何量度，然後從快顯功能表直接從表格調整歸因模型。
