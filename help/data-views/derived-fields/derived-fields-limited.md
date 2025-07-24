---
title: 衍生欄位
description: 派生欄位是透過一組適用函數和函數範本來指定結構描述欄位和/或標準元件的報告時間操作。
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 27%

---


# 衍生欄位（有限測試）{#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>這是尚未普遍提供的新衍生欄位函式的初步檔案。 使用此資訊來瞭解新的衍生欄位函式。 本檔案仍可能會有所變更，根據本文的最新版本，恕不提供任何法律義務。
>><br/>請參閱[衍生欄位](derived-fields.md)，以取得一般衍生欄位功能以及目前可用的函式與函式範本的相關資訊。
>

## 函數引用

{{select-package}}

對於每個支援的函數，請參閱以下詳細資訊：

- 規格：
   - 輸入資料類型：支援的資料類型，
   - 輸入：可能輸入的值，
   - 包含的運算子：此功能支援的運算子 (如果有)，
   - 限制：套用於此特定函數的限制，
   - 輸出。

- 使用案例，包括：
   - （選擇性）定義衍生欄位之前的資料，
   - 如何定義衍生欄位，
   - （選擇性）定義衍生欄位後的資料。

- 限制 (如果適用)。



<!-- DATE MATH -->

### 日期數學 {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="日期數學"
>abstract="此函式提供傳回兩個日期或日期時間欄位之間差異的功能。"

傳回兩個日期或兩個日期時間欄位之間的差異。

+++ 詳細資料

## 規格 {#datemath-io}

| 輸入資料類型 | 輸入 | 包含的運算子 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>日期</li><li>日期和時間</li></ul> | <ul><li>[!UICONTROL 範圍]<ul><li>事件</li><li>工作階段</li><li>人員</li></ul></li><li>[!UICONTROL 數值]:<ul><li>日期</li><li>日期時間</li><li>靜態日期（使用者輸入）</li><li>靜態日期時間（使用者輸入）</li><li>動態的日期<ul><li>今天</li></ul></li><li>動態日期時間<ul><li>現在</li></ul></li></ul></li><li>[!UICONTROL 粒度]：<ul><li>秒</li><li>分鐘</li><li>小時</li><li>日</li><li>週</li><li>月</li><li>季</li><li>年</li></ul></li><li>針對每個日期或日期時間傳回：<ul><li>第一個（在工作階段或人員內）</li><li>上次（在工作階段或人員內）</li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位有 2 個函數</p> | <p>新的衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例 1 {#datemath-uc1}

身為飯店公司的行銷分析師，您想要瞭解上週客戶簽到日期與預訂日期之間的天數差異。


### 衍生欄位 {#datemath-uc1-derivedfield}

您定義一個 `Days between booking and check-in` 衍生欄位。您使用[!UICONTROL DATE MATH]函式定義規則，以計算[!UICONTROL 預訂日期]與[!DNL Person]簽到日期[!UICONTROL 之間]範圍的天數。 您選取[!UICONTROL 天]作為[!UICONTROL 輸出粒度]。 而且您選取[!UICONTROL 傳回]預訂日期[!UICONTROL 和]簽到日期[!UICONTROL 的最後一個]，以確保計算中使用最後一個人員範圍的值。

![日期數學規則的熒幕擷圖](assets/datemath-1.png)


## 使用案例 2 {#datemath-uc2}

身為實體店的行銷分析師，您想要瞭解客戶上次造訪商店是在多少天前。 您可以使用行動應用程式內的地理位置功能以及商店中的信標，擷取客戶的實體造訪。

### 衍生欄位 {#datemath-uc2-derivedfield}

您定義一個新的 `Days Since Visit To Shop` 衍生欄位。您使用[!UICONTROL DATE MATH]函式來定義規則，以計算自訂日期時間（您在[!UICONTROL Date]中指定）與[!UICONTROL 當地時間] （來自事件資料集的[!UICONTROL placeContext]欄位群組）之間的天數，其中具有[!UICONTROL 人員]的[!UICONTROL 重複資料刪除範圍]。 您選取「[!UICONTROL 傳回最後]」以確保計算中使用[!UICONTROL 當地時間]的最後一個人員範圍值。 選取「日」作為[!UICONTROL 輸出粒度]。

![日期數學規則2](assets/datemath-2.png)的熒幕擷圖


## 使用案例 3 {#datemath-uc3}

您想要瞭解工作階段中的客戶下訂單前的搜尋時間（分鐘）。

您定義新的`Time Between Search And Order In Minutes`衍生欄位，它是兩個[[!UICONTROL CASE WHEN]函式](#case-when)的結果，用來定義[!UICONTROL 搜尋時間]和[!UICONTROL 訂購時間]值。
然後使用這兩個值來計算差異，其中的[!UICONTROL DATE MATH]函式的[!UICONTROL 範圍]設定為[!UICONTROL 工作階段]，值設定為[!UICONTROL 搜尋時間]和[!UICONTROL 順序時間]，而[!UICONTROL 輸出粒度]設定為[!UICONTROL 分鐘]。 針對這兩個值，您選取[!UICONTROL 傳回第一個]，以確保傳回第一個[!UICONTROL 搜尋時間]和[!UICONTROL 訂購時間]。

![日期數學規則3](assets/datemath-3.png)的熒幕擷圖



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### 深度 {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="深度"
>abstract="此函數可傳回任何欄位的深度，與事件深度標準元件的功能相似。"

傳回欄位深度，類似於現成可用的標準事件深度維度[](/help/components/dimensions/overview.md#standard-dimensions)。

+++ 詳細資料

## 規格 {#depth-io}

| 輸入資料類型 | 輸入 | 包含的運算子 | 限制 | 輸出 |
|---|---|---|---|---|
| 任何 | 任何欄位 | 不適用 | 每個衍生欄位有 3 個函數 | 新的衍生欄位 |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## 使用案例 {#depth-uc1}

您想要瞭解搜尋深度（您也可以將其解譯為搜尋次數）。 因此，您稍後可以使用該搜尋深度來查詢與特定搜尋深度關聯的搜尋字詞。


### 衍生欄位 {#depth-uc1-derivedfield}

您定義一個新的 `Search Depth` 衍生欄位。您使用[!UICONTROL DEPTH]函式定義規則來擷取[!UICONTROL Search]的深度，並將其儲存在新的衍生欄位中。

深度規則![的](assets/depth-1.png)熒幕擷圖

+++


<!-- TYPECASE -->

### 型別轉換 {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="型別轉換"
>abstract="此函數可以立即變更欄位類型，讓 Customer Journey Analytics 中的欄位可以進行其他轉換。"

變更欄位的欄位型別，使其可用於Customer Journey Analytics中的其他轉換。

+++ 詳細資料

## 規格 {#typecast-io}

| 輸入資料類型 | 輸入 | 包含的運算子 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>數值</li><li>日期</li><li>日期和時間</li><li>字串</li></ul> | <ul><li>[!UICONTROL 欄位] | <p><ul><li>整數<ul><li>至字串<strong>（必須）</strong></li></ul></li><li>雙倍<ul><li>至字串<strong>（必須）</strong><ul><li>包含要繼承的小數位數（「最多5位？」）</li></ul></li><li>至整數<strong> （應該）</strong></li></ul></li><li>位元組<ul><li>至字串<strong>（必須）</strong></li></ul></li><li>長整數<ul><li>至字串<strong>（必須）</strong></li></ul></li><li>日期<ul><li>至字串<strong>（必須）</strong><ul><li>提供定義輸出格式的功能</li></ul></li><li>範例<ul><li>日期（例如2025年1月7日）<ul><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 2025-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 01/07/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MMM DD, YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例如： 2025年1月7日</li></ul></li></ul></li></ul></li></ul></li><li>日期和時間<ul><li>至字串<strong>（必須）</strong><ul><li>提供定義輸出格式的功能</li></ul></li><li>範例<ul><li data-stringify-indent="0" data-stringify-border="0">日期 — 時間（例如2025年1月7日，1:30pm，52秒）<ul><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 2025-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY/MM/DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MMM DD, YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例如： 2025年1月7日13:30:52</li></ul></li></ul></li></ul></li><li>字串<ul><li>至數值<strong>（應該）</strong><ul><li>如果值的性質不是數值，則會傳回null。</li><li>我們需要使用者輸入精確度及要使用的地區設定。 </li></ul></li></ul></li></ul></li></ul></p> | <p>每個衍生欄位有 3 個函數</p> | <p>新的衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例 1 {#typecast-uc1}

您有一個整數值位畫面高度（例如事件資料集的device.screenHeight），您想將其當作字串型維度使用。


### 衍生欄位 {#typecast-uc1-derivedfield}

您定義一個 `Screen Height` 衍生欄位。您使用[!UICONTROL TYPECAST]函式定義規則以[!UICONTROL Typecast為] [!UICONTROL 字串] [!UICONTROL 熒幕高度]欄位，並將其儲存在新的衍生欄位中。

![Typecast規則1](assets/typecast-1.png)的熒幕擷圖



## 使用案例 2 {#typecast-uc2}

您想在同類群組表格（僅支援整數）中使用「收入」，但「收入」欄位具有「雙倍」型別。

![Typecast規則2](assets/typecast-2.png)的熒幕擷圖


### 衍生欄位 {#typecast-uc2-derivedfield}

您定義一個 `Revenue (integer)` 衍生欄位。您使用[!UICONTROL TYPECAST]函式定義規則給[!UICONTROL Typecast to] [!UICONTROL Integer] [!UICONTROL 收入]欄位，並將其儲存在新的衍生欄位中。


+++
