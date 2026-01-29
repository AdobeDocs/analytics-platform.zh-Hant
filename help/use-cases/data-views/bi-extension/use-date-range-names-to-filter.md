---
title: 使用日期範圍名稱進行篩選
description: 在Customer Journey Analytics中，使用日期範圍名稱來篩選各種BI工具中BI擴充功能的使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# 使用日期範圍名稱進行篩選

在此使用案例中，您想使用已在Customer Journey Analytics中定義的日期範圍來篩選及報告去年的發生次數（事件）。

+++ Customer Journey Analytics

若要使用日期範圍製作報表，請在Customer Journey Analytics中設定日期範圍，並選取&#x200B;**[!UICONTROL 標題]** `Last Year 2023`。

![Customer Journey Analytics使用日期範圍名稱來篩選](../assets/cja-daterange.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用日期範圍名稱以篩選使用案例的]**&#x200B;面板中使用該日期範圍：

![Customer Journey Analytics不重複計數值](../assets/cja-using-date-range-filter-names-to-filter.png)

請注意，在自由表格視覺效果中定義的日期範圍會如何覆寫套用至面板的日期範圍。

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL daterangemonth]**。
   1. 選取&#x200B;**[!UICONTROL 日期範圍名稱]**。
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

   您看到顯示擷取此視覺效果&#x200B;**[!UICONTROL 資料的]**&#x200B;錯誤的視覺效果。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：

   1. 選取此視覺效果&#x200B;**[!UICONTROL 上]**&#x200B;篩選器中的&#x200B;**[!UICONTROL daterangeName is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 基本篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 在&#x200B;**[!UICONTROL 搜尋]**&#x200B;欄位底下，選取&#x200B;**[!UICONTROL 去年度2023]**，這是您在Customer Journey Analytics中定義的日期範圍名稱。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 資料行]**&#x200B;移除&#x200B;**[!UICONTROL 日期範圍名稱]**。

   您會看到已套用&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;篩選器的資料表已更新。 您的Power BI案頭應該如下所示。

   ![使用日期範圍名稱篩選的Power BI案頭](../assets/uc8-powerbi-final.png)

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍名稱\]]**&#x200B;對話方塊中，確定已選取&#x200B;**[!UICONTROL 從清單中選取]**，並從清單中選取&#x200B;**[!UICONTROL 去年的2023]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL Daterangemonth]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 列]**&#x200B;旁的欄位中。 選取&#x200B;**[!UICONTROL Daterangemonth]**&#x200B;並選取&#x200B;**[!UICONTROL 月]**。 值變更為&#x200B;**[!UICONTROL MONTH(Daterangemonth)]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 發生次數]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表]**。
   1. 從工具列選取&#x200B;**[!UICONTROL 交換列與欄]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](../assets/uc8-tableau-final.png)

>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍名稱]**。
1. 將&#x200B;**[!UICONTROL Cc資料檢視日期範圍名稱]**&#x200B;篩選器指定為&#x200B;**[!UICONTROL 是]**，並從值清單中選取&#x200B;**[!UICONTROL 去年度2023]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL Daterange Month]**，然後選取&#x200B;**[!UICONTROL Month]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](../assets/uc8-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc8-jupyter-input.png)

1. 從下拉式功能表中選取&#x200B;**[!UICONTROL 釣魚產品]**。

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。 請確定您使用適當的日期範圍名稱。 例如，`Last Year 2023`。

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

