---
title: 篩選運算子
description: 判斷元件與篩選器內值的互動方式。
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
source-git-commit: 87da431752c235c442d13fd185c7ab8f6cf20eba
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 47%

---

# 篩選運算子

篩選器產生器可讓您使用選取的運算子來比較和限制值。 運算子分為兩類： [!UICONTROL 標準] 和 [!UICONTROL 不重複計數].

## 標準運算子

| 運算子 | 說明 |
| --- | --- |
| 等於 | 傳回完全符合數值或字串值的項目。如果使用萬用字元，請使用「符合」運算子。 |
| 不等於 | 傳回所有不含輸入值的項目。如果使用萬用字元，請使用「不符合」運算子。 |
| 包含 | 傳回含有輸入值字串的項目。 例如，如果字串維度的規則包含 `"Search"`，它會比對任何具有子字串的頁面 `"Search"` 包括 `"Search Results"`, `"Search"`，和 `"Searching"`. 此運算子區分大小寫。 |
| 不包含 | 與輸入值匹配的所有項目將從結果中排除。 例如，如果字串維度的規則不包含 `"Search"`，則會排除任何具有子字串的頁面 `"Search"` 包括 `"Search Results"`, `"Search"`，和 `"Searching"`. |
| 包含全部 | 傳回以任何順序包含所有子字串（以空格分隔）的項目。 例如，輸入 `"Search Results"` 與此運算子相符 `"Search Results"` 和 `"Results of Search"`，但不是 `"Search"` 或 `"Results"` 獨立。 此運算子最多支援100個以空格分隔的字詞。 |
| 不包含任何 | 與每個輸入值相符的所有項目都會從結果中排除。 例如，輸入 `"Search Results"` 搭配此運算子將排除 `"Search Results"` 和 `"Results of Search"`，但不是 `"Search"` 或 `"Results"`. 此運算子最多支援100個以空格分隔的字詞。 |
| 包含任何 | 傳回包含任何指定子字串的項目。 例如，輸入 `"Search Results"` 與此運算子相符 `"Search Results"`, `"Results of Search"`, `"Search"`，和 `"Results"`. 此運算子最多支援100個以空格分隔的字詞。 |
| 不包含任何 | 符合任何子字串的所有項目都會從結果中排除。 例如，輸入 `"Search Results"` 會排除 `"Search Results"`, `"Results of Search"`, `"Search"`，和 `"Results"`. 此運算子最多支援100個以空格分隔的字詞。 |
| 開始於 | 傳回以輸入值的字元或字串開頭的項目。 |
| 不開始於 | 傳回未以輸入值的字元或字串開頭的項目。 |
| 終止於 | 傳回以輸入值的字元或字串結尾的項目。 |
| 不終止於 | 傳回未以輸入值的字元或字串結尾的項目。 |
| matches | 根據給定的數值或字串值，傳回完全符合的項目。支援使用星號(`*`)。 此運算子區分大小寫。 例如：<ul><li>`a*e` matches `ae`, `abcde`, `adobe`，和 `a whole sentence`.</li><li>`adob*` matches `adobe`, `adobe analytics`，和 `adobo recipe`</li><li>`*dobe` matches `dobe`, `adobe`，和 `cute little dobe`.</li></ul> |
| 不符合 | 會排除符合字串的所有項目。 支援使用星號(`*`)。 |
| 存在 | 如果值非null，則傳回項目。 |
| 不存在 | 如果值為null，則傳回項目。 |

## Distinct Count 運算子

您可以劃分維度內項目不重複計數的區段。例如，您可以為檢視5個以上不重複產品的訪客，或檢視5個以上不重複頁面的造訪，建立篩選器。

| 運算子 | 說明 |
| --- | --- |
| 等於 | 傳回唯一計數等於輸入值的維度項目。 |
| 不等於 | 傳回唯一計數不等於輸入值的維度項目。 |
| 大於 | 傳回唯一計數大於輸入值的維度項目。 |
| 小於 | 傳回唯一計數小於輸入值的維度項目。 |
| 大於或等於 | 傳回唯一計數大於或等於輸入值的維度項目。 |
| 小於或等於 | 傳回唯一計數小於或等於輸入值的維度項目。 |
