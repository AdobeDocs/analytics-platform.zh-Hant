---
title: 合併事件資料集
description: 了解 CJA 如何透過合併資料集來建立連線。
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
source-git-commit: 2b6ef07963d648d757f9c1baef123bff416a871a
workflow-type: ht
source-wordcount: '326'
ht-degree: 100%

---


# 合併事件資料集

建立連線時，CJA 會將所有結構和資料合併成單一資料集。CJA 會使用這個「合併事件資料集」來製作報表。在連線中納入多個結構或資料集時：

* 結構會合併。重複的結構欄位會合併。
* 每個資料集的「人員 ID」欄會合併為一欄，不論其名稱為何。此欄是識別 CJA 中獨特訪客的基礎。
* 會根據時間戳記處理列。

## 範例

請參考下列範例。您有兩個事件資料集，各自包含不同資料的不同欄位。

>[!NOTE]
>
>Adobe Experience Platform 通常以 Unix 毫秒為單位儲存時間戳記。此範例會使用日期和時間，以便閱讀。

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

使用這兩個事件資料集建立連線時，系統會使用下表來製作報表。

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

這個合併事件資料集會用來製作報表。某列是來自哪個資料集並不重要；CJA 將所有資料視為位於相同資料集中。如果兩個資料集中都出現相符的人員 ID，則會將其視為同一位獨特訪客。如果兩個資料集中都出現相符的人員 ID，且時間戳記在 30 分鐘內，則視為同一工作階段的一部分。

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
