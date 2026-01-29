---
title: 每月趨勢
description: Customer Journey Analytics中各種BI工具中BI擴充功能的每月趨勢使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 0%

---

# 每月趨勢


在此使用案例中，您想要顯示表格和簡單的線條視覺效果，以顯示2023年的發生次數（事件）每月趨勢。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 每月趨勢]**&#x200B;面板：

![Customer Journey Analytics每月趨勢視覺效果](../assets/cja_monthly_trend.png)

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
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

   您會看到一個表格，其中顯示當月的發生次數。 為獲得更好的可見度，請放大視覺效果。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：

   1. 從這個視覺效果&#x200B;**[!UICONTROL 上的]**&#x200B;篩選條件中選取&#x200B;**[!UICONTROL daterangemonth is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 位於或晚於]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 位於]** `1/1/2024.`時顯示專案。您可以使用行事曆圖示挑選和選取日期。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

   您會看到已套用&#x200B;**[!UICONTROL daterangemonth]**&#x200B;篩選器的資料表已更新。

1. 在&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中：

   1. 選取&#x200B;**[!UICONTROL 折線圖]**&#x200B;視覺效果。

   使用與表格相同的資料時，折線圖視覺效果會取代表格。 您的Power BI案頭應該如下所示。

   ![Power BI案頭使用案例2日期範圍篩選器](../assets/uc4-pbi-filter-daterange.png)

1. 線上圖視覺效果上：

   1. 選取![更多](/help/assets/icons/More.svg)。
   1. 從內容功能表中，選取&#x200B;**[!UICONTROL 顯示為表格]**。

   主要檢視已更新，顯示線條視覺效果和表格。 您的Power BI案頭應該如下所示。

   ![Power BI案頭使用案例2最終每日趨勢視覺效果](../assets/uc4-pbi-filter-final.png)

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並指定`01/01/2023` - `01/01/2024`的期間。

      ![Tableau案頭篩選器](../assets/uc4-tableau-filter.png)

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖放&#x200B;**[!UICONTROL Daterangeday]**，並將專案拖放到&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。
      * 從&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL MONTH]**，以便將值更新為&#x200B;**[!UICONTROL MONTH(Daterangeday)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中的&#x200B;**[!UICONTROL 資料表（*量值名稱*）]**&#x200B;清單拖放&#x200B;**[!UICONTROL 發生次數]**，並將專案拖放到&#x200B;**[!UICONTROL 資料列]**&#x200B;旁的欄位中。 值會自動轉換為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭圖形](../assets/uc4-tableau-graph.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Graph`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 請確定已選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。 在資料檢視中：
   1. 選取右上方的&#x200B;**[!UICONTROL 顯示我]**，並選取&#x200B;**[!UICONTROL 文字表格]** （左上方的視覺效果），將資料檢視的內容修改成表格。
   1. 將&#x200B;**[!UICONTROL MONTH(Daterangeday)]**&#x200B;從&#x200B;**[!UICONTROL 欄]**&#x200B;拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭資料](../assets/uc4-tableau-data.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL Graph]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 圖形]**&#x200B;工作表下方的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放至&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。
   1. 在檢視中選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表，並將&#x200B;**[!UICONTROL 整個檢視]**&#x200B;修改為&#x200B;**[!UICONTROL 固定寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭儀表板1](../assets/uc4-tableau-dashboard.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。
      ![Looker篩選器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2024/01/01]**。
1. 從左側&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;邊欄，
   1. 從&#x200B;**[!UICONTROL DIMENSIONS‣]**&#x200B;的清單中選取&#x200B;**[!UICONTROL Daterangemonth Date]**，然後選取&#x200B;**[!UICONTROL Month]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](../assets/uc4-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
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

   ![Jupyter Notebook結果](../assets/uc4-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc4-rstudio-results.png)

>[!ENDTABS]

+++
