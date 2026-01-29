---
title: 使用區段名稱來分段
description: 在Customer Journey Analytics的各種BI工具中，使用區段名稱來區段BI擴充功能的使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# 使用區段名稱來分段

在此使用案例中，您要將現有的區段用於「釣魚」產品類別，即您在Customer Journey Analytics中定義的類別。 對2023年1月期間的產品名稱和發生次數（事件）進行細分和報告。

+++ Customer Journey Analytics

檢查您要在Customer Journey Analytics中使用的區段。

![Customer Journey Analytics使用篩選器名稱來篩選](../assets/cja-fishing-products.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用區段名稱將區段]**&#x200B;面板中針對使用案例使用該區段：

![Customer Journey Analytics不重複計數值](../assets/cja-using-filter-names-to-filter.png)

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
   1. 選取&#x200B;**[!UICONTROL 篩選器名稱]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

您看到顯示擷取此視覺效果&#x200B;**[!UICONTROL 資料的]**&#x200B;錯誤的視覺效果。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：

   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 篩選器名稱為（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 基本篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 在&#x200B;**[!UICONTROL 搜尋]**&#x200B;欄位底下，選取&#x200B;**[!UICONTROL 釣魚產品]**，這是Customer Journey Analytics中定義的現有篩選的名稱。
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 日期範圍是（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 在]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 在]** `2/1/2023`之前時顯示專案。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 資料行]**&#x200B;移除&#x200B;**[!UICONTROL filterName]**。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 資料行]**&#x200B;移除&#x200B;**[!UICONTROL 日期範圍]**。

   您會看到已套用&#x200B;**[!UICONTROL filterName]**&#x200B;篩選器的資料表已更新。 您的Power BI案頭應該如下所示。

   ![使用日期範圍名稱篩選的Power BI案頭](../assets/uc9-powerbi-final.png)


>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選器\[篩選器名稱\]]**&#x200B;對話方塊中，確定已選取&#x200B;**[!UICONTROL 從清單選取]**，並從清單選取&#x200B;**[!UICONTROL 釣魚產品]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[Daterang\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**，然後選取`01/01/2023` - `01/02/2023`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL 產品名稱]**&#x200B;從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 發生次數]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](../assets/uc9-tableau-final.png)

>[!TAB 觀察者]

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
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 篩選‣器名稱]**。
1. 確定&#x200B;**[!UICONTROL 是]**&#x200B;篩選的選取專案。
1. 從可能的值清單中選取&#x200B;**[!UICONTROL 釣魚產品]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](../assets/uc9-looker-result.png)



>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc9-jupyter-input.png)

1. 從下拉式功能表中選取&#x200B;**[!UICONTROL 釣魚產品]**。

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc9-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ```{r} `到` ``` `之間的下列陳述式。 請確定您使用適當的篩選器名稱。 例如，`Fishing Products`。

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
