---
title: Customer Journey Analytics BI 擴充功能
description: 了解如何使用Power BI、Tableau Desktop 或其他 BI，並透過 Customer Journey Analytics BI 擴充功能來存取資料檢視。
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '3247'
ht-degree: 96%

---

# Customer Journey Analytics BI 擴充功能

{{select-package}}

[!DNL Customer Journey Analytics BI extension] 讓 SQL 可以存取您在 Customer Journey Analytics 中定義的[資料檢視](./data-views.md)。您的資料工程師和分析師可能更熟悉 Power BI、Tableau Desktop 或其他企業情報和視覺化工具 (也稱為 BI 工具)。他們現在可以根據 Customer Journey Analytics 使用者在建立 Analysis Workspace 專案時所使用的相同資料檢視來建立報告和儀表板。

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home) 是 SQL 與 Experience Platform 資料湖中可用資料之間的介面。啟用 [!DNL Customer Journey Analytics BI extension] 之後即可延伸 [!DNL Query Service] 的功能，讓您在 [!DNL Query Service] 工作階段中以表格或視圖形式查看 Customer Journey Analytics 資料檢視。因此，使用 [!DNL Query Service] 作為 PostgresSQL 介面的企業情報工具，可以直接立即受益於這項延伸功能。

主要優點包括：

* 無需在 BI 工具之內重新建立 Customer Journey Analytics 資料檢視的同等呈現形式。<br/>有關資料檢視功能的更多資訊，請參閱「[資料檢視](data-views.md)」以了解必須重新建立的內容。
* BI 工具和 Customer Journey Analytics 之間的報告和分析維持更高的一致性。
* 結合 Customer Journey Analytics 資料與 BI 工具中已有的其他資料來源。

## 先決條件

若要使用此功能，您可以使用過期或非過期憑證將 BI 工具連接到 [!DNL Customer Journey Analytics BI extension]。「[認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)」提供關於設定有到期日的認證或無到期日的認證之詳細資訊。
以下是設定 CJA 權限的其他步驟
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### 到期的認證

若要使用即將過期的憑證，您可以：

* 授予 Adobe Experience Platform 和 Customer Journey Analytics 的存取權。
* 授予產品管理員對 Customer Journey Analytics 的存取權限，以便您可以查看、編輯、更新或刪除連線和資料檢視。

或者你可以：

* 授予您想要存取的資料檢視存取權限。
* 授予對 Customer Journey Analytics BI 擴充功能的存取權限。

### 不會到期的認證

若要使用不會過期的認證：

* 在 Experience Platform 中建立不會過期的認證。
* 依照[過期認證](#Expiring-credentials)中所提及的步驟，授予不會過期認證的存取權限。

若要了解更多資訊，請參閱「[Customer Journey 存取控制](../technotes/access-control.md)」，特別是[產品管理員附加權限](../technotes/access-control.md#product-admin-additional-permissions)和 [Admin Console 中的 Customer Journey Analytics 權限](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console)。


## 使用情況

要使用 [!DNL Customer Journey Analytics BI extension] 功能，您可以直接使用 SQL 或使用特定的 BI 工具所提供的拖放體驗。

### SQL

您可以使用查詢編輯器或標準 PostgresSQL 命令列介面 (CLI) 用戶端，直接在 SQL 陳述式中使用該功能。

+++ 查詢編輯器

在 Adobe Experience Platform 中：

1. 在左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(從「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」)。

1. 選取「![建立查詢](assets/Smock_AddCircle_18_N.svg)**[!UICONTROL **&#x200B;建立查詢&#x200B;**]**」。

1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

1. 若要執行查詢，請鍵入 SQL 陳述式並選取「![播放](assets/Smock_Play_18_N.svg)」按鈕 (或按 `[SHIFT]` + `[ENTER]`)。

+++


+++ PostgresSQL CLI

1. 在 Adobe Experience Platform 中，查尋並複製您的 PostgresSQL 認證：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 要複製命令字串，請使用「![複製](assets/Smock_Copy_18_N.svg)」(在「**[!UICONTROL ** PSQL 指令&#x200B;**]**」區段)。

1. 開啟命令或終端機視窗。

1. 若要登入並開始執行查詢，請將命令字串貼到您的終端。

+++

請參閱「[查詢編輯器 UI 指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/user-guide)」以了解更多資訊。


### BI 工具

目前，已針對下面所列工具支援並測試 [!DNL Customer Journey Analytics BI extension]。其他使用 PSQL 介面的 BI 工具可能也可以運作，但尚未得到正式支援。

+++ Power BI

1. 在 Adobe Experience Platform 中，查詢 PostgresSQL 認證的詳細資訊：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 在 Power BI 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

1. 在 Power BI 中：

   1. 在主視窗中，從頂端列選取「**[!UICONTROL **&#x200B;取得資料&#x200B;**]**」。

   1. 在左側邊欄中選取「**[!UICONTROL 更多...]**」。

   1. 在「**取得資料**」畫面中，搜尋 `PostgresSQL`，並從清單中選取「**[!UICONTROL ** PostgresSQL 資料庫&#x200B;**]**」。

   1. 在「**[!UICONTROL ** PostgressSQL 資料庫&#x200B;**]**」對話方塊中：

      1. 將「**[!UICONTROL **&#x200B;主機&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;伺服器&#x200B;**]**」文字欄位。

      1. 將「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」文字欄位。

         將 `?FLATTEN` 新增到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數，以便讀起來像 `prod:cja?FLATTEN`。請參閱「[將巢狀資料結構展平以供協力廠商 BI 工具使用](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)」以了解更多資訊。

      1. 當提示「**[!UICONTROL 資料連線]**」模式時，選取  **[!UICONTROL DirectQuery]**。

      1. 系統會提示您輸入「**[!UICONTROL 使用者名稱]**」和「**[!UICONTROL 密碼]**」。使用 Experience Platform 查詢[!UICONTROL 認證]的同等參數。


   1. 成功登入之後，Power BI 的&#x200B;**[!UICONTROL **&#x200B;導覽器&#x200B;**]**&#x200B;中會顯示 Customer Journey Analytics 資料檢視表格。

   1. 選取您要使用的資料檢視表格並選取「**[!UICONTROL **&#x200B;載入&#x200B;**]**」。

   與一個或多個所選表格關聯的所有維度和指標顯示在右窗格，您隨時可以用於視覺化。

   請參閱「[將 Power BI 連接到 Query Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/power-bi)」以了解更多資訊。另請參閱「[BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」，了解詳細範例。

+++

+++Tableau Desktop

1. 在 Adobe Experience Platform 中，查詢 PostgresSQL 認證的詳細資訊：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 在 Tableau Desktop 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

1. 在 Tableau Desktop 中：

   1. 在左側邊欄，選取「**[!UICONTROL **&#x200B;更多&#x200B;**]**」(從「**[!UICONTROL **&#x200B;至伺服器&#x200B;**]**」)。

   1. 從清單中選取「**[!UICONTROL ** PostgresSQL **]**」。

   1. 在「[!UICONTROL PostgresSQL]」對話方塊中：

      1. 將「**[!UICONTROL **&#x200B;主機&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;伺服器&#x200B;**]**」文字欄位。

      1. 將「**[!UICONTROL **&#x200B;連接埠&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;連接埠&#x200B;**]**」文字欄位。

      1. 將「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」文字欄位。

         將 `%3FFLATTEN` 新增到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數，以便讀起來像 `prod:cja%3FFLATTEN`。請參閱「[將巢狀資料結構展平以供協力廠商 BI 工具使用](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)」以了解更多資訊。

      1. 選取「**[!UICONTROL **&#x200B;使用者名稱和密碼&#x200B;**]**」(從「**[!UICONTROL **&#x200B;驗證&#x200B;**]**」清單)。

      1. 將「**[!UICONTROL **&#x200B;使用者名稱&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;使用者名稱&#x200B;**]**」文字欄位。

      1. 將「**[!UICONTROL **&#x200B;密碼&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;密碼&#x200B;**]**」文字欄位。

      1. 選取「**[!UICONTROL **&#x200B;登入&#x200B;**]**」。

   1. Customer Journey Analytics 資料檢視顯示為「**[!UICONTROL **&#x200B;表格&#x200B;**]**」清單中的表格。

   1. 將想要使用的表格拖曳到畫布上。

   現在您可以使用資料檢視表格中的資料建立報告和視覺化。

   請參閱「[將 Tableau 連線到 Query Service ](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/tableau)」以了解更多資訊。另請參閱「[BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」的詳細範例。

+++

+++ Looker

1. 在 Adobe Experience Platform 中，查詢 PostgresSQL 認證的詳細資訊：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 在 Looker.中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

1. 在 Looker 中：

   1. 選取左邊欄的「**[!UICONTROL 管理員]**」。
   1. 選取「**[!UICONTROL 連線]**」。
   1. 選取「**[!UICONTROL 新增連線]**」。
   1. 在&#x200B;**[!UICONTROL 將資料庫連接到 Looker]** 畫面中，設定新連線時貼上適當的值。確保選取 **[!UICONTROL PostgreSQL 9.5+]** 作為程式語言。
   1. 選擇「**[!UICONTROL 測試]**」來測試您的連線。
   1. 成功後，選取「**[!UICONTROL 更新]**」以儲存您的連線。

   現在您可以使用資料檢視表格中的資料建立報告和視覺化。

   請參閱「[將 Looker 連線到 Query Service ](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/looker)」以了解更多資訊。另請參閱「[BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」的詳細範例。

+++

+++ Jupyter Noteboook

1. 在 Adobe Experience Platform 中，查詢 PostgresSQL 認證的詳細資訊：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 在 Jupyter Notebook 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

1. 在 Jupyter Notebook 中：

   1. 確保您使用所需的資料庫。
   1. 在建立和執行連線時使用適當的值。
   1. 透過執行相關查詢來測試您的連線。

   成功後，您可以使用資料來建立報告和視覺效果。

   請參閱「[將 Jupyter Notebook 連接到 Query Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/jupyter-notebook)」以了解更多資訊。另請參閱「[BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」的詳細範例。

+++

+++ RStudio

1. 在 Adobe Experience Platform 中，查詢 PostgresSQL 認證的詳細資訊：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   1. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   1. 從&#x200B;**[!UICONTROL 資料庫]**&#x200B;下拉式功能表的資料庫清單中，選取您沙箱的`cja`資料庫。 例如 `prod:cja`。

   1. 在 Jupyter Notebook 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

1. 在 RStudio 中：

   1. 確保您使用所需的資料庫。
   1. 在建立和執行連線時使用適當的值。
   1. 透過執行相關查詢來測試您的連線。

   成功後，您可以使用資料來建立報告和視覺效果。

   請參閱「[將 RStudio 連線到 Query Service ](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/rstudio)」以了解更多資訊。另請參閱「[BI 擴充功能使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」，了解詳細範例 (即使用 RPostgres 套件)。

+++

如需關於各種可用工具的概觀與更多資訊，請參閱「[將用戶端連接到 Query Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/overview)」。

請參閱「[使用案例](/help/use-cases/data-views/bi-extension-usecases.md)」，了解如何使用 Customer Journey Analytics BI 擴充功能來完成大量使用案例。

## 功能

依預設設定，您的資料檢視具有根據其易記名稱產生的表格適用名稱。例如，名為「[!UICONTROL 我的網路資料檢視]」的資料檢視具有檢視名稱「`my_web_data_view`」。您可以定義在 BI 工具中使用的資料檢視首選名稱。請參閱「[資料檢視設定](create-dataview.md#settings)」，了解更多資訊。

如果想要使用資料檢視 ID 作為表格名稱，可以在連線時於資料庫名稱新增選用的 `CJA_USE_IDS` 設定。例如，`prod:cja?CJA_USE_IDS` 使用如「`dv_ABC123`」這樣的名稱來顯示您的資料檢視。

### 資料控管

Customer Journey Analytics 中的任何資料控管相關設定，都是繼承自 Adobe Experience Platform。Customer Journey Analytics 和 Adobe Experience Platform Data Governance 整合後，便可以標記敏感的 Customer Journey Analytics 資料以及執行隱私權原則。

在 Experience Platform 使用的資料集上所建立的隱私權標籤和原則，可以出現在 Customer Journey Analytics 資料檢視工作流程中。因此，使用 [!DNL Customer Journey Analytics BI extension] 查詢的資料，若發生不符合所定義的隱私權標籤和原則的情況，便會顯示適當的警告或錯誤。

### 清單資料檢視

在標準 PostgreSQL CLI 中，可以使用 `\dv` 列出您的檢視

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres
```

### 巢狀與展平

依預設，資料檢視的綱要使用巢狀結構，就像原始的 XDM 綱要一樣。該整合也支援 `FLATTEN` 選項。您可以使用此選項強制展平資料檢視 (以及工作階段中的任何其他表格) 的結構描述。展平能讓不支援結構化綱要的 BI 工具變得更容易使用。請參閱「[在 Query Service 中使用巢狀資料結構](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)」以了解更多資訊。


### 預設和限制

使用 BI 擴充功能時，有下列額外的預設和限制：

* BI 擴充功能要求對查詢結果設定列限制。預設值為 50，但您可以在 SQL 中使用 `LIMIT n` 覆寫此值，範圍`n`在 1 - 50000 之間。
* BI 擴充功能需要日期範圍來限制用來計算的資料列。預設值為最近 30 天，但你可以在 SQL `WHERE` 條款中覆寫此設定，方法是使用特殊 [`timestamp`](#timestamp) 或者 [`daterange`](#date-range) 欄。
* BI 擴充功能需要彙總查詢。你不能使用 SQL `SELECT * FROM ...` 取得原始的底層列。從高層次來看，您的彙總查詢應該使用：
   * 使用 `SUM` 和/或 `COUNT` 來選取總計。<br/> 例如， `SELECT SUM(metric1), COUNT(*) FROM ...`
   * 選取按維度劃分的量度。<br/>例如，`SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
   * 選取不同的量度值。<br/>例如， `SELECT DISTINCT dimension1 FROM ...`

     如需更多詳細資訊，請參閱「[支援的 SQL](#supported-sql)」。


### 支援 SQL

有關支援哪些 SQL 類型的完整參考，請參閱「[Query Service SQL 參考](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/sql/overview)」。

有關可以使用的 SQL 範例，請參閱下表。

+++ 範例

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>模式</th>
            <th>範例</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>結構描述探索 </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>排名或劃分 </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> 子句 </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>不重複，頂端
維度值 </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>量度總計 </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>多維度
劃分
和頂端不重複 </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>子選擇：
篩選其他
結果 </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  按照 dim1 分組
)
其中 dim1 在 ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>子選擇：
查詢橫跨
資料視圖 </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>子選擇：
分層來源、
篩選，
以及彙總 </td>
            <td>使用子選擇分層：
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
使用 CTE WITH 的分層：
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>選取量度
先於或
混合於
維度者 </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### 維度

您可以選取依預設可用或在資料檢視中定義的任何維度。您可以使用維度 ID 來選取維度。

### 量度

可供選取的量度有：

* 依預設可用的任何量度；
* 在資料檢視中已定義；
* 相容於使用者有權存取之資料檢視的計算量度。

您可以把量度 ID 包含在 `SUM(metric)` 運算式中來選取量度，就像處理其他 SQL 來源一樣。

您可以使用：

* `SELECT COUNT(*)` 或 `COUNT(1)` 以取得發生次數量度。
* `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 以計算某個維度的近似不重複值。詳細資訊請參閱「[計數不重複值](#counting-distinct-values)」。
* [內聯計算](#inline-calculations)可動態組合量度和/或對其進行數學計算。

#### 計算不重複值

由於 Customer Journey Analytics 運作原理的根本性質，可以獲得精確不重複計數的唯一維度是 `adobe_personid` 維度。以下 SQL 陳述式 `SELECT COUNT(DISTINCT adobe_personid)` 或者 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 傳回預設人員量度的數值，即不重複人員的計數。對於其他維度，傳回近似的不重複計數。

#### 條件式量度

您可以嵌入一個 `IF` 或者 `CASE` 子句在 `SUM` 或 `COUNT` 函數中，以便新增所選量度特定的其他劃分條件。新增這些子句類似於將區段套用至工作區報告表格中的量度欄。

範例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### 內聯計算

您可以在您 `SELECT` 內的量度運算式套用更多數學運算。可以使用此數學運算，取代在計算量度中定義數學運算。下表列出所支援的運算式類型。

| 運算子或函數 | 詳細資料 |
|---|---|
| `+`、`-`、`*`、`/` 和 `%` | 加、減、乘、除和模數/餘數 |
| `-X` 或 `+X` | 變更符號或量度，其中 X 是量度運算式 |
| `PI()` | π 常數 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、 `ASIN`、`ATAN`、`COSH`、`SINH` 與 `TANH` | 一元數學函數 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二進位數學函數 |

{style="table-layout:auto"}

### 特殊欄

#### 時間戳記

`timestamp` 特殊欄用於提供查詢的日期範圍。日期範圍可用 `BETWEEN` 運算式或一對 `timestamp` `>`、`>=`、`<`、`<=` 檢查項用 `AND` 連結在一起。
`timestamp` 是選用的，如果未提供完整範圍，則使用預設值：

* 如果僅提供最小值 (`timestamp > X` 或者 ` timestamp >= X`)，範圍是從 X 到現在。
* 如果僅提供最大值 (`timestamp < X` 或者 `timestamp <= X`)，範圍為 X 減 30 天至 X。
* 如果未提供任何內容，則範圍是從現在減 30 天至現在。

時間戳記範圍將轉換為 RankedRequest 的日期範圍全域區段。
時間戳記欄位也可以用於「日期時間」函數以剖析或截斷事件時間戳記。

#### 日期範圍

`daterange` 特別欄的運作原理類似於 `timestamp`，但是劃分僅限於全天。`daterange` 也是選用的，而且具有和 `timestamp` 相同的預設範圍。
`daterange` 欄位也可以用於「日期時間」函數以剖析或截斷事件日期。

 `daterangeName` 特殊欄可用於使用命名的日期範圍 (例如 `Last Quarter`) 來劃分查詢。

>[!NOTE]
>
>Power BI 不支援少於一天 (小時、30 分鐘、5 分鐘等) 的 `daterange` 量度。
>

#### 區段 ID

`filterId` 特殊欄是選擇性的，且用於將外部定義的區段套用至查詢。將外部定義的區段套用至查詢，類似於將區段拖曳到工作區的面板上。您可以透過進行 `AND` 的方式使用多個區段 ID。

有 `filterId` 時，您可以透過 `filterName` 來使用區段名稱而非 ID。

### WHERE 子句

`WHERE` 子句的處理分為三個步驟：

1. 從`timestamp`、`daterange` 或 `daterangeName` 特殊欄位尋找日期範圍。

1. 尋找任何外部定義的 `filterId` 或 `filterName` 以納入區段。

1. 將其餘的運算式轉變為臨時區段。

透過剖析第一層的 `AND` (在 `WHERE` 子句中) 來完成處理。每個用 `AND`-ed 方式連結的頂層運算式必須與上方其中一個相符。任何比第一層的 `AND` 更深的內容，或者，如果 `WHERE` 子句在頂層使用 `OR`，則做為臨時區段處理。

### 排序順序

依預設，查詢會依照第一個選取的量度以遞減順序對結果進行排序。您可以透過指定 `ORDER BY ... ASC` 或 `ORDER BY ... DESC` 覆寫預設的排列順序。如果您使用 `ORDER BY`，則必須在第一個選定的量度上指定 `ORDER BY`。

您也可以在量度前面使用 `-` (減號)，來反轉順序。下面的兩個陳述式都會產生相同的順序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般函數支援

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 目前不支援類型轉換，但不會引發錯誤。`CAST` 函數被忽略。 |
| [時間戳記](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 將時間字串剖析為時間戳記以供 `WHERE` 子句使用。 |
| [至時間戳記](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 將時間字串剖析為時間戳記以供 `WHERE` 子句使用，可選擇提供該時間字串的格式。 |
| [日期](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 將日期字串剖析為時間戳記以供 `WHERE` 子句使用。 |
| [至日期](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 將日期字串剖析為時間戳記以供 `WHERE` 子句使用，可選擇提供該日期字串的格式。 |

{style="table-layout:auto"}

### 維度函數支援

這些函數可以用於 `SELECT`、`WHERE` 子句中的維度，或條件式量度。

**字串函數**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在傳入的欄位上產生動態的維度身分識別。 |

{style="table-layout:auto"}

**日期時間函數**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [年](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [月](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [日](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [星期](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。 |
| [一年當中的第幾天](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [週](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [季度](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [小時](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。 |
| [分鐘](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。 |
| [擷取](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。對於此函數的某些部分，請使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。<br/>支援的部份有：<br> - 關鍵字：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 字串：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [日期 (部分)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。對於此函數的某些部分，請使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。<br/>支援的字串部分有：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [日期 (截斷)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在傳入的欄位上產生動態的維度身分識別。<br/>支援的字串詳細程度有：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |

{style="table-layout:auto"}

### 部分支援

某些 SQL 功能僅部分受 BI 擴充功能支援，並且不會傳回與其他資料庫所看到相同的結果。此特定功能是在由各種 BI 工具產生的 SQL 中使用，而 BI 擴充功能沒有完全匹配的 SQL。因此，BI 擴充功能會著重在有限的實施，且其中使用最少的 BI 工具而不會引發錯誤。如需詳細資訊，請參閱下列表格。

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| MIN() 和 MAX() | ``MIN(daterange)`` 或 <br/> ``MAX(daterange)`` | `timestamp`、`daterange` 或任何 `daterangeX` (如 `daterangeday`) 的 `MIN()` 將傳回 2 年前。<br/><br/> `timestamp`、`daterange` 或任何 `daterangeX` (如 `daterangeday`) 的 `MAX()` 將傳回目前的日期/時間。任何其他維度、量度或運算式的 <br/><br/>`MIN()` 或 `MAX()` 都會傳回 0。 |

{style="table-layout:auto"}
