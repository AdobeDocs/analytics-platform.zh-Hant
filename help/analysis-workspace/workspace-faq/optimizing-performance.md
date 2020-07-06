---
description: 'null'
title: Analysis Workspace 效能最佳化
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 98%

---


# Analysis Workspace 效能最佳化

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

特定因子可以影響 Analysis Workspace 中專案的效能在開始建立專案之前，請務必先了解各項貢獻因素，以便以最有效的方式規劃及建立專案。以下列出影響效能的因素，以及將專案最佳化的最佳實踐。Analysis Workspace 效能是 Adobe 主打的功能之一，也是我們持續致力改善的項目。

## 區段邏輯複雜度

複雜的區段可能對專案效能造成重大影響。會使區段增加複雜度的因素 (按影響程度由上往下排序) 包括：

* 「包含」、「包含任何」、「符合」、「開始於」或「終止於」運算子
* 連續區段，特別是使用維度限制 (「之內」/「之後」) 時
* 區段使用的維度內不重複維度項目數量 (例如：具有 10 個不重複項目的頁面 =「A」，其速度會比具有 100000 個不重複項目的頁面 =「A」更快)
* 使用的不同維度數量 (例如：頁面 =「首頁」和頁面 =「搜尋結果」，其速度會比 eVar 1 =「紅色」和 eVar 2 =「藍色」更快)
* 多個「或」運算子 (而非「和」)
* 範圍各異的巢狀容器 (例如：「訪客」當中「造訪」內的「點擊」)

**邏輯複雜度相關最佳實務**

雖然有些複雜度因子無法避免，但您可以思考有哪些機會可降低您區段的複雜度。一般而言，區段條件越明確越好。例如：

* 若使用容器，在區段頂端使用單一容器，其速度會比一系列巢狀容器更快。
* 若使用運算子，「等於」會比「包含」更快，而「等於任何」會比「包含任何」更快。
* 若使用多個條件，「和」運算子會比一系列「或」運算子更快。此外，請盡可能將多個 OR 陳述式簡化為一個「等於任何」陳述式。

另外，[分類](https://docs.adobe.com/content/help/zh-Hant/analytics/components/classifications/c-classifications.html)可協助將許多值併入精準的群組中，讓您可從這些群組建立區段。與包含許多 OR 陳述式或「包含」標準的區段相比，針對分類群組而劃分的效能較佳。

## 要求的資料範圍

要求的專案資料範圍將影響 Analysis Workspace 的效能。

**日期範圍相關最佳實務**

可能情況下，提取資料時請不要超出所需。

記住，日期範圍 (紫色元件) 會覆蓋面板日期範圍。因此，如果您使用不同日期範圍作為欄 (例如，「上個月」、「上週」和「昨天」欄)，面板日期範圍不必跨越所有的欄日期範圍。可簡單將其設為昨天，因自由表格中使用的資料範圍會覆蓋面板。如需在 Analysis Workspace 中使用日期範圍的相關資訊，請看[這段影片](https://www.youtube.com/watch?v=ybmv6EBmhn0)。

請使用[日期比較選項](/help/components/date-ranges/time-comparison.md)來提取您要比較的特定期間資料。例如，如果您需要顯示上個月的資料來與去年同用份比較，不必將面板設定為過去 13 個月的資料，只要使用比較時間範圍選項來顯示年對年的效能。

## 視覺效果的數目

一個專案中包含的圖表視覺效果數目，會影響 Analysis Workspace 的整體回應。

**視覺效果數目相關最佳實務**

減少專案中的視覺效果數目。Analysis Workspace 會在幕後為您新增的每個視覺效果做大量處理，因此請對報表的消費者來說最重要的視覺效果定出優先順序，並且若有需要的話，將支援的視覺效果分到其他更詳細的專案。

## 視覺效果的複雜度 (區段、量度、篩選器)

專案本身新增的視覺效果類型 (例如，流失率與自由表格對比) 對專案效能的影響不大。視覺效果的複雜度會增加處理時間。增加視覺效果複雜度的因素包括：

* 要求的資料範圍，如前述
* 套用的區段數；例如，用來作為自由表格列的區段
* 使用複雜區段
* 自由表格的靜態項目列或欄
* 自由表格列所套用的篩選器
* 包含的量度數目，尤其是使用了區段的計算量度

**視覺效果複雜度相關最佳實務**

如果您注意到您的專案載入速度不如預期，可以的話，試著將一些區段取代為 eVar 和篩選器。

如果您發現自己時常使用公司重要資料點的區段和計算量度，請考慮改良實作，用更直接的方式擷取這些資料點。使用 Adobe Experience Platform Launch 之類的標記管理器和 Adobe 的處理規則，可以快速輕鬆地執行實施變更。若要深入了解如何簡化複雜區段，請見上方的「區段邏輯複雜度」。

## 面板數目

一個面板可以有許多視覺效果，因此，面板數目也會影響 Analysis Workspace 的整體回應。

**面板數目相關最佳實務**

請勿在一個專案中加入所有所需項目，盡可能針對特定用途或利害關係人群組建立個別專案。使用標記將專案依主題組織整理，並與股東群組共用相關專案。

如果需要更多專案組織方式，記住[直接連結](https://www.youtube.com/watch?v=6IOEewflG2U)到專案也是一個做法。建立內部的專案索引，讓股東更容易找到他們要找的。

如果一個工作區需要許多面板，請先摺疊面板再儲存和共用。載入專案時，Analysis Workspace 只會載入展開面板的內容。直到使用者展開，否則不會載入摺疊的面板。這種做法有兩個優點：

* 摺疊的面板可節省專案的整體載入時間
* 對報表消費者來說，摺疊的面板是以邏輯方式組織專案的好方法

## 報表套裝的大小

報表套裝的大小可能看來是個重大因素，但實際上由於 Adobe 的資料處理方式，它在專案效能上只扮演一個小角色

## 同時存取 Analysis Workspace 的人數

如果使用者分別存取不同報表套裝，則同時存取 Analysis Workspace 或特定專案的人數對 Analysis Workspace 的效能沒有實質影響。如果使用者同時存取相同報表套裝，效能就會受影響。

## Analysis Workspace 的常見錯誤訊息

在與 Analysis Workspace 互動時，您可能會遇到錯誤。錯誤可能的發生原因有很多，以下列出最常見的幾種。

| 錯誤訊息 | 為何發生這項錯誤？ |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | 您的組織針對特定報表套裝同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案、已排程報表、已排程警報，以及同時提出報表請求的使用者數量。建議您將要針對報表套裝提出的請求和排程平均分配在一整天時間內。 |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe 遇到需要解決的問題。建議您透過客戶服務請求提交錯誤代碼。 |
| `The request is too complex.` | 您的報表請求規模過大，無法執行。造成此錯誤的因素包括請求的規模所導致的逾時、區段或搜尋篩選器中有過多相符項目、加入的量度過多、維度和量度組合不相容等。建議您簡化請求。 |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | 建議您縮小搜尋文字的條件，並再次嘗試請求。 |
| `This dimension does not currently support non-default attribution models.` | 建議您使用與[歸因 IQ](../attribution/overview.md) 相容的維度來取代表格中的維度。 |
| `Your request failed as a result of too many columns or pre-configured rows.` | 建議您移除某些欄或列，或將它們分割為個別的視覺效果。 |
