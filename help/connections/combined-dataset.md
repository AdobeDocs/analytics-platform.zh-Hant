---
title: 合併事件資料集
description: 瞭解Customer Journey Analytics如何透過合併資料集來建立連線。
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 2f2e4ac68f7a410b8046daae2f90af75ffdedab5
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 41%

---


# 合併事件資料集

當您建立連線時，Customer Journey Analytics會將所有事件資料集合併到單一資料集中。 Customer Journey Analytics會使用此合併事件資料集製作報表（以及設定檔和查詢資料集）。 當您在連線中包含多個事件資料集時：

* 資料集中的欄位資料，根據 **相同結構描述路徑** 都會合併至合併資料集中的單一欄。
* 為每個資料集指定的「人員ID」欄，會合併至合併資料集中的單一欄， **無論其名稱為何**. 此欄是識別Customer Journey Analytics中不重複人員的基礎。
* 會根據時間戳記處理列。
* 事件會解析至毫秒層級。

## 範例

請參考下列範例。您有兩個事件資料集，各自包含不同資料的不同欄位。

>[!NOTE]
>
>Adobe Experience Platform通常以UNIX®毫秒為單位儲存時間戳記。 此範例會使用日期和時間，以便閱讀。

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

使用這兩個事件資料集建立連線時，且已識別

* `example_id` 做為第一個資料集的人員ID，並且
* `different_id` 做為第二個資料集的人員ID，

下列合併資料集用於製作報表。

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

為了說明結構描述路徑的重要性，請考慮此情境。 在第一個資料集中， `string_color` 是以結構描述路徑為基礎 `_experience.whatever.string_color` 和結構描述路徑上的第二個資料集  `_experience.somethingelse.string_color`. 在此案例中，資料為 **非** 已合併至所產生合併資料集中的一欄。 結果改為兩個 `string_color` 合併資料集中的欄。

這個合併事件資料集會用來製作報表。某列是來自哪個資料集並不重要。 Customer Journey Analytics將所有資料視為在相同資料集中。 如果兩個資料集中都出現相符的人員ID，則會將其視為同一個不重複人員。 如果兩個資料集中都出現相符的人員 ID，且時間戳記在 30 分鐘內，則視為同一工作階段的一部分。

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

## 跨頻道分析

合併資料集的下一個層級是跨管道分析，也就是根據通用識別碼（人員ID）來合併來自不同管道的資料集。 跨管道分析可藉由拼接功能受益，讓您為資料集的人員ID重設金鑰，讓資料集可正確更新，以順暢地合併多個資料集。 拼接會檢視已驗證和未驗證工作階段的使用者資料，以產生拼接ID。

跨管道分析可讓您回答下列問題：

* 有多少人在某個管道開始體驗，但在不同管道結束體驗？
* 有多少人與我的品牌互動？他們使用的裝置數量與類型為何？他們互相重疊的程度？
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何？登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換？
* 如果考慮跨裝置歷程，我對行銷活動成效的理解會有何改變？ 我的漏斗分析會有何改變？
* 使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同？


如需跨管道分析的詳細資訊，請參閱特定使用案例：

* [跨頻道分析](../use-cases/cross-channel/cross-channel.md)

如需有關拼接功能的更深入討論，請前往：

* [拼接概述](/help/stitching/overview.md)
* [常見問題](/help/stitching/faq.md)

