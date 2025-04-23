---
title: 運算子
description: 決定元件如何與區段中的值互動。
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
feature: Filters, Segments
role: User
source-git-commit: 85a22d1e57925f0512ce0cc658cfba1008339d91
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 54%

---

# 運算子

區段產生器可讓您使用選取的運運算元來比較和限制元件的值。 運算子有兩種類別: [[!UICONTROL 標準]](#standard-operators)和[[!UICONTROL 不重複計算]](#distinct-count-operators)。

## 標準運算子

| 運算子 | 說明 |
| --- | --- |
| **[!UICONTROL 等於]** | 傳回完全符合數值或字串值的項目。如果使用萬用字元，請使用符合運運算元。 |
| **[!UICONTROL 不等於]** | 傳回所有不含輸入值的項目。如果使用萬用字元，請使用does not match運運算元。 |
| **[!UICONTROL 等於任何]** | 傳回包含匹配所輸入之子字串值的任何項目，以分號隔開。 |
| **[!UICONTROL 包含]** | 傳回含有輸入值字串的項目。 例如，如果頁面名稱維度的值包含`Search`，此運運算元會比對名稱中包含子字串`Search`的所有頁面，包括`Search Results`、`Search`和`Searching`。 此運算子區分大小寫。 |
| **[!UICONTROL 不包含]** | 從結果中排除和輸入值相符的所有專案。 例如，如果Page Name維度的值不包含`Search`，此運運算元會排除名稱中含有子字串`Search`的所有頁面，包括`Search Results`、`Search`和`Searching`。 |
| **[!UICONTROL 包含全部]** | 傳回包含任何順序的子字串 (以空格分隔) 的項目。 例如，指定`Search Results`作為此運運算元的值會符合`Search Results`和`Results of Search`，但不會單獨符合`Search`或`Results`。 此運算子支援最多達 100 個以空格分隔的單字。 |
| **[!UICONTROL 不包含任何]** | 從結果中排除和每個輸入值相符的所有專案。 例如，指定`Search Results`作為此運運算元的值將會排除`Search Results`和`Results of Search`，但不會排除`Search`或`Results`。 此運算子支援最多達 100 個以空格分隔的單字。 |
| **[!UICONTROL 包含任何]** | 傳回包含任何指定子字串的項目。 例如，指定`Search Results`作為此運運算元的值會符合`Search Results`、`Results of Search`、`Search`和`Results`。 此運算子支援最多達 100 個以空格分隔的單字。 |
| **[!UICONTROL 不包含任何]** | 從結果中排除和任何子字串相符的所有專案。 例如，指定`Search Results`作為此運運算元的值將會排除`Search Results`、`Results of Search`、`Search`和`Results`。 此運算子支援最多達 100 個以空格分隔的單字。 |
| **[!UICONTROL 開始於]** | 傳回以指定值的字元或字串開頭的專案。 |
| **[!UICONTROL 不開始於]** | 傳回未以指定值的字元或字串開頭的專案。 |
| **[!UICONTROL 終止於]** | 傳回以指定值的字元或字串結尾的專案。 |
| **[!UICONTROL 不終止於]** | 傳回未以指定值的字元或字串結尾的所有專案。 |
| **[!UICONTROL 符合]** | 根據給定的數值或字串值，傳回完全符合專案的專案。 使用星號 (`*`) 支援萬用字元。 此運算子區分大小寫。例如：<ul><li>`a*e` 會比對 `ae`、`abcde`、`adobe` 和 `a whole sentence`。</li><li>`adob*` 會比對 `adobe`、`adobe analytics` 和 `adobo recipe`</li><li>`*dobe` 會比對 `dobe`、`adobe` 和 `cute little dobe`。</li></ul> |
| **[!UICONTROL 不符合]** | 排除和字串相符的所有項目。 支援使用星號 (`*`) 的萬用字元。 |
| **[!UICONTROL 存在]** | 若該值並非空值，則傳回項目。 |
| **[!UICONTROL 不存在]** | 若該值為空值，則傳回項目。 |

## Distinct Count 運算子

您可以劃分維度內項目不重複計數的區段。例如，您可以為檢視5個以上不重複產品或造訪（已檢視5個以上不重複頁面）的使用者建立區段。

| 運算子 | 說明 |
| --- | --- |
| **[!UICONTROL 等於]** | 傳回唯一計數等於輸入值的維度項目。 |
| **[!UICONTROL 不等於]** | 傳回唯一計數不等於輸入值的維度項目。 |
| **[!UICONTROL 大於]** | 傳回唯一計數大於輸入值的維度項目。 |
| **[!UICONTROL 小於]** | 傳回唯一計數小於輸入值的維度項目。 |
| **[!UICONTROL 大於或等於]** | 傳回唯一計數大於或等於輸入值的維度項目。 |
| **[!UICONTROL 小於或等於]** | 傳回唯一計數小於或等於輸入值的維度項目。 |
