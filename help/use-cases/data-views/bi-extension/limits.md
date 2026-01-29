---
title: 限制
description: 在Customer Journey Analytics中限制各種BI工具中BI擴充功能的使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 0%

---

# 限制


在此使用案例中，您想要報告2023年期間前5次出現產品名稱。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 限制]**&#x200B;面板：

![Customer Journey Analytics限制面板](../assets/cja-limit.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL 日期範圍]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 日期範圍是（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 相對日期]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 位於最後]** `1` **[!UICONTROL 日曆年]**&#x200B;時顯示專案。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL product_name is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 前N]**&#x200B;位作為&#x200B;**[!UICONTROL 篩選器型別]**。
   1. 選取&#x200B;**[!UICONTROL 顯示專案]** **[!UICONTROL 前]** `5` **[!UICONTROL 依值]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖放&#x200B;**[!UICONTROL 總和發生次數]**&#x200B;並將它拖放到&#x200B;**[!UICONTROL 在此處新增資料欄位]**。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

1. 在「視覺效果」窗格中：
   * 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從資料行移除日期範圍。

   您的Power BI案頭應該如下所示。

   ![使用日期範圍名稱篩選的Power BI案頭](../assets/uc12-powerbi-final.png)

Power BI Desktop使用BI副檔名執行的查詢包含`limit`陳述式，但不包含預期的陳述式。 Power BI Desktop會使用明確的產品名稱結果，強制執行前5次發生的限制。

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 相對日期]**，選取&#x200B;**[!UICONTROL 年]**，然後選取&#x200B;**[!UICONTROL 先前的年]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL 產品名稱]**&#x200B;從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 發生次數]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。
   1. 在&#x200B;**[!UICONTROL 列]**&#x200B;中選取&#x200B;**[!UICONTROL 產品名稱]**。 從下拉式功能表中選取&#x200B;**[!UICONTROL 篩選器]**。
      1. 在&#x200B;**[!UICONTROL 篩選器\[產品名稱\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 前]**&#x200B;個索引標籤。
      1. 選取&#x200B;**[!UICONTROL 依欄位：]** **[!UICONTROL 前]** `5` **[!UICONTROL 依發生次數]** **[!UICONTROL 總和]**。
      1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。

         ![AlertRed](/help/assets/icons/AlertRed.svg)您注意到表格消失。 依發生次數選取前5個產品名稱，使用此篩選條件&#x200B;**無法**&#x200B;正常運作。
      1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 產品名稱]**，並從下拉式選單中選取&#x200B;**[!UICONTROL 移除]**。 表格會重新出現。
   1. 選取&#x200B;**[!UICONTROL 標籤]**&#x200B;托架中的&#x200B;**[!UICONTROL 總和（發生次數）]**。 從下拉式功能表中選取&#x200B;**[!UICONTROL 篩選器]**。
      1. 在&#x200B;**[!UICONTROL 篩選器\[發生次數\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 至少]**。
      1. 輸入`47.799`作為值。 此值可確保表格中只顯示前5個專案。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。

         您的Tableau桌上型電腦應如下所示。

         ![Tableau案頭限制](../assets/uc12-tableau-final.png)

如上所示，在定義產品名稱的「前5個發生次數」篩選條件時，Tableau Desktop執行的此查詢會失敗。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

定義發生次數的「前5名」篩選器時，Tableau Desktop執行的查詢如下所示。 此限制在查詢和套用的使用者端中不可見。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，重新整理您的連線。 選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 清除快取並重新整理]**。
1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。
      ![Looker篩選器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2024/01/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 請確定您在&#x200B;**[!UICONTROL Purchase Revenue↓5&rbrace;欄上選取]** 1&rbrace; （**[!UICONTROL 遞減，排序順序： 1]**）。**&#x200B;**
1. 請確定您在&#x200B;**[!UICONTROL Purchase Revenue↓5&rbrace;欄上選取]** 1&rbrace; （**[!UICONTROL 遞減，排序順序： 1]**）。**&#x200B;**
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](../assets/uc12-looker-result.png)

Looker使用BI副檔名產生的查詢包括`FETCH NEXT 5 ROWS ONLY`，這表示限制是透過Looker和BI副檔名執行。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc12-jupyter-results.png)

如Jupyter Notebook中所定義，查詢由BI擴充功能執行。

>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

   ```R
   ## Dimension 1 Limited
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE) %>%
      head(5)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc12-rstudio-results.png)

RStudio使用BI副檔名產生的查詢包含`LIMIT 5`，這表示限制是透過RStudio和BI副檔名套用。

```sql
SELECT "product_name", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2024-01-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "n" DESC
LIMIT 5
```

>[!ENDTABS]

+++
