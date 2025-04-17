---
title: 分段概觀
description: 瞭解區段的用途以及如何建立簡單區段。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 716d6423c0cc8b91aa4951952191e0fd0e627c0f
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 7%

---


# 分段概觀

Customer Journey Analytics可讓您建立、管理、共用功能強大、具針對性的對象區段，並套用至您的報表。 篩選器可讓您根據特性或互動來識別人員、工作階段或事件的子集。 篩選設計為編碼化的客群深入分析，您可以根據特定需求建立篩選，然後驗證、編輯並與其他團隊成員分享。

篩選條件可以根據：

- 屬性（瀏覽器型別、裝置、造訪次數、國家/地區、性別）、
- 互動（促銷活動、關鍵字搜尋、搜尋引擎）、
- 退出和登入點（來自Facebook、定義的登陸頁面、反向連結網域、地理圍欄事件的人），
- 自訂變數（表單欄位、定義的類別、客戶ID）、
- 和其他條件。

如需建立區段可用的各種選項，請參閱[建立區段](/help/components/filters/create-filters.md)。 然後，在[區段產生器](filter-builder.md)中建立、修改及儲存區段的定義。 或者，您可以使用[快速區段產生器](quick-filters.md)來建立快速區段。 您也可以從Workspace中的視覺效果產生區段，例如使用[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)視覺效果。

您使用[區段管理員](manage-filters.md)來管理區段。

## 規劃區段

尤其是作為管理員，正確規劃區段會提高使用區段的可能性。 規劃區段時，請考量下列事項：

- **對象**：誰將使用您的區段？ 請確定您提供清楚的區段說明，讓對象瞭解：
   - 此區段在哪方面有用？

   - 我應何時使用此區段？

- **範圍**：哪個[區段容器](#filter-containers)最能代表您想要的資料？ 使用的容器越小越好。

- **元件**：決定要包含在區段定義中的元件，以及條件應該針對哪些值進行驗證。

- **程式**：考慮您的區段的核准程式。 Customer Journey Analytics中沒有核准工作流程，但您仍可組織流程以判斷您是否核准區段。

- **模組化**：定義考慮到模組化的區段。 您區段的使用者應該能夠輕鬆地[棧疊區段](filter-builder.md#stack-filters)，以建立強大的新區段。


## 區段型別

您可以建立三種型別的區段：

### 快速區段

快速區段可讓您在指定的Workspace專案中輕鬆探索資料，而不需要在[區段產生器](/help/components/filters/create-filters.md)中建立區段。 您可以直接在Workspace介面中定義區段。 如需詳細資訊，請參閱[快速區段](quick-filters.md)。

### 一般區段

規則區段可讓您根據一或多個條件識別資料（人員、工作階段、事件）。 如果您有多個條件，可使用And和Or等邏輯運運算元進一步定義區段。 您可以使用容器來分組條件並建立更複雜的區段。 如需詳細資訊，請參閱[區段產生器](filter-builder.md)。

### 循序區段

>[!IMPORTANT]
>
>您必須有&#x200B;**Select**&#x200B;套件才能建立跨管道循序區段。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

循序區段可讓您根據導覽（整個網站的頁面檢視、與行動應用程式中場景的互動，或使用機上盒上的選單）識別資料（人員、工作階段、事件）。 循序區段可協助您識別（舉例來說）某人喜歡什麼、避免什麼。 您可以使用Then邏輯運運算元來定義循序區段。 如需詳細資訊，請參閱[循序區段](seg-sequential-build.md)。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 區段容器 {#containers}

區段是以人員、工作階段和事件層級階層為基礎，使用巢狀容器模型。 巢狀容器可讓您定義容器之間和容器內的條件。


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 人員</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> 工作階段</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> 事件</td>
</tr>
</table>

>[!NOTE]
>
>若為Adobe Analytics使用者：
> 
> - 在Adobe Analytics中，**人員**&#x200B;容器稱為&#x200B;**訪客**&#x200B;容器。
> - 在Adobe Analytics中，**工作階段**&#x200B;容器稱為&#x200B;**造訪**&#x200B;容器。
> - 在Adobe Analytics中，**事件**&#x200B;容器稱為&#x200B;**點選**&#x200B;容器。
>

區段會設定條件，以根據條件來區隔人員、工作階段或事件。 例如，區隔人員的條件是根據人員特性和導覽特徵。 若要進一步劃分資料，您可以劃分特定工作階段、頁面檢視事件、熒幕點選、機上盒的功能表選擇等等。 您也可以對從CRM或忠誠度系統擷取的屬性進行分段。 [區段產生器](/help/components/filters/filter-builder.md)提供簡易的介面，讓您在巢狀階層式「人員」、「工作階段」或「事件」容器中建立這些子集並套用條件。

[區段產生器](/help/components/filters/filter-builder.md)中使用的容器架構將「人員」定義為最外層的容器。 此容器包含個人在各工作階段和事件（例如頁面檢視、行動應用程式畫面或機上盒的選單畫面）專屬的總體資料。 巢狀「工作階段」容器可讓您設定規則，以根據工作階段劃分人員的資料。 巢狀「事件」容器可讓您根據個別互動來劃分人員資訊。 每個容器均可讓您根據個人的歷史記錄、依工作階段劃分的互動來進行報告，或對個別事件進行劃分。

### 「人員」容器

「人員」容器包含符合容器中所指定條件之人員的每個工作階段和每個事件。 當您定義具有簡單條件（如`Page Name equals Checkout`）的區段時，「人員」容器會解析為：

- 所有造訪過名為`Checkout`之頁面的使用者。
- 這些人員的所有工作階段。
- 這些人員的所有事件資料。

「人員」容器是定義範圍最廣的容器，在此層級產生的報表會為所有符合篩選條件的人傳回事件和工作階段。 根據定義的日期範圍，「人員」容器最容易發生變更。
「人員」容器可以包含以人員整體歷史記錄為基礎的值：

- 首次購買間隔天數。
- 原始登入頁面或行動應用程式首頁。
- 原始反向連結網域。

### 「工作階段」容器

「工作階段」容器可讓您識別特定工作階段的頁面互動或行動應用程式互動、促銷活動或轉換。 「工作階段」容器是最常使用的容器，因為它會在符合規則時擷取整個工作階段的行為。 「工作階段」容器也可讓您定義建立和套用區段時要包含或排除的工作階段。  當您定義具有簡單條件（如`Page Name equals Checkout`）的區段時，工作階段容器會解析為：

- 造訪名稱為`Checkout`之頁面的所有工作階段。
- 這些工作階段的所有事件資料。

「工作階段」容器可協助您回答下列問題：

- 有多少場會議同時涉及網路和客服中心資料來源？
- 成功的銷售轉換歸因於哪些頁面？

「工作階段」容器包括以每個工作階段事件為基礎的值：

- 工作階段型別。
- 登入頁面。
- 回訪頻率。
- 參與率量度。
- 線性配置的量度。

Customer Journey Analytics中的資料檢視可讓您決定工作階段持續的時間，以及建立新工作階段的時間。 例如，您可以根據每次使用者啟動您的行動應用程式來定義新的行動應用程式工作階段。 如需詳細資訊，請參閱[工作階段設定](/help/data-views/session-settings.md)。

### 事件容器

「事件」容器定義您要在區段中納入或排除的頁面、行動應用程式或其他事件型別。 這是可用容器中最窄的。 它可讓您在條件為真的情況下，識別行動應用程式中的特定點按、頁面檢視、點選按鈕等。 「事件」容器可讓您檢視單一追蹤程式碼，或隔離行動應用程式特定區域中的行為。 您可能也會想要在動作發生時精準指出特定值，例如下訂單時的行銷管道。 當您定義具有簡單條件（例如`Page Name equals Checkout`）的區段時，事件容器會解析為：

- 頁面名稱等於`Checkout`的所有頁面檢視事件。

「事件」容器包含以值為基礎的單一頁面劃分，適用於：

- 產品
- 清單 Prop
- 清單維度
- 銷售維度（在事件情境中）


### 邏輯群組容器

邏輯群組可讓您將條件群組至單一循序區段查核點。 作為序列的一部分，在識別為[!UICONTROL 邏輯群組]的容器中定義的邏輯，會在任何先前的循序查核點之後，以及任何後續的循序查核點之前評估。 如需詳細資訊，請參閱[邏輯群組](seg-sequential-build.md#logic-group)。

### 巢狀內嵌容器

在其他容器中建立容器時，您實際上是要在區段內建立區段。 下列邏輯會套用至巢狀容器：

1. 使用最外層的容器，判斷包含的是什麼資料。報表中會捨棄不符合此外部規則的任何資料。
2. 將巢狀區段定義套用至其餘資料。 巢狀區段定義不適用於第一個定義捨棄的任何資料。
3. 重複此步驟，直到所有巢狀容器區段定義都已計算完畢。 剩餘的資料會包含在結果中，並用於報表。

>[!NOTE]
>
>當您在區段內巢狀內嵌區段（例如，從「元件」面板將區段拖曳至區段定義上）時，會以拖曳區段定義的復本（而非參照）建立容器。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[建立區段](create-filters.md)
>[區段產生器](filter-builder.md)
>[快速區段](quick-filters.md)
>[循序區段](seg-sequential-build.md)
>[管理區段](manage-filters.md)
>
