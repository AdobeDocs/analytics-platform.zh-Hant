---
title: 使用Dimension值來分段
description: 在Customer Journey Analytics中的各種BI工具中，使用維度值來區隔BI擴充功能的使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# 使用維度值劃分割槽段

您使用&#x200B;**[!UICONTROL 產品類別]**&#x200B;的動態&#x200B;**[!UICONTROL 狩獵]**值，從狩獵類別中劃分產品。 或者，對於不支援動態擷取產品類別值的BI工具，您可以在Customer Journey Analytics中建立新的區段，對搜尋產品類別中的產品進行區段。
然後，您想要使用新區段，報告2023年1月期間，搜尋類別中產品的產品名稱和發生次數（事件）。

+++ Customer Journey Analytics

在Customer Journey Analytics中建立具有&#x200B;**[!UICONTROL 標題]** `Hunting Products`的新區段。

![Customer Journey Analytics使用Dimension值來區段](../assets/cja-hunting-products.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用Dimension值來篩選使用案例的]**&#x200B;面板中使用該區段：

![Customer Journey Analytics不重複計數值](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 從功能表選取&#x200B;**[!UICONTROL 首頁]**，然後從工具列選取&#x200B;**[!UICONTROL 重新整理]**。 您必須重新整理連線，才能擷取您剛才在Customer Journey Analytics中定義的新篩選器。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL 日期範圍]**。
   1. 選取&#x200B;**[!UICONTROL product_category]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

您看到顯示擷取此視覺效果&#x200B;**[!UICONTROL 資料的]**&#x200B;錯誤的視覺效果。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 篩選器名稱為（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 基本篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 日期範圍是（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 在]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 在]** `2/1/2023`之前時顯示專案。
   1. 選取&#x200B;**[!UICONTROL 基本篩選器]**&#x200B;作為&#x200B;**[!UICONTROL product_category]**&#x200B;的&#x200B;**[!UICONTROL 篩選器型別]**，並從可能的值清單中選取&#x200B;**[!UICONTROL Hunting]**。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 資料行]**&#x200B;移除&#x200B;**[!UICONTROL filterName]**。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 資料行]**&#x200B;移除&#x200B;**[!UICONTROL 日期範圍]**。

   您會看到已套用&#x200B;**[!UICONTROL product_category]**&#x200B;篩選器的資料表已更新。 您的Power BI案頭應該如下所示。

   ![使用日期範圍名稱篩選的Power BI案頭](../assets/uc10-powerbi-final.png)



>[!TAB Tableau案頭]

![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop不支援從Customer Journey Analytics擷取產品類別的動態清單。 此使用案例會改用新建立的&#x200B;**[!UICONTROL 狩獵產品]**&#x200B;篩選器，並使用篩選器名稱critia。

1. 在&#x200B;**[!UICONTROL 資料Source]**&#x200B;檢視的&#x200B;**[!UICONTROL 資料]**&#x200B;下，從&#x200B;**[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**&#x200B;上的內容功能表選取&#x200B;**[!UICONTROL 重新整理]**。 您必須重新整理連線，才能擷取您剛才在Customer Journey Analytics中定義的新篩選器。
1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選器\[篩選器名稱\]]**&#x200B;對話方塊中，確定已選取&#x200B;**[!UICONTROL 從清單中選取]**，並從清單中選取&#x200B;**[!UICONTROL 搜尋產品]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**，然後選取`01/01/2023` - `1/2/2023`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL 產品名稱]**&#x200B;從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 發生次數]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](../assets/uc10-tableau-final.png)

>[!TAB 觀察者]

1. 在1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，重新整理您的連線。 選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 清除快取並重新整理]**。
1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。
      ![Looker篩選器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍日期]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/02/01]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**&#x200B;以新增另一個篩選器。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 產‣品類別]**。
1. 確定&#x200B;**[!UICONTROL 是]**&#x200B;作為篩選的選取專案。

![AlertRed](/help/assets/icons/AlertRed.svg)查閱未顯示&#x200B;**[!UICONTROL 產品類別]**&#x200B;的可能值清單。

![觀察者計數相異](../assets/uc10-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc10-jupyter-input.png)

1. 從下拉式功能表中選取&#x200B;**[!UICONTROL 搜尋]**。

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ```{r} `到` ``` `之間的下列陳述式。 確定您使用適當的類別。 例如，`Hunting`。

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

