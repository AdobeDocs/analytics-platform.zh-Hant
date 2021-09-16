---
title: 無值選項元件設定
description: 判斷維度為空時如何處理。
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 35%

---


# 無值選項元件設定

沒有值選項可讓您判斷Analysis Workspace如何處理資料集中的事件包含量度，但維度未包含值的情況。 您可以選擇此維度項目的名稱、將其完全隱藏，甚至將其視為實際值。

![沒有值選項](../assets/no-value-options.png)

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 如果顯示，請呼叫「無值」] | 可讓您將&#x200B;**[!UICONTROL 無值]**&#x200B;維度項目重新命名為其他項目的文字欄位。 |
| [!UICONTROL 預設不顯示「無」值] | 不會在報告中顯示此值。未與此維度系結的量度發生次數不會顯示在報表中。 |
| [!UICONTROL 預設顯示「無」值] | 在報表中顯示此值。 |
| [!UICONTROL 將「無值」視為值] | 以您在[!UICONTROL 下指定的文字取代資料中的空白值。如果顯示，請呼叫&quot;No value&quot;]。 例如，如果您以行動裝置類型為維度，您可將&#x200B;**[!UICONTROL &#x200B;「No value&#x200B;」]**&#x200B;項目重新命名為「Desktop」。將此欄位變更為自訂值時，會將自訂值視為合法的字串值。 因此，如果您在此欄位中輸入「Red」值，出現在資料中的字串「Red」執行個體將落在您已指定的相同條列項目下。 |
