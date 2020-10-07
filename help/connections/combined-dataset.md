---
title: 組合事件資料集
description: 瞭解 CJA 如何藉由合併資料集來建立連線。
translation-type: tm+mt
source-git-commit: ef05a948cb2036db24c8e308695e3615613d98d8
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 83%

---


# 組合事件資料集

建立連線時，CJA 會將所有結構和資料合併到單一資料集中。CJA使用此&#39;組合事件資料集&#39;來報告。 在連線中納入多個結構或資料集時：

* 結構會合併。重複的結構欄位會合併。
* 每個資料集的「人員 ID」欄會合併為一欄，不論其名稱為何。此欄是識別 CJA 中獨特訪客的基礎。
* 會根據時間戳記處理列。

## 範例

考量下列範例.您有兩個事件資料集，每個資料集的欄位都包含不同的資料。

>[!NOTE]
>
> Adobe Experience Platform 通常以 Unix 毫秒為單位儲存時間戳記。此範例中為了可讀性，會使用日期和時間。

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

使用這兩個事件資料集建立連接時，將使用下表進行報告。

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

此組合事件資料集是用於報告的項目。 某列是來自哪個資料集並不重要；CJA 將所有資料視為位於相同資料集中。如果兩個資料集中都出現相符的人員 ID，則會將其視為同一位獨特訪客。如果兩個資料集中都出現相符的人員 ID，且時間戳記在 30 分鐘內，則視為同一工作階段的一部分。

此概念也適用於歸因。某列是來自哪個資料集並不重要；歸因的運作方式與所有事件都來自單一資料集的情形完全相同。以上表為例：

如果您的連線僅包含第一個表格而不含第二個表格，則使用上次接觸歸因的 `string_color` 維度和 `metric_a` 量度來提取報表，並顯示：

| string_color | metric_a |
| --- | --- |
| 未指定 | 6 |
| 藍色 | 3 |
| 紅色 | 2 |

不過，如果連線中同時包含兩個表格，則歸因會變更，因為這兩個資料集中都有 `user_847`。第二個資料集屬性中的一列將 `metric_a` 歸因為「黃色」，其之前為未指定：

| string_color | metric_a |
| --- | --- |
| 黃色 | 6 |
| 藍色 | 3 |
| 紅色 | 2 |
