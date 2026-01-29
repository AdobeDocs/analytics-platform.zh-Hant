---
title: 轉換
description: Customer Journey Analytics中各種BI工具中BI擴充功能的轉換使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 0%

---

# 轉換


您想要瞭解各種BI工具對Customer Journey Analytics物件（例如維度、量度、篩選器、計算量度和日期範圍）的轉換。

+++ Customer Journey Analytics

在Customer Journey Analytics中，您在[資料檢視](/help/data-views/data-views.md)中定義資料集的哪些元件及如何公開為[維度](/help/components/dimensions/overview.md)和[量度](/help/components/apply-create-metrics.md)。 該維度和量度的定義會使用BI擴充功能向BI工具公開。
您將[篩選器](/help/components/segments/seg-overview.md)、[計算量度](/help/components/calc-metrics/calc-metr-overview.md)和[日期範圍](/help/components/date-ranges/overview.md)等元件用作Workspace專案的一部分。 這些元件也會透過BI擴充功能向BI工具公開。

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

Customer Journey Analytics物件可在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中使用，並可從您在Power BI Desktop中選取的表格擷取。 例如，**[!UICONTROL public.cc_data_view]**。 表格的名稱與您在Customer Journey Analytics中為資料檢視定義的外部ID相同。 例如，具有&#x200B;**[!UICONTROL 標題]** `C&C - Data View`和&#x200B;**[!UICONTROL 外部識別碼]** `cc_data_view`的資料檢視。

**維度**
來自Customer Journey Analytics的維度以[!UICONTROL 元件ID]識別。 [!UICONTROL 元件ID]已在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;具有[!UICONTROL 元件識別碼] **[!UICONTROL product_name]**，這是Power BI Desktop中維度的名稱。
來自Customer Journey Analytics的日期範圍維度（例如**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可用作&#x200B;**[!UICONTROL daterangeday]**、**[!UICONTROL daterangeweek]**、**[!UICONTROL daterangemonth]**&#x200B;等。

**個量度**
來自Customer Journey Analytics的量度以[!UICONTROL 元件ID]識別。 [!UICONTROL 元件ID]已在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有[!UICONTROL 元件識別碼] **[!UICONTROL purchase_revenue]**，這是Power BI Desktop中量度的名稱。 **[!UICONTROL ∑]**&#x200B;表示量度。 當您在任何視覺效果中使用量度時，量度會重新命名為&#x200B;**[!UICONTROL *量度的總和&#x200B;*]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為**[!UICONTROL filterName]**&#x200B;欄位的一部分使用。 當您在Power BI Desktop中使用&#x200B;**[!UICONTROL filterName]**&#x200B;欄位時，可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 外部ID]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;具有[!UICONTROL 外部識別碼] **[!UICONTROL product_name_count_distinct]**，並在Power BI Desktop中顯示為**[!UICONTROL cm_product_name_count_distinc]**t。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為**[!UICONTROL daterangeName]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL daterangeName]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Power BI Desktop提供使用[資料分析運算式(DAX)](https://learn.microsoft.com/en-us/dax/dax-overview)的自訂轉換功能。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 在報表檢視中，選取長條圖視覺效果。
1. 在[資料]窗格中選取&#x200B;**[!UICONTROL product_name]**。
1. 在工具列中選取&#x200B;**[!UICONTROL 新資料行]**。
1. 在公式編輯器中，定義名稱為`product_name_lower`的新欄，如`product_name_lower = LOWER('public.cc_data_view[product_name])`。
   ![Power BI案頭轉換至Lower](../assets/uc14-powerbi-transformation.png)
1. 請確定您在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中選取新的&#x200B;**[!UICONTROL product_name_lower]**&#x200B;欄，而非&#x200B;**[!UICONTROL product_name]**&#x200B;欄。
1. 在表格視覺效果中選取&#x200B;**[!UICONTROL 更多]**&#x200B;中的![以表格](/help/assets/icons/More.svg)報告。

   您的Power BI案頭應該如下所示。
   ![Power BI案頭轉換最終版](../assets/uc14-powerbi-final.png)

自訂轉換會導致SQL查詢的更新。 請參閱下列SQL範例中`lower`函式的使用：

```sql
select "_"."product_name_lower",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name_lower" as "product_name_lower",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterange" as "daterange",
            "_"."product_name" as "product_name",
            "_"."purchase_revenue" as "purchase_revenue",
            "_"."purchases" as "purchases",
            lower("_"."product_name") as "product_name_lower"
        from 
        (
            select "_"."daterange",
                "_"."product_name",
                "_"."purchase_revenue",
                "_"."purchases"
            from 
            (
                select "daterange",
                    "product_name",
                    "purchase_revenue",
                    "purchases"
                from "public"."cc_data_view" "$Table"
            ) "_"
            where ("_"."daterange" < date '2024-01-01' and "_"."daterange" >= date '2023-01-01') and ("_"."product_name" in ('4G Cellular Trail Camera', '4K Wildlife Trail Camera', 'Wireless Trail Camera', '8-Person Cabin Tent', '20MP No-Glow Trail Camera', 'HD Wildlife Camera', '4-Season Mountaineering Tent', 'Trail Camera', '16MP Trail Camera with Solar Panel', '10-Person Family Tent'))
        ) "_"
    ) "rows"
    group by "product_name_lower"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```

>[!TAB Tableau案頭]

每當您在工作表中工作時，**[!UICONTROL Data]**&#x200B;側邊欄中都會有Customer Journey Analytics物件。 並從您選取做為Tableau中&#x200B;**[!UICONTROL 資料來源]**&#x200B;頁面一部分的資料表中擷取。 例如，**[!UICONTROL cc_data_view]**。 表格的名稱與您在Customer Journey Analytics中為資料檢視定義的外部ID相同。 例如，具有&#x200B;**[!UICONTROL 標題]** `C&C - Data View`和&#x200B;**[!UICONTROL 外部識別碼]** `cc_data_view`的資料檢視。

**維度**
來自Customer Journey Analytics的維度以[!UICONTROL 元件名稱]識別。 已在您的Customer Journey Analytics資料檢視中定義[!UICONTROL 元件名稱]。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;有[!UICONTROL 元件名稱] **[!UICONTROL 產品名稱]**，這是Tableau中維度的名稱。 所有維度皆由&#x200B;**[!UICONTROL Abc]**識別。
來自Customer Journey Analytics的日期範圍維度（例如**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可用作&#x200B;**[!UICONTROL Daterangeday]**、**[!UICONTROL Daterangeweek]**、**[!UICONTROL Daterangemonth]**&#x200B;等。 使用日期範圍維度時，您必須從下拉式選單中選取適當的日期或時間定義，以套用至該日期範圍維度。 例如，**[!UICONTROL 年]**，**[!UICONTROL 季]**，**[!UICONTROL 月]**，**[!UICONTROL 日]**。

**個量度**
來自Customer Journey Analytics的量度由[!UICONTROL 元件名稱]識別。 已在您的Customer Journey Analytics資料檢視中定義[!UICONTROL 元件名稱]。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有[!UICONTROL 元件名稱] **[!UICONTROL Purchase Revenue]**，這是Tableau中量度的名稱。 所有量度都由&#x200B;**[!UICONTROL #]**&#x200B;識別。 當您在任何視覺效果中使用量度時，量度會重新命名為&#x200B;**[!UICONTROL Sum（*量度*）]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為**[!UICONTROL 篩選器名稱]**&#x200B;欄位的一部分使用。 當您在Tableau中使用&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位時，可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 標題]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;有[!UICONTROL 標題] **[!UICONTROL 產品名稱（相異計數）]**，並在Tableau中顯示為&#x200B;**[!UICONTROL Cm產品名稱相異計數]**。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為**[!UICONTROL 日期範圍名稱]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Tableau Desktop提供使用[計算欄位](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm)的自訂轉換功能。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 從主功能表選取&#x200B;**[!UICONTROL 分析]** > **[!UICONTROL 建立計算欄位]**。
   1. 使用函式&#x200B;**[!UICONTROL 定義]**&#x200B;小寫的產品名稱`LOWER([Product Name])`。
      ![Tableau計算欄位](../assets/uc14-tableau-calculated-field.png)
   1. 選取&#x200B;**[!UICONTROL 確定]**。
1. 選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;拖曳&#x200B;**[!UICONTROL 小寫產品名稱]**，並將專案拖放至&#x200B;**[!UICONTROL 列]**&#x200B;旁的欄位中。
   1. 從&#x200B;**[!UICONTROL 列]**&#x200B;移除&#x200B;**[!UICONTROL 產品名稱]**。
1. 選取&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。

您的Tableau桌上型電腦應如下所示。

轉換後的![Tableau案頭](../assets/uc14-tableau-final.png)

自訂轉換會導致SQL查詢的更新。 請參閱下列SQL範例中`LOWER`函式的使用：

```sql
SELECT LOWER(CAST(CAST("cc_data_view"."product_name" AS TEXT) AS TEXT)) AS "Calculation_1562467608097775616",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-12-31')))
GROUP BY 1
HAVING ((SUM("cc_data_view"."purchase_revenue") >= 999999.99999998999) AND (SUM("cc_data_view"."purchase_revenue") <= 2000000.00000002))
```

>[!TAB 觀察者]

可在&#x200B;**[!UICONTROL 探索]**&#x200B;介面中使用Customer Journey Analytics物件。 和會隨著在Looker中設定連線、專案和模型而擷取。 例如，**[!UICONTROL cc_data_view]**。 檢視的名稱與您在Customer Journey Analytics中為資料檢視定義的外部ID相同。 例如，具有&#x200B;**[!UICONTROL 標題]** `C&C - Data View`和&#x200B;**[!UICONTROL 外部識別碼]** `cc_data_view`的資料檢視。

**維度**
Customer Journey Analytics的維度會在**[!UICONTROL Cc資料檢視]**&#x200B;左側邊欄中列為&#x200B;**[!UICONTROL DIMENSION]**。 維度是在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;具有&#x200B;**[!UICONTROL DIMENSION]** **[!UICONTROL 產品名稱]**，這是Looker中維度的名稱。
來自Customer Journey Analytics的日期範圍維度（如**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可做為&#x200B;**[!UICONTROL Daterangeday Date]**、**[!UICONTROL Daterangeweek Date]**、**[!UICONTROL Daterangemonth Date]**&#x200B;等。  使用日期範圍維度時，您必須選取適當的日期或時間定義。 例如，**[!UICONTROL 年]**，**[!UICONTROL 季]**，**[!UICONTROL 月]**，**[!UICONTROL 日期]**。

**個量度**
Customer Journey Analytics的量度在**[!UICONTROL Cc資料檢視]**&#x200B;左側邊欄中列為&#x200B;**[!UICONTROL DIMENSION]**。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有&#x200B;**[!UICONTROL DIMENSION]** **[!UICONTROL Purchase Revenue]**。 若要實際做為量度使用，請建立如上例所示的自訂量值欄位，或使用維度的捷徑。 例如，**[!UICONTROL ⋮]**，選取&#x200B;**[!UICONTROL 彙總]**，然後選取&#x200B;**[!UICONTROL 總計]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為**[!UICONTROL 篩選器名稱]**&#x200B;欄位的一部分使用。 當您在Looker中使用&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位時，您可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 標題]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;有[!UICONTROL 標題] **[!UICONTROL 產品名稱（相異計數）]**，並在回顧中顯示為&#x200B;**[!UICONTROL 公分產品名稱相異計數]**。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為**[!UICONTROL 日期範圍名稱]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Looker使用自訂欄位建置器提供自訂轉換功能，如上所示。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 從左側邊欄中的&#x200B;**[!UICONTROL ‣自訂欄位]**&#x200B;區段：
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 自訂Dimension]**。
   1. 在`lower(${cc_data_view.product_name})`運算式&#x200B;**[!UICONTROL 文字區域中輸入]**。 當您開始輸入`Product Name`時，會以正確的語法協助您。
      ![Looker轉換範例](../assets/uc14-looker-transformation.png)
   1. 輸入`product name`作為&#x200B;**[!UICONTROL 名稱]**。
   1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

您應該會看到類似表格，如下所示。

![Looker轉換結果](../assets/uc14-looker-result.png)


自訂轉換會導致SQL查詢的更新。 請參閱下列SQL範例中`LOWER`函式的使用：

```sql
SELECT
    LOWER((cc_data_view."product_name")) AS "product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchase_revenue",
    COALESCE(SUM(CAST(( cc_data_view."purchases"  ) AS DOUBLE PRECISION)), 0) AS "sum_of_purchases"
FROM public.cc_data_view  AS cc_data_view
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-01')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```

>[!TAB Jupyter Notebook]

Customer Journey Analytics物件（維度、量度、篩選器、計算量度和日期範圍）可當作您建構的內嵌SQL查詢的一部分來使用。 請參閱之前的範例。

**自訂轉換**

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT LOWER(product_category) AS `Product Category`, COUNT(*) AS EVENTS \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc13-jupyter-results.png)

如Jupyter Notebook中所定義，查詢由BI擴充功能執行。

>[!TAB RStudio]

Customer Journey Analytics元件（維度、量度、篩選器、計算量度和日期範圍）在R語言中類似命名物件提供。 請參閱使用元件的元件。請參閱之前的範例。

**自訂轉換**

1. 在新區塊中輸入` ```{r} `到` ``` `之間的下列陳述式。

   ```R
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange <= "2024-01-01") %>%
      mutate(d2=lower(product_category)) %>%
      group_by(d2) %>%
      count() %>%
      arrange(d2, .by_group = FALSE)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc13-rstudio-results.png)

RStudio使用BI擴充功能產生的查詢包含`lower`，這表示自訂轉換是由RStudio和BI擴充功能執行。

```sql
SELECT "d2", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*, lower("product_category") AS "d2"
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" <= '2024-01-01')
) AS "q01"
GROUP BY "d2"
ORDER BY "d2"
LIMIT 1000
```

>[!ENDTABS]

+++

