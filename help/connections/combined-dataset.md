---
title: 合併的資料集
description: 瞭解CJA如何結合資料集建立連線。
translation-type: tm+mt
source-git-commit: f9cdcb8a6efe688d553929c3081f3239e0691cd9

---


# 合併的資料集

當您建立連線時，CJA會將所有結構描述和資料集合在單一資料集中。 CJA使用這個&#39;組合資料集&#39;來報告。 在連接中包含多個方案或資料集時：

* 結合結構。 將合併重複的架構欄位。
* 每個資料集的「人員ID」欄會合併為單一欄，不論其名稱為何。 此欄是識別CJA中獨特訪客的基礎。
* 根據時間戳記處理列。

## 範例

考量下列範例. 您有兩個資料集，每個資料集的欄位包含不同的資料。

> [!NOTE] Adobe Experience Platform通常以Unix毫秒為單位儲存時間戳記。 為了在此範例中顯示可讀性，會使用日期和時間。

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

使用這兩個資料集建立連接時，將使用下表進行報告。

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

這組合的資料集是用於報告的資料集。 一列是哪個資料集並不重要；CJA將所有資料視為位於相同資料集。 如果兩個資料集中都出現相符的「人員ID」，則會將其視為相同的唯一訪客。 如果在30分鐘內，兩個資料集中都出現相符的人員ID，且時間戳記不超過30分鐘，則視為同一作業的一部分。

此概念也適用於歸因。 一列是哪個資料集並不重要；歸因的運作方式與所有事件來自單一資料集的情形完全相同。 以上表為例：

如果您的連線僅包含第一個表格而非第二個表格，則使用上次接觸歸因的維度和 `string_color` 度量 `metric_a` 來提取報表會顯示：

| string_color | metric_a |
| --- | --- |
| 藍色 | 5 |
| 未指定 | 6 |
| 紅色 | 2 |

不過，如果您在連接中同時包含兩個表，則歸因會變更，因為這 `user_847` 兩個資料集都有。 第二個資料集屬性的一列 `metric_a` 為「黃色」，先前未指定這些屬性：

| string_color | metric_a |
| --- | --- |
| 黃色 | 6 |
| 紅色 | 2 |
| 藍色 | 3 |
