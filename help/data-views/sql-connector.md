---
title: SQL 連接器
description: 了解如何透過 SQL 連接器使用 Query Service、Power BI 和/或 Tableau 來存取資料檢視。
solution: Customer Journey Analytics
feature: SQL Connector
hide: true
hidefromtoc: true
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
source-git-commit: 1b03689820c91a823cd7cf8ff42e3f5ee46083e5
workflow-type: ht
source-wordcount: '2938'
ht-degree: 100%

---

# SQL 連接器

{{release-limited-testing}}

{{select-package}}

[!DNL Customer Journey Analytics SQL Connector] 讓 SQL 可以存取您在 Customer Journey Analytics 中定義的[資料檢視](./data-views.md)。您的資料工程師和分析師可能更熟悉 Power BI、Tableau 或其他企業情報和視覺化工具 (也稱為 BI 工具)。他們現在可以根據 Customer Journey Analytics 使用者在建立 Analysis Workspace 專案時所使用的相同資料檢視來建立報告和儀表板。

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) 是 SQL 與 Experience Platform 資料湖中可用資料之間的介面。啟用 [!DNL Customer Journey Analytics SQL Connector] 之後即可延伸 [!DNL Query Service] 的功能，讓您在 [!DNL Query Service] 工作階段中以表格或視圖形式查看 Customer Journey Analytics 資料檢視。因此，使用 [!DNL Query Service] 作為 PostgresSQL 介面的企業情報工具，可以直接立即受益於這項延伸功能。

主要優點包括：

- 無需在 BI 工具之內重新建立 Customer Journey Analytics 資料檢視的同等呈現形式。<br/>有關資料檢視功能的更多資訊，請參閱「[資料檢視](data-views.md)」以了解必須重新建立的內容。<br/>

- BI 工具和 Customer Journey Analytics 之間的報告和分析維持更高的一致性。

- 結合 Customer Journey Analytics 資料與 BI 工具中已有的其他資料來源。

## 先決條件

若要使用此功能，您必須

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

- 設定相關產品設定檔、使用者群組和/或個別使用者的功能。<br/>
使用者必須具有以下項目的存取權：
   - Experience Platform Query Service，
   - Customer Journey Analytics Workspace 專案，以及
   - 他們想要使用的 Customer Journey Analytics 資料檢視。

- 使用有到期日或無到期日的認證將 BI 工具連接到 Customer Journey Analytics SQL 連接器。[認證指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en)提供關於設定有到期日的認證或無到期日的認證之詳細資訊。

如需其他資訊，請參閱 Customer Journey Analytics 管理區段的「[存取控制](../admin/cja-access-control.md)」。


## 使用情況

要使用 [!DNL Customer Journey Analytics SQL Connector] 功能，您可以直接使用 SQL 或使用特定的 BI 工具所提供的拖放體驗。

### SQL

您可以使用查詢編輯器或標準 PostgresSQL 命令列介面 (CLI) 用戶端，直接在 SQL 陳述式中使用該功能。

+++ 查詢編輯器

在 Experience Platform UI 中：

1. 在左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(從「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」)。

2. 選取「![建立查詢](assets/Smock_AddCircle_18_N.svg)**[!UICONTROL **&#x200B;建立查詢&#x200B;**]**」。

3. 若要執行查詢，請鍵入 SQL 陳述式並選取「![播放](assets/Smock_Play_18_N.svg)」按鈕 (或按 SHIFT + ENTER)。

+++


+++ PostgresSQL CLI

1. 在 Experience Platform UI 中，搜尋並複製您的 PostgresSQL 認證：

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   2. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   3. 要複製連接字串，請使用「![複製](assets/Smock_Copy_18_N.svg)」(在「**[!UICONTROL ** PSQL 指令&#x200B;**]**」區段)。

2. 開啟 PostgresSQL CLI。

3. 要登入並開始執行查詢，請將連接字串貼上到 PostgresSQL CLI。

+++

請參閱「[查詢編輯器 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en)」以了解更多資訊。


### BI 工具

目前，Customer Journey Analytics SQL 連接器僅支援 Power BI 和 Tableau 並通過測試。其他使用 PSQL 介面的 BI 工具可能也可以運作，但尚未得到正式支援。

+++ Power BI

1. 在 Adobe Experience Platform UI 中，尋找您的 PostgresSQL 認證的詳細資訊。

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   2. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   3. 在 Power BI 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

2. 在 Power BI 中：

   1. 在主視窗中，從頂端列選取「**[!UICONTROL **&#x200B;取得資料&#x200B;**]**」。

   2. 在左側邊欄中選取「**[!UICONTROL **&#x200B;更多...**]**」。

   3. 在「**取得資料**」畫面中，搜尋 `PostgresSQL`，並從清單中選取「**[!UICONTROL ** PostgresSQL 資料庫&#x200B;**]**」。

   4. 在「**[!UICONTROL ** PostgressSQL 資料庫&#x200B;**]**」對話方塊中：

      1. 將「**[!UICONTROL **&#x200B;主機&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;伺服器&#x200B;**]**」文字欄位。

      2. 將「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」文字欄位。

         將 `?FLATTEN` 新增到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數，以便讀起來像 `prod:cja?FLATTEN`。請參閱「[將巢狀資料結構展平以供協力廠商 BI 工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en)」以了解更多資訊。

      3. 在出現「**[!UICONTROL **&#x200B;資料連線&#x200B;**]**」模式的提示時，選取「**[!UICONTROL ** DirectQuery **]**」以確保資料結構適當地展平。

      4. 系統會提示您輸入「**[!UICONTROL **&#x200B;使用者名稱&#x200B;**]**」和「**[!UICONTROL **&#x200B;密碼&#x200B;**]**」。使用 Experience Platform 查詢[!UICONTROL 認證]的同等參數。


   5. 成功登入之後，Power BI 的&#x200B;**[!UICONTROL **&#x200B;導覽器&#x200B;**]**&#x200B;中會顯示 Customer Journey Analytics 資料檢視表格。在資料檢視表格的名稱中使用 `dv_` 以利識別。


   6. 選取您要使用的資料檢視表格並選取「**[!UICONTROL **&#x200B;載入&#x200B;**]**」。

   與一個或多個所選表格關聯的所有維度和指標顯示在右窗格，您隨時可以用於視覺化。

   請參閱「[將 Power BI 連接到 Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en)」以了解更多資訊。

+++

+++Tableau

1. 在 Experience Platform UI 中，尋找 PostgresSQL 認證的詳細資訊。

   1. 從左側邊欄選取「**[!UICONTROL **&#x200B;查詢&#x200B;**]**」(在「**[!UICONTROL **&#x200B;資料管理&#x200B;**]**」之下)。

   2. 從頂端列選取「**[!UICONTROL **&#x200B;認證&#x200B;**]**」。

   3. 在 Tableau 中需要時，使用「![複製](assets/Smock_Copy_18_N.svg)」複製每個 Postgres 認證參數 ([!UICONTROL 主機]、[!UICONTROL 連接埠]、[!UICONTROL 資料庫]、[!UICONTROL 使用者名稱]與其他)。

2. 在 Tableau 中：

   1. 在左側邊欄，選取「**[!UICONTROL **&#x200B;更多&#x200B;**]**」(從「**[!UICONTROL **&#x200B;至伺服器&#x200B;**]**」)。

   2. 從清單中選取「**[!UICONTROL ** PostgresSQL **]**」。

   3. 在「[!UICONTROL PostgresSQL]」對話方塊中：

      1. 將「**[!UICONTROL **&#x200B;主機&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;伺服器&#x200B;**]**」文字欄位。

      2. 將「**[!UICONTROL **&#x200B;連接埠&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;連接埠&#x200B;**]**」文字欄位。

      3. 將「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」文字欄位。

         將 `%3FFLATTEN` 新增到「**[!UICONTROL **&#x200B;資料庫&#x200B;**]**」參數，以便讀起來像 `prod:cja%3FFLATTEN`。請參閱「[將巢狀資料結構展平以供協力廠商 BI 工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en)」以了解更多資訊。

      4. 選取「**[!UICONTROL **&#x200B;使用者名稱和密碼&#x200B;**]**」(從「**[!UICONTROL **&#x200B;驗證&#x200B;**]**」清單)。

      5. 將「**[!UICONTROL **&#x200B;使用者名稱&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;使用者名稱&#x200B;**]**」文字欄位。

      6. 將「**[!UICONTROL **&#x200B;密碼&#x200B;**]**」參數 (取自 Experience Platform 查詢[!UICONTROL 認證]) 貼上到「**[!UICONTROL **&#x200B;密碼&#x200B;**]**」文字欄位。

      7. 選取「**[!UICONTROL **&#x200B;登入&#x200B;**]**」。

   4. Customer Journey Analytics 資料檢視顯示為「**[!UICONTROL **&#x200B;表格&#x200B;**]**」清單中的表格。資料檢視表格的前置詞為 `dv_`。

   5. 將想要使用的表格拖曳到畫布上。

   現在您可以使用資料檢視表格中的資料建立報告和視覺化。

   請參閱「[將 Tableau 連線到 Query Service ](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en)」以了解更多資訊。

+++

如需關於各種可用工具的概觀與更多資訊，請參閱「[將用戶端連接到 Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en)」。

## 功能

依預設設定，您的資料檢視具有根據其易記名稱產生的表格適用名稱。例如，名為「[!UICONTROL 我的網路資料]」的資料檢視具有檢視名稱「`dv_my_web_data`」。

如果想要使用資料檢視 ID 作為表格名稱，可以在連線時於資料庫名稱新增選用的 `CJA_USE_IDS` 設定。例如，`prod:all?CJA_USE_IDS` 使用如「`dv_ABC123`」這樣的名稱來顯示您的資料檢視。

### 資料控管

Customer Journey Analytics 中的任何資料控管相關設定，都是繼承自 Adobe Experience Platform。Customer Journey Analytics 和 Adobe Experience Platform Data Governance 整合後，便可以標記敏感的 Customer Journey Analytics 資料以及執行隱私權原則。

在 Experience Platform 使用的資料集上所建立的隱私權標籤和原則，可以出現在 Customer Journey Analytics 資料檢視工作流程中。因此，使用 Customer Journey Analytics SQL 連接器查詢的資料，若發生不符合所定義的隱私權標籤和原則的情況，便會顯示適當的警告或錯誤。

### 清單資料檢視

在標準 PostgreSQL CLI 中，可以使用 `\dv` 列出您的檢視

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### 巢狀與展平

依預設，資料檢視的綱要使用巢狀結構，就像原始的 XDM 綱要一樣。該整合也支援 `FLATTEN` 選項。您可以使用此選項強制展平資料檢視 (以及工作階段中的任何其他表格) 的綱要。展平能讓不支援結構化綱要的 BI 工具變得更容易使用。請參閱「[在 Query Service 中使用巢狀資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en)」以了解更多資訊。

### 支援 SQL

有關支援哪些 SQL 類型的完整參考，請參閱「[Query Service SQL 參考](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en)」。

有關可以使用的 SQL 範例，請參閱下表。

+++ 範例

| 模式 | 範例 |
|---|---|
| 結構探索 | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| 排名/分解 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  filterId = &#39;12345&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39; AND<br/>  AND (dim2 = &#39;A&#39; OR dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;))<br/>GROUP BY dim1</pre> |
| HAVING 子句 | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| 不重複，頂端<br/>維度值 | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= &#39;2022-01-01&#39; AND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| 量度總計 | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</pre> |
| 多維度<br/>分解<br/>和頂端不重複 | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| 子選擇：<br/>其他結果<br/>篩選 | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| 子選擇：<br/>加入<br/>不在 <br/>Customer Journey Analytics 內的資料集 | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| 子選擇：<br/>查詢橫跨<br/>多個資料檢視 | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| 子選擇：<br/>分層來源、<br/>篩選<br/>和彙總 | 使用子選擇分層：<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WHERE \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>使用 CTE WITH 的分層：<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN &#39;2021-01-01&#39; AND &#39;2021-02-01&#39;<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| 選取<br/>量度先於<br/>或混合於<br/>維度者 | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN &#39;2022-01-01&#39; AND &#39;2022-01-02&#39;<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### 維度

您可以選取依預設可用或在資料檢視中定義的任何維度。您可以使用維度 ID 來選取維度。

### 量度

可供選取的量度有：

- 依預設可用的任何量度，

- 在資料檢視中已定義，

- 相容於使用者有權存取之資料檢視的計算量度。

您可以把量度 ID 包含在 `SUM(metric)` 運算式中來選取量度，就像處理其他 SQL 來源一樣。

您可以使用：

- `SELECT COUNT(*)` 或 `COUNT(1)` 以取得發生次數量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 以計算某個維度的近似不重複值。詳細資訊請參閱「[計數不重複](#counting-distincts)」。

- [內聯計算](#inline-calculations)可動態組合量度和/或對其進行數學計算。

#### 計數不重複

由於 Customer Journey Analytics 運作原理的根本性質，可以獲得精確不重複計數的唯一維度是 `adobe_personid` 維度。以下 SQL 陳述式 `SELECT COUNT(DISTINCT adobe_personid)` 或者 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 傳回預設人員量度的數值，即不重複人員的計數。對於其他維度，傳回近似的不重複計數。

#### 條件式量度

您可以嵌入一個 `IF` 或者 `CASE` 子句在 `SUM` 或 `COUNT` 函數中，以便新增所選量度特定的其他篩選條件。新增這些子句類似於將篩選器套用至工作區報告表格中的量度欄。

範例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 內聯計算

您可以額外套用到 `SELECT` 的量度運算式，而不是在計算量度中定義數學。下表列出所支援的運算式類型。

| 運算子或函數 | 詳細資料 |
|---|---|
| `+`、`-`、`*`、`/` 和 `%` | 加、減、乘、除和模數/餘數 |
| `-X` 或 `+X` | 變更符號或量度，其中 X 是量度運算式 |
| `PI()` | π 常數 |
| `POSITIVE`、`NEGATIVE`、`ABS`、`FLOOR`、`CEIL`、`CEILING`、`EXP`、`LN`、`LOG10`、`LOG1P`、`SQRT`、`CBRT`、`DEGREES`、`RADIANS`、`SIN`、`COS`、`TAN`、`ACOS`、 `ASIN`、`ATAN`、`COSH`、`SINH` 與 `TANH` | 一元數學函數 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二進位數學函數 |

{style="table-layout:auto"}

### 特殊欄

**時間戳記**

`timestamp` 特殊欄用於提供查詢的日期範圍。日期範圍可用 `BETWEEN` 運算式或一對 `timestamp` `>`、`>=`、`<`、`<=` 檢查項用 `AND` 連結在一起。
`timestamp` 是選用的，如果未提供完整範圍，則使用預設值：

- 如果僅提供最小值 (`timestamp > X` 或者 ` timestamp >= X`)，範圍是從 X 到現在。

- 如果僅提供最大值 (`timestamp < X` 或者 `timestamp <= X`)，範圍為 X-30 天到 X。

- 如果未提供任何內容，則範圍是從現在 -30 天到現在。

時間戳記範圍將轉換為 RankedRequest 的日期範圍全域篩選條件。
時間戳記欄位也可以用於「日期時間」函數以剖析、截斷事件時間戳記。

**日期範圍**

`daterange` 特別欄的運作原理類似於 `timestamp`，但是篩選僅限於全天。`daterange` 也是選用的，而且具有和 `timestamp` 相同的預設範圍。
`daterange` 欄位也可以用於「日期時間」函數以剖析、截斷事件日期。

**filterId**

`filterId` 特殊欄是選用的，且用於將外部定義的篩選條件套用至查詢。將外部定義的篩選器套用至查詢，類似於將篩選條件拖曳到工作區的面板上。您可以透過 `AND` 的方式提供多個篩選條件 ID。

### WHERE 子句

WHERE 子句的處理分為三個步驟：

1. 從 `timestamp` 特殊欄位尋找日期範圍。

2. 尋找任何外部定義的 `filterId` 以納入篩選條件。

3. 將其餘的運算式轉變為臨時篩選條件。

透過剖析第一層的`AND` (在 `WHERE` 子句中) 來完成處理。每個用 `AND` 方式連結的頂層運算式必須與上方其中一個相符。任何比第一層的 `AND` 更深的東西，或者，如果 `WHERE` 子句在頂層使用 `OR`，則作為臨時篩選條件處理。

### ORDER BY

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
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 目前不支援類型轉換，但不會引發錯誤。`CAST` 函數被忽略。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 將時間字串剖析為時間戳記以供 `WHERE` 子句使用。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 將時間字串剖析為時間戳記以供 `WHERE` 子句使用，可選擇提供該時間字串的格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 將日期字串剖析為時間戳記以供 `WHERE` 子句使用。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 將日期字串剖析為時間戳記以供 `WHERE` 子句使用，可選擇提供該日期字串的格式。 |

{style="table-layout:auto"}

### 維度函數支援

這些函數可以用於 `SELECT`、`WHERE` 子句中的維度，或條件式量度。

**字串函數**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在傳入的欄位上產生動態的維度識別。 |

{style="table-layout:auto"}

**日期時間函數**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [YEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [MONTH(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [DAY(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [DAYOFWEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。 |
| [DAYOFYEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [WEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [QUARTER(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [HOUR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。 |
| [MINUTE(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在傳入的欄位上產生動態的維度識別。 |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在傳入的欄位上產生動態的維度識別。對於此函數的某些部分，請使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。<br/>支援的部份有：<br> - 關鍵字：`YEAR`、`MONTH`、`DAYOFMONTH`、`DAYOFWEEK`、`DAYOFYEAR`、`WEEK`、`QUARTER`、`HOUR`、`MINUTE`。<br/>- 字串：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [DATE_PART(part, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在傳入的欄位上產生動態的維度識別。對於此函數的某些部分，請使用項目 ID 而不是值，因為您需要的是數字而不是易記名稱。<br/>支援的字串部分有：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |
| [DATE_TRUNC(granularity, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在傳入的欄位上產生動態的維度識別。<br/>支援的字串詳細程度有：`'YEAR'`、`'Y'`、`'MONTH'`、`'M'`、`'DAYOFMONTH'`、`'DAY'`、`'D'`、`'DAYOFWEEK'`、`'DOW'`、`'DAYOFYEAR'`、`'DOY'`、`'WEEK'`、`'WOY`、`'W'`、`'QUARTER'`、`'QOY'`、`'Q'`、`'HOUR'` 或 `'MINUTE'`。 |

{style="table-layout:auto"}
