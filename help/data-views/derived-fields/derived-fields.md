---
title: 衍生欄位
description: 衍生欄位會透過一組可用函式和函式範本，指定結構描述欄位和/或標準元件的報告時間操控。
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
source-git-commit: 1fddf0e8421b35021a1f1641a684cacbc0ec1f0d
workflow-type: tm+mt
source-wordcount: '8366'
ht-degree: 12%

---

# 衍生欄位

衍生欄位是Adobe Customer Journey Analytics中即時報告功能的重要方面。 衍生欄位可讓您透過可自訂的規則產生器，迅速定義 (通常是複雜的) 資料操作。然後，您可以在[Workspace](../../analysis-workspace/home.md)中使用該衍生欄位作為元件（量度或維度），甚至在[資料檢視](../data-views.md)中進一步將該衍生欄位定義為元件。

相較於在Customer Journey Analytics以外的其他位置轉換或操控資料，衍生欄位可節省大量時間和精力。 例如[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hant)、[資料Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)或您自己的擷取轉換載入(ETL) /擷取載入轉換(ELT)程式。

衍生欄位是在[資料檢視](../data-views.md)中定義，是根據定義為規則的一組函式，並套用至可用的標準和/或結構描述欄位。

範例使用案例包括：

- 定義衍生的「頁面名稱」欄位，更正不正確收集之頁面名稱值以更正頁面名稱值。

- 定義衍生的行銷管道欄位，以根據一或多個條件（例如URL引數、頁面URL、頁面名稱）決定適當的行銷管道。

## 衍生欄位介面 {#interface}

當您建立或編輯衍生欄位時，請使用衍生欄位介面。

![衍生欄位對話方塊的熒幕擷圖](assets/derived-field-dialog.png)


|  | 名稱 | 說明 |
|---------|----------|--------|
| 1 | **選取器** | 您可使用選取器區域來選取您的函式、函式範本、結構描述欄位或標準欄位，並將其拖放至規則產生器。 <br/>使用下拉式清單來選取： <br/>![函式](assets/Smock_Function_18_N.svg) [!UICONTROL 函式] — 列出可用的[函式](#function-reference)，</br>![函式範本圖示](assets/Smock_FileTemplate_18_N.svg) [!UICONTROL 函式範本] — 列出可用的[函式範本](#function-templates)，<br/>![結構描述欄點陣圖示](assets/Smock_Folder_18_N.svg) [!UICONTROL 結構描述欄位] — 列出資料集類別（事件、設定檔、查詢）和先前定義的衍生欄位中可用的欄位，以及<br/>![標準欄點陣圖示](assets/Smock_DragHandle_18_N.svg) [!UICONTROL 標準欄位] — 可用欄位例如Platform資料集ID)。 選擇器中只會顯示字串和數值標準欄位。 如果函式支援其他資料型別，則可以為規則介面中的值或欄位選取具有這些其他資料型別的標準欄位。<br/>您可以使用![搜尋圖示](assets/Smock_Search_18_N.svg)搜尋方塊來搜尋功能、功能範本、結構描述和標準欄位。 <br/>您可以選取![篩選圖示](assets/Smock_Filter_18_N.svg)篩選來篩選選取的物件清單，並在[!UICONTROL 篩選欄位中指定]對話方塊。 您可以對每個篩選器使用![關閉圖示](assets/CrossSize75.svg)，輕鬆移除篩選器。 |
| 2 | **規則產生器** | 您可使用一或多個規則依序建置衍生欄位。 規則是函式的特定實作，因此一律只與一個函式相關聯。 將函式拖放至規則產生器，即可建立規則。 函式型別會決定規則的介面。<br/>如需詳細資訊，請參閱[規則介面](#rule-interface)。 <br/>您可以在規則產生器中已有可用的規則開始、結束或之間插入函式。 規則產生器中的最後一個規則會決定衍生欄位的最終輸出。 |
| 3 | **[!UICONTROL **&#x200B;欄位設定&#x200B;**]** | 您可以命名和描述衍生欄位，並檢查其欄位型別。 |
| 4 | **[!UICONTROL **&#x200B;最終輸出&#x200B;**]** | 此區域會根據過去30天的資料以及您在規則產生器中對衍生欄位所做的變更，顯示輸出值的即時更新預覽。 |

{style="table-layout:auto"}

## 欄位範本精靈 {#wizard}

第一次存取衍生欄位介面時，會顯示[!UICONTROL 以欄位範本開始]精靈。

1. 選取最能描述您嘗試建立的欄位型別的範本。
2. 選取&#x200B;**[!UICONTROL **&#x200B;選取&#x200B;**]**&#x200B;按鈕以繼續。

衍生欄位對話方塊會填入規則（和函式），對於您選取的欄位型別而言是必要或有用的。 如需可用範本的詳細資訊，請參閱[函式範本](#function-templates)。

## 規則介面 {#rules}

在規則產生器中定義規則時，您會使用規則介面。

![衍生欄位規則介面的熒幕擷圖](assets/rule-interface.png)

|  | 名稱 | 說明 |
|---------|----------|--------|
| A | **規則名稱** | 依預設，規則名稱為&#x200B;**規則X** （X代表序號）。 若要編輯規則的名稱，請選取其名稱，然後輸入新名稱，例如`Query Parameter`。 |
| B | **函式名稱** | 規則的選取函式名稱，例如[!UICONTROL URL PARSE]。 當函式是函式序列中的最後一個並決定最終輸出值時，函式名稱后面會有[!UICONTROL - FINAL OUTPUT]，例如[!UICONTROL URL PARSE - FINAL OUTPUT]。 <br/>若要顯示包含函式詳細資訊的快顯視窗，請選取![說明圖示](assets/Smock_HelpOutline_18_N.svg)。 |
| C | **規則描述** | 您可以選擇新增說明至規則。<br/>選取![更多圖示](assets/More.svg)，然後選取&#x200B;**[!UICONTROL **&#x200B;新增描述&#x200B;**]**&#x200B;以新增描述，或選取&#x200B;**[!UICONTROL **&#x200B;編輯描述&#x200B;**]**&#x200B;以編輯現有的描述。<br/>使用編輯器輸入說明。 您可以使用工具列來格式化文字（使用樣式選擇器、粗體、斜體、底線、右側、左側、置中、顏色、數字清單、專案符號清單），以及新增連結至外部資訊。 <br/>若要完成說明的編輯，請在編輯器外按一下。 |
| D | **功能區域** | 定義函式的邏輯。 介面取決於函式的型別。 [!UICONTROL 欄位]或[!UICONTROL 值]的下拉式清單會根據函式預期的輸入型別，顯示所有可用的欄位類別（規則、標準欄位、欄位）。 或者，您也可以將欄位從架構和標準欄位選擇器拖放至欄位或值。 當該拖曳欄位源自查閱資料集時，查閱函式會自動插入在您定義的函式之前。 <br/>如需每個支援函式的詳細資訊，請參閱[函式參考](#function-reference)。 |

{style="table-layout:auto"}

## 建立衍生欄位 {#create}

1. 選取現有的資料檢視或建立資料檢視。 如需詳細資訊，請參閱[資料檢視](../data-views.md)。

2. 選取資料檢視的&#x200B;**[!UICONTROL **&#x200B;元件&#x200B;**]**&#x200B;標籤。

3. 從左側邊欄選取&#x200B;**[!UICONTROL **&#x200B;建立衍生欄位&#x200B;**]**。

4. 若要定義衍生欄位，請使用[!UICONTROL 建立衍生欄位]介面。 請參閱[衍生欄位介面](#derived-field-interface)。

   若要儲存您的新衍生欄位，請選取&#x200B;**[!UICONTROL **&#x200B;儲存&#x200B;**]**。

5. 您的新衍生欄位已新增到[!UICONTROL 衍生欄位>]容器，做為資料檢視左側邊欄中&#x200B;**[!UICONTROL **&#x200B;結構描述欄位&#x200B;**]**&#x200B;的一部分。


## 編輯衍生欄位 {#edit}

1. 選取現有的資料檢視。 如需詳細資訊，請參閱[資料檢視](../data-views.md)。

2. 選取資料檢視的&#x200B;**[!UICONTROL **&#x200B;元件&#x200B;**]**&#x200B;標籤。

3. 選取左側[!UICONTROL 連線]窗格中的&#x200B;**[!UICONTROL **&#x200B;結構描述欄位&#x200B;**]**&#x200B;索引標籤。

4. 選取&#x200B;**[!UICONTROL **&#x200B;衍生欄位>**]**&#x200B;容器。

5. 將滑鼠停留在您要編輯的衍生欄位上，並選取![編輯圖示](assets/Smock_Edit_18_N.svg)。

6. 若要編輯衍生欄位，請使用[!UICONTROL 編輯衍生欄位]介面。 請參閱[衍生欄位介面](#derived-field-interface)。

   - 選取&#x200B;**[!UICONTROL **&#x200B;儲存&#x200B;**]**&#x200B;以儲存更新的衍生欄位。

   - 選取&#x200B;**[!UICONTROL **&#x200B;取消&#x200B;**]**&#x200B;以取消您對衍生欄位所做的任何變更。

   - 選取&#x200B;**[!UICONTROL **&#x200B;另存新檔&#x200B;**]**，將衍生欄位另存為新衍生欄位。 新的衍生欄位與新增了`(copy)`的原始已編輯衍生欄位同名。

或者，如果您已在資料檢視中使用衍生欄位做為維度或量度的元件：

1. 選取元件。 請注意，元件的名稱可能與衍生欄位不同。

1. 在「元件」面板中，選取「結構描述」欄位名稱底下衍生欄位旁的![編輯圖示](assets/Smock_Edit_18_N.svg)。

1. 若要編輯衍生欄位，請使用[!UICONTROL 編輯衍生欄位]介面。 請參閱[衍生欄位介面](#derived-field-interface)。

   - 選取&#x200B;**[!UICONTROL **&#x200B;儲存&#x200B;**]**&#x200B;以儲存更新的衍生欄位。

   - 選取&#x200B;**[!UICONTROL **&#x200B;取消&#x200B;**]**&#x200B;以取消您對衍生欄位所做的任何變更。

   - 選取&#x200B;**[!UICONTROL **&#x200B;另存新檔&#x200B;**]**，將衍生欄位另存為新衍生欄位。 新的衍生欄位與新增了`(copy)`的原始已編輯衍生欄位同名。



## 刪除衍生欄位 {#delete}

1. 選取現有的資料檢視。 如需詳細資訊，請參閱[資料檢視](../data-views.md)。

2. 選取資料檢視的&#x200B;**[!UICONTROL **&#x200B;元件&#x200B;**]**&#x200B;標籤。

3. 在[!UICONTROL 連線]窗格中選取&#x200B;**[!UICONTROL **&#x200B;結構描述欄位&#x200B;**]**&#x200B;索引標籤。

4. 選取&#x200B;**[!UICONTROL **&#x200B;衍生欄位>**]**&#x200B;容器。

5. 將滑鼠停留在您要刪除的衍生欄位上，並選取![編輯圖示](assets/Smock_Edit_18_N.svg)。

6. 在[!UICONTROL 編輯衍生欄位]介面中，選取&#x200B;**[!UICONTROL 刪除]**。

   [!UICONTROL 刪除元件]對話方塊會要求您確認刪除。 考慮任何外部參考，這些參考可能存在於資料檢視之外的衍生欄位。

   - 選取&#x200B;**[!UICONTROL **&#x200B;繼續&#x200B;**]**&#x200B;以刪除衍生欄位。

或者，如果您已在資料檢視中使用衍生欄位做為維度或量度的元件：

1. 選取元件。 請注意，元件的名稱可能與衍生欄位不同。

1. 在「元件」面板中，選取「結構描述」欄位名稱底下衍生欄位旁的![編輯圖示](assets/Smock_Edit_18_N.svg)。

1. 在[!UICONTROL 編輯衍生欄位]介面中，選取&#x200B;**[!UICONTROL 刪除]**。

   [!UICONTROL 刪除元件]對話方塊會要求您確認刪除。 考慮任何外部參考，這些參考可能存在於資料檢視之外的衍生欄位。

   - 選取&#x200B;**[!UICONTROL **&#x200B;繼續&#x200B;**]**&#x200B;以刪除衍生欄位。

>[!NOTE]
>
>衍生欄位在Customer Journey Analytics中的連線層級進行管理。 任何與該連線關聯的資料檢視中衍生欄位所做的任何變更，都會套用至所有這些關聯的資料檢視。



## 函數範本 {#templates}

若要快速建立特定使用案例的衍生欄位，可使用函式範本。 這些函式範本可從衍生欄位介面的選取器區域存取，或在[!UICONTROL 以欄位範本開始]精靈中第一次使用時顯示。


### 行銷管道 {#mchannel}

此函式範本使用規則集合來建立行銷管道。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![行銷管道範本規則產生器的熒幕擷圖](assets/function-template-marketing-channel-template.png)

+++

### 退回數 {#bounces}

此函式範本使用規則集合來識別網站跳出。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![彈回規則產生器的熒幕擷圖](assets/function-template-bounces.png)

+++

### 多維度合併 {#multi-dim}

此函式範本將兩個值合併為一個。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![多Dimension組合規則產生器的熒幕擷圖](assets/function-template-multi-dimension-combine.png)

+++

### 易記的資料集名稱 {#friendlyname}

此函式範本提供可讀的資料集名稱。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![易記資料集名稱規則產生器的熒幕擷圖](assets/function-template-friendly-dataset-name.png)

+++

### URL 中的頁面名稱 {#pagename}

此函式範本會建立簡單的頁面名稱。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![來自URL規則產生器的頁面名稱熒幕擷圖](assets/function-template-page-name-from-url.png)

+++

### 假期季節 {#holiday}

此函式範本將一年中的關鍵時間分類。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![假日季節規則產生器的熒幕擷圖](assets/function-template-holiday-season.png)

+++

### 每月目標 {#goals}

此函式範本設定自訂的每月目標。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![每月目標規則產生器的熒幕擷圖](assets/function-template-monthly-goals.png)

+++

### 取得分隔清單中的所有值 {#allvalues}

此函式範本將有限的清單轉換為陣列。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![在分隔清單規則產生器中取得所有值的熒幕擷圖](assets/function-template-get-all-values-in-delimited-list.png)

+++

### 取得分隔清單中的第一個值 {#firstvalue}

此函式範本取得分隔清單中的第一個值。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![在分隔清單規則產生器中取得第一個值的熒幕擷圖](assets/function-template-get-first-value-in-delimited-list.png)

+++

### 取得分隔清單中的最後一個值 {#lastvalue}

此函式範本取得分隔清單中的最後一個值。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![在分隔清單規則產生器中取得最後一個值的熒幕擷圖](assets/function-template-get-last-value-in-delimited-list.png)

+++

### 網域名稱 {#domain}

此函式範本使用規則運算式擷取網域名稱。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![網域名稱規則產生器的熒幕擷圖](assets/function-template-domain-name.png)

+++

### 取得查詢字串參數 {#querystring}

此函式範本會擷取查詢字串值。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![取得查詢字串引數規則產生器的熒幕擷圖](assets/function-template-get-query-string-parameter.png)

+++

### 轉變欄位 {#transition}

此函式範本將報告從一個欄位轉移到另一個欄位。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![轉換欄位規則產生器的熒幕擷圖](assets/function-template-transition-field.png)

+++

### 簡單的機器人偵測 {#botdetection}

此函式範本實作簡易機器人識別。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![簡易機器人偵測規則產生器的熒幕擷圖](assets/function-template-simple-bot-detection.png)

+++

### 退出連結 {#exit}

此函式範本會識別工作階段中最後一個點按的連結。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![退出連結規則產生器的熒幕擷圖](assets/function-template-exit-link.png)

+++

### 下載連結 {#download}

此函式範本會標籤常見的下載連結。

+++ 詳細資料

若要使用範本，您必須為列示為範本規則一部分的每個函式指定正確的引數。 如需詳細資訊，請參閱[函式參考](#function-reference)。

![下載連結規則產生器的熒幕擷圖](assets/function-template-download-link.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## 函式參考 {#functionref}

{{select-package}}

如需各個支援功能的詳細資訊，請參閱以下內容：

- 規格：
   - 輸入資料型別：支援的資料型別，
   - 輸入：可能的輸入值，
   - 包含的運運算元：此函式支援的運運算元（如果有的話）、
   - 限制：適用於此特定函式的限制，
   - 輸出。

- 使用案例，包括：
   - 定義衍生欄位之前的資料，
   - 如何定義衍生欄位，
   - 定義衍生欄位後的資料。

- 限制（如果適用）。


<!-- CASE WHEN -->

### 情況 {#casewhen}

根據一或多個欄位的定義條件套用條件。 然後，系統會根據條件的順序，使用這些條件來定義新衍生欄位中的值。

+++ 詳細資料

## 規格 {#casewhen-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL If]， [!UICONTROL Else If]容器：</p><ul><li>[!UICONTROL 值]</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul><li>[!UICONTROL 條件] （根據選取的值型別，檢視包含的運運算元）</li></ul></li><li>[!UICONTROL 然後將值設為]，[!UICONTROL 否則將值設為]：</p><ul><li>[!UICONTROL 值]</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></ul></li></ul> | <p>字串</p><ul><li>等於</li><li>等於任何字詞</li><li>包含片語</li><li>包含任何字詞</li><li>包含所有字詞</li><li>開始於</li><li>以任何字詞開始</li><li>終止於</li><li>以任何字詞結尾</li><li>不等於</li><li>不等於任何字詞</li><li>不包含此片語</li><li>不包含任何字詞</li><li>不包含所有字詞</li><li>不開始於</li><li>開頭不是任何詞語</li><li>不終止於</li><li>結尾不是任何詞語</li><li>已設定</li><li>未設定</li></ul><p>數值</p><ul><li>等於</li><li>不等於</li><li>大於</li><li>大於或等於</li><li>小於</li><li>小於或等於</li><li>已設定</li><li>未設定</li></ul><p>日期</p><ul><li>等於</li><li>不等於</li><li>晚於</li><li>晚於或等於</li><li>早於</li><li>早於或等於</li><li>已設定</li><li>未設定</li></ul> | <ul><li>每個衍生欄位5個函式</li><li>每個衍生欄位有200個[運運算元](#operators)。 「反向連結網域包含Google」是單一運運算元的範例。 </li></ul> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例1 {#casewhen-uc1}

若要定義規則以識別各種行銷管道，請套用階層式邏輯以將行銷管道欄位設定為適當的值：

- 如果反向連結來自搜尋引擎，且頁面具有查詢字串值，其中`cid`包含`ps_`，則行銷管道應識別為&#x200B;[!DNL *付費搜尋*]。
- 如果反向連結來自搜尋引擎，而頁面沒有查詢字串`cid`，則行銷管道應識別為&#x200B;[!DNL *免費搜尋*]。
- 如果頁面有`cid`包含`em_`的查詢字串值，則行銷管道應識別為&#x200B;[!DNL *電子郵件*]。
- 如果頁面有`cid`包含`ds_`的查詢字串值，則行銷管道應識別為&#x200B;[!DNL *顯示廣告*]。
- 如果頁面有`cid`包含`so_`的查詢字串值，則行銷管道應識別為&#x200B;[!DNL *付費社交*]。
- 如果反向連結來自[!DNL twitter.com]、[!DNL facebook.com]、[!DNL linkedin.com]或[!DNL tiktok.com]的反向連結網域，則行銷管道應識別為&#x200B;[!DNL *自然社交*]。
- 如果上述規則都不相符，則行銷管道應識別為&#x200B;[!DNL *其他反向連結*]。

如果您的網站收到下列範例事件（包含[!UICONTROL 反向連結]和[!UICONTROL 頁面URL]），這些事件的識別方式如下：

| [!DNL Event] | [!DNL Referrer] | [!DNL Page URL] | [!DNL Marketing Channel] |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | [!DNL Natural Social] |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | [!DNL Display] |
| 3 | | `https://site.com/?cid=em_12345678` | [!DNL Email] |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | [!DNL Paid Search] |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | [!DNL Email] |
| 6 | `https://google.com` |  | [!DNL Natural Search] |

{style="table-layout:auto"}

### 在此之前的資料 {#casewhen-uc1-databefore}

| [!DNL Referrer] | [!DNL Page URL] |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` | |

{style="table-layout:auto"}

### 衍生欄位 {#casewhen-uc1-derivedfield}

您定義`Marketing Channel`衍生欄位。 您使用[!UICONTROL CASE WHEN]函式來定義規則，這些規則會根據`Page URL`和`Referring URL`欄位的現有值為建立值。

請注意，在套用[!UICONTROL CASE WHEN]規則之前，使用函式[!UICONTROL URL PARSE]來定義規則以擷取`Page Url`和`Referring Url`的值。

規則1](assets/case-when-1.png)時的![案例熒幕擷圖

### 之後的資料 {#casewhen-uc1-dataafter}

| [!DNL Marketing Channel] |
|----|
| [!DNL Natural Social] |
| [!DNL Display] |
| [!DNL Email] |
| [!DNL Paid Search] |
| [!DNL Email] |
| [!DNL Natural Search] |

{style="table-layout:auto"}


## 使用案例2 {#casewhen-uc2}

您已在您的[!DNL Product Finding Methods]維度中收集數個不同的搜尋變體。 若要瞭解搜尋與瀏覽的整體效能，您必須花大量時間手動結合結果。

您的網站會收集您[!DNL Product Finding Methods]維度的下列值。 最後，所有這些值都表示搜尋。

| 收集的值 | 實際值 |
|---|---|
| [!DNL search p13n_no] | [!DNL search] |
| [!DNL search p13n_yes] | [!DNL search] |
| [!DNL search refine p13n_no] | [!DNL search] |
| [!DNL search refine p13n_yes] | [!DNL search] |
| [!DNL search redirect p13n_yes] | [!DNL search] |
| [!DNL search-redirect] | [!DNL search] |

{style="table-layout:auto"}


### 在此之前的資料 {#casewhen-uc2-databefore}

| [!DNL Product Finding Methods] |
|----|
| [!DNL search p13_no] |
| [!DNL search p13_yes] |
| [!DNL browse] |
| [!DNL search refine p13_no] |
| [!DNL search refine p13_yes] |
| [!DNL browse] |
| [!DNL search redirect p13_yes] |
| [!DNL search-redirect] |
| [!DNL browse] |

{style="table-layout:auto"}

### 衍生欄位 {#casewhen-uc2-derivedfield}

您定義`Product Finding Methods (new)`衍生欄位。 您在規則產生器中建立下列[!UICONTROL CASE WHEN]規則。 這些規則會使用[!UICONTROL 包含片語]條件，將邏輯套用至`search`和`browse`的舊[!UICONTROL 產品尋找方法]欄位值的所有可能變化。

![規則2](assets/case-when-2.png)時案例的熒幕擷圖

### 之後的資料 {#casewhen-uc2-dataafter}

| [!DNL Product Finding Methods (new)] |
|----|
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |
| [!DNL search] |
| [!DNL search] |
| [!DNL browse] |

{style="table-layout:auto"}


## 使用案例3 {#casewhen-uc3}

作為旅行公司，您想要針對預訂的旅行報告分段旅行期間，以便報告分段旅行長度。

假設：

- 組織正在將運送航程期間收集到數值欄位中。
- 他們想要將1-3天的期間儲存在名為&#39;[!DNL short trip]&#39;的貯體中
- 他們想要將4-7天期間儲存至名為&#39;[!DNL medium trip]&#39;的貯體
- 他們想要將8天以上的期間儲存至名為&#39;[!DNL long trip]&#39;的貯體
- 1天期間預訂了132次行程
- 已預訂110次旅行，為期2天
- 已預訂105次行程，為期3天
- 已預訂99次行程，為期4天
- 已預訂92次行程，為期5天
- 已預訂85次行程，為期6天
- 已預訂82次行程，為期7天
- 已預訂78次行程，為期8天
- 已預訂50次行程，為期9天
- 預訂了44次行程，為期10天
- 預訂了38次行程，為期11天
- 預訂了31次旅行，為期12天

您需要的報表應如下所示：

| [!DNL Trip Duration Type] | [!DNL Bookings] |
|----|---:|
| [!DNL medium trip] | 358 |
| [!DNL short trip] | 347 |
| [!DNL long trip] | 241 |

{style="table-layout:auto"}

### 在此之前的資料 {#casewhen-uc3-databefore}

| [!DNL Trip Duration] |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### 衍生欄位 {#casewhen-uc3-derivedfield}

您定義`Trip Duration (bucketed)`衍生欄位。 您在規則產生器中建立下列[!UICONTROL CASE WHEN]規則。 此規則套用邏輯至將舊的[!UICONTROL 行程持續時間]欄位值儲存為三個值： `short trip`、`medium  trip`和`long trip`。

規則3](assets/case-when-3.png)時的![案例熒幕擷圖


### 之後的資料 {#casewhen-uc3-dataafter}

| [!DNL Trip Duration (bucketed)] |
|---|
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL short trip] |
| [!DNL medium trip] |
| [!DNL medium trip] |
| [!DNL long trip] |
| [!DNL medium trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL short trip] |
| [!DNL long trip] |
| [!DNL long trip] |


## 詳細資訊 {#casewhen-more-info}

Customer Journey Analytics使用巢狀容器結構，仿照Adobe Experience Platform的[XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) (Experience Data Model)建模。 如需詳細背景資訊，請參閱[容器](../create-dataview.md#containers)和[篩選容器](../../components/filters/filters-overview.md#filter-containers)。 此容器模型雖然本身有彈性，但在使用規則產生器時施加了一些限制。

Customer Journey Analytics會使用以下預設容器模型：

<p align="center">
<img src="./assets/containers.png" width="50%" valign="middle">
</p>

下列限制套用，並在&#x200B;*選取*&#x200B;和&#x200B;*設定*&#x200B;值時強制執行。

|  | 限制 |
|:---:|----|
| **A** | 您&#x200B;*選取相同[!UICONTROL If]、[!UICONTROL Else If]建構（使用[!UICONTROL And]或[!UICONTROL Or]）的值必須源自相同的容器，而且可以是任何型別（字串![String](assets/Smock_ABC_18_N.svg)、數值![Numeric](assets/Smock_123_18_N.svg)等等）。*&#x200B;相依性A](assets/dependency-a.png)的<br/>![熒幕擷圖 |
| **B** | 您&#x200B;*在規則中設定*&#x200B;的所有值都必須來自相同的容器，且必須具有相同的型別或相同型別的衍生值。<br/> 相依性B](assets/dependency-b.png)的![熒幕擷圖 |
| **C** | 您&#x200B;*在[!UICONTROL If]，[!UICONTROL Else If]規則中的建構值*&#x200B;不&#x200B;*必須源自相同的容器，而且*&#x200B;不&#x200B;*必須是相同的型別。<br/>* 相依性C](assets/dependency-c.png)的![熒幕擷圖 |

{style="table-layout:auto"}

+++

<!-- CLASSIFY -->

### 分類 {#classify}

定義一組值，在新衍生欄位中以對應值取代。

+++ 詳細資料

## 規格 {#classify-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 要分類的欄位]：<ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></li><li>[!UICONTROL 當值等於]且[!UICONTROL 將值取代為]時：</p><ul><li>字串</li></ul><li>顯示原始值<ul><li>布林值</li></ul></li></ul> | <p>不適用</p> | <ul><li>每個衍生欄位5個函式</li><li>每個衍生欄位有200個[運運算元](#operators)。 [!UICONTROL 當值等於原始值]時[!UICONTROL 將值取代為新值]的每個專案都視為作業。</li></ul> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例1 {#classify-uc1}

CSV檔案確實包含`hotelID`的索引鍵資料行，以及與`hotelID`關聯的一或多個其他資料行： `city`、`rooms`、`hotel name`。
您正在收集維度中的[!DNL Hotel ID]，但想要建立衍生自CSV檔案中`hotelID`的[!DNL Hotel Name]維度。

**CSV檔案結構和內容**

| [!DNL hotelID] | [!DNL city] | [!DNL rooms] | [!DNL hotel name] |
|---|---|---:|---|
| [!DNL SLC123] | [!DNL Salt Lake City] | 40 | [!DNL SLC Downtown] |
| [!DNL LAX342] | [!DNL Los Angeles] | 60 | [!DNL LA Airport] |
| [!DNL SFO456] | [!DNL San Francisco] | 75 | [!DNL Market Street] |
| [!DNL AMS789] | [!DNL Amsterdam] | 50 | [!DNL Okura] |

{style="table-layout:auto"}

**目前的報告**

| [!DNL Hotel ID] | 產品檢視 |
|---|---:|
| [!DNL SLC123] | 200 |
| [!DNL LX342] | 198 |
| [!DNL SFO456] | 190 |
| [!DNL AMS789] | 150 |

{style="table-layout:auto"}


**所要的報告**

| [!DNL Hotel Name] | 產品檢視 |
|----|----:|
| [!DNL SLC Downtown] | 200 |
| [!DNL LA Airport] | 198 |
| [!DNL Market Street] | 190 |

{style="table-layout:auto"}

### 在此之前的資料 {#classify-uc1-databefore}

| [!DNL Hotel ID] |
|----|
| [!DNL SLC123] |
| [!DNL LAX342] |
| [!DNL SFO456] |
| [!DNL AMS789] |

{style="table-layout:auto"}


### 衍生欄位 {#classify-uc1-derivedfield}

您定義`Hotel Name`衍生欄位。 您使用[!UICONTROL CLASSIFY]函式來定義規則，您可以在其中分類[!UICONTROL 飯店ID]欄位的值，並以新值取代。

如果您想要包含尚未定義成要分類之值的一部分的原始值（例如飯店ID AMS789），請務必選取&#x200B;**[!UICONTROL 顯示原始值]**。 這可確保AMS789是衍生欄位輸出的一部分，儘管該值未分類。

![分類規則1](assets/classify-1.png)的熒幕擷圖

### 之後的資料 {#classify-uc1-dataafter}

| [!DNL Hotel Name] |
|----|
| [!DNL SLC Downtown] |
| [!DNL LA Airport] |
| [!DNL Market Street] |

{style="table-layout:auto"}


## 使用案例2 {#classify-uc2}

您已收集好幾個頁面的URL，而不是好記的頁面名稱。 這個混合值集合會中斷報表。

### 在此之前的資料 {#classify-uc2-databefore}

| [!DNL Page Name] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| [!DNL Deals & Offers] |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### 衍生欄位 {#classify-uc2-derivedfield}

您定義`Page Name (updated)`衍生欄位。 您使用[!UICONTROL CLASSIFY]函式來定義規則，您可以在其中將現有[!UICONTROL 頁面名稱]欄位的值分類，並以更新的正確值取代。

![分類規則2](assets/classify-2.png)的熒幕擷圖

### 之後的資料 {#classify-uc2-dataafter}

| [!DNL Page Name (updated)] |
|---|
| [!DNL Home Page] |
| [!DNL Flight Search] |
| [!DNL Hotel Search] |
| [!DNL Package Search] |
| [!DNL Deals & Offers] |
| [!DNL Reviews] |
| [!DNL Generate Quote] |


## 詳細資訊 {#classify-moreinfo}

「分類」規則介面中提供下列額外功能：

- 若要快速清除所有表格值，請選取![清除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Erase_18_N.svg) **[!UICONTROL 清除所有表格值]**。
- 若要上傳包含「當值等於時」的原始值和取代值的新值的CSV檔案，請選取![CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL 上傳CSV]**。
- 若要下載範本，以建立具有原始值和新值的CSV檔案來上傳，請選取![下載](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL 下載CSV範本]**。
- 若要下載CSV檔案，並在規則介面中填入所有原始值和新值，請選取![下載](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Download_18_N.svg) **[!UICONTROL 下載CSV值]**。


+++

<!-- CONCATENATE -->

### 串連 {#concatenate}

將欄位值結合至具有已定義分隔字元的單一新衍生欄位。

+++ 詳細資料

## 規格 {#concatenate-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li></ul> | <ul><li>[!UICONTROL 值]：<ul><li>規則</li><li>標準欄位</li><li>欄位</li><li>字串</li></ul></li><li>[!UICONTROL 分隔符號]：<ul><li>字串</li></ul></li> </ul> | <p>不適用</p> | <p>每個衍生欄位2個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例 {#concatenate-uc}

您目前正在以個別欄位收集來源和目的地機場代碼。 您想要取用這兩個欄位，並將它們合併成以連字型大小(-)分隔的單一維度。 因此，您可以分析來源與目的地的組合，以識別預訂的最上層路由。

假設：

- 來源和目的地值會收集在相同表格中的個別欄位中。
- 使用者決定在值之間使用分隔字元&#39;-&#39;。

想像會發生下列預約：

- 客戶ABC123預訂鹽湖城(SLC)和奧蘭多(MCO)之間的航班
- 客戶ABC456預訂鹽湖城(SLC)和洛杉磯(LAX)之間的航班
- 客戶ABC789預訂鹽湖城(SLC)和西雅圖(SEA)之間的航班
- 客戶ABC987預訂鹽湖城(SLC)和聖荷西(SJO)之間的航班
- 客戶ABC654預訂鹽湖城(SLC)和奧蘭多(MCO)之間的航班

所需的報表應如下所示：

| 來源/目的地 | Bookings |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### 在此之前的資料 {#concatenate-uc-databefore}

| 來源 | 目標 |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### 衍生欄位 {#concatenate-derivedfield}

您定義`Origin - Destination`衍生欄位。 您使用[!UICONTROL CONCATENATE]函式定義規則，以使用`-` [!UICONTROL 分隔符號]串連[!UICONTROL Original]和[!UICONTROL Destination]欄位。

![串連規則的熒幕擷圖](assets/concatenate.png)

### 之後的資料 {#concatenate-dataafter}

| 來源 — 目的地<br/>（衍生欄位） |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++


### 重複資料刪除 {#dedup}

避免多次計算值。

+++ 詳細資料


## 規格 {#deduplicate-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li></ul> | <ul><li>[!UICONTROL 值]：<ul><li>規則</li><li>標準欄位</li><li>欄位</li><li>字串</li></ul></li><li>[!UICONTROL 領域]：<ul><li>「人」</li><li>工作階段</li></ul></li><li>[!UICONTROL 重複資料刪除ID]：<ul><li>規則</li><li>標準欄位</li><li>欄位</li><li>字串</li></ul><li>[!UICONTROL 要保留的值]：<ul><li>保留第一個執行個體</li><li>保留最後一個執行個體</li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位5個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例1 {#deduplicate-uc1}

您想要防止在使用者重新載入預訂確認頁面時計算重複收入。 在相同事件上收到收入時，您可以在識別碼處使用預訂確認ID來避免再次計算收入。

### 在此之前的資料 {#deduplicate-uc1-databefore}

| 預訂確認ID | 收入 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 359 |
| ABC123456789 | 359 |

{style="table-layout:auto"}

### 衍生欄位 {#deduplicate-uc1-derivedfield}

您定義`Booking Confirmation`衍生欄位。 您使用[!UICONTROL DEDUPLICATE]函式定義規則，以使用[!UICONTROL 重複資料刪除ID] [!UICONTROL 預約確認ID]為[!UICONTROL 範圍] [!DNL Person]重複資料刪除[!UICONTROL 值] [!DNL Booking]。 您選取[!UICONTROL 保留第一個執行個體]作為[!UICONTROL 要保留的值]。

![串連規則的熒幕擷圖](assets/deduplicate-1.png)

### 之後的資料 {#deduplicate-uc1-dataafter}

| 預訂確認ID | 收入 |
|----|---:|
| ABC123456789 | 359 |
| ABC123456789 | 0 |
| ABC123456789 | 0 |

{style="table-layout:auto"}

## 使用案例2 {#deduplicate-uc2}

您可以使用事件作為搭配外部行銷活動的促銷活動點進代理。 重新載入和重新導向會造成事件量度膨脹。 您想要刪除追蹤程式碼維度的重複專案，以便只收集第一個專案，並將事件過度計數最小化。

### 在此之前的資料 {#deduplicate-uc2-databefore}

| 訪客 ID | 行銷管道 | 活動 |
|----|---|---:|
| ABC123 | 付費搜尋 | 1 |
| ABC123 | 付費搜尋 | 1 |
| ABC123 | 付費搜尋 | 1 |
| DEF123 | 電子郵件 | 1 |
| DEF123 | 電子郵件 | 1 |
| JKL123 | 免費搜尋 | 1 |
| JKL123 | 免費搜尋 | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#deduplicate-uc2-derivedfield}

您定義新的`Tracking Code (deduplicated)`衍生欄位。 您使用[!UICONTROL DEDUPLICATE]函式來定義規則，以重複刪除具有[!UICONTROL 工作階段]的[!UICONTROL 重複刪除範圍]和[!UICONTROL 保留第一個執行個體]的[!UICONTROL 追蹤代碼]，作為[!UICONTROL 要保留的值]。

![串連規則的熒幕擷圖](assets/deduplicate-2.png)

### 之後的資料 {#deduplicate-uc2-dataafter}

| 訪客 ID | 行銷管道 | 活動 |
|----|---|---:|
| ABC123 | 付費搜尋 | 1 |
| DEF123 | 電子郵件 | 1 |
| JKL123 | 免費搜尋 | 1 |

{style="table-layout:auto"}

+++


<!-- FIND AND REPLACE -->

### 尋找並取代 {#find-replace}

尋找所選欄位中的所有值，並在新的衍生欄位中以不同的值取代這些值。

+++ 詳細資料

## 規格 {#findreplace-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li></ul> | <ul><li>[!UICONTROL 值]<ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></li><li>[!UICONTROL 尋找全部]、[!UICONTROL 並以]取代全部：<ul><li>字串</li></ul></li></ul></ul> | <p>字串</p><ul><li>[!UICONTROL 尋找全部]、[!UICONTROL 並以]取代全部</li></ul> | <p>每個衍生欄位5個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例 {#findreplace-uc}

您收到一些外部行銷管道報表的格式錯誤值，例如`email%20 marketing`而非`email marketing`。 這些格式錯誤的值會割裂您的報表，並使您更難以檢視電子郵件的執行情形。 您想要將`email%20marketing`取代為`email marketing`。

**原始報告**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 500 |
| [!DNL email %20marketing] | 24 |

{style="table-layout:auto"}

**偏好的報告**

| [!DNL External Marketing Channels] | [!DNL Sessions] |
|---|--:|
| [!DNL email marketing] | 524 |


### 在此之前的資料 {#findreplace-uc-databefore}

| [!DNL External Marketing] |
|----|
| [!DNL email marketing] |
| [!DNL email%20marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email%20marketing] |

{style="table-layout:auto"}

### 衍生欄位 {#findreplace-uc-derivedfield}

您定義`Email Marketing (updated)`衍生欄位。 您使用[!UICONTROL FIND AND REPLACE]函式定義規則，尋找並以`email marketing`取代`email%20marketing`的所有具體值。

![尋找與取代規則的熒幕擷圖](assets/find-and-replace.png)

### 之後的資料 {#findreplace-uc-dataafter}

| [!DNL External Marketing (updated)] |
|----|
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |
| [!DNL email marketing] |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### 查詢 {#lookup}

使用查詢資料集中的欄位來查詢值，並在新的衍生欄位中傳回值或用於進一步的規則處理。

+++ 詳細資料

## 規格 {#lookup-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 要套用查閱的欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul><li>[!UICONTROL 查詢資料集]</li><ul><li>資料集</li></ul><li>[!UICONTROL 比對索引鍵]<ul><li>規則</li><li>欄位</li></ul></li><li>要傳回的值<ul><li>規則</li><li>欄位</li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位3個函式</p> | <p>下一個規則中用於進一步處理的新衍生欄位或值</p> |

{style="table-layout:auto"}

## 使用案例 {#lookup-uc}

您想要使用客戶點按透過Adobe Target顯示的個人化橫幅時收集的活動ID來查詢活動名稱。 想要搭配Analytics for Target (A4T)活動（包含活動ID和活動名稱）使用查詢資料集。

### A4T查詢資料集 {#lookup-uc-lookup}

| 活動ID | 活動名稱 |
|---|---|
| 415851 | MVT測試類別頁面 |
| 415852 | Luma - Campaign Max 2022 |
| 402922 | 首頁橫幅 |

{style="table-layout:auto"}

### 衍生欄位 {#lookup-uc-derivedfield}

您定義`Activity Name`衍生欄位。 您使用[!UICONTROL LOOKUP]函式定義規則，以從您收集的資料（在[!UICONTROL 要套用查詢的欄位]欄位中指定）中查詢值（例如&#x200B;**[!DNL ActivityIdentifier]**）。 您從[!UICONTROL 查詢資料集]清單中選取查詢資料集（例如&#x200B;**[!DNL New CJA4T Activities]**）。 然後您從[!UICONTROL 比對索引鍵]清單中選取識別碼欄位（例如&#x200B;**[!DNL ActivityIdentifier]**），並從[!UICONTROL 要傳回]的值清單中選取要傳回的欄位（例如&#x200B;**[!DNL ActivityName]**）。

![小寫規則的熒幕擷圖](assets/lookup.png)

## 詳細資訊 {#lookup-more-info}

查詢函式會在報表時間套用至Customer Journey Analytics從您設定為連線一部分的查詢資料集中擷取的資料。

您可以在規則產生器中快速插入[!UICONTROL 查詢]函式，該函式已包含一或多個其他函式。

1. 從選取器中選取&#x200B;**[!UICONTROL 結構描述欄位]**。
1. 選取![結構描述欄點陣圖示](assets/Smock_Folder_18_N.svg) **[!UICONTROL 查詢資料集]**。
1. 選取您的查詢資料集，並尋找您要用於查詢的欄位。
1. 將查詢欄位拖放至函式的任何可用輸入欄位上（例如Case When）。 有效時，藍色方塊（標示為&#x200B;**[!UICONTROL + Add]**）可讓您放置欄位，並在您放置查閱欄位的函式之前自動插入Lookup函式。 插入的Lookup函式會自動填入所有欄位的相關值。
   ![查詢拖曳](assets/lookup-drag.png)

+++


<!-- LOWERCASE -->

### 小寫 {#lowercase}

將欄位中的值轉換為小寫，並將其儲存到新的衍生欄位中。

+++ 詳細資料

## 規格 {#lowercase-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul> | <p>不適用</p> | <p>每個衍生欄位2個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例 {#lowercase-uc}

您想要將所有收集的產品名稱轉換為小寫，以便正確製作報表。

### 在此之前的資料 {#lowercase-uc-databefore}

| 收集的產品名稱 | 產品檢視 |
|---|---:|
| 網球拍 | 35 |
| 網球拍 | 33 |
| 網球拍 | 21 |
| 棒球棒 | 15 |
| 棒球棒 | 12 |
| 棒球棒 | 10 |

{style="table-layout:auto"}

### 衍生欄位 {#lowercase-uc-derivedfield}

您定義`Product Names`衍生欄位。 您使用[!UICONTROL LOWERCASE]函式定義規則，將[!UICONTROL 收集的產品名稱]欄位的值轉換為小寫，並儲存在新的衍生欄位中。

![小寫規則的熒幕擷圖](assets/lowercase.png)


### 之後的資料 {#lowercase-uc-dataafter}

| 產品名稱 | 產品檢視 |
|---|---|
| 網球拍 | 89 |
| 棒球棒 | 37 |

{style="table-layout:auto"}

+++

<!-- MATH -->

### Math {#math}

在數值欄位上使用基本的數學運運算元（加、減、乘、除與加冪）。

+++ 詳細資料

## 規格 {#math-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>數值</li></ul> | <ul><li>一或多個數值欄位</li><li>一或多個運運算元（加、減、乘、除、升冪）</li><li>使用者輸入值</li></ul> | <ul><li>`+` （新增）</li><li>`-` （減）</li><li>`*` （乘）</li><li>`/` （除）</li><li>`^` （提升至電源）</li></ul> | <ul><li>每個衍生欄位25個作業</li><li>每個衍生欄位5個數學函式</li></ul> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例 {#math-uc}

由於膨脹，您想要以5%的膨脹率來更正已擷取的CRM資料的收入數。

### 在此之前的資料 {#math-uc-databefore}

| CRM ID | 年收入 |
|---|---:|
| 1234 | 35,070,000 |
| 4133 | 7,500,000 |
| 8110 | 10,980 |
| 2201 | 42,620 |

{style="table-layout:auto"}

### 衍生欄位 {#math-uc-derivedfield}

您定義`Corrected Annual Revenue`衍生欄位。 您使用[!UICONTROL MATH]函式來定義將原始年度收入數字乘以1.05的規則。

![數學規則的熒幕擷圖](assets/math.png)


### 之後的資料 {#math-uc-dataafter}

| CRM ID | 更正的年度收入 |
|---|---:|
| 1234 | 36,823,500 |
| 4133 | 7,875,000 |
| 8110 | 11,529,00 |
| 2201 | 44,751 |

{style="table-layout:auto"}

## 詳細資訊 {#math-more-info}

若要建立公式：

1. 只要開始輸入公式欄位和符合您輸入內容的數值欄位，就會出現在快顯功能表中。 或者，您可以從左窗格的可用欄位中拖放數值欄位。
   ![數學更多資訊1](assets/math-more-info-1.png)

1. 新增運算元（例如`*`要相乘），然後加上另一個欄位或靜態值。 您可以使用括弧來定義更複雜的公式。

1. 若要插入靜態值（例如`1.05`），請輸入值並從快顯功能表選取&#x200B;**[!UICONTROL 將&#x200B;*x*新增為靜態值]**&#x200B;或將&#x200B;**[!UICONTROL 新增 — *x*為負靜態值]**。
   ![數學更多資訊2](assets/math-more-info-2.png)

1. 綠色核取記號![核取記號](./assets/checkmark.svg)</span>表示您的數學公式是否有效，否則您將會看到警告![警示](./assets/alert.svg)和訊息[!UICONTROL 公式運算式無效]。
   ![數學更多資訊3](assets/math-more-info-3.png)

在[!UICONTROL MATH]函式中使用靜態數字時，有一些重要的考量：

- 靜態值需與欄位相關聯。 例如，不支援只搭配靜態欄位使用[!UICONTROL MATH]函式。
- 您無法在靜態值上使用raise to power運運算元(`ˆ`)。
- 如果您在公式中使用多個靜態值，這些靜態值應該使用括弧分組，公式才有效。 例如：

   - 此公式傳回錯誤。
     ![數學更多資訊4](assets/math-more-info-4.png)

   - 此公式有效。
     ![數學更多資訊5](assets/math-more-info-5.png)

使用Math函式進行點選層級的計算。 針對以事件、工作階段或人員範圍為基礎的計算，使用[Summarize](#summarize)函式。

+++


<!-- MERGE FIELDS -->

### 合併欄位 {#merge}

將兩個不同欄位的值合併到新的衍生欄位。

+++ 詳細資料

## 規格 {#merge-fields-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul> | <p>不適用</p> | <p>每個衍生欄位5個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例 {#merge-fields-uc}

您想要建立由頁面名稱欄位和來電原因欄位組成的維度，其目的在於跨管道分析歷程。

### 在此之前的資料 {#merge-fields-uc-databefore}

| 頁面名稱 | 工作階段 | 訪客 |
|---|--:|--:|
| 說明頁面 | 250 | 200 |
| 首頁 | 500 | 250 |
| 產品詳細資料頁面 | 300 | 200 |

{style="table-layout:auto"}

| 來電原因 | 工作階段 | 訪客 |
|---|--:|--:|
| 關於我訂單的問題 | 275 | 250 |
| 變更我的訂單 | 150 | 145 |
| 訂購時發生問題 | 100 | 95 |

{style="table-layout:auto"}

### 衍生欄位 {#merge-fields-uc-derivedfield}

您定義`Cross Channel Interactions`衍生欄位。 您使用[!UICONTROL MERGE FIELDS]函式定義規則，以合併[!UICONTROL 頁面名稱]欄位和[!UICONTROL 來電原因]欄位的值，並將其儲存在新的衍生欄位中。

![合併欄位規則的熒幕擷圖](assets/merge-fields.png)

### 之後的資料 {#merge-fields-uc-dataafter}

| 跨頻道互動 | 工作階段 | 訪客 |
|---|--:|--:|
| 首頁 | 500 | 250 |
| 產品詳細資料頁面 | 300 | 200 |
| 關於我訂單的問題 | 275 | 250 |
| 說明頁面 | 250 | 200 |
| 變更我的訂單 | 150 | 145 |
| 訂購時發生問題 | 100 | 95 |

{style="table-layout:auto"}

## 詳細資訊 {#merge-fields-moreinfo}

您必須在「合併欄位」規則中選取相同型別的欄位。 例如，如果您選取「日期」欄位，則您要合併的所有其他欄位都必須是「日期」欄位。

![合併欄位上限制的熒幕擷圖](assets/merge-fields-constraint.png)

+++


<!-- NEXT OR PREVIOUS -->

### 下一個或上一個 {#next-previous}

以欄位作為輸入，並解析工作階段或使用範圍內該欄位的下一個或上一個值。 這僅適用於「造訪」和「事件」表格欄位。

+++ 詳細資料

## 規格 {#prevornext-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul><li>[!UICONTROL 方法]：<ul><li>上一個值</li><li>下一個值</li></ul></li><li>[!UICONTROL 領域]：<ul><li>「人」</li><li>工作階段</li></ul></li><li>[!UICONTROL 索引]：<ul><li>數值</li></ul><li>[!UICONTROL 包含重複專案]：<ul><li>布林值</li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位3個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例 {#prevornext-uc1}

您想要瞭解&#x200B;**next**&#x200B;或&#x200B;**previous**&#x200B;值是您收到的資料，並考慮到重複值。

### 資料 {#prevornext-uc1-databefore}

**範例1 — 處理包含重複**

| 已接收資料 | 下一個值<br/>工作階段<br/>索引= 1<br/>包含重複專案 | 下一個值<br/>工作階段<br/>索引= 1<br/>不包含重複專案 | 先前的值<br/>工作階段<br/>索引= 1<br/>包含重複專案 | 先前的值<br/>工作階段<br/>索引= 1<br/>不包含重複專案 |
|---|---|---|---|---|
| 首頁 | 首頁 | 搜尋 | *沒有值* | *沒有值* |
| 首頁 | 搜尋 | 搜尋 | 首頁 | *沒有值* |
| 搜尋 | 搜尋 | 產品詳細資料 | 首頁 | 首頁 |
| 搜尋 | 產品詳細資料 | 產品詳細資料 | 搜尋 | 首頁 |
| 產品詳細資料 | 搜尋 | 搜尋 | 搜尋 | 搜尋 |
| 搜尋 | 產品詳細資料 | 產品詳細資料 | 產品詳細資料 | 產品詳細資料 |
| 產品詳細資料 | 搜尋 | 搜尋 | 搜尋 | 搜尋 |
| 搜尋 | 搜尋 | *沒有值* | 產品詳細資料 | 產品詳細資料 |
| 搜尋 | *沒有值* | *沒有值* | 搜尋 | 產品詳細資料 |

{style="table-layout:auto"}

**範例2 — 處理收到的資料中包含空白值的重複專案**

| 已接收資料 | 下一個值<br/>工作階段<br/>索引= 1<br/>包含重複專案 | 下一個值<br/>工作階段<br/>索引= 1<br/>不包含重複專案 | 先前的值<br/>工作階段<br/>索引= 1<br/>包含重複專案 | 先前的值<br/>工作階段<br/>索引= 1<br/>不包含重複專案 |
|---|---|---|---|---|
| 首頁 | 首頁 | 搜尋 | *沒有值* | *沒有值* |
| 首頁 | 首頁 | 搜尋 | 首頁 | *沒有值* |
| 首頁 | 搜尋 | 搜尋 | 首頁 | *沒有值* |
| 搜尋 | 搜尋 | 產品詳細資料 | 首頁 | 首頁 |
|   |   |   |   |   |
| 搜尋 | 搜尋 | 產品詳細資料 | 搜尋 | 首頁 |
| 搜尋 | 產品詳細資料 | 產品詳細資料 | 搜尋 | 首頁 |
| 產品詳細資料 | *沒有值* | *沒有值* | 搜尋 | 搜尋 |
|   |   |   |   |   |

{style="table-layout:auto"}

### 衍生欄位 {#prevnext-uc1-derivedfield}

您定義`Next Value`或`Previous value`衍生欄位。 您使用[!UICONTROL NEXT或PREVIOUS]函式來定義選取已接收[!UICONTROL 資料]欄位的規則，選取[!UICONTROL 下一個值]或[!UICONTROL 上一個值]做為[!UICONTROL 方法]，[!UICONTROL 工作階段]做為Scope，並將[!UICONTROL Index]的值設定為`1`。

![合併欄位規則的熒幕擷圖](assets/prevnext-next.png)

## 詳細資訊 {#prevnext-moreinfo}

您只能選取屬於「造訪」或「事件」表格的欄位。

[!UICONTROL 包含重複專案]決定如何處理[!UICONTROL NEXT或PREVIOUS]函式的重複值。

- 包含重複專案外觀和下一個或上一個值。 如果選取[!UICONTROL 包含重複專案]，它將忽略目前點選中下一個或上一個值的所有循序重複專案。

- 選取欄位中沒有（空白）值的列，將不會在[!UICONTROL NEXT或PREVIOUS]函式輸出中傳回下一個或上一個值。

+++

<!-- REGEX REPLACE -->

### 規則運算式取代 {#regex-replace}

使用規則運算式將欄位中的值取代為新的衍生欄位。

+++ 詳細資料

## 規格 {#regex-replace-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></ul><ul><li>[!UICONTROL 規則運算式]：</li><ul><li>字串</li></ul></li><li>[!UICONTROL 輸出格式]：<ul><li>字串</li></ul></ul><ul><li>區分大小寫</li><ul><li>布林值</li></ul></li></ul></li> | <p>不適用</p> | <p>每個衍生欄位1個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例 {#regex-replace-uc}

您想要擷取URL的一部分，並作為唯一頁面識別碼來分析流量。 您針對規則運算式使用`[^/]+(?=/$|$)`來擷取URL的結尾，並將`$1`作為輸出模式。

### 在此之前的資料 {#regex-replace-uc-databefore}

| 頁面 URL |
|---|
| `https://business.adobe.com/products/analytics/adobe-analytics-benefits.html` |
| `https://business.adobe.com/products/analytics/adobe-analytics.html` |
| `https://business.adobe.com/products/experience-platform/customer-journey-analytics.html` |
| `https://business.adobe.com/products/experience-platform/adobe-experience-platform.html` |

{style="table-layout:auto"}

### 衍生欄位 {#regex-replace-uc-derivedfield}

您建立`Page Identifier`衍生欄位。 您使用[!UICONTROL REGEX REPLACE]函式定義規則，以使用`[^/]+(?=/$|$)`的[!UICONTROL Regex]和`$1`的[!UICONTROL 輸出格式]來取代[!UICONTROL 反向連結URL]欄位的值。

![Regex Replac規則的熒幕擷圖](assets/regex-replace.png)


### 之後的資料 {#regex-replace-uc-dataafter}

| 頁面識別碼 |
|---|
| adobe-analytics-benefits.html |
| adobe-analytics.html |
| customer-journey-analytics.html |
| adobe-experience-platform.html |

## 詳細資訊 {#regex-replace-more-info}

Customer Journey Analytics使用Perl規則運算式語法的子集。 支援下列運算式：

| 運算式 | 說明 |
| --- | --- |
| `a` | 單一字元 `a`。 |
| `a\|b` | 單一字元 `a` 或 `b`。 |
| `[abc]` | 單一字元 `a`、`b` 或 `c`。 |
| `[^abc]` | 除了 `a`、`b` 或 `c` 之外的任一單一字元。 |
| `[a-z]` | `a`-`z` 範圍內的任一單一字元。 |
| `[a-zA-Z0-9]` | `a`-`z`、`A`-`Z` 或數字 `0`-`9` 範圍內的任一單一字元。 |
| `^` | 和行的開頭相符。 |
| `$` | 和行的結尾相符。 |
| `\A` | 字串的開頭。 |
| `\z` | 字串的結尾。 |
| `.` | 符合任一字元。  |
| `\s` | 任一空格字元。 |
| `\S` | 任何非空格字元。 |
| `\d` | 任何數字。 |
| `\D` | 任何非數字。 |
| `\w` | 任一字母、數字或底線。 |
| `\W` | 任一非單詞字元。 |
| `\b` | 任何單詞邊界。 |
| `\B` | 任一非單詞邊界的字元。 |
| `\<` | 單詞的開頭。 |
| `\>` | 單詞的結尾。 |
| `(...)` | 擷取括號內的所有內容。 |
| `(?:...)` | 未標示擷取。防止在輸出字串中參考相符項。 |
| `a?` | 零個或一個 `a`。 |
| `a*` | 零個或更多 `a`。 |
| `a+` | 一個或更多 `a`。 |
| `a{3}` | 剛好 3 個 `a`。 |
| `a{3,}` | 3 個或更多 `a`。 |
| `a{3,6}` | 介於 3 個和 6 個 `a` 之間。 |

您可以在[!UICONTROL 輸出格式]中以不限次數和任何順序的方式使用這些序列，以實現所需的字串輸出。

| 輸出預留位置序列 | 說明 |
| --- | --- |
| `$&` | 和全部運算式相符的輸出。 |
| `$n` | 和第n個子運算式相符的輸出。 例如，`$1`輸出第一個子運算式。 |
| ``$` `` | 輸出找到的最後一個相符項的結尾 (如果沒有找到之前的相符項，則為文字的開頭) 和目前相符項的開頭之間的文字。 |
| `$+` | 輸出和規則運算式中最後一個標籤的子運算式相符的內容。 |
| `$$` | 輸出字串字元 `"$"`。 |

{style="table-layout:auto"}

+++

<!-- SPLIT -->

### Split {#split}

將欄位中的值分割成新的衍生欄位。

+++ 詳細資料

## 規格 {#split-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></ul><ul><li>[!UICONTROL 方法]：</li><ul><li>從左側</li><li>從右側</li><li>轉換為陣列</li></ul></li><li>對於分隔字元：<ul><li>字串</li></ul><li>針對索引：<ul><li>數值</li></ul></li> | <p>不適用</p> | <p>每個衍生欄位5個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}

## 使用案例1 {#split-uc1}

您可在單一維度中將語音應用程式回應收集到分隔清單中。 您想要清單中的每個值在回應報表中成為唯一值。

### 在此之前的資料 {#split-uc1-databefore}

| 語音應用程式回應 | 活動 |
|---|--:|
| 非常棒，完全合理，會推薦給其他人 | 1 |
| 很棒，有點混亂，會推薦給其他人 | 1 |
| 不是很好，很混亂，不會向其他人推薦 | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#split-u1-derivedfield}

您建立`Responses`衍生欄位。 您使用[!UICONTROL SPLIT]函式定義規則，以使用[!UICONTROL Convert to array]方法，以`,`作為[!UICONTROL 分隔符號]，轉換[!UICONTROL 語音應用程式回應]欄位的值。

![分割規則1](assets/split-1.png)的熒幕擷圖

### 之後的資料 {#split-uc1-dataafter}

| 回應 | 活動 |
|---|--:|
| 非常棒 | 2 |
| 會推薦給其他人 | 2 |
| 不太好 | 1 |
| 完全合理 | 1 |
| 有點令人困惑 | 1 |
| 非常令人困惑 | 1 |
| 不會推薦給其他人 | 1 |

{style="table-layout:auto"}

## 使用案例2 {#split-uc2}

您可在單一維度中將語音應用程式回應收集到分隔清單中。 您想要將清單中第一個值的回應放入其本身的維度中。 您想要將清單中的最後一個值放入其本身的維度中。

### 在此之前的資料 {#split-uc2-databefore}

| 回應 | 活動 |
|---|--:|
| 非常棒，非常合理，會推薦給其他人 | 1 |
| 很棒，有點混亂，會推薦給其他人 | 1 |
| 不是很好，很混亂，不會向其他人推薦 | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#split-u2-derivedfield}

您建立`First Response`衍生欄位。 您使用[!UICONTROL SPLIT]函式定義規則，以從回應`,`左側的[!UICONTROL 回應]欄位取得第一個值做為分隔符號。

![分割規則的熒幕擷圖 — 第一個值](assets/split-2.png)

您可以建立一個`Second Response`衍生欄位，以從[!UICONTROL 回應]欄位取得最後一個值，方法是選取「從右側」、「1」作為「分隔符號」、「1」作為「索引」。

![分割規則的熒幕擷圖 — 最後一個值](assets/split-3.png)

### 之後的資料 {#split-uc2-dataafter}

| 第一個回應 | 活動 |
|---|--:|
| 非常棒 | 2 |
| 不太好 | 1 |

{style="table-layout:auto"}

| 第二個回應 | 活動 |
|---|--:|
| 會推薦給其他人 | 2 |
| 不會推薦給其他人 | 1 |

{style="table-layout:auto"}

+++

<!-- SUMMARIZE -->

### 總結 {#summarize}

在事件、工作階段和使用者層級，將彙總型別函式套用至量度或維度。

+++ 詳細資料

## 規格 {#summarize-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li><li>數值</li><li>日期</li></ul> | <ul><li>值<ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></li><li>摘要方法</li><li>範圍<ul><li>事件</li><li>工作階段</li><li>「人」</li></ul></li></ul> | <ul><li>數值<ul><li>MAX — 從一組值傳回最大值</li><li>MIN — 從一組值傳回最小值</li><li>MEDIAN — 傳回一組值的中位數</li><li>MEAN — 傳回一組值的平均值</li><li>SUM — 傳回一組值的和</li><li>COUNT — 傳回收到的值數目</li><li>DISTINCT — 傳回不同值集</li></ul></li><li>字串<ul><li>DISTINCT — 傳回不同值集</li><li>COUNT DISTINCT — 傳回不同值的數量</li><li>MOST COMMON — 傳回最常收到的字串值</li><li>LEAST COMMON — 傳回最不常收到的字串值</li><li>FIRST — 收到的第一個值；僅適用於工作階段和事件表格</li><li>LAST — 收到的最後一個值；僅適用於工作階段和事件表格</li></ul></li><li>日期<ul><li>DISTINCT — 傳回不同值集</li><li>COUNT DISTINCT — 傳回不同值的數量</li><li>MOST COMMON — 傳回最常收到的字串值</li><li>LEAST COMMON — 傳回最不常收到的字串值</li><li>FIRST — 收到的第一個值；僅適用於工作階段和事件表格</li><li>LAST — 收到的最後一個值；僅適用於工作階段和事件表格</li><li>EARLIEST — 收到的最早值（由時間決定）；僅適用於工作階段與事件表格</li><li>LATEST — 收到的最新值（由時間決定）；僅適用於工作階段和事件表格</li></ul></li></ul> | 每個衍生欄位3個函式 | 新增衍生欄位 |

{style="table-layout:auto"}

## 使用案例 {#summarize-uc}

您想要將「新增至購物車收入」分類為三種不同的類別：「小」、「Medium」和「大」。 這可讓您分析和識別高價值客戶的特徵。

### 在此之前的資料 {#summarize-uc-databefore}

假設：

- 「加入購物車收入」會以數值欄位收集。

情境：

- CustomerABC123在購物車中為ProductABC新增35美元，然後單獨新增ProductDEF到購物車中新增75美元。
- CustomerDEF456在購物車中新增50美元購買ProductGHI，然後在購物車中另外新增ProductJKL，價格為275美元。
- CustomerGHI789為ProductMNO的購物車新增$500。

邏輯：

- 如果訪客的購物車收入總計不到$150，則設定為小。
- 如果訪客的購物車收入總計大於$150但小於$500，請設為Medium。
- 如果訪客的購物車收入總計大於或等於$500，則設定為大。

結果：

- CustomerABC123加到購物車收入的總計$110。
- CustomerDEF456的購物車總收入為$325。
- CustomerGHI789加到購物車收入的總和$500。

### 衍生欄位 {#summarize-uc-derivedfield}

您建立`Add To Cart Revenue Size`衍生欄位。 您使用[!UICONTROL SUMMARIZE]函式和[!UICONTROL Sum] [!UICONTROL Summarize方法]，並將[!UICONTROL 範圍]設定為[!UICONTROL 人員]，來加總[!UICONTROL cart_add]欄位的值。 然後使用第二個[!UICONTROL CASE WHEN]規則將結果分割為樹狀目錄類別大小。

![摘要規則1](assets/summarize.png)的熒幕擷圖



### 之後的資料 {#summarize-uc-dataafter}

| 新增至購物車收入大小 | 訪客 |
|---|--:|
| 小 | 1 |
| 媒體 | 1 |
| 大 | 1 |

{style="table-layout:auto"}

## 詳細資訊 {#summarize-more-info}

使用摘要函式進行以事件、工作階段或人員範圍為基礎的計算。 使用[Math](#math)函式進行點選層級的計算。

+++

<!-- TRIM -->

### 修剪

從欄位值的開頭或結尾，將空格、特殊字元或字元數修剪成新的衍生欄位。

+++ 詳細資料

## 規格 {#trim-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li></ul> | <ul><li>[!UICONTROL 欄位]<ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul></li><li>修剪空白字元</li><li>修剪特殊字元<ul><li>特殊字元的輸入</li></ul></li><li>從左側修剪<ul><li>從 <ul><li>字串開始</li><li>位置<ul><li>位置#</li></ul></li><li>字串<ul><li>字串值</li><li>索引</li><li>標幟以包含字串</li></ul></li></ul></li><li>結束日期<ul><li>字串結束</li><li>位置<ul><li>位置#</li></ul></li><li>字串<ul><li>字串值</li><li>索引</li><li>標幟以包含字串</li></ul></li><li>長度</li></ul></li></ul></li><li>從右側修剪<ul><li>從 <ul><li>字串結束</li><li>位置<ul><li>位置#</li></ul></li><li>字串<ul><li>字串值</li><li>索引</li><li>標幟以包含字串</li></ul></li></ul></li><li>結束日期<ul><li>字串開始</li><li>位置<ul><li>位置#</li></ul></li><li>字串<ul><li>字串值</li><li>索引</li><li>標幟以包含字串</li></ul></li><li>長度</li></ul></li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位1個函式</p> | <p>新增衍生欄位</p> |


## 使用案例1 {#trim-uc1}

您會收集產品資料，但該資料包含可分割報表的隱藏空白字元。 您想要輕鬆修剪任何多餘的空格

### 在此之前的資料 {#trim-uc1-databefore}

| 產品 ID | 活動 |
|---|--:|
| `"prod12356 "` | 1 |
| `"prod12356"` | 1 |
| `" prod12356"` | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#trim-u1-derivedfield}

您建立`Product Identifier`衍生欄位。 您使用[!UICONTROL TRIM]函式定義規則以從&#x200B;**[!UICONTROL 產品識別碼]**&#x200B;欄位&#x200B;**[!UICONTROL 修剪空白字元]**。

![分割規則1](assets/trim-1.png)的熒幕擷圖

### 之後的資料 {#trim-uc1-dataafter}

| 產品識別碼 | 活動 |
|---|--:|
| `"prod12356"` | 3 |

{style="table-layout:auto"}

## 使用案例2 {#trim-uc2}

您在頁面名稱上收集的資料在頁面名稱結尾包含一些錯誤的特殊字元，這些字元必須移除。

### 在此之前的資料 {#trim-uc2-databefore}

| 名稱 | 活動 |
|---|--:|
| 首頁# | 1 |
| 首頁？ | 1 |
| 首頁% | 1 |
| 首頁&amp; | 1 |
| 首頁/ | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#trim-u2-derivedfield}

您建立`Page Name`衍生欄位。 您使用[!UICONTROL TRIM]函式定義規則，以使用[!UICONTROL 特殊字元] `#?%&/`從[!UICONTROL 名稱]欄位修剪特殊字元]。[!UICONTROL 

![分割規則的熒幕擷圖 — 第一個值](assets/trim-2.png)

### 之後的資料 {#trim-uc2-dataafter}

| 頁面名稱 | 活動 |
|---|--:|
| 首頁 | 5 |

{style="table-layout:auto"}


## 使用案例3 {#trim-uc3}

您收集包括storeID的資料。 storeID包含縮寫後的美國州碼，做為前兩個字元。 您只想在報告中使用該州碼。

### 在此之前的資料 {#trim-uc3-databefore}

| storeID | 活動 |
|---|--:|
| CA293842 | 1 |
| CA423402 | 1 |
| UT123418 | 1 |
| UT189021 | 1 |
| ID028930 | 1 |
| 或234223 | 1 |
| NV22342 | 1 |

{style="table-layout:auto"}

### 衍生欄位 {#trim-u3-derivedfield}

您建立`Store Identifier`衍生欄位。 您使用[!UICONTROL TRIM]函式定義規則以[!UICONTROL 從右側]截斷[!UICONTROL storeID]欄位（從字串結尾到位置`3`）。

![分割規則的熒幕擷圖 — 第一個值](assets/trim-3.png)

### 之後的資料 {#trim-uc3-dataafter}

| 存放區識別碼 | 活動 |
|---|--:|
| CA | 2 |
| UT | 2 |
| ID | 1 |
| OR | 1 |
| NV | 1 |

{style="table-layout:auto"}
+++


<!-- URL PARSE -->

### URL 剖析

剖析URL的不同部分，包括通訊協定、主機、路徑或查詢引數。

+++ 詳細資料

## 規格 {#urlparse-io}

| 輸入資料型別 | 輸入 | 包含的運運算元 | 限制 | 輸出 |
|---|---|---|---|---|
| <ul><li>字串</li></ul> | <ul><li>[!UICONTROL 欄位]：</li><ul><li>規則</li><li>標準欄位</li><li>欄位</li></ul><li>[!UICONTROL 選項]：<ul><li>[!UICONTROL 取得通訊協定]</li><li>[!UICONTROL 取得主機]</li><li>[!UICONTROL 取得路徑]</li><li>[!UICONTROL 取得查詢字串值]<ul><li>[!UICONTROL 查詢引數]：<ul><li>字串</li></ul></li></ul></li><li>[!UICONTROL 取得雜湊值]</li></ul></li></ul></li></ul> | <p>不適用</p> | <p>每個衍生欄位5個函式</p> | <p>新增衍生欄位</p> |

{style="table-layout:auto"}


## 使用案例1 {#urlparse-uc1}

您只想要使用反向連結URL的反向連結網域，作為行銷管道規則集的一部分。

### 在此之前的資料 {#urlparse-uc1-databefore}

| [!DNL Referring URL] |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### 衍生欄位 {#urlparse-uc1-derivedfield}

您定義`Referring Domain`衍生欄位。 您使用[!UICONTROL URL PARSE]函式定義規則，以便從[!UICONTROL 反向連結URL]欄位擷取主機，並將其儲存在新的衍生欄位中。

![URL剖析規則1](assets/url-parse-1.png)的熒幕擷圖

### 之後的資料 {#urlparse-uc1-dataafter}

| [!DNL Referrer Domain] |
|----|
| [!DNL www.google.com] |
| [!DNL duckduckgo.com] |
| [!DNL t.co] |
| [!DNL l.facebook.com] |

{style="table-layout:auto"}


## 使用案例2 {#urlparse-uc2}

您想要在[!DNL Page URL]中使用查詢字串的`cid`引數值，做為衍生追蹤程式碼報表輸出的一部分。

### 在此之前的資料 {#urlparse-uc2-databefore}

| [!DNL Page URL] |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### 衍生欄位 {#urlparse-uc2-derivedfield}

您定義`Query String CID`衍生欄位。 您使用[!UICONTROL URL PARSE]函式定義規則，以擷取[!UICONTROL 頁面URL]欄位中查詢字串引數的值，並將`cid`指定為查詢引數。 輸出值會儲存在新的衍生欄位中。

![URL剖析規則2](assets/url-parse-2.png)的熒幕擷圖

### 之後的資料 {#urlparse-uc2-dataafter}

| [!DNL Query String CID] |
|----|
| [!DNL abc123] |
| [!DNL def123] |
| [!DNL xyz123] |

{style="table-layout:auto"}

+++

## 限制

下列限制一般適用於衍生欄位功能：

- 為衍生欄位定義規則時，您最多可以使用十個不同的結構描述欄位（不包括標準欄位）。
   - 根據此最多10個不同的結構描述欄位，只允許最多3個查詢結構描述或設定檔結構描述欄位。
- 每個Customer Journey Analytics連線最多可以有100個衍生欄位。


### 函式限制摘要

| 函數 | 限制 |
|---|---|
| <p>情況</p> | <ul><li>5案例當每個衍生欄位有函式時</li><li>每個衍生欄位有200個[運運算元](#operators)</li></ul> |
| <p>分類</p> | <ul><li>5依衍生欄位分類函式</li><li>每個衍生欄位有200個[運運算元](#operators)</li></ul> |
| <p>串連</p> | <ul><li>每個衍生欄位2個串連函式</li></ul> |
| <p>重複資料刪除</p> | <ul><li>5每個衍生欄位刪除重複函式</li></ul> |
| <p>尋找和取代</p> | <ul><li>每個衍生欄位2個尋找和取代函式</li></ul> |
| <p>查詢</p> | <ul><li>每個衍生欄位5個查詢函式</li></ul> |
| <p>小寫</p> | <ul><li>每個衍生欄位2個小寫函式</li></ul> |
| <p>Math</p> | <ul><li>每個衍生欄位25個作業</li><li>每個衍生欄位5個數學函式</li></ul> |
| <p>合併欄位</p> | <ul><li>每個衍生欄位有2個合併欄位函式</li></ul> |
| <p>下一個或上一個</p> | <ul><li>每個衍生欄位3個下一個或上一個函式</li></ul> |
| <p>規則運算式取代</p> | <ul><li>每個衍生欄位有1個Regex取代函式</li></ul> |
| <p>Split</p> | <ul><li>每個衍生欄位5個分割函式</li></ul> |
| <p>總結</p> | <ul><li>3每個衍生欄位的函式摘要</li></ul> |
| <p>修剪</p> | <ul><li>每個衍生欄位1個修剪函式</li></ul> |
| <p>URL 剖析</p> | <ul><li>每個衍生欄位有5個URL剖析函式</li></ul> |

{style="table-layout:auto"}

### 運算子

If或Else If建構中的運運算元（在Case When函式中）是條件與&#x200B;**one**&#x200B;值的組合。 條件的每個額外值都會增加運運算元的數量。

例如，底下的條件使用13個運運算元。

![範例運運算元](assets/operators-sample.png)

Classification函式中的運運算元是[!UICONTROL 當值等於原始值]時[!UICONTROL 以新值取代值]的單一專案。

例如，底下的「分類」規則使用3個運運算元。

![分類規則1](assets/classify-1.png)的熒幕擷圖


## 詳細資訊 {#trim-more-info}

[`Trim`](#trim)和[`Lowercase`](#lowercase)是[資料檢視](../component-settings/overview.md)中元件設定可用的功能。 使用衍生欄位可讓您結合這些函式，直接在Customer Journey Analytics中進行更複雜的資料轉換。 例如，您可以使用`Lowercase`移除事件欄位中的區分大小寫功能，然後使用[`Lookup`](#lookup)將新的小寫欄位與只有小寫查詢索引鍵的查詢資料集進行比對。 或者，在新欄位設定`Lookup`之前，您可以使用`Trim`來移除字元。

衍生欄位中支援查閱和設定檔欄位，可讓您根據事件查閱和設定檔屬性來轉換資料。 在有查詢或設定檔資料集中的帳戶層級資料的B2B案例中，這會特別有用。 此外，這項支援對於在查閱資料（如行銷活動資訊和選件型別）或設定檔資料（如成員層級和帳戶型別）的常見欄位中操作資料非常有用。

如需衍生欄位的詳細背景資訊，請參閱：

- [充分利用您的資料：在Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/making-the-most-of-your-data-a-framework-for-using-derived/ba-p/601670)中使用衍生欄位的架構

- Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/derived-fields-use-cases-for-customer-journey-analytics/ba-p/601679)的[衍生欄位使用案例
