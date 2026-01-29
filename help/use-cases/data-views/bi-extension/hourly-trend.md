---
title: 每小時趨勢
description: Customer Journey Analytics中各種BI工具中BI擴充功能的每小時趨勢使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 每小時趨勢


## 每小時趨勢

在此使用案例中，您想要顯示表格和簡單的線條視覺效果，以顯示2023年1月1日事件（事件）的每小時趨勢。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 每小時趨勢]**&#x200B;面板：

![Customer Journey Analytics每小時趨勢視覺效果](../assets/cja_hourly_trend.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **不**&#x200B;瞭解如何處理日期時間欄位，因此不支援&#x200B;**[!UICONTROL daterangehour]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute]**&#x200B;等維度。

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並指定`01/01/2023` - `02/01/2023`的期間。

      ![Tableau案頭篩選器](../assets/uc3-tableau-filter.png)

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖放&#x200B;**[!UICONTROL Daterangehour]**，並將專案拖放到&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。
      * 從&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 更多]** > **[!UICONTROL 小時]**，以便將值更新為&#x200B;**[!UICONTROL 小時(Daterangeday)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中的&#x200B;**[!UICONTROL 資料表（*量值名稱*）]**&#x200B;清單拖放&#x200B;**[!UICONTROL 發生次數]**，並將專案拖放到&#x200B;**[!UICONTROL 資料列]**&#x200B;旁的欄位中。 值會自動轉換為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭圖形](../assets/uc3-tableau-graph.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Graph`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 請確定已選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。 在&#x200B;**[!UICONTROL 資料]**&#x200B;檢視中：
   1. 選取右上方的&#x200B;**[!UICONTROL 顯示我]**，並選取&#x200B;**[!UICONTROL 文字表格]** （左上方的視覺效果），將資料檢視的內容修改成表格。
   1. 將&#x200B;**[!UICONTROL HOUR(Daterangeday)]**&#x200B;從&#x200B;**[!UICONTROL 欄]**&#x200B;拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭資料](../assets/uc3-tableau-data.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL Graph]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 圖形]**&#x200B;工作表下方的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放至&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。
   1. 在檢視中選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表，並將&#x200B;**[!UICONTROL 整個檢視]**&#x200B;修改為&#x200B;**[!UICONTROL 固定寬度]**。

      您的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視應如下所示。

      ![Tableau案頭儀表板1](../assets/uc3-tableau-dashboard.png)


>[!TAB 觀察者]


1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。
      ![Looker篩選器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/01/02]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;區段，
   1. 從&#x200B;**[!UICONTROL ‣DIMENSIONS]**&#x200B;清單中選取&#x200B;**[!UICONTROL Daterangehour Date]**，然後選取&#x200B;**[!UICONTROL Time]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](../assets/uc3-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc3-jupyter-results.png)


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

   ![RStudio結果](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
