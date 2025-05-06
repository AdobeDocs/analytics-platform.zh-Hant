---
title: 維度概觀
description: 瞭解什麼是維度以及如何在Customer Journey Analytics中使用維度
feature: Dimensions
exl-id: 3592808b-17fd-401d-ab12-ff0308b21f45
source-git-commit: ed7e9a6c34c5f8ba9ba4f75be05768409cbc158d
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 36%

---

# 維度概觀

維度是Customer Journey Analytics中用於分析資料的元件型別。 例如，您在[Analysis Workspace](/help/analysis-workspace/home.md)或[Report Builder](/help/report-builder/rb-overview.md)中建置報表時，會使用維度。

Customer Journey Analytics維度的型別不受限制；值可以是數值、文字、物件、清單或所有專案的混合。

Customer Journey Analytics中的基本報表會針對量度欄（通常是數值）顯示維度列（通常是字串值）。

例如，如果您將「頁面」維度與「人物」量度結合，您將會看到排名報表，其中顯示您的訪客最多人瀏覽的頁面：

| 頁面 | 人員 |
| --- | ---: |
| 首頁 | 800 |
| 產品頁面 | 500 |
| 購買頁面 | 100 |

{style="table-layout:fixed"}

每個維度分別代表您的網站不同的部分或面向。您可以將其中的一或多個維度與一或多個量度結合，以建立所需的報表。


## 建立維度

Customer Journey Analytics管理員可以[在資料檢視中建立維度](/help/data-views/create-dataview.md#components)。

## 預設維度

建立資料檢視時，系統會預設將下列以時間為基礎的元件新增為資料檢視的維度：

- 15 分鐘
- 30 分鐘
- 5 分鐘
- 日
- 當月日期
- 星期
- 年中的日
- 小時
- 小時
- 分鐘
- 小時期間各分鐘
- 月
- 月份
- 季
- 季別
- 秒
- 年度內的第幾週
- 年

## 新增維度說明

Customer Journey Analytics管理員可在資料檢視內或直接在Analysis Workspace中新增維度和其他元件的說明。 有關如何將說明新增至維度的資訊，請參閱[新增元件說明](/help/components/add-component-descriptions.md)。
