---
description: 了解 Adobe Analysis Workspace 及其相關元件的已知限制
title: 已知限制
feature: Workspace Basics
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
TQID: https://experienceleague.adobe.com/rbguvYCSFfbmMVr5IBC1M9OD0wDIG0Z4p28Z2dOerBc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 100%

---

# 已知限制

以下為 Analysis Workspace 及其相關元件的已知限制清單：

## 表格

* 日期範圍或量度在表格中設為列時，無法新增日期比較欄。
* 區段在表格中設為列時，「從選取項目建立量度」功能會遭停用。 此外，「從選取項目建立量度」不可套用至對齊日期的欄。
* 用於劃分列的條件式格式無法使用自訂範圍。
* 採用「加總列中的值來計算總計」設定時 (通常與「靜態」列項目搭配使用)，表格總列數無法跟隨趨勢產生變化。

## 視覺效果

* 善用[!UICONTROL 「流失」]、[!UICONTROL 「流量」]、[!UICONTROL 「同類群組」]、[!UICONTROL 「直方圖」]等區段的視覺效果，無法將計算量度設為輸入項目。
* [!UICONTROL 流量]：「登入/退出」維度 (例如[!UICONTROL 「登入頁面」]) 無法用於「流量」。
* [!UICONTROL 同類群組]：非整數無法當作同類群組條件使用。

## 區段

* [!UICONTROL 「事件」]、[!UICONTROL 「人員」]等特定量度和維度無法進行劃分。
* 在[面板放置區](/help/analysis-workspace/c-panels/panels.md)中建立的臨時區段是一種快速區段。 除非設定為公開，否則它們不會顯示在 Workspace 或區段元件管理器的左側面板中。 如需詳細資訊，請參閱[快速區段](/help/components/segments/seg-quick.md)。

## 計算量度

* 特定視覺化呈現中無法使用計算量度。 請參閱[視覺化呈現](#visualizations)。
* 「[!UICONTROL 歸因]」面板中無法使用計算量度，因為計算量度本身可能包含個別的歸因模型。
* 如果從工作區中建立計算量度，而非經由「[!UICONTROL 元件 > 區段]」建立，則某些元件和運算子會無法使用。 例如 [!UICONTROL IP 位址]。

## 日期範圍

* 自訂日期範圍不支援「[!UICONTROL 去年的今天]」、「[!UICONTROL 上個月的今天]」等。


## 報告設定

* [!UICONTROL 「報表設定」]頁面上的某些設定並不適用。 Analysis Workspace 僅會使用以下幾種位於底部的[!UICONTROL 「語言/貨幣/編碼」]設定：[!UICONTROL 「千位分隔符號」]、[!UICONTROL 「排程報表編碼」]和[!UICONTROL 「CSV 分隔符號字元」]。

