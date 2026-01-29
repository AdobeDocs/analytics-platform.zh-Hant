---
title: 多個Dimension排名
description: Customer Journey Analytics中多種BI工具的BI擴充功能多維度排名使用案例
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 1%

---

# 多個維度排名


在此使用案例中，您想要顯示一個表格，其中劃分2023年產品類別中產品名稱的購買收入和購買。 此外，您想使用一些視覺效果來說明產品類別分佈以及每個產品類別內的產品名稱貢獻。

+++ Customer Journey Analytics

使用案例的&#x200B;**[!UICONTROL 多個Dimension排名]**&#x200B;面板範例：

![Customer Journey Analytics多個Dimension排名面板](../assets/cja-multiple-dimension-ranked.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](connect-and-validate.md)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 若要確保日期範圍套用至所有視覺效果，請將&#x200B;**[!UICONTROL daterangeday]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖放至此頁面上的&#x200B;**[!UICONTROL 篩選器]**。
   1. 從此頁面的&#x200B;**[!UICONTROL 篩選器]**&#x200B;中選取&#x200B;**[!UICONTROL daterangeday is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 相對日期]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 位於最後]** `1` **[!UICONTROL 日曆年]**&#x200B;時顯示專案。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL datarangeday]**。
   1. 選取&#x200B;**[!UICONTROL product_category]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL sum purchase_revenue]**
   1. 選取&#x200B;**[!UICONTROL 購買總和]**

1. 若要將垂直長條圖修改為表格，請確定您已選取表格，並從&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中選取&#x200B;**[!UICONTROL 矩陣]**。
   * 從&#x200B;**[!UICONTROL 資料行]**&#x200B;拖曳&#x200B;**[!UICONTROL product_name]**，並將欄位拖放到[!UICONTROL 視覺效果]窗格中的&#x200B;**[!UICONTROL 資料列]******[!UICONTROL product_categor]****y下。

1. 若要限制表格內顯示的產品數量，請在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中選取&#x200B;**[!UICONTROL product_name is (All)]**。

   1. 選取&#x200B;**[!UICONTROL 進階篩選]**。
   1. 選取&#x200B;**[!UICONTROL 篩選器型別]** **[!UICONTROL 前N]** **[!UICONTROL 顯示專案]** **[!UICONTROL 前]** `15` **[!UICONTROL 依值]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格將&#x200B;**[!UICONTROL 購買]**&#x200B;拖曳至&#x200B;**[!UICONTROL 在此新增資料欄位]**。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

1. 若要改善可讀性，請從頂端功能表選取&#x200B;**[!UICONTROL 檢視]**，然後選取&#x200B;**[!UICONTROL 頁面檢視]** > **[!UICONTROL 實際大小]**，並調整表格視覺效果的大小。

1. 若要劃分表格中的每個類別，請在產品類別層級選取&#x200B;**[!UICONTROL +]**。 您的Power BI案頭應該如下所示。

   ![Power BI案頭多維度排名對照表](../assets/uc6-powerbi-data.png)

1. 從頂端功能表選取&#x200B;**[!UICONTROL 首頁]**，然後選取&#x200B;**[!UICONTROL 新增視覺效果]**。 新的視覺效果已新增至您的報表。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL product_category]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL purchase_revenue]**。

1. 若要修改視覺效果，請選取長條圖，然後從&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中選取&#x200B;**[!UICONTROL 樹狀圖]**。
1. 請確定&#x200B;**[!UICONTROL product_category]**&#x200B;列在&#x200B;**[!UICONTROL Category]**&#x200B;之下，而&#x200B;**[!UICONTROL product_name]**&#x200B;列在&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格的&#x200B;**[!UICONTROL 詳細資料]**&#x200B;之下。

   您的Power BI案頭應該如下所示。

   ![Power BI案頭多維度排名樹狀圖](../assets/uc6-powerbi-treemap.png)

1. 從頂端功能表選取&#x200B;**[!UICONTROL 首頁]**，然後選取&#x200B;**[!UICONTROL 新增視覺效果]**。 新的視覺效果已新增至您的報表。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL product_category]**。
   1. 選取&#x200B;**[!UICONTROL purchase_revenue]**。
   1. 選取&#x200B;**[!UICONTROL 購買]**。

1. 在&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中：
   1. 若要修改視覺效果，請選取&#x200B;**[!UICONTROL 折線圖和棧疊直條圖]**。
   1. 將&#x200B;**[!UICONTROL sum_of_purchases]**&#x200B;從&#x200B;**[!UICONTROL 欄y軸]**&#x200B;拖曳至&#x200B;**[!UICONTROL 行y軸]**。

1. 在報表中，重新整理個別視覺效果。

   您的Power BI案頭應該如下所示。

   ![Power BI案頭多維度排名最後](../assets/uc6-powerbi-final.png)


>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 相對日期]**，選取&#x200B;**[!UICONTROL 年]**，並指定&#x200B;**[!UICONTROL 上一年]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](../assets/uc6-tableau-filter.png)

   1. 拖曳&#x200B;**[!UICONTROL 產品類別]**，並拖曳至&#x200B;**[!UICONTROL 欄]**&#x200B;旁。
   1. 拖曳&#x200B;**[!UICONTROL Purchase Revenue]**，並放置到&#x200B;**[!UICONTROL 列]**&#x200B;旁。 值變更為&#x200B;**[!UICONTROL SUM（購買收入）]**。
   1. 將購買拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁。 值變更為&#x200B;**[!UICONTROL SUM（購買）]**。
   1. 選取&#x200B;**[!UICONTROL SUM（購買）]**，並從下拉式功能表選取&#x200B;**[!UICONTROL 雙軸]**。
   1. 選取&#x200B;**[!UICONTROL 標籤]**&#x200B;中的&#x200B;**[!UICONTROL SUM（購買）]**，並從下拉式功能表中選取&#x200B;**[!UICONTROL 行]**。
   1. 在&#x200B;**[!UICONTROL 標籤]**&#x200B;中選取&#x200B;**[!UICONTROL SUM(Purchase Revenue)]**，並從下拉式功能表中選取&#x200B;**[!UICONTROL 列]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;功能表選取&#x200B;**[!UICONTROL 整個檢視]**。
   1. 選取圖表中的&#x200B;**[!UICONTROL 購買收入]**&#x200B;標題，並確認購買收入為遞增順序。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多維度排名類別](../assets/uc6-tableau-category.png)

1. 將目前的&#x200B;**[!UICONTROL 工作表1]**&#x200B;重新命名為`Category`。
1. 選取&#x200B;**[!UICONTROL 新增工作表]**&#x200B;以建立新工作表，並將它重新命名為`Data`。

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 相對日期]**，選取&#x200B;**[!UICONTROL 年]**，並指定&#x200B;**[!UICONTROL 上一年]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL 購買收入]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 欄]**。 值變更為&#x200B;**[!UICONTROL SUM（購買收入）]**。
   1. 將&#x200B;**[!UICONTROL Purchase]**&#x200B;從&#x200B;**[!UICONTROL Data]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 欄]** （在&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;旁）。 值變更為&#x200B;**[!UICONTROL SUM（購買）]**。
   1. 將&#x200B;**[!UICONTROL 產品類別]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 將&#x200B;**[!UICONTROL 產品名稱]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 產品類別]**&#x200B;旁的&#x200B;**[!UICONTROL 列]**。
   1. 若要將兩個水準列變更為表格，請從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表格]**。
   1. 若要限制產品數量，請在&#x200B;**[!UICONTROL 量值值]**&#x200B;中選取&#x200B;**[!UICONTROL 購買]**。 從下拉式功能表中選取&#x200B;**[!UICONTROL 篩選器]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[購買\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 至少]**&#x200B;並輸入`7000`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;****「符合」下拉式功能表中選取&#x200B;**[!UICONTROL 「符合寬度]**」。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多重Dimension排名資料](../assets/uc6-tableau-data.png)

1. 選取&#x200B;**[!UICONTROL 新工作表]**&#x200B;以建立新工作表，並將它重新命名為&#x200B;**[!UICONTROL 樹狀圖]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 相對日期]**，選取&#x200B;**[!UICONTROL 年]**，並指定&#x200B;**[!UICONTROL 上一年]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 列]**。 值變更為&#x200B;**[!UICONTROL SUM(Purchase Revenue)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格將&#x200B;**[!UICONTROL Purchase]**&#x200B;拖曳至&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;旁的&#x200B;**[!UICONTROL 列]**。 值變更為&#x200B;**[!UICONTROL SUM（購買）]**。
   1. 將&#x200B;**[!UICONTROL 產品類別]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 欄]**。
   1. 將&#x200B;**[!UICONTROL 產品名稱]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖曳至&#x200B;**[!UICONTROL 欄]**。
   1. 若要將兩個垂直長條圖變更為樹狀圖，請從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 樹狀圖]**。
   1. 若要限制產品數量，請在&#x200B;**[!UICONTROL 量值值]**&#x200B;中選取&#x200B;**[!UICONTROL 購買]**。 從下拉式功能表中選取&#x200B;**[!UICONTROL 篩選器]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[購買\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 至少]**&#x200B;並輸入`7000`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多重Dimension排名資料](../assets/uc6-tableau-treemap.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL 類別]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 樹狀圖]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視的&#x200B;**[!UICONTROL 類別]**&#x200B;工作表下。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視的&#x200B;**[!UICONTROL 樹狀圖]**&#x200B;工作表下。
   1. 調整檢視中的每個頁面大小。

   您的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視應如下所示。

   ![Tableau案頭儀表板1](../assets/uc6-tableau-final.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。
      ![Looker篩選器](../assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2024/01/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL 產品類別]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
1. 從左側邊欄中的&#x200B;**[!UICONTROL ‣自訂欄位]**&#x200B;區段：
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 自訂量值]**。
   1. 在&#x200B;**[!UICONTROL 建立自訂量值]**&#x200B;對話方塊中：
      1. 從&#x200B;**[!UICONTROL 要量值]**&#x200B;的欄位下拉式功能表中選取&#x200B;**[!UICONTROL 購買收入]**。
      1. 從&#x200B;**[!UICONTROL 量值型別]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 總和]**。
      1. 輸入&#x200B;**[!UICONTROL 名稱]**&#x200B;的自訂欄位名稱。 例如：`Sum of Purchase Revenue`。
      1. 選取&#x200B;**[!UICONTROL 欄位詳細資料]**&#x200B;標籤。
      1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式選單中選取&#x200B;**[!UICONTROL 小數]**，並確定`0`是以&#x200B;**[!UICONTROL 小數]**輸入。
         ![Looker自訂量度欄位](../assets/uc5-looker-customfield.png)
      1. 選取&#x200B;**[!UICONTROL 「儲存」]**。
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中再次選取&#x200B;**[!UICONTROL 自訂量值]**。 在&#x200B;**[!UICONTROL 建立自訂]**&#x200B;量值對話方塊中：
      1. 從&#x200B;**[!UICONTROL 要測量]**&#x200B;的欄位下拉式功能表中選取&#x200B;**[!UICONTROL 購買]**。
      1. 從&#x200B;**[!UICONTROL 量值型別]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 總和]**。
      1. 輸入&#x200B;**[!UICONTROL 名稱]**&#x200B;的自訂欄位名稱。 例如：`Sum of Purchases`。
      1. 選取&#x200B;**[!UICONTROL 欄位詳細資料]**&#x200B;標籤。
      1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式選單中選取&#x200B;**[!UICONTROL 小數]**，並確定`0`是以&#x200B;**[!UICONTROL 小數]**&#x200B;輸入。
      1. 選取&#x200B;**[!UICONTROL 「儲存」]**。
   1. 這兩個欄位都會自動新增至資料檢視。
1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;區段中，選取&#x200B;**[!UICONTROL +篩選器]**。 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中。 選取‣**[!UICONTROL 自訂欄位]**，然後選取&#x200B;**[!UICONTROL 購買收入]**。
1. 選取&#x200B;**[!UICONTROL 是>]**&#x200B;並輸入`800000`以限制結果。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。
1. 選取&#x200B;**[!UICONTROL 視覺效果]**&#x200B;中的&#x200B;**[!UICONTROL 編輯]**&#x200B;以更新視覺效果。 在快顯對話框中：
   1. 選取&#x200B;**[!UICONTROL 繪圖]**&#x200B;標籤。
   1. 向下捲動並選取&#x200B;**[!UICONTROL 編輯圖表設定]**。
   1. 修改&#x200B;**[!UICONTROL 圖表設定（覆寫）]**&#x200B;中的JSON （如下方熒幕擷圖所示），然後選取&#x200B;**[!UICONTROL 預覽]**。

      ![Looker視覺化設定](../assets/uc6-looker-visualization.png)

   1. 選取&#x200B;**[!UICONTROL 「套用」]**。
   1. 選取![編輯](/help/assets/icons/CrossSize75.svg)旁的&#x200B;**[!UICONTROL CrossSize75]**&#x200B;以隱藏快顯對話方塊

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](../assets/uc6-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_category AS `Product Category`, product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1, 2 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby(['Product Category', 'Product Name'], as_index=False).sum()
   plt.figure(figsize=(8, 8))
   sns.scatterplot(x='Product Category', y='Product Name', size='Purchase Revenue', sizes=(10, 200), hue='Purchases', palette='husl', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](../assets/uc6-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ```{r} `到` ``` `之間的下列陳述式。

   ```R
   ## Multiple dimensions ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_category, product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](../assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++
