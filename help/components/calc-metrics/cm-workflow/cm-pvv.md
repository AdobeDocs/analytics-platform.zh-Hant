---
description: 瞭解如何建立簡單的計算量度。
title: 建立簡單的計算量度
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 10%

---

# 建立簡單的計算量度

下列資訊說明如何建立簡單的&#x200B;*每次造訪頁面檢視次數*&#x200B;量度。

1. 開始建立量度，如[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中所述。
1. 命名量度`Page Views per Session`或類似名稱。
1. 為量度提供使用者易記的&#x200B;**[!UICONTROL 說明]**，以顯示該量度的用途。
1. 選取正確的&#x200B;**[!UICONTROL 格式]**。 在此範例中，請選擇&#x200B;**[!UICONTROL 小數]**。
1. 決定您要報表顯示多少小數位數。
1. 在&#x200B;**[!UICONTROL 顯示上升趨勢為]**&#x200B;下拉式功能表中，選取▲ **[!UICONTROL 良好（綠色）]**。
1. 新增「**[!UICONTROL 標記]**」用以組織量度。
1. 針對此計算量度，請先將&#x200B;**[!UICONTROL 頁面檢視次數]**&#x200B;從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件拖曳至畫布的&#x200B;**[!UICONTROL 定義]**&#x200B;區段。
1. 然後從&#x200B;**[!UICONTROL Metrics]**&#x200B;元件拖曳&#x200B;**[!UICONTROL 工作階段]**，並將量度拖曳至&#x200B;**[!UICONTROL 頁面檢視]**&#x200B;下方（等到藍線出現為止，再拖曳量度）。
1. 選取除![除](/help/assets/icons/Divide.svg)運運算元。 （除數是預設運運算元。）
1. 當您建置量度時，可以看到量度的&#x200B;**[!UICONTROL 預覽]**。
1. **[!UICONTROL 產品相容性]**&#x200B;顯示計算量度是否在Customer Journey Analytics中的所有地方都相容（實驗除外）。

   ![簡單計算量度](assets/simple-calculated-metric.png)
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   注意「**[!UICONTROL 摘要]**」公式會隨著您變更量度定義而更新。

1. （選擇性）若要共用、核准、（重新）標籤、重新命名或刪除量度，您可以前往[計算量度管理員](/help/components/calc-metrics/cm-workflow/cm-manager.md)。

