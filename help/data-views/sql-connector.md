---
title: SQL連接器
description: 瞭解如何使用查詢服務、Power BI和/或表來使用SQL連接器訪問資料視圖。
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 829f7556c731ce55ccf1e03e2dea69b12e4501e4
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 2%

---

# SQL連接器

{{release-limited-testing}}

的 [!DNL Customer Journey Analytics (CJA) SQL Connector] 啟用對 [資料視圖](./data-views.md) 你在CJA里定義的。 您的資料工程師和分析師可能更熟悉Power BI、Tableau或其他業務智慧和可視化工具（進一步稱為BI工具）。 現在，他們可以基於CJA用戶在建立其Analysis Workspace項目時使用的相同資料視圖建立報告和儀表板。

Adobe Experience Platform [查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant?lang=tw) 是SQL介面，可用於資料湖的Experience Platform。 使用 [!DNL CJA SQL Connector] 啟用，功能 [!DNL Query Service] 擴展，以將CJA資料視圖作為表或視圖 [!DNL Query Service] 會話。 因此，使用商業智慧工具 [!DNL Query Service] 因為他們的PostgresSQL介面可以無縫地從此擴展功能中受益。

主要好處是：

- 無需在BI工具本身內重新建立CJA資料視圖的等效表示。 <br/>請參閱 [資料視圖](data-views.md) 瞭解有關資料視圖功能的詳細資訊，以瞭解必須重新建立的內容。<br/>

- 在BI工具和CJA之間的報告和分析方面有更大的一致性。

- 將CJA資料與BI工具中已有的其他資料源組合。

## 先決條件

要使用此功能，您必須

- 啟用 [!UICONTROL CJA SQL連接器] 你的Experience Platform組織。

- 配置相關產品配置檔案、用戶組和/或單個用戶的功能。<br/>
用戶必須具有以下權限：
   - Experience Platform查詢服務，
   - CJA Workspace項目和
   - CJA資料視圖。

- 使用非過期憑據過期將BI工具連接到CJA SQL Connector。 蘇 [憑據指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) 提供了有關設定過期憑據或未過期憑據的詳細資訊。

請參閱 [訪問控制](../admin/cja-access-control.md) 的子目錄。


## 使用狀況

使用 [!DNL CJA SQL Connector] 功能，您可以直接使用SQL，也可以使用特定BI工具中提供的拖放體驗。

### SQL

可以使用查詢編輯器或標準PostgresSQL命令行介面(CLI)客戶端直接在SQL陳述式中使用該功能。

+++ 查詢編輯器

在Experience PlatformUI中：

1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從 **[!UICONTROL **&#x200B;資料管理&#x200B;**]** 左欄。

2. 選擇 ![建立查詢](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **&#x200B;建立查詢&#x200B;**]**。

3. 要執行查詢，請鍵入SQL陳述式並選擇 ![播放](assets/Smock_Play_18_N.svg) 按鈕（或按Shift + Enter鍵）。

+++


+++ PostgresSQL CLI

1. 在Experience PlatformUI中，查找並複製PostgresSQL憑據：

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左欄（下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑據&#x200B;**]** 按鈕。

   3. 要複製連接字串，請使用 ![複製](assets/Smock_Copy_18_N.svg) 的 **[!UICONTROL ** PSQL命令&#x200B;**]** 的子菜單。

2. 開啟PostgresSQL CLI。

3. 要登錄並開始執行查詢，請在PostgresSQL CLI中貼上連接字串。

+++

請參閱 [查詢編輯器UI指南](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) 的子菜單。


### BI工具

目前，CJA SQL連接器支援用於Power BI和Tableau。

+++ Power BI

1. 在Adobe Experience PlatformUI中，查找PostgresSQL憑據的詳細資訊。

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左欄（下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑據&#x200B;**]** 按鈕。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 複製每個Postgres憑據參數([!UICONTROL 主機]。 [!UICONTROL 埠]。 [!UICONTROL 資料庫]。 [!UICONTROL 用戶名]等)，以滿足Power BI需要。

2. 在Power BI:

   1. 在主窗口中，選擇 **[!UICONTROL **&#x200B;獲取資料&#x200B;**]** 的上界。

   2. 選擇 **[!UICONTROL **&#x200B;更多……**]** 左欄。

   3. 在 **獲取資料** 螢幕，搜索 `PostgresSQL` 的 **[!UICONTROL ** PostgresSQL資料庫&#x200B;**]** 清單中。

   4. 在 **[!UICONTROL ** PostgressSQL資料庫&#x200B;**]** 對話框：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 的子菜單。

      2. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 在 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 的子菜單。

         添加 `?FLATTEN` 到 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數，因此它讀起來像 `prod:all?FLATTEN` 例如。 請參閱 [拼合用於第三方BI工具的嵌套資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 的子菜單。

      3. 提示時 **[!UICONTROL **&#x200B;資料連接&#x200B;**]** 模式，選擇 **[!UICONTROL **&#x200B;直接查詢&#x200B;**]** 確保資料結構正確展平。

      4. 系統會提示您 **[!UICONTROL **&#x200B;用戶名&#x200B;**]** 和 **[!UICONTROL **&#x200B;密碼&#x200B;**]**。 使用Experience Platform查詢中的等效參數 [!UICONTROL 憑據]。
   5. 成功登錄後，CJA資料視圖表將出現在Power BI **[!UICONTROL **&#x200B;導航器&#x200B;**]**。 資料視圖表通過使用 `dv_` 以他們的名字。


   6. 選擇要使用的資料視圖表並選擇 **[!UICONTROL **&#x200B;載入&#x200B;**]**。

   與一個或多個選定表關聯的所有維和度量都顯示在右窗格中，可在可視化中使用。

   請參閱 [將Power BI連接到查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) 的子菜單。

+++

+++Tableau

1. 在Experience PlatformUI中，查找PostgresSQL憑據的詳細資訊。

   1. 選擇 **[!UICONTROL **&#x200B;查詢&#x200B;**]** 從左欄（下） **[!UICONTROL **&#x200B;資料管理&#x200B;**]**)。

   2. 選擇 **[!UICONTROL **&#x200B;憑據&#x200B;**]** 按鈕。

   3. 使用 ![複製](assets/Smock_Copy_18_N.svg) 複製每個Postgres憑據參數([!UICONTROL 主機]。 [!UICONTROL 埠]。 [!UICONTROL 資料庫]。 [!UICONTROL 用戶名]Tableau需要時。

2. 在Tableau中：

   1. 選擇 **[!UICONTROL **&#x200B;更多&#x200B;**]** 從 **[!UICONTROL **&#x200B;到伺服器&#x200B;**]** 左欄。

   2. 選擇 **[!UICONTROL ** PostgresSQL **]** 清單中。

   3. 在 [!UICONTROL PostgresSQL] 對話框：

      1. 貼上 **[!UICONTROL **&#x200B;主機&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;伺服器&#x200B;**]** 的子菜單。

      2. 貼上 **[!UICONTROL **&#x200B;埠&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;埠&#x200B;**]** 的子菜單。

      3. 貼上 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 的子菜單。

         添加 `%3FFLATTEN` 到 **[!UICONTROL **&#x200B;資料庫&#x200B;**]** 參數，因此它讀起來像 `prod:all%3FFLATTEN` 例如。 請參閱 [拼合用於第三方BI工具的嵌套資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 的子菜單。

      4. 選擇 **[!UICONTROL **&#x200B;用戶名和密碼&#x200B;**]** 從 **[!UICONTROL **&#x200B;驗證&#x200B;**]** 清單框。

      5. 貼上 **[!UICONTROL **&#x200B;用戶名&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;用戶名&#x200B;**]** 的子菜單。

      6. 貼上 **[!UICONTROL **&#x200B;密碼&#x200B;**]** 參數來自Experience Platform查詢 [!UICONTROL 憑據] 入 **[!UICONTROL **&#x200B;密碼&#x200B;**]** 的子菜單。

      7. 選擇 **[!UICONTROL **&#x200B;登錄&#x200B;**]**。
   4. CJA資料視圖顯示為 **[!UICONTROL **&#x200B;表格&#x200B;**]** 清單框。 資料視圖表的前置詞為 `dv_`。

   5. 拖動要在畫布上使用的表。

   現在，您可以使用資料視圖表中的資料來構建報表和可視化。

   請參閱 [將Tableau連接到查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) 的子菜單。

+++

請參閱 [將客戶端連接到查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) 查看各種工具的概述和詳細資訊。

## 功能

預設情況下，資料視圖具有從友好名稱生成的表安全名稱。 例如，名為 [!UICONTROL 我的Web資料] 具有視圖名稱 `dv_my_web_data`。

如果要將資料視圖ID用作表名，可以添加可選 `CJA_USE_IDS` 連接時設定為資料庫名。 比如說， `prod:all?CJA_USE_IDS` 顯示資料視圖 `dv_ABC123`。

### 資料控管

Customer Journey Analytics中與資料治理相關的設定繼承自Adobe Experience Platform。 CJA 與 Adobe Experience Platform 資料控管之間的整合可讓您標示敏感的 CJA 資料強制執行隱私權原則。

在 Experience Platform 使用的資料集上建立的隱私權標籤和原則，可以在 CJA 資料檢視工作流程中出現。因此，使用CJA SQL Connector查詢的資料在不遵守定義的隱私標籤和策略時顯示相應的警告或錯誤。

### 列出資料視圖

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

### 嵌套與拼合

預設情況下，資料視圖的架構使用嵌套結構，就像原始的XDM架構一樣。 整合還支援 `FLATTEN` 的雙曲餘切值。 可以使用此選項強制將資料視圖（以及會話中的任何其他表）展平的模式。 拼合允許在不支援結構化架構的BI工具中更方便地使用。 請參閱 [在Query Service中使用嵌套資料結構](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) 的子菜單。

### 支援的SQL

請參閱 [查詢服務SQL引用](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) 以獲得有關支援的SQL類型的完整引用。

有關陣列和示例的概述，請參閱下面的「陣列」(Patterns)表格。

+++模式

| 圖案 | 範例 |
|---|---|
| 架構發現 | <pre>從dv1中選擇*，其中1=0</pre> |
| 排名/細分 | <pre>SELECT dim1,SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按DIM1分組</pre><pre>SELECT dim1,SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，並且<br/>  filterId = &#39;12345&#39;<br/>按DIM1分組</pre><pre>SELECT dim1,SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間，並且<br/>  和(dim2 = &#39;A&#39;或dim3 IN(&#39;X&#39;、&#39;Y&#39;、&#39;Z&#39;))<br/>按DIM1分組</pre> |
| HAVING子句 | <pre>SELECT dim1,SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按DIM1分組<br/>M1>100</pre> |
| 不同，頂部 <br/>維度值 | <pre>從dv1中選擇DISTINCT dim1</pre><pre>選擇dim1 AS dv1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按DIM1分組</pre><pre>選擇dim1 AS dv1<br/>從dv1<br/>其中\&#39;timestamp\&#39; >= &#39;2022-01-01&#39;和\&#39;timestamp\&#39; &lt; &#39;2022-01-02&#39;<br/>按DIM1分組<br/>按和排序（度量1）<br/>限制15</pre> |
| 度量合計 | <pre>選擇SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</pre> |
| 多維<br/>故障<br/>和頂部顯示 | <pre>SELECT dim1、dim2、SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1、dim2、SUM(metric1)AS m1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按1、2分組<br/>按1、2排序</pre><pre>選擇DISTINCT dim1, dim2<br/>從dv1</pre> |
| 子選擇：<br/>其他結果<br/>過濾 | <pre>SELECT dim1, m1<br/>自(<br/>  SELECT dim1,SUM(metric1)AS m1<br/>  從dv1<br/>  其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間</br>  按DIM1分組<br/>)<br/>其中dim1在(&#39;A&#39;, &#39;B&#39;)</pre> |
| 子選擇：<br/>加入<br/>資料集不在<br/>CJA | <pre>選擇b.key 、 a.dim1 、 a.m1<br/>自(<br/>  SELECT dim1,SUM(metric1)AS m1<br/>  從dv1<br/>  其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按DIM1分組<br/>)<br/>a.dim1 = b.key上的左連接查找b</pre> |
| 子選擇：<br/>跨查詢<br/>資料視圖 | <pre>SELECT鍵，SUM(m1)AS合計<br/>自(<br/>  選擇dim1 AS鍵，SUM(metric1)AS m1<br/>  從dv1<br/>  其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按DIM1分組<br/><br/>  聯合<br/><br/>  選擇dim2作為鍵，SUM(m1)AS m1<br/>  源dv2<br/>  其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  按dim2分組<br/>按鍵分組<br/>訂單總數</pre> |
| 子選擇： <br/>分層源， <br/>過濾， <br/>和聚合 | 使用子選項分層：<br><pre>SELECT rows.dim1,SUM(rows.m1)AS total<br/>自(<br/>  SELECT \_.dim1,\_.m1<br/>  自(<br/>    從dv1選擇\*<br/>    其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>  )\_<br/>  其中\_.dim1在(&#39;A&#39;、&#39;B&#39;、&#39;C&#39;)<br/>行<br/>按1分組<br/>訂單總數</pre><br/>使用CTE WITH的層：<br/><pre>行為(<br/>  WITH \_ AS(<br/>    SELECT * FROM data_ares<br/>    其中， \&#39;timestamp\&#39;介於&#39;2021-01-01&#39;和&#39;2021-02-01&#39;之間<br/>  )<br/>  選擇_.item 、 _.units自_<br/>  其中_.item不為NULL<br/>)<br/>SELECT rows.item,SUM(rows.units)AS單位<br/>從(「A」、「B」、「C」)中的WHERE rows.item行<br/>GROUP BY rows.item</pre> |
| 選擇<br/>指標在<br/> 或與<br/>尺寸 | <pre>選擇SUM(metric1)AS m1, dim1<br/>從dv1<br/>其中， \&#39;timestamp\&#39;介於&#39;2022-01-01&#39;和&#39;2022-01-02&#39;之間<br/>按2分組</pre> |

{style="table-layout:auto"}

+++

### 維度

您可以選擇預設可用或在資料視圖中定義的任何維。 按維的ID選擇維。

### 量度

可供選擇的度量包括：

- 預設情況下可用的任何度量，

- 定義的

- 與用戶有權訪問的資料視圖相容的計算度量。

通過包含在 `SUM(metric)` 表達式，就像您對其他SQL源所做的一樣。

您可以使用:

- `SELECT COUNT(*)` 或 `COUNT(1)` 獲取具體值度量。

- `SELECT COUNT(DISTINCT dimension)` 或 `SELECT APPROX_COUNT_DISTINCT(dimension)` 計算尺寸的近似非重複值。 請參閱 [計數區分](#counting-distincts)。

- [內聯計算](#inline-calculations) 即時合併度量和/或對它們進行數學運算。

#### 計數區分

由於CJA工作方式的基本性質，您唯一能夠獲得精確不同計數的維是 `adobe_personid` 維。 以下SQL陳述式 `SELECT COUNT(DISTINCT adobe_personid)` 或 `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` 返回預設訪問者度量的值，該度量是不同人員的計數。 對於其他維，將返回一個近似的不同計數。

#### 條件度量

您可以嵌入 `IF` 或 `CASE` 子句 `SUM` 或 `COUNT` 函式，以添加特定於所選度量的其他篩選。 添加這些子句類似於將篩選器應用於Workspace報表中的度量列。

範例：

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### 內聯計算

您可以將其他表達式應用於 `SELECT` 而不是在計算度量中定義數學。 下表列出了支援的表達式類型。

| 運算子或函式 | 詳細資料 |
|---|---|
| `+`, `-`, `*`, `/`, 和 `%` | 加、減、乘、除和模/余數 |
| `-X` 或 `+X` | 更改符號或度量，其中X是度量表達式 |
| `PI()` | π常數 |
| `POSITIVE`。 `NEGATIVE`。 `ABS`。 `FLOOR`。 `CEIL`。 `CEILING`。 `EXP`。 `LN`。 `LOG10`。 `LOG1P`。 `SQRT`。 `CBRT`。 `DEGREES`。 `RADIANS`。 `SIN`。 `COS`。 `TAN`。 `ACOS`。 `ASIN`。 `ATAN`。 `COSH`。 `SINH`, `TANH` | 一元數學函式 |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | 二進位數學函式 |

{style="table-layout:auto"}

### 特殊列

**時間戳記**

的 `timestamp` 特殊列用於提供查詢的日期範圍。 日期範圍可用 `BETWEEN` 表達式或對 `timestamp` `>`。 `>=`。 `<`。 `<=` 檢查 `AND`一起死。
的 `timestamp` 為可選，如果未提供完整範圍，則使用預設值：

- 如果僅提供最小值(`timestamp > X` 或 ` timestamp >= X`)，範圍從X到現在。

- 如果僅提供最大值(`timestamp < X` 或 `timestamp <= X`)，範圍是X-30天到X。

- 如果未提供任何內容，則範圍為現在–30天。

時間戳範圍將轉換為RawnedRequest中的日期範圍全局篩選器。
時間戳欄位也可用在Date-Time函式中以分析、截斷事件時間戳。

**日期範圍**

的 `daterange` 特殊欄類似  `timestamp`但是，篩選限制為全天。 的 `daterange` 也是可選的，並且具有與 `timestamp`。
的 `daterange` 欄位也可用於Date-Time函式中來分析、截斷事件日期。

**篩選器ID**

的 `filterId` 特殊列是可選的，用於將外部定義的篩選器應用於查詢。 將外部定義的篩選器應用於查詢類似於在Workspace的面板上拖動篩選器。 可以提供多個篩選器ID `AND` — 他們。

### WHERE子句

WHERE子句分三步處理：

1. 查找日期範圍 `timestamp` 特殊領域。

2. 查找任何外部定義的 `filterId`清單。

3. 將其餘表達式轉換為即席篩選器。

處理通過解析 `AND`的 `WHERE` 。 每個頂級 `AND`ed表達式必須與上述其中一個匹配。 任何比第一層更深的東西 `AND`s，或者，如果 `WHERE` 子句使用 `OR`在頂層，將作為即席篩選器處理。

### 排序依據

預設情況下，查詢按第一個選定度量按降序排序結果。 通過指定 `ORDER BY ... ASC` 或 `ORDER BY ... DESC`。 如果您使用 `ORDER BY`，必須指定 `ORDER BY` 在第一個選定度量上。

也可以使用 `-` （減）。 以下兩個語句的排序相同：

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### 一般功能支援

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [CAST（列AS類型）](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` 或 <br/> `` `timestamp`::string `` | 當前不支援類型轉換，但未引發任何錯誤。 的 `CAST` 函式。 |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | 將時間字串解析為時間戳，以在 `WHERE` 。 |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | 將時間字串解析為時間戳，以在 `WHERE` 子句，可選地為該時間字串提供格式。 |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | 將日期字串分析為時間戳，以便在 `WHERE` 。 |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | 將日期字串分析為時間戳，以便在 `WHERE` 子句，可選地為該日期字串提供格式。 |

{style="table-layout:auto"}

### Dimension功能支援

這些函式可用於 `SELECT`。 `WHERE` 子句或條件度量中。

**字串函式**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | 在傳入欄位上生成動態維標識。 |

{style="table-layout:auto"}

**日期 — 時間函式**

| 函數 | 範例 | 詳細資料 |
|---|---|---|
| [YEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [MONTH（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [DAY（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [DAYOFWEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | 在傳入欄位上生成動態維標識。 使用項目ID而不是值，因為您需要的數字不是友好名稱。 |
| [DAYOFYEAR（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [WEEK（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [QUARTER（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [HOUR（日期或日期 — 時間）](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | 在傳入欄位上生成動態維標識。 使用項目ID而不是值，因為您需要的數字不是友好名稱。 |
| [MINUTE（日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | 在傳入欄位上生成動態維標識。 |
| [EXTRACT（部件自日期或日期時間）](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | 在傳入欄位上生成動態維標識。 使用項目ID，而不是此函式的某些部分的值，因為您需要的數字不是友好名稱。<br/>支援的部件包括：<br> — 關鍵字： `YEAR`。 `MONTH`。 `DAYOFMONTH`。 `DAYOFWEEK`。 `DAYOFYEAR`。 `WEEK`。 `QUARTER`。 `HOUR`。 `MINUTE`。<br/> — 字串：  `'YEAR'`。 `'Y'`。 `'MONTH'`。 `'M'`。 `'DAYOFMONTH'`。 `'DAY'`。 `'D'`。 `'DAYOFWEEK'`。 `'DOW'`。 `'DAYOFYEAR'`。 `'DOY'`。 `'WEEK'`。 `'WOY`&#39; `'W'`。 `'QUARTER'`。 `'QOY'`。 `'Q'`。 `'HOUR'`或 `'MINUTE'`。 |
| [DATE_PART（部件、日期或日期 — 時間）](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | 在傳入欄位上生成動態維標識。 使用項目ID，而不是此函式的某些部分的值，因為您需要的數字不是友好名稱。<br/>支援的字串部分包括： `'YEAR'`。 `'Y'`。 `'MONTH'`。 `'M'`。 `'DAYOFMONTH'`。 `'DAY'`。 `'D'`。 `'DAYOFWEEK'`。 `'DOW'`。 `'DAYOFYEAR'`。 `'DOY'`。 `'WEEK'`。 `'WOY`&#39; `'W'`。 `'QUARTER'`。 `'QOY'`。 `'Q'`。 `'HOUR'`或 `'MINUTE'`。 |
| [DATE_TRUNC（粒度、日期或日期 — 時間）](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | 在傳入欄位上生成動態維標識。<br/>支援的字串粒度為： `'YEAR'`。 `'Y'`。 `'MONTH'`。 `'M'`。 `'DAYOFMONTH'`。 `'DAY'`。 `'D'`。 `'DAYOFWEEK'`。 `'DOW'`。 `'DAYOFYEAR'`。 `'DOY'`。 `'WEEK'`。 `'WOY`&#39; `'W'`。 `'QUARTER'`。 `'QOY'`。 `'Q'`。 `'HOUR'`或 `'MINUTE'`。 |

{style="table-layout:auto"}

