---
title: SQL Connector
description: 了解如何使用Query Service、Tableau和/或Tableau來使用SQL Connector存取資料檢視。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 4205995fdc54e4d7626f17de79573751a5c63d26
workflow-type: tm+mt
source-wordcount: '2879'
ht-degree: 2%

---

# SQL Connector

{{release-limited-testing}}

此 [!DNL Customer Journey Analytics (CJA) SQL Connector] 啟用對 [資料檢視](./data-views.md) 在CJA中定義的規則。 您的資料工程師和分析師可能更熟悉Power BI、Tableau或其他商業智慧和視覺化工具（進一步稱為BI工具）。 現在，他們可以根據CJA使用者建立其Analysis Workspace專案時所使用的相同資料檢視，來建立報表和控制面板。

Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant?lang=tw) 是SQL介面，用於資料湖中可用的資料Experience Platform。 使用 [!DNL CJA SQL Connector] 已啟用， [!DNL Query Service] 可延伸，以在 [!DNL Query Service] 工作階段。 因此，使用商業智慧工具 [!DNL Query Service] 由於其PostgresSQL介面可從這一擴展功能中無縫獲益。

主要好處是：

- 無需在BI工具本身內重新建立CJA資料檢視的相等表示法。 <br/>請參閱 [資料檢視](data-views.md) 如需資料檢視功能的詳細資訊，請了解必須重新建立的項目。<br/>

- BI工具和CJA之間的報表和分析更一致。

- 將CJA資料與BI工具中已提供的其他資料來源結合。

## 先決條件

若要使用此功能，您必須

- 啟用 [!UICONTROL CJA SQL Connector] 在您的Experience Platform組織中。

- 設定相關產品設定檔、使用者群組和/或個別使用者的功能。<br/>
使用者必須擁有下列權限：
   - Experience Platform查詢服務、
   - CJA工作區專案和
   - CJA資料檢視他們想使用。

- 對未到期的憑證使用到期前連結，將BI工具連接至CJA SQL Connector。 請參閱 [認證指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 有關設定即將到期的憑據或未到期的憑據的詳細資訊。


## 使用狀況

若要使用 [!DNL CJA SQL Connector] 功能，您可以直接使用SQL，或使用特定BI工具中可用的拖放體驗。

### SQL

您可以使用查詢編輯器或標準PostgresSQL命令行介面(CLI)客戶端，直接在SQL陳述式中使用該功能。

+++ 查詢編輯器

在Experience PlatformUI中：

1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從 **[!UICONTROL **&#x200B;資料管理&#x200B;**]** 在左側邊欄。

2. 選擇 ![建立查詢](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;建立查詢&#x200B;**]**.

3. 要執行查詢，請鍵入SQL陳述式並選擇 ![播放](assets/Smock_Play_18_N.svg) 按鈕（或按SHIFT + ENTER鍵）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查找並複製您的PostgresSQL憑證：

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄(下方 **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑證&#x200B;**]** 的上界。

   3. 若要複製連線字串，請使用 ![複製](assets/Smock_Copy_18_N.svg) 在 **[!UICONTROL ** PSQL命令&#x200B;**]** 區段。

2. 開啟PostgresSQL CLI。

3. 要登錄並開始執行查詢，請將連接字串貼到PostgresSQL CLI中。

+++

請參閱 [查詢編輯器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 以取得更多資訊。


### BI工具

目前，Power BI和Tableau均支援CJA SQL Connector。

+++ Power BI

1. 在Adobe Experience Platform UI中，查找PostgresSQL憑證的詳細資訊。

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄(下方 **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑證&#x200B;**]** 的上界。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 複製每個Postgres憑據參數([!UICONTROL 主機], [!UICONTROL 埠], [!UICONTROL 資料庫], [!UICONTROL 使用者名稱]等)，以滿足Power BI的需求。

2. 在Power BI中：

   1. 在主窗口中，選擇 **[!UICONTROL **&#x200B;取得資料&#x200B;**]** 的上界。

   2. 選擇 **[!UICONTROL **&#x200B;更多……**]** 在左側邊欄。

   3. 在 **取得資料** 螢幕，搜索 `PostgresSQL` ，然後選取 **[!UICONTROL ** PostgresSQL資料庫&#x200B;**]** 從清單中。

   4. 在 **[!UICONTROL ** PostgressSQL資料庫&#x200B;**]** 對話框：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 文字欄位。

      2. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] in **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 文字欄位。

         新增 `?FLATTEN` 到 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數，所以看起來就像 `prod:all?FLATTEN` 例如， 請參閱 [平面化巢狀資料結構以搭配第三方BI工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得更多資訊。

      3. 提示輸入時 **[!UICONTROL **&#x200B;資料連接&#x200B;**]** 模式，選擇 **[!UICONTROL ** DirectQuery **]** 以確保資料結構會正確平面化。

      4. 系統提示您 **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** 和 **[!UICONTROL **&#x200B;密碼&#x200B;**]**. 從Experience Platform查詢使用等效參數 [!UICONTROL 憑證].
   5. 成功登入後，CJA資料檢視表格會顯示在Power BI的 **[!UICONTROL **&#x200B;導覽器&#x200B;**]**. 資料檢視表格的識別方式為： `dv_` 在他們的名字裡。


   6. 選擇要使用的資料視圖表並選擇 **[!UICONTROL **&#x200B;載入&#x200B;**]**.

   與一或多個所選表格相關聯的所有維度和量度都會顯示在右窗格中，供您視覺化使用。

   請參閱 [將Power BI連接到查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 以取得更多資訊。

+++

+++Tableau

1. 在Experience PlatformUI中，查找PostgresSQL憑證的詳細資訊。

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左側邊欄(下方 **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑證&#x200B;**]** 的上界。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 複製每個Postgres憑據參數([!UICONTROL 主機], [!UICONTROL 埠], [!UICONTROL 資料庫], [!UICONTROL 使用者名稱]，及其他)。

2. 在Tableau中：

   1. 選擇 **[!UICONTROL **&#x200B;更多&#x200B;**]** 從 **[!UICONTROL **&#x200B;到伺服器&#x200B;**]** 在左側邊欄。

   2. 選擇 **[!UICONTROL ** PostgresSQL **]** 從清單中。

   3. 在 [!UICONTROL PostgresSQL] 對話框：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 文字欄位。

      2. 貼上 **[!UICONTROL **&#x200B;埠&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;埠&#x200B;**]** 文字欄位。

      3. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 文字欄位。

         新增 `%3FFLATTEN` 到 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數，所以看起來就像 `prod:all%3FFLATTEN` 例如， 請參閱 [平面化巢狀資料結構以搭配第三方BI工具使用](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得更多資訊。

      4. 選擇 **[!UICONTROL **&#x200B;使用者名稱和密碼&#x200B;**]** 從 **[!UICONTROL **&#x200B;驗證&#x200B;**]** 清單。

      5. 貼上 **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;使用者名稱&#x200B;**]** 文字欄位。

      6. 貼上 **[!UICONTROL **&#x200B;密碼&#x200B;**]** 來自Experience Platform查詢的參數 [!UICONTROL 憑證] into **[!UICONTROL **&#x200B;密碼&#x200B;**]** 文字欄位。

      7. 選擇 **[!UICONTROL **&#x200B;登入&#x200B;**]**.
   4. CJA資料檢視在 **[!UICONTROL **&#x200B;表格&#x200B;**]** 清單。 資料檢視表格的前置詞為 `dv_`.

   5. 拖曳您要在畫布上使用的表格。

   您現在可以使用資料檢視表格中的資料，以建立報表和視覺效果。

   請參閱 [將Tableau連接至查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 以取得更多資訊。

+++

請參閱 [將客戶端連接到查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 以取得各種可用工具的概觀和詳細資訊。

## 功能

依預設，您的資料檢視會從其好記名稱產生表格安全名稱。 例如，資料檢視命名為 [!UICONTROL 我的Web資料] 有檢視名稱 `dv_my_web_data`.

如果您想使用資料檢視ID作為表格名稱，則可新增選用 `CJA_USE_IDS` 在連接時將設定為資料庫名稱。 例如， `prod:all?CJA_USE_IDS` 以 `dv_ABC123`.

### 資料控管

Customer Journey Analytics中與資料控管相關的設定繼承自Adobe Experience Platform。 CJA 與 Adobe Experience Platform 資料控管之間的整合可讓您標示敏感的 CJA 資料強制執行隱私權原則。

在 Experience Platform 使用的資料集上建立的隱私權標籤和原則，可以在 CJA 資料檢視工作流程中出現。因此，使用CJA SQL Connector查詢的資料在不符合所定義的隱私權標籤和原則時，會顯示適當的警告或錯誤。

### 清單資料檢視

在標準PostgreSQL CLI中，可以使用 `\dv`

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

### 巢狀與平面化

依預設，資料檢視的結構會使用巢狀結構，就像原始XDM結構一樣。 整合也支援 `FLATTEN` 選項。 您可以使用此選項來強制平面化資料檢視（以及工作階段中的任何其他表格）的結構。 拼合功能可讓不支援結構化結構的BI工具更輕鬆使用。 請參閱 [在查詢服務中使用巢狀資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 以取得更多資訊。

### 支援的SQL

請參閱 [查詢服務SQL參考](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以獲得支援的SQL類型的完整參考。

如需模式和範例的概觀，請參閱下方的「模式」表格。

+++模式

| 圖樣 | 範例 |
|---|---|
| 架構發現 | <pre>從1=0的dv1中選擇*</pre> |
| 排名/劃分 | <pre>選取「維度1」、「總和（量度1）」作為m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按維1分組</pre><pre>選取「維度1」、「總和（量度1）」作為m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，以及<br/>  filterId = &#39;12345&#39;<br/>按維1分組</pre><pre>選取「維度1」、「總和（量度1）」作為m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，以及<br/>  和(dim2 = &#39;A&#39;或dim3, IN(&#39;X&#39;、&#39;Y&#39;、&#39;Z&#39;))<br/>按維1分組</pre> |
| HAVING子句 | <pre>選取「維度1」、「總和（量度1）」作為m1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按維1分組<br/>m1 > 100 |
| 不同，頂部 <br/>維度值 | <pre>從dv1中選擇DISTINCT DIM1</pre><pre>選擇DIM1作為dv1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按維1分組</pre><pre>選擇DIM1作為dv1<br/>從dv1<br/>其中\&#39;timestamp\&#39; >= &#39;2022-01-01&#39;和\&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>按維1分組<br/>依總和排序（量度1）<br/>上限15</pre> |
| 量度總計 | <pre>將SUM(metric1)選為M1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</pre> |
| 多維度<br/>劃分<br/>和頂尖 | <pre>選取「維度1」、「維度2」、「總和（量度1）」和「m1」<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按dim1、dim2分組</pre><pre>選取「維度1」、「維度2」、「總和（量度1）」和「m1」<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按1、2分組<br/>按1、2排序</pre><pre>選擇DISTINCT DIM1, dim2<br/>從dv1</pre> |
| 子選擇：<br/>其他結果<br/>篩選 | <pre>選擇dim1, m1<br/>從(<br/>  選取「維度1」、「總和（量度1）」作為m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</br>  按維1分組<br/>)<br/>其中dim1 in(&#39;A&#39;, &#39;B&#39;)</pre> |
| 子選擇：<br/>加入<br/>資料集未在<br/>CJA | <pre>選取b.key、a.dim1、a.m1<br/>從(<br/>  選取「維度1」、「總和（量度1）」作為m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按維1分組<br/>)<br/>a.dim1 = b.key上的左側聯接查閱b</pre> |
| 子選擇：<br/>跨<br/>資料檢視 | <pre>SELECT KEY, SUM(m1)AS total<br/>從(<br/>  選取「dim1」作為索引鍵，「SUM(metric1)」作為m1<br/>  從dv1<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按維1分組<br/><br/>  聯合<br/><br/>  選擇DIM2作為鍵，SUM(m1)作為m1<br/>  從dv2<br/>  其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按DIM2分組<br/>按鍵分組<br/>按合計訂購</pre> |
| 子選擇： <br/>分層源， <br/>篩選， <br/>和匯總 | 使用子選項分層：<br><pre>選擇ROWS.dim1, SUM(rows.m1)AS total<br/>從(<br/>  選擇\_.dim1,\_.m1<br/>  從(<br/>    從dv1中選擇\*<br/>    其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  )\_<br/>  其中\_.dim1 in(&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>)列<br/>按1分組<br/>按合計訂購</pre><br/>使用CTE與的層：<br/><pre>將行作為(<br/>  「\_」為(<br/>    SELECT * FROM data_ares<br/>    其中\&#39;timestamp\&#39;介於&#39;2021-01-01&#39;和&#39;2021-02-01&#39;之間<br/>  )<br/>  選擇_.item,_.units FROM _<br/>  其中_.item不是NULL<br/>)<br/>選擇ROWS.item, SUM(rows.units)AS單位<br/>從(「A」、「B」、「C」)中的rows.item<br/>按行.item分組</pre> |
| 選取<br/>量度之前<br/> 或與<br/>維度 | <pre>選擇SUM(metric1)AS m1, dim1<br/>從dv1<br/>其中\&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按2分組</pre> |

{style="table-layout:auto"}

+++

### 維度

您可以選取任何預設可用或在資料檢視中定義的維度。 您可以依其ID選取維度。

### 量度

可供選取的量度為：

- 任何預設可用的量度，

- 定義，

- 與使用者可存取的資料檢視相容的計算量度。

您可以透過包在 `SUM(metric)` 表達式，就像處理其他SQL源一樣。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 以取得發生次數量度。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 計算維度的近似相異值。 請參閱 [計算差異](#counting-distincts).

- [內嵌計算](#inline-calculations) 即時結合量度和/或對其進行數學運算。

#### 計算差異

由於CJA運作方式的基礎性質，您唯一能取得完全不同計數的維度為 `adobe_personid` 維度。 以下SQL陳述式 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 傳回預設訪客量度的值，即不重複人員的計數。 對於其他維度，會傳回近似相異計數。

#### 條件量度

您可以內嵌 `IF` 或 `CASE` 子句 `SUM` 或 `COUNT` 函式，新增特定於所選量度的其他篩選。 新增這些子句類似於將篩選器套用至工作區報表表格中的量度欄。

範例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 內嵌計算

您可以將其他運算式套用至 `SELECT` 而不是在計算量度中定義數學。 下表列出支援的運算式類型。

| 運算子或函式 | 詳細資料 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、減、乘、除和模數/余數 |
| `-X` 或 `+X` | 變更以X為量度運算式的符號或量度 |
| `PI()` | π常數 |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`，和 `TANH` | 一元數學函式 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二進位數學函式 |

{style="table-layout:auto"}

### 特殊欄

**時間戳記**

此 `timestamp` 特殊欄可用來提供查詢的日期範圍。 日期範圍可以使用 `BETWEEN` 運算式或一組 `timestamp` `>`, `>=`, `<`, `<=` 檢查 `AND`一起。
此 `timestamp` 為選用，若未提供完整範圍，則會使用預設值：

- 若僅提供最小值(`timestamp > X` 或 ` timestamp >= X`)，範圍是從X到現在。

- 若僅提供最大值(`timestamp < X` 或 `timestamp <= X`)，範圍從X-30天到X。

- 若未提供任何內容，則範圍為從現在到30天。

時間戳記範圍會轉換為RankedRequest中的日期範圍全域篩選。
時間戳記欄位也可用於日期時間函式，以剖析、截斷事件時間戳記。

**日期範圍**

此 `daterange` 特殊欄的作用類似  `timestamp`，但篩選僅限於整天。 此 `daterange` 也是選用項目，且預設範圍與相同 `timestamp`.
此 `daterange` 欄位也可用於日期時間函式中以剖析、截斷事件日期。

**filterId**

此 `filterId` 特殊欄是選用欄，可用來將外部定義的篩選器套用至查詢。 將外部定義的篩選器套用至查詢類似於在工作區中拖曳面板上的篩選器。 可提供多個篩選ID `AND` — 他們。

### WHERE子句

WHERE子句分三步處理：

1. 從 `timestamp` 特殊欄位。

2. 查找任何外部定義 `filterId`包含在篩選中。

3. 將剩餘的運算式轉換為臨機篩選。

處理是透過剖析 `AND`在 `WHERE` 條。 每個頂層 `AND`ed運算式必須符合上述其中一個。 任何比第一層更深的 `AND`s，若 `WHERE` 子句使用 `OR`在頂層，會以臨機篩選的形式處理。

### 排序依據

依預設，查詢會依第一個選取的量度，以遞減順序排序結果。 您可以指定 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`. 如果您使用 `ORDER BY`，您必須指定 `ORDER BY` 在第一個選取的量度上。

您也可以使用 `-` （減）。 以下兩個陳述式會產生相同的排序：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支援

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [CAST（列AS類型）](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 目前不支援類型轉換，但未擲回錯誤。 此 `CAST` 函式時，才會忽略。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 將時間字串剖析為時間戳記，以用於 `WHERE` 條。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 將時間字串剖析為時間戳記，以用於 `WHERE` 子句，可選地為該時間字串提供格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 將日期字串剖析為時間戳記，以用於 `WHERE` 條。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 將日期字串剖析為時間戳記，以用於 `WHERE` 子句，可選地為該日期字串提供格式。 |

{style="table-layout:auto"}

### Dimension功能支援

這些函式可用於 `SELECT`, `WHERE` 條件量度中的。

**字串函式**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在傳遞的欄位中產生動態維度身分。 |

{style="table-layout:auto"}

**日期時間函式**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [YEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [MONTH（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [DAY（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [DAYOFWEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 使用項目ID而非值，因為您需要的數字不是好記的名稱。 |
| [DAYOFYEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [WEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [QUARTER（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [HOUR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 使用項目ID而非值，因為您需要的數字不是好記的名稱。 |
| [MINUTE（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 |
| [EXTRACT（部件自日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 使用項目ID，而不是此函式某些部分的值，因為您需要的編號不是好記的名稱。<br/>支援的部件包括：<br> — 關鍵字： `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/> — 字串：  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`，或 `'MINUTE'`. |
| [DATE_PART（part、date或date-time）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在傳遞的欄位中產生動態維度身分。 使用項目ID，而不是此函式某些部分的值，因為您需要的編號不是好記的名稱。<br/>支援的字串部分包括： `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`，或 `'MINUTE'`. |
| [DATE_TRUNC（粒度、日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在傳遞的欄位中產生動態維度身分。<br/>支援的字串粒度為： `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&#39;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`，或 `'MINUTE'`. |

{style="table-layout:auto"}

