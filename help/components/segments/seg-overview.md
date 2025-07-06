---
title: 區段概述
description: 了解區段的用途以及如何建立簡單區段。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 99%

---


# 分段概觀

Customer Journey Analytics 可讓您建立、管理、共用並套用功能強大、具針對性的客群區段，並套用至您的報表。區段讓您根據特性或互動，來識別人員、工作階段或事件的子集。區段設計為編碼化的客群深入分析，您可以根據特定需求建立區段，然後驗證、編輯並與其他團隊成員分享。

區段能奠基於：

- 屬性 (瀏覽器類型、裝置、造訪次數、國家/地區、性別)、
- 互動 (促銷活動、關鍵字搜尋、搜尋引擎)、
- 進入和退出 (訪客來自 Facebook、已定義的登陸頁面、反向連結網域)、
- 自訂變數 (表單欄位、已定義的類別、客戶 ID)
- 以及其他標準。

有關建立區段時可使用的各種選項，請參閱[建立區段](/help/components/segments/seg-create.md)。然後，在「[區段產生器](seg-builder.md)」中建置、修改並儲存區段的定義。或者，您可以使用「[快速區段產生器](seg-quick.md)」建立快速區段。您也可以從 Workspace 中的視覺效果產生區段，例如使用「[流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)」視覺效果。

您可以使用「[區段管理員](seg-manage.md)」來管理區段。

## 規劃區段

特別是身為管理員，適當的區段規劃可以提高區段使用的機會。規劃區段時請考慮以下事項：

- **客群**：誰會使用您的區段？確保提供清楚的區段說明，以便客群理解：
   - 此區段在哪方面有用？

   - 我應何時使用此區段？

- **範圍**：哪一個[區段容器](#segment-containers) 最能代表您所需的資料？使用的容器越小越好。

- **元件**：決定在區段定義中包含哪些元件，以及應該根據哪些值來驗證條件。

- **流程**：考慮為您的區段制定核准流程。Customer Journey Analytics 中沒有核准工作流程，但您仍然可以組織流程來決定是否核准某個區段。

- **模組化**：定義區段時要考慮模組化。您的區段使用者應該要能夠輕鬆[堆疊區段](seg-builder.md#stack-filters)，以建立功能強大的新區段。


## 區段類型

您可以建立三種類型的區段：

### 快速區段

快速區段可讓您輕鬆探索特定 Workspace 專案內的資料，而無須在[區段產生器](/help/components/segments/seg-create.md)中建立區段。您可以直接在 Workspace 介面中定義您的區段。如需詳細資訊，請參閱[快速區段](seg-quick.md)。

### 規則區段

規則區段可讓您根據一或多個條件識別資料 (人員、工作階段、事件)。如果您有多個條件，則可以使用邏輯運算子 (如 And 和 Or) 進一步定義區段。您可以使用容器將條件進行分組，並建立更複雜的區段。如需詳細資訊，請參閱[區段產生器](seg-builder.md)。

### 循序區段

>[!IMPORTANT]
>
>您必須擁有「**精選**」套裝才能建立跨管道循序區段。如果您不確定自己擁有哪一種 Customer Journey Analytics 套裝，請聯絡您的管理員。

循序區段讓您可以根據導覽 (網站上的頁面瀏覽量、與行動應用程式場景的互動，或使用機上盒上的選單) 識別資料 (人員、工作階段、事件)。循序區段可協助識別人員的好惡等指標。您可以使用 Then 邏輯運算子來定義循序區段。如需詳細資訊，請參閱[循序區段](seg-sequential-build.md)。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## 區段容器 {#containers}

區段使用巢狀容器模型，並以人員、工作階段和事件層級階層為根據。巢狀容器可讓您定義容器之間和容器內部的條件。


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> 個人</td>
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
>針對 Adobe Analytics 使用者：
> 
> - **人員**&#x200B;容器在 Adobe Analytics 中稱為「**訪客**&#x200B;容器」。
> - **區段**&#x200B;容器在 Adobe Analytics 中稱為「**造訪**&#x200B;容器」。
> -  **事件**&#x200B;容器在 Adobe Analytics 中稱為「**點擊** 容器」。
>

區段會設定條件，並根據條件細分人員、工作階段或事件。例如，細分人員的條件是根據其特徵與導覽行為。為了進一步劃分資料，您可以根據特定工作階段、頁面檢視事件、畫面點擊、機上盒的選單選項等進行細分。您也可以根據從 CRM 或忠誠度系統中收錄的屬性進行細分。[區段產生器](/help/components/segments/seg-builder.md)提供簡易的介面，您能以巢狀的階層式「人員」、「工作階段」或「事件」容器形式建立這些子集並套用條件。

[區段產生器](/help/components/segments/seg-builder.md)中所採用的容器架構將「人員」定義為最外層容器。此容器包含與特定人員相關的總體資料，涵蓋跨工作階段與事件 (例如頁面瀏覽量、行動應用程式畫面或機上盒選單畫面) 等內容。巢狀「工作階段」容器可讓您設定規則，以根據工作階段劃分人員的資料。巢狀「事件」容器可讓您根據個別互動來劃分人員的資料。每個容器均可讓您根據人員的歷史記錄、依工作階段劃分的互動來製作報告，或對個別事件進行劃分。

### 「人員」容器

「人員」容器包含符合容器中指定條件的人員的每個工作階段和每個事件。當您使用像「`Page Name equals Checkout`」這樣的簡單條件定義一個區段時，「人員」容器將解析為：

- 所有造訪過名稱為「`Checkout`」的頁面的人員。
- 這些人員的所有工作階段。
- 這些人員的所有事件資料。

作為定義最廣泛的容器，在「人員」容器層級產生的報告，將會傳回所有符合區段條件之人員的事件和工作階段。「人員」容器最容易隨定義的日期範圍而發生變更。
「人員」容器可以包含以人員整體歷史記錄為基礎的值：

- 首次購買間隔天數
- 原始登入頁面或行動應用程式主畫面。
- 原始反向連結網域

### 「工作階段」容器

「工作階段」容器可讓您識別特定工作階段的頁面互動或行動應用程式互動、促銷活動或轉換。「工作階段」容器是最常使用的容器，因為此容器會在符合規則時擷取整個工作階段的行為。「工作階段」容器也可讓您定義當建立和套用區段時要納入或排除的區段。當您使用像「`Page Name equals Checkout`」這樣的簡單條件定義一個區段時，「工作階段」容器將解析為：

- 造訪名稱為「`Checkout`」的頁面的所有工作階段。
- 這些工作階段的所有事件資料。

工作階段容器可以幫助您回答以下問題：

- 有多少個工作階段同時參與了網頁和呼叫中心資料來源？
- 成功的銷售轉換歸因於哪些頁面？

「工作階段」容器包括以每個工作階段事件為基礎的值：

- 工作階段類型。
- 登入頁面。
- 回訪頻率。
- 參與率量度。
- 線性配置的量度。

Customer Journey Analytics 的資料視圖可讓您決定工作階段持續的時間，以及何時建立新工作階段。例如，您可以將每次使用者啟動行動應用程式的動作，定義為一個新的行動應用程式工作階段。如需詳細資訊，請參閱[工作階段設定](/help/data-views/session-settings.md)。

### 事件容器

「事件」容器定義您想要在區段中包含或排除的頁面、行動應用程式或其他類型的事件。它是目前最狹義的容器。它可讓您識別在特定條件成立時，行動應用程式中的點擊、頁面瀏覽或按鈕點擊等行為。「事件」容器可讓您檢視單一追蹤程式碼，或隔離行動應用程式特定區域內的行為。您可能也想要找出動作發生時的特定值 (例如提出訂單時所用的行銷管道)。當您使用像「`Page Name equals Checkout`」這樣的簡單條件定義一個區段時，「事件」容器將解析為：

- 頁面名稱等於「`Checkout`」的所有頁面瀏覽事件。

「事件」容器包含下列項目中以值為基礎的單頁劃分：

- 產品
- 清單 Prop
- 清單維度
- 銷售維度 (在事件的情境中)



### B2B 容器

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

當您有權存取 [Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md) 時，可以使用其他可用於區段的容器。您可以在「[B2B 概念和功能](/help/getting-started/cja-b2b-concepts-features.md)」中找到有關使用這些附加容器的更多詳細資訊。


### 邏輯群組容器

邏輯群組讓您能將條件分組至單一循序區段查核點。作為序列的一部分，標示為「[!UICONTROL 邏輯群組]」的容器定義邏輯，會在前一個循序查核點之後、下一個循序查核點之前進行評估。如需詳細資訊，請查閱「[邏輯群組](seg-sequential-build.md#logic-group)」。

### 巢狀容器

在其他容器內建立容器時，其實是在區段內建立區段。巢狀容器所套用的邏輯如下：

1. 使用最外層的容器，判斷包含的是什麼資料。不符合此外層規則的資料將在報告中遭到捨棄。
2. 將巢狀區段定義套用至其餘資料。巢狀區段定義不適用於第一個定義所排除的任何資料。
3. 重複此動作，直到計算過所有巢狀容器的區段定義為止。接著，剩餘資料便會納入結果，並用於報告中。

>[!NOTE]
>
>當您將一個區段嵌入另一個區段中 (例如，您從「元件」面板中拖曳一個區段至您的區段定義上)，將會建立一個容器，其中包含所拖曳的區段定義的副本 (而非引用)。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[建立區段](seg-create.md)
>>[區段產生器](seg-builder.md)
>>[快速區段](seg-quick.md)
>>[循序區段](seg-sequential-build.md)
>>[管理區段](seg-manage.md)
