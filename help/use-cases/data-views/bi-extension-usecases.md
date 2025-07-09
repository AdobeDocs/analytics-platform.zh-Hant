---
title: Customer Journey Analytics中BI擴充功能的使用案例
description: 多個使用案例說明如何在Customer Journey Analytics的各種BI工具中使用BI擴充功能
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: 3d1e3b79-402d-44ff-86b3-be9fd5494e19
source-git-commit: 4b3effffe944df9aaf473c27acc5b2260acbb753
workflow-type: tm+mt
source-wordcount: '13444'
ht-degree: 2%

---

# BI 擴充功能使用案例

本文記錄如何使用Customer Journey Analytics BI擴充功能完成許多使用案例。 每個使用案例都會說明Customer Journey Analytics功能，以及支援的每個BI工具的詳細資料：

* **Power BI案頭版**。 使用的版本是2.137.1102.0 64位元（2024年10月）。
* **Tableau案頭**。 使用的版本為2024.1.5 (20241.24.0705.0334) 64位元。
* **觀察者**。 線上版本25.0.23，透過[looker.com](https://looker.com)提供
* **Jupyter筆記本**。 使用的版本是7.3.2。
* **RStudio**。 使用的版本為2024.12.0，版本編號467。

已記錄下列使用案例：

* **連線**
   * [連線並列出資料檢視](#connect-and-validate)

* **報告和分析**
   * [每日趨勢](#daily-trend)
   * [每小時趨勢](#hourly-trend)
   * [每月趨勢](#monthly-trend)
   * [單一維度排名](#single-dimension-ranked)
   * [多個維度排名](#multiple-dimension-ranked)
   * [計算不同的維度值](#count-distinct-dimension-values)
   * [使用日期範圍名稱進行篩選](#use-date-range-names-to-filter)
   * [使用區段名稱來分段](#use-segment-names-to-segment)
   * [使用維度值劃分割槽段](#use-dimension-values-to-segment)
   * [排序](#sort)
   * [限制](#limits)

* **瞭解**

   * [轉換](#transformations)
   * [視覺效果](#visualizations)
   * [注意事項](#caveats)

**connect**&#x200B;使用案例著重於如何使用Customer Journey Analytics BI擴充功能連線BI工具。

**報表和分析**&#x200B;使用案例會指示如何在目前支援的BI工具中完成類似的Customer Journey Analytics視覺效果。

**瞭解**&#x200B;使用案例提供以下詳細資訊：

* 當您使用BI工具來報告和分析時所發生的轉換。
* Customer Journey Analytics和BI工具之間的視覺效果異同。
* 您應留意的每個BI工具注意事項。


## 連線並驗證

此使用案例會設定從BI工具到Customer Journey Analytics的連線、列出可用的資料檢視，並選取要使用的資料檢視。

+++ Customer Journey Analytics

這些指示參考到包含以下物件的範例環境：

* 資料檢視： **[!UICONTROL C&amp;C — 資料檢視]** 🅐。
* 維度： **[!UICONTROL 產品名稱]** 🅑和&#x200B;**[!UICONTROL 產品類別]** 🅒。
* 量度： **[!UICONTROL 購買收入]** 🅓和&#x200B;**[!UICONTROL 購買]** 🅔。
* 篩選器： **[!UICONTROL 釣魚產品]** 🅕。

![Customer Journey Analytics基本設定](assets/cja-base.png)

當您進行使用案例時，請將這些範例物件取代為您特定環境的物件。

+++

+++ BI 工具

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 從Experience Platform查詢服務UI存取必要的認證和引數。

   1. 導覽至您的Experience Platform沙箱。
   1. 從左側邊欄選取![查詢](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查詢]**。
   1. 在&#x200B;**[!UICONTROL 查詢]**&#x200B;介面中選取&#x200B;**[!UICONTROL 認證]**&#x200B;標籤。
   1. 從`prod:cja`資料庫&#x200B;**[!UICONTROL 下拉式功能表中選取]**。

      ![查詢服務認證](assets/queryservice-credentials.png)

1. 啟動Power BI Desktop。
   1. 從主介面中，選取&#x200B;**[!UICONTROL 從其他來源取得資料]**。
   1. 在&#x200B;**[!UICONTROL 取得資料]**&#x200B;對話方塊中：

      ![PowerBI PostgreSQL資料庫](assets/powerbi-postgresql.png)
      1. 搜尋並選取&#x200B;**[!UICONTROL PostgreSQL資料庫]**。
      1. 選取&#x200B;**[!UICONTROL 連線]**。
   1. 在&#x200B;**[!UICONTROL PostgreSQL資料庫]**&#x200B;對話方塊中：

      ![PowerBI案頭伺服器和資料庫設定](assets/powerbi-serverdatabase.png)
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 主機]**&#x200B;和&#x200B;**[!UICONTROL 連線埠]**&#x200B;值，以`:`分隔，做為&#x200B;**[!UICONTROL 伺服器]**&#x200B;的值。 例如：`examplecompany.platform-query.adobe.io:80`。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 資料庫]**&#x200B;值。 將`?FLATTEN`新增至您貼上的值。 例如，`prod:cja?FLATTEN`。
      1. 選取&#x200B;**[!UICONTROL DirectQuery]**&#x200B;作為&#x200B;**[!UICONTROL 資料連線模式]**。
      1. 選取&#x200B;**[!UICONTROL 確定]**。
   1. 在&#x200B;**[!UICONTROL PostgreSQL資料庫]** - **[!UICONTROL 資料庫]**&#x200B;對話方塊中：

      ![PowerBI案頭使用者和密碼](assets/powerbi-userpassword.png)
      1. 使用![複製](/help/assets/icons/Copy.svg)從&#x200B;**[!UICONTROL 使用者名稱]**&#x200B;和&#x200B;**[!UICONTROL 密碼]**&#x200B;欄位的Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板中複製&#x200B;**[!UICONTROL 使用者名稱]**&#x200B;和&#x200B;**[!UICONTROL 密碼]**&#x200B;值。 如果您使用[不會到期的認證](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect)，請使用不會到期的認證的密碼。
      1. 確定&#x200B;**[!UICONTROL 的下拉式功能表「選取要套用這些設定至]**&#x200B;的層級」已設定為您先前定義的&#x200B;**[!UICONTROL 伺服器]**。
      1. 選取&#x200B;**[!UICONTROL 連線]**。
   1. 在&#x200B;**[!UICONTROL 導覽器]**&#x200B;對話方塊中，會擷取資料檢視。 此擷取作業可能需要一些時間。 擷取後，您會在Power BI Desktop中看到下列內容。

      ![Power BI Destkop載入資料](assets/powerbi-navigator-load.png)
      1. 從左側面板的清單中選取&#x200B;**[!UICONTROL public.cc_data_view]**。
      1. 您有兩個選項:
         1. 選取&#x200B;**[!UICONTROL 載入]**&#x200B;以繼續並完成設定。
         1. 選取&#x200B;**[!UICONTROL 轉換資料]**。 您會看到一個對話方塊，您可以選擇將轉換套用為組態的一部分。

            ![Power BI案頭轉換資料](assets/powerbi-transform-data.png)
            * 選取&#x200B;**[!UICONTROL 關閉並套用]**。
   1. 一段時間後，**[!UICONTROL public.cc_data_view]**&#x200B;會顯示在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中。 選取![V形右側](/help/assets/icons/ChevronRight.svg)以顯示維度和量度。

      ![已載入Power BI Destkop伺服器資料](assets/powerbi-navigator-loaded.png)


### 是否平面化

Power BI Desktop支援下列`FLATTEN`引數案例。 如需詳細資訊，請參閱[平面化巢狀資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)。

| FLATTEN引數 | 範例 | 支援 | 備註 |
|---|---|:---:|---|
| 無 | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **建議使用的選項！** |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCycle](/help/assets/icons/CloseCircle.svg) | Power BI案頭顯示錯誤： **[!UICONTROL 無法使用提供的認證進行驗證。 請再試一次。]** |

### 詳細資訊

* [先決條件](/help/data-views/bi-extension.md#prerequisites)
* [認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)
* [將Power BI連線至查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/power-bi)。




>[!TAB Tableau案頭]

1. 從Experience Platform查詢服務UI存取必要的認證和引數。

   1. 導覽至您的Experience Platform沙箱。
   1. 從左側邊欄選取![查詢](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查詢]**。
   1. 在&#x200B;**[!UICONTROL 查詢]**&#x200B;介面中選取&#x200B;**[!UICONTROL 認證]**&#x200B;標籤。
   1. 從`prod:cja`資料庫&#x200B;**[!UICONTROL 下拉式功能表中選取]**。

      ![查詢服務認證](assets/queryservice-credentials.png)

1. 啟動Tableau。
   1. 從&#x200B;**[!UICONTROL 下的左側邊欄選取]** PostgreSQL **[!UICONTROL 以連線至伺服器]**。 如果無法取得，請選取&#x200B;**[!UICONTROL 更多……]**，然後從&#x200B;**[!UICONTROL 安裝的聯結器]**&#x200B;中選取&#x200B;**[!UICONTROL PostgreSQL]**。

      ![Tableau聯結器](assets/tableau-connectors.png)
   1. 在&#x200B;**[!UICONTROL PostgreSQL]**&#x200B;對話方塊的&#x200B;**[!UICONTROL 一般]**&#x200B;索引標籤中：

      ![Tableau登入對話方塊](assets/tableau-signin.png)
      1. 使用![複製](/help/assets/icons/Copy.svg)將&#x200B;**[!UICONTROL 主機]**&#x200B;從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到&#x200B;**[!UICONTROL 伺服器]**。
      1. 使用![複製](/help/assets/icons/Copy.svg)將&#x200B;**[!UICONTROL 連線埠]**&#x200B;從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到&#x200B;**[!UICONTROL 連線埠]**。
      1. 使用![複製](/help/assets/icons/Copy.svg)將&#x200B;**[!UICONTROL 資料庫]**&#x200B;從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到&#x200B;**[!UICONTROL 資料庫]**。 將`%3FFLATTEN`新增至您貼上的值。 例如：`prod:cja%3FFLATTEN`。
      1. 從&#x200B;**[!UICONTROL 驗證]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 使用者名稱和密碼]**。
      1. 使用![複製](/help/assets/icons/Copy.svg)將&#x200B;**[!UICONTROL 使用者名稱]**&#x200B;從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到&#x200B;**[!UICONTROL 使用者名稱]**。
      1. 使用![複製](/help/assets/icons/Copy.svg)將&#x200B;**[!UICONTROL 密碼]**&#x200B;從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到&#x200B;**[!UICONTROL 密碼]**。 如果您使用[不會到期的認證](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials?lang=en#use-credential-to-connect)，請使用不會到期的認證的密碼。
      1. 請確定已核取&#x200B;**[!UICONTROL 需要SSL]**。
      1. 選取「**[!UICONTROL 登入]**」。

      Tableau Desktop驗證連線時，您看到&#x200B;**[!UICONTROL 處理中要求]**&#x200B;對話方塊。
   1. 在主視窗中，您會在左窗格的&#x200B;**[!UICONTROL 資料Source]**&#x200B;頁面中看到：
      * **[!UICONTROL 連線]**&#x200B;下的連線名稱。
      * **[!UICONTROL 資料庫]**&#x200B;底下的資料庫名稱。
      * **[!UICONTROL 表格]**&#x200B;下的表格清單。

        ![Tableau已連線](assets/tableau-connected.png)
      1. 將&#x200B;**[!UICONTROL cc_data_view]**&#x200B;專案拖放到顯示&#x200B;**[!UICONTROL 將表格]**&#x200B;拖曳到此處的主檢視上。
   1. 主視窗會顯示&#x200B;**[!UICONTROL cc_data_view]**&#x200B;資料檢視的詳細資料。

      ![Tableau已連線](assets/tableau-validation.png)

### 是否平面化

Tableau Desktop支援下列`FLATTEN`引數案例。 如需詳細資訊，請參閱[平面化巢狀資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)。

| FLATTEN引數 | 範例 | 支援 | 備註 |
|---|---|:---:|---|
| 無 | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **建議使用的選項**。 請注意，`%3FFLATTEN`是`?FLATTEN`的URL編碼版本。 |

### 詳細資訊

* [先決條件](/help/data-views/bi-extension.md#prerequisites)
* [認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)
* [將Tableau案頭連線至查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/clients/tableau)。


>[!TAB 觀察者]

1. 從Experience Platform查詢服務UI存取必要的認證和引數。

   1. 導覽至您的Experience Platform沙箱。
   1. 從左側邊欄選取![查詢](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查詢]**。
   1. 在&#x200B;**[!UICONTROL 查詢]**&#x200B;介面中選取&#x200B;**[!UICONTROL 認證]**&#x200B;標籤。
   1. 從`prod:cja`資料庫&#x200B;**[!UICONTROL 下拉式功能表中選取]**。

      ![查詢服務認證](assets/queryservice-credentials.png)

1. 登入Looker

   1. 選取左邊欄的「**[!UICONTROL 管理員]**」。
   1. 選取「**[!UICONTROL 連線]**」。
   1. 選取「**[!UICONTROL 新增連線]**」。
   1. 在&#x200B;**[!UICONTROL 將資料庫連線到Looker畫面]**。

      ![Looker連線到資料庫](assets/looker-connect.png)

      1. 輸入連線的&#x200B;**[!UICONTROL 名稱]**，例如`Example Looker Connection`。
      1. 請確定已選取&#x200B;**[!UICONTROL 所有專案]**&#x200B;做為&#x200B;**[!UICONTROL 連線範圍]**。
      1. 選取&#x200B;**[!UICONTROL PostgreSQL 9.5+]**&#x200B;作為方言。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 主機]**&#x200B;值，作為&#x200B;**[!UICONTROL 主機]**&#x200B;的值。 例如：`examplecompany.platform-query.adobe.io`。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 連線埠]**&#x200B;值，作為&#x200B;**[!UICONTROL 連線埠]**&#x200B;的值。 例如：`80`。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 資料庫]**&#x200B;值，作為&#x200B;**[!UICONTROL 資料庫]**&#x200B;的值。 將`%3FFLATTEN`新增至您貼上的值。 例如，`prod:cja%3FFLATTEN`。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 使用者名稱]**&#x200B;值，作為&#x200B;**[!UICONTROL 使用者名稱]**&#x200B;的值。
      1. 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上&#x200B;**[!UICONTROL 密碼]**&#x200B;值，作為&#x200B;**[!UICONTROL 密碼]**&#x200B;的值。
      1. 選取&#x200B;**[!UICONTROL 選擇性設定]**&#x200B;的&#x200B;**[!UICONTROL 全部展開]**。
      1. 將每個節點的&#x200B;**[!UICONTROL 最大連線數]**&#x200B;設定為`5`。
      1. 確定&#x200B;**[!UICONTROL SSL]**&#x200B;已啟用。
      1. 選取&#x200B;**[!UICONTROL 測試]**&#x200B;以測試連線。 您應該會看到橫幅出現在畫面頂端，並顯示&#x200B;**[!UICONTROL Success， can connect JDBC ....]**&#x200B;之類的訊息。
      1. 選取&#x200B;**[!UICONTROL 連線]**&#x200B;以建立和儲存連線。
   1. 您會在&#x200B;**[!UICONTROL 連線]**&#x200B;介面中看到新連線。
   1. 從&#x200B;**管理員←3&rbrace;選取**&#x200B;管理員&#x200B;**[!UICONTROL 以移至左側邊欄中的主導覽。]**
   1. 選取&#x200B;**[!UICONTROL 開發]**。
   1. 選取&#x200B;**[!UICONTROL 專案]**。
   1. 選取LookML專案中的&#x200B;**[!UICONTROL 新模型]**。
   1. 以確保不會影響其他使用者。 出現提示時，選取「進入開發模式」。
   1. 在&#x200B;**[!UICONTROL 建立模型]**&#x200B;體驗中：
      1. 在&#x200B;**[!UICONTROL ➊中，選取資料庫連線]**：
         1. 在&#x200B;**[!UICONTROL 選取資料庫連線]**&#x200B;中選取您的資料庫連線。 例如： **[!UICONTROL example_looker_connection]**。
         1. 在&#x200B;**[!UICONTROL 中命名您的專案為此模型建立新的LookML專案]**。 針對`example: example_looker_project`。
         1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
      1. 在&#x200B;**[!UICONTROL ➋中選取資料表]**：
         1. 選取&#x200B;**[!UICONTROL public]**，然後確定已選取您的Customer Journey Analytics資料檢視。 例如： ![SelectBox](/help/assets/icons/SelectBox.svg) **[!UICONTROL cc_data_view]**。
         1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
      1. 在&#x200B;**[!UICONTROL ➌中選取主索引鍵]**：
         1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
      1. 在&#x200B;**[!UICONTROL ➍中選取要建立的探索]**：
         1. 請確定您選取檢視。 例如： **[!UICONTROL cc_data_view.view]**。
         1. 選取&#x200B;**[!UICONTROL 「下一步」]**。
      1. 在&#x200B;**[!UICONTROL ➎中輸入模型名稱]**：
         1. 為您的模型命名。 例如：`example_looker_model`。
      1. 選取&#x200B;**[!UICONTROL 完成並探索資料]**。

   系統會將您重新導向至Looker的&#x200B;**[!UICONTROL 探索]**&#x200B;介面，準備探索資料。



### 是否平面化

Looker支援`FLATTEN`引數的下列案例。 如需詳細資訊，請參閱[平面化巢狀資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)。

| FLATTEN引數 | 範例 | 支援 | 備註 |
|---|---|:---:|---|
| 無 | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **建議使用的選項**。 請注意，`%3FFLATTEN`是`?FLATTEN`的URL編碼版本。 |

### 詳細資訊

* [先決條件](/help/data-views/bi-extension.md#prerequisites)
* [認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)


>[!TAB Jupyter Notebook]

1. 從Experience Platform查詢服務UI存取必要的認證和引數。

   1. 導覽至您的Experience Platform沙箱。
   1. 從左側邊欄選取![查詢](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查詢]**。
   1. 在&#x200B;**[!UICONTROL 查詢]**&#x200B;介面中選取&#x200B;**[!UICONTROL 認證]**&#x200B;標籤。
   1. 從`prod:cja`資料庫&#x200B;**[!UICONTROL 下拉式功能表中選取]**。

      ![查詢服務認證](assets/queryservice-credentials.png)

1. 請確定您已設定專用的Python虛擬環境，以執行Jupyter Notebook環境。
1. 確認已在虛擬環境中安裝必要的程式庫：
   * ipython-sql： `pip install ipython-sql`。
   * psycopg2-binary： `pip install psycopg-binary`。
   * sqlalchemy： pip `install sqlalchemy`。

1. 從您的虛擬環境啟動Jupyter Notebook： `jupyter notebook`。
1. 建立新的筆記本，或下載[此範例筆記本](assets/BI-Extension.ipynb.zip)。
1. 在第一個儲存格中，輸入並執行：

   ```
   %config SqlMagic.style = '_DEPRECATED_DEFAULT'
   ```

1. 在新儲存格中輸入連線的設定引數。 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上設定引數所需值的值。 例如：

   ```
   import ipywidgets as widgets
   from IPython.display import display
   
   config_host = widgets.Text(description='Host:', value='example.platform-query-stage.adobe.io',
                           layout=widgets.Layout(width="600px"))
   display(config_host)
   config_port = widgets.IntText(description='Port:', value=80,
                              layout=widgets.Layout(width="200px"))
   display(config_port)
   config_db = widgets.Text(description='Database:', value='prod:cja',
                         layout=widgets.Layout(width="300px"))
   display(config_db)
   config_username = widgets.Text(description='Username:', value='EC582F955C8A79F70A49420E@AdobeOrg',
                               layout=widgets.Layout(width="600px"))
   display(config_username)
   config_password = widgets.Password(description='Password:', value='***',
                                   layout=widgets.Layout(width="600px"))
   display(config_password)
   ```

1. 執行儲存格。
1. 使用![複製](/help/assets/icons/Copy.svg)將密碼從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到Jupyter Notebook中的&#x200B;**[!UICONTROL 密碼]**&#x200B;欄位。

   ![Jupter Notebook設定步驟1](assets/jupyter-config-step1.png)

1. 在新儲存格中，輸入陳述式以載入SQL擴充功能、必要的程式庫並與Customer Journey Analytics連線。

   ```python
   %load_ext sql
   from sqlalchemy import create_engine
   %sql postgresql://{config_username.value}:{config_password.value}@{config_host.value}:{config_port.value}/{config_db.value}?sslmode=require
   ```

   執行殼層。 您應該不會看到任何輸出，但儲存格應該會在沒有任何警告的情況下執行。

   ![Jupyer筆記本設定步驟4](assets/jupyter-config-step2.png)

1. 在新呼叫中，輸入陳述式，以根據連線取得可用資料檢視的清單。

   ```python
   %%sql
   SELECT n.nspname as "Schema",
      c.relname as "Name",
      CASE c.relkind WHEN 'r' THEN 'table' WHEN 'v' THEN 'view' WHEN 'm' THEN 'materialized view' WHEN 'i' THEN 'index' WHEN 'S' THEN 'sequence' WHEN 's' THEN 'special' WHEN 't' THEN 'TOAST table' WHEN 'f' THEN 'foreign table' WHEN 'p' THEN 'partitioned table' WHEN 'I' THEN 'partitioned index' END as "Type",
      pg_catalog.pg_get_userbyid(c.relowner) as "Owner"
   FROM pg_catalog.pg_class c
   LEFT JOIN pg_catalog.pg_namespace n ON n.oid = c.relnamespace
   WHERE c.relkind IN ('v','')
      AND n.nspname <> 'pg_catalog'
      AND n.nspname !~ '^pg_toast'
      AND n.nspname <> 'information_schema'
      AND pg_catalog.pg_table_is_visible(c.oid)
      AND c.relname NOT LIKE '%test%'
      AND c.relname NOT LIKE '%ajo%'
   ORDER BY 1,2;
   ```

   執行殼層。 您應該會看到輸出類似下列熒幕擷圖的畫面。

   ![Jupyter Notebook設定步驟5](assets/jupyter-config-step3.png)

   您應該會在資料檢視清單中看到&#x200B;**[!UICONTROL cc_data_view]**。

### 是否平面化

Jupyter Notebook支援`FLATTEN`引數的下列案例。 如需詳細資訊，請參閱[平面化巢狀資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)。

| FLATTEN引數 | 範例 | 支援 | 備註 |
|---|---|:---:|---|
| 無 | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CloseCycle](/help/assets/icons/CloseCircle.svg) | |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **建議使用的選項**。 請注意，`%3FFLATTEN`是`?FLATTEN`的URL編碼版本。 |

### 詳細資訊

* [先決條件](/help/data-views/bi-extension.md#prerequisites)
* [認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)

>[!TAB RStudio]

1. 從Experience Platform查詢服務UI存取必要的認證和引數。

   1. 導覽至您的Experience Platform沙箱。
   1. 從左側邊欄選取![查詢](/help/assets/icons/DataSearch.svg) **[!UICONTROL 查詢]**。
   1. 在&#x200B;**[!UICONTROL 查詢]**&#x200B;介面中選取&#x200B;**[!UICONTROL 認證]**&#x200B;標籤。
   1. 從`prod:cja`資料庫&#x200B;**[!UICONTROL 下拉式功能表中選取]**。

      ![查詢服務認證](assets/queryservice-credentials.png)

1. 啟動RStudio。
1. 建立新的R Markdown檔案，或下載[此範例R Markdown檔案](assets/BI-Extension.Rmd.zip)。
1. 在第一個區塊中，輸入下列介於` ` ``{r} `到` `` ` `之間的陳述式。 使用![複製](/help/assets/icons/Copy.svg)從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼上值至各種引數（如`host`、`dbname`和`user`）所需的值。 例如：

   ```R
   library(rstudioapi)
   library(DBI)
   library(dplyr)
   library(tidyr)
   library(RPostgres)
   library(ggplot2)
   
   host <- rstudioapi::showPrompt(title = "Host", message = "Host", default = "orangestagingco.platform-query-stage.adobe.io")
   dbname <- rstudioapi::showPrompt(title = "Database", message = "Database", default = "prod:cja?FLATTEN")
   user <- rstudioapi::showPrompt(title = "Username", message = "Username", default = "EC582F955C8A79F70A49420E@AdobeOrg")
   password <- rstudioapi::askForPassword(prompt = "Password")
   ```

1. 執行區塊。 系統會提示您輸入&#x200B;**[!UICONTROL 主機]**、**[!UICONTROL 資料庫]**&#x200B;和&#x200B;**[!UICONTROL 使用者]**。 只需接受您在上一步中提供之值。
1. 使用![複製](/help/assets/icons/Copy.svg)將密碼從Experience Platform **[!UICONTROL 查詢]** **[!UICONTROL 到期認證]**&#x200B;面板複製並貼到RStudio中的&#x200B;**[!UICONTROL 密碼]**&#x200B;對話方塊提示字元。

   ![RStudio設定步驟1](assets/rstudio-config-step1.png)

1. 建立新的區塊，並輸入下列介於` ` `` {r} `到` `` ` `之間的陳述式。

   ```R
   con <- dbConnect(
      RPostgres::Postgres(),
      host = host,
      port = 80,
      dbname = dbname,
      user = user,
      password = password,
      sslmode = 'require'
   )
   ```

1. 執行區塊。 如果連線成功，應該不會看到任何輸出。


1. 建立新的區塊，並輸入下列介於` ` `` {r} `到` `` ` `之間的陳述式。

   ```R
   views <- dbListTables(con)
   print(views)
   ```

1. 執行區塊。 您應該看到`character(0)`是唯一輸出。


1. 建立新的區塊，並輸入下列介於` ` `` {r} `到` `` ` `之間的陳述式。

   ```R
   glimpse(dv)
   ```

1. 執行區塊。 您應該會看到輸出類似下列熒幕擷圖的畫面。

   ![RStudio設定步驟2](assets/rstudio-config-step2.png)

### 是否平面化

RStudio支援`FLATTEN`引數的下列案例。 如需詳細資訊，請參閱[平面化巢狀資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/key-concepts/flatten-nested-data)。

| FLATTEN引數 | 範例 | 支援 | 備註 |
|---|---|:---:|---|
| 無 | `prod:cja` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | |
| `?FLATTEN` | `prod:cja?FLATTEN` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **建議使用的選項**。 |
| `%3FFLATTEN` | `prod:cja%3FFLATTEN` | ![CloseCycle](/help/assets/icons/CloseCircle.svg) | |

### 詳細資訊

* [先決條件](/help/data-views/bi-extension.md#prerequisites)
* [認證指南](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/ui/credentials)

>[!ENDTABS]

+++


## 每日趨勢

在此使用案例中，您想要顯示一個表格和簡單的線條視覺效果，顯示從2023年1月1日到2023年1月31日的每日發生次數（事件）趨勢。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 每日趨勢]**&#x200B;面板：

![Customer Journey Analytics每日趨勢面板](assets/cja_daily_trend.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>請確認您已驗證[成功的連線，而且可以列出並使用您要嘗試此使用案例之BI工具的資料檢視](#connect-and-validate)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL daterangeday]**。
   1. 選取&#x200B;**[!UICONTROL 發生次數總和]**。

   您會看到一個表格，其中顯示當月的發生次數。 為獲得更好的可見度，請放大視覺效果。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：

   1. 從這個視覺效果&#x200B;**[!UICONTROL 上的]**&#x200B;篩選條件中選取&#x200B;**[!UICONTROL daterangeday is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 位於或晚於]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 位於]** `2/1/2023.`時顯示專案。您可以使用行事曆圖示挑選和選取日期。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

   您會看到已套用&#x200B;**[!UICONTROL daterangeday]**&#x200B;篩選器的資料表已更新。

1. 在&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中，選取&#x200B;**[!UICONTROL 折線圖]**&#x200B;視覺效果。

   使用與表格相同的資料時，折線圖視覺效果會取代表格。 您的Power BI案頭應該如下所示。

   ![Power BI案頭使用案例2日期範圍篩選器](assets/uc2-pbi-daterange.png)

1. 線上圖視覺效果上：

   1. 選取![更多](/help/assets/icons/More.svg)。
   1. 從內容功能表中，選取&#x200B;**[!UICONTROL 顯示為表格]**。

   主要檢視已更新，顯示線條視覺效果和表格。 您的Power BI案頭應該如下所示。

   ![Power BI案頭使用案例2最終每日趨勢視覺效果](assets/uc2-pbi-final.png)

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;檢視進行切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並指定`01/01/2023` - `01/02/2023`的期間。

      ![Tableau案頭篩選器](assets/uc2-tableau-filter.png)

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖放&#x200B;**[!UICONTROL Daterangeday]**，並將專案拖放到&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。
      * 從&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL Day]**，以便將值更新為&#x200B;**[!UICONTROL DAY(Daterangeday)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中的&#x200B;**[!UICONTROL 資料表（*量值名稱*）]**&#x200B;清單拖放&#x200B;**[!UICONTROL 發生次數]**，並將專案拖放到&#x200B;**[!UICONTROL 資料列]**&#x200B;旁的欄位中。 值會自動轉換為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭圖形](assets/uc2-tableau-graph.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Graph`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 請確定已選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。 在&#x200B;**[!UICONTROL 資料]**&#x200B;檢視中：
   1. 選取右上方的&#x200B;**[!UICONTROL 顯示我]**，並選取&#x200B;**[!UICONTROL 文字表格]** （左上方的視覺效果），將資料檢視的內容修改成表格。
   1. 從工具列選取&#x200B;**[!UICONTROL 交換列與欄]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭資料](assets/uc2-tableau-data.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL Graph]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 圖形]**&#x200B;工作表下方的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放至&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。
   1. 在檢視中選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表，並將&#x200B;**[!UICONTROL 整個檢視]**&#x200B;修改為&#x200B;**[!UICONTROL 固定寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭儀表板1](assets/uc2-tableau-dashboard.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍日期]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/02/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;區段，
   1. 從&#x200B;**[!UICONTROL DIMENSIONS‣]**&#x200B;的清單中選取&#x200B;**[!UICONTROL 日期範圍日期]**，然後選取&#x200B;**[!UICONTROL 日期]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](assets/uc2-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangeday AS Date, COUNT(*) AS Events \
             FROM cc_data_view \
             WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
             GROUP BY 1 \
             ORDER BY Date ASC
   df = data.DataFrame()
   df = df.groupby('Date', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Date', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](assets/uc2-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

   ```R
   ## Daily Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(daterangeday) %>%
      count() %>%
      arrange(daterangeday, .by_group = FALSE)
   ggplot(df, aes(x = daterangeday, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Date")
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](assets/uc2-rstudio-results.png)

>[!ENDTABS]

+++


## 每小時趨勢

在此使用案例中，您想要顯示表格和簡單的線條視覺效果，以顯示2023年1月1日事件（事件）的每小時趨勢。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 每小時趨勢]**&#x200B;面板：

![Customer Journey Analytics每小時趨勢視覺效果](assets/cja_hourly_trend.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **不**&#x200B;瞭解如何處理日期時間欄位，因此不支援&#x200B;**[!UICONTROL daterangehour]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute]**&#x200B;等維度。

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並指定`01/01/2023` - `02/01/2023`的期間。

      ![Tableau案頭篩選器](assets/uc3-tableau-filter.png)

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖放&#x200B;**[!UICONTROL Daterangehour]**，並將專案拖放到&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。
      * 從&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 更多]** > **[!UICONTROL 小時]**，以便將值更新為&#x200B;**[!UICONTROL 小時(Daterangeday)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中的&#x200B;**[!UICONTROL 資料表（*量值名稱*）]**&#x200B;清單拖放&#x200B;**[!UICONTROL 發生次數]**，並將專案拖放到&#x200B;**[!UICONTROL 資料列]**&#x200B;旁的欄位中。 值會自動轉換為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭圖形](assets/uc3-tableau-graph.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Graph`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 請確定已選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。 在&#x200B;**[!UICONTROL 資料]**&#x200B;檢視中：
   1. 選取右上方的&#x200B;**[!UICONTROL 顯示我]**，並選取&#x200B;**[!UICONTROL 文字表格]** （左上方的視覺效果），將資料檢視的內容修改成表格。
   1. 將&#x200B;**[!UICONTROL HOUR(Daterangeday)]**&#x200B;從&#x200B;**[!UICONTROL 欄]**&#x200B;拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭資料](assets/uc3-tableau-data.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL Graph]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 圖形]**&#x200B;工作表下方的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放至&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。
   1. 在檢視中選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表，並將&#x200B;**[!UICONTROL 整個檢視]**&#x200B;修改為&#x200B;**[!UICONTROL 固定寬度]**。

      您的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視應如下所示。

      ![Tableau案頭儀表板1](assets/uc3-tableau-dashboard.png)


>[!TAB 觀察者]


1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/01/02]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;區段，
   1. 從&#x200B;**[!UICONTROL ‣DIMENSIONS]**&#x200B;清單中選取&#x200B;**[!UICONTROL Daterangehour Date]**，然後選取&#x200B;**[!UICONTROL Time]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](assets/uc3-looker-result.png)


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

   ![Jupyter Notebook結果](assets/uc3-jupyter-results.png)


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

   ![RStudio結果](assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++


## 每月趨勢

在此使用案例中，您想要顯示表格和簡單的線條視覺效果，以顯示2023年的發生次數（事件）每月趨勢。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 每月趨勢]**&#x200B;面板：

![Customer Journey Analytics每月趨勢視覺效果](assets/cja_monthly_trend.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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

   ![Power BI案頭使用案例2日期範圍篩選器](assets/uc4-pbi-filter-daterange.png)

1. 線上圖視覺效果上：

   1. 選取![更多](/help/assets/icons/More.svg)。
   1. 從內容功能表中，選取&#x200B;**[!UICONTROL 顯示為表格]**。

   主要檢視已更新，顯示線條視覺效果和表格。 您的Power BI案頭應該如下所示。

   ![Power BI案頭使用案例2最終每日趨勢視覺效果](assets/uc4-pbi-filter-final.png)

>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並指定`01/01/2023` - `01/01/2024`的期間。

      ![Tableau案頭篩選器](assets/uc4-tableau-filter.png)

   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖放&#x200B;**[!UICONTROL Daterangeday]**，並將專案拖放到&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。
      * 從&#x200B;**[!UICONTROL Daterangeday]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL MONTH]**，以便將值更新為&#x200B;**[!UICONTROL MONTH(Daterangeday)]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中的&#x200B;**[!UICONTROL 資料表（*量值名稱*）]**&#x200B;清單拖放&#x200B;**[!UICONTROL 發生次數]**，並將專案拖放到&#x200B;**[!UICONTROL 資料列]**&#x200B;旁的欄位中。 值會自動轉換為&#x200B;**[!UICONTROL SUM（發生次數）]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭圖形](assets/uc4-tableau-graph.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Graph`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 請確定已選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。 在資料檢視中：
   1. 選取右上方的&#x200B;**[!UICONTROL 顯示我]**，並選取&#x200B;**[!UICONTROL 文字表格]** （左上方的視覺效果），將資料檢視的內容修改成表格。
   1. 將&#x200B;**[!UICONTROL MONTH(Daterangeday)]**&#x200B;從&#x200B;**[!UICONTROL 欄]**&#x200B;拖曳至&#x200B;**[!UICONTROL 列]**。
   1. 從工具列的&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表，將&#x200B;**[!UICONTROL 標準]**&#x200B;修改為&#x200B;**[!UICONTROL 整個檢視]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭資料](assets/uc4-tableau-data.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL Graph]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 圖形]**&#x200B;工作表下方的&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放至&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。
   1. 在檢視中選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表，並將&#x200B;**[!UICONTROL 整個檢視]**&#x200B;修改為&#x200B;**[!UICONTROL 固定寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭儀表板1](assets/uc4-tableau-dashboard.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2024/01/01]**。
1. 從左側&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;邊欄，
   1. 從&#x200B;**[!UICONTROL DIMENSIONS‣]**&#x200B;的清單中選取&#x200B;**[!UICONTROL Daterangemonth Date]**，然後選取&#x200B;**[!UICONTROL Month]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](assets/uc4-looker-result.png)


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

   ![Jupyter Notebook結果](assets/uc4-jupyter-results.png)


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

   ![RStudio結果](assets/uc4-rstudio-results.png)

>[!ENDTABS]

+++


## 單一維度排名

在此使用案例中，您想要顯示一個表格和簡單的橫條圖視覺效果，以顯示2023年產品名稱的購買和購買收入。

+++ Customer Journey Analytics

使用案例的&#x200B;**[!UICONTROL 單一Dimension排名]**&#x200B;面板範例：

![Customer Journey Analytics單一維度排名視覺效果](assets/cja-single-dimension-ranked.png)

+++

<!--

+++ BI tools

>[!PREREQUISITES]
>
>Ensure you have validated [a successful connection, can list data views, and use a data view](#connect-and-validate) for the BI tool for which you want to try out this use case. 
>

>[!BEGINTABS]

>[!TAB Power BI Desktop] 

1. In the **[!UICONTROL Data]** pane:
   1. Select **[!UICONTROL daterange]**.
   1. Select **[!UICONTROL product_name]**.
   1. Select **[!UICONTROL sum purchase_revenue]**.
   1. Select **[!UICONTROL sum purchases]**.
   
   You see an empty table displaying only the column headers for the selected element. For better visibility, enlarge the visualization.

1. In the **[!UICONTROL Filters]** pane:

   1. Select the **[!UICONTROL daterange is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Select **[!UICONTROL Relative date]** as the **[!UICONTROL Filter type]**.
   1. Define the filter to **[!UICONTROL Show items when the value]** **[!UICONTROL is in the last]** `1` **[!UICONTROL calendar years]**.
   1. Select **[!UICONTROL Apply filter]**.
   
   You see the table updated with the applied **[!UICONTROL daterange]** filter.

1. In the **[!UICONTROL Visualization]** pane:

   1. Use ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove **[!UICONTROL daterange]** from **[!UICONTROL Columns]**.
   1. Drag and drop **[!UICONTROL Sum of purchases_revenue]** underneath **[!UICONTROL Sum of purchases]** in **[!UICONTROL Columns]**.

1. On the Table visualization:
   
   1. Select **[!UICONTROL Sum of purchase_revenue]** to sort the product names in descending purchase revenue order. Your Power BI Desktop should look like below.
   
   ![Power BI Desktop Use Case 5 Table status](assets/uc5-pbi-table.png)

1. In the **[!UICONTROL Filters]** pane:

   1. Select **[!UICONTROL product_name is (All)]**.
   1. Set **[!UICONTROL Filter type]** to **[!UICONTROL Top N]**.
   1. Define the filter to **[!UICONTROL Show items]** **[!UICONTROL Top]** `10` **[!UICONTROL By value]**.
   1. Drag and drop **[!UICONTROL purchase_revenue]** into **[!UICONTROL By value]** **[!UICONTROL Add data fields here]**.
   1. Select **[!UICONTROL Apply filter]**.

   You see the table updated with values for purchase revenue in sync with the Freeform table visualization in Analysis Workspace.

1. In the **[!UICONTROL Visualizations]** pane:

   1. Select the **[!UICONTROL Line and stacked column chart]** visualization. 

   A line and stacked column chart visualization replaces the table while using the same data as the table.

1. Drag and drop **[!UICONTROL purchases]** onto **[!UICONTROL Line y-axis]** in the **[!UICONTROL Visualizations]** pane.

   The line and stacked column chart is updated. Your Power BI Desktop should look like below.

   ![Power BI Desktop Use Case 5 Graph](assets/uc5-pbi-chart.png)

1. On the Line and stacked column chart visualization:

   1. Select ![More](/help/assets/icons/More.svg).
   1. From the context menu, select **[!UICONTROL Show as a table]**.

   The main view is updated to show both a line visualization and a table.

   ![Power BI Desktop Use Case 2 Final Daily Trend visualization](assets/uc5-pbi-final.png)

>[!TAB Tableau Desktop]

1. Select the **[!UICONTROL Sheet 1]** tab at the bottom to switch from **[!UICONTROL Data source]**. In the **[!UICONTROL Sheet 1]** view:
   1. Drag the **[!UICONTROL Daterange]** entry from the **[!UICONTROL Tables]** list in the **[!UICONTROL Data]** pane and drop the entry onto the **[!UICONTROL Filters]** shelf.
   1. In the **[!UICONTROL Filters Field \[Daterange\]]** dialog, select **[!UICONTROL Range of Dates]** and select **[!UICONTROL Next >]**.
   1. In the **[!UICONTROL Filter \[Daterange\]]** dialog, select **[!UICONTROL Range of dates]** and specify a period of `01/01/2023` - `31/12/2023`. Select **[!UICONTROL Apply]** and **[!UICONTROL OK]**.

      ![Tableau Desktop Filter](assets/uc5-tableau-filter.png)

   1. Drag and drop **[!UICONTROL Product Name]** from the **[!UICONTROL Tables]** list in the **[!UICONTROL Data]** pane and drop the entry in the field next to **[!UICONTROL Rows]**.
   1. Drag and drop **[!UICONTROL Purchases]** from the **[!UICONTROL Tables (*Measure Names*)]** list in the **[!UICONTROL Data]** pane and drop the entry in the field next to **[!UICONTROL Rows]**. The value is automatically converted to **[!UICONTROL SUM(Purchases)]**.
   1. Drag and drop **[!UICONTROL Purchase Revenue]** from the **[!UICONTROL Tables (*Measure Names*)]** list in the **[!UICONTROL Data]** pane and drop the entry in the field next to **[!UICONTROL Columns]** and left from **[!UICONTROL SUM(Purchases)]**. The value is automatically converted to **[!UICONTROL SUM(Purchase Revenue)]**.
   1. To order both charts in descending purchase revenue order, hover over the **[!UICONTROL Purchase Revenue]** title and select the sort icon.
   1. To limit the number of entries in the charts, select **[!UICONTROL SUM(Purchase Revenue)]** in **[!UICONTROL Rows]** and from the drop-down menu select **[!UICONTROL Filter]**.
   1. In the **[!UICONTROL Filter \[Purchase Revenue\]]** dialog select **[!UICONTROL Range of values]** and enter appropriate values. For example: `1,000,000` - `2,000,000`. Select **[!UICONTROL Apply]** and **[!UICONTROL OK]**.
   1. To convert the two bar charts to a dual combination chart, select **[!UICONTROL SUM(Purchases)]** in **[!UICONTROL Rows]** and from the drop-down menu, select **[!UICONTROL Dual Axis]**. The bar charts transform into a scatter plot.
   1. To modify the scatter plot to a bar chart:
      1. Select **[!UICONTROL SUM(Purchases)]** in the **[!UICONTROL Marks]** area and select **[!UICONTROL Line]** from the drop-down menu.
      1. Select **[!UICONTROL SUM(Purchase Revenue)]** in the **[!UICONTROL Marks]** area and select **[!UICONTROL Bar]** from the drop-down menu.

   Your Tableau Desktop should look like below.

   ![Tableau Desktop Graph](assets/uc5-tableau-graph.png)

1. Select **[!UICONTROL Duplicate]** from the **[!UICONTROL Sheet 1]** tab context menu to create a second sheet.
1. Select **[!UICONTROL Rename]** from the **[!UICONTROL Sheet 1]** tab context menu to rename the sheet to `Data`.
1. Select **[!UICONTROL Rename]** from the **[!UICONTROL Sheet 1 (2)]** tab context menu to rename the sheet to `Graph`.
1. Ensure that the **[!UICONTROL Data]** sheet is selected.
   1. Select **[!UICONTROL Show me]** at the top right and select **[!UICONTROL Text table]** (upper left top visualization) to modify the content of the two charts to a table.
   1. To order purchase revenue in descending order, hover over **[!UICONTROL Purchase Revenue]** in the table and select ![SortOrderDown](/help/assets/icons/SortOrderDown.svg).
   1. Select **[!UICONTROL Entire View]** from the **[!UICONTROL Fit]** drop-down menu.

   Your Tableau Desktop should look like below.

   ![Tableau Desktop Data](assets/uc5-tableau-data.png)

1. Select **[!UICONTROL New Dashboard]** tab button (at the bottom) to create a new **[!UICONTROL Dashboard 1]** view. In the **[!UICONTROL Dashboard 1]** view:
   1. Drag and drop the **[!UICONTROL Graph]** sheet from the **[!UICONTROL Sheets]** shelf onto the **[!UICONTROL Dashboard 1]** view that reads *Drop sheets here*.
   1. Drag and drop the **[!UICONTROL Data]** sheet from the **[!UICONTROL Sheets]** shelf below the **[!UICONTROL Graph]** sheet onto the **[!UICONTROL Dashboard 1]** view.
   1. Select the **[!UICONTROL Data]** sheet in the view and modify **[!UICONTROL Entire View]** to **[!UICONTROL Fix Width]**.

   Your **[!UICONTROL Dashboard 1]** view should look like below.

   ![Tableau Desktop Dashboard 1](assets/uc5-tableau-dashboard.png)



>[!TAB Looker]

1. In the **[!UICONTROL Explore]** interface of Looker, ensure you do have a clean setup. If not, select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Remove fields and filters]**.
1. Select **[!UICONTROL + Filter]** underneath **[!UICONTROL Filters]**.
1. In the **[!UICONTROL Add Filter]** dialog:
   1. Select **[!UICONTROL ‣ Cc Data View]**
   1. From the list of fields, select **[!UICONTROL ‣ Daterange Date]** then **[!UICONTROL Daterange Date]**.
      ![Looker filter](assets/uc2-looker-filter.png)
1. Specify the **[!UICONTROL Cc Data View Daterange Date]** filter as **[!UICONTROL is in range]** **[!UICONTROL 2023/01/01]** **[!UICONTROL until (before)]** **[!UICONTROL 2024/01/01]**.
1. From the **[!UICONTROL ‣ Cc Data View]** section in the left rail, select **[!UICONTROL Product Name]**.
1. From the **[!UICONTROL ‣ Custom Fields]** section in the left rail:
   1. Select **[!UICONTROL Custom Measure]** from the **[!UICONTROL + Add]** drop-down menu. 
   1. In the **[!UICONTROL Create custom measure]** dialog:
      1. Select **[!UICONTROL Purchase Revenue]** from the **[!UICONTROL Field to measure]** drop-down menu.
      1. Select **[!UICONTROL Sum]** from the **[!UICONTROL Measure type]** drop-down menu.
      1. Enter a custom field name for **[!UICONTROL Name]**. For example: `Purchase Revenue`.
      1. Select the **[!UICONTROL Field details]** tab.
      1. Select **[!UICONTROL Decimals]** from the **[!UICONTROL Format]** drop-down menu and ensure `0` is entered in **[!UICONTROL Decimals]**.
         ![Looker custom metric field](assets/uc5-looker-customfield.png)
      1. Select **[!UICONTROL Save]**.
   1. Select **[!UICONTROL Custom Measure]** once more from the **[!UICONTROL + Add]** drop-down menu. In the **[!UICONTROL Create custom]** measure dialog:
      1. Select **[!UICONTROL Purchases]** from the **[!UICONTROL Field to measure]** drop-down menu.
      1. Select **[!UICONTROL Sum]** from the **[!UICONTROL Measure type]** drop-down menu.
      1. Enter a custom field name for **[!UICONTROL Name]**. For example: `Sum of Purchases`.
      1. Select the **[!UICONTROL Field details]** tab.
      1. Select **[!UICONTROL Decimals]** from the **[!UICONTROL Format]** drop-down menu and ensure `0` is entered in **[!UICONTROL Decimals]**.
      1. Select **[!UICONTROL Save]**.
   1. Both fields are automatically added to the Data view. 
1. Select **[!UICONTROL + Filter]** to add another **[!UICONTROL Filters]** and to limit the data.
1. In the **[!UICONTROL Add Filter]** dialog, select **[!UICONTROL ‣ Custom Fields]**, then **[!UICONTROL Purchase Revenue]**.
1. Make the appropriate selections and enter the proposed values, so the filter reads **[!UICONTROL is between inclusive]** `1000000` **[!UICONTROL AND]** `2000000`.
1. Select **[!UICONTROL Run]**.
1. Select **[!UICONTROL ‣ Visualization]** to display the line visualization.
1. Select **[!UICONTROL Edit]** in **[!UICONTROL Visualization]** to update the visualization. In the popup dialog:
   1. Select the **[!UICONTROL Series]** tab.
   1. Scroll down to see **[!UICONTROL Purchases]** and change the **[!UICONTROL Type]** to **[!UICONTROL Line]**.
   1. Select the **[!UICONTROL Y]** tab.
   1. Drag **[!UICONTROL Purchases]** from the **[!UICONTROL Left 1 ]** container to where it reads **[!UICONTROL *Drag series here to create a new left axis*]**. This action creates a **[!UICONTROL Left 2]** container.
      ![Looker visualization configuration](assets/uc5-looker-visualization.png)
   1. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) next to **[!UICONTROL Edit]** to hide the popup dialog

You should see a visualization and table similar as shown below.

![Looker result daily trend](assets/uc5-looker-result.png)


>[!TAB Jupyter Notebook]

1. Enter the following statements in a new cell.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Purchase Revenue', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Execute the cell. You should see output similar to the screenshot below.

   ![Jupyter Notebook Results](assets/uc5-jupyter-results.png)


>[!TAB RStudio]

1. Enter the following statements between ` ```{r} ` and ` ``` ` in a new chunk.

   ```R
   library(tidyr)

   ## Single dimension ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases)) %>%
      arrange(product_name, .by_group = FALSE)
   dfV <- df %>%
      head(5)
   ggplot(dfV, aes(x = purchase_revenue, y = product_name)) +
      geom_col(position = "dodge") +
      geom_text(aes(label = purchase_revenue), vjust = -0.5)
   print(df)
   ```

1. Run the chunk. You should see output similar to the screenshot below.

   ![RStudio Results](assets/uc5-rstudio-results.png)

>[!ENDTABS]

+++

-->


## 多個維度排名

在此使用案例中，您想要顯示一個表格，其中劃分2023年產品類別中產品名稱的購買收入和購買。 此外，您想使用一些視覺效果來說明產品類別分佈以及每個產品類別內的產品名稱貢獻。

+++ Customer Journey Analytics

使用案例的&#x200B;**[!UICONTROL 多個Dimension排名]**&#x200B;面板範例：

![Customer Journey Analytics多個Dimension排名面板](assets/cja-multiple-dimension-ranked.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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
   * 從&#x200B;**[!UICONTROL 資料行]**&#x200B;拖曳&#x200B;**[!UICONTROL product_name]**，並將欄位拖放到[!UICONTROL 視覺效果]窗格中的&#x200B;**[!UICONTROL 資料列]**&#x200B;**&#x200B;**&#x200B;[!UICONTROL product_categor]&#x200B;**&#x200B;**&#x200B;y下。

1. 若要限制表格內顯示的產品數量，請在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中選取&#x200B;**[!UICONTROL product_name is (All)]**。

   1. 選取&#x200B;**[!UICONTROL 進階篩選]**。
   1. 選取&#x200B;**[!UICONTROL 篩選器型別]** **[!UICONTROL 前N]** **[!UICONTROL 顯示專案]** **[!UICONTROL 前]** `15` **[!UICONTROL 依值]**。
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格將&#x200B;**[!UICONTROL 購買]**&#x200B;拖曳至&#x200B;**[!UICONTROL 在此新增資料欄位]**。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

1. 若要改善可讀性，請從頂端功能表選取&#x200B;**[!UICONTROL 檢視]**，然後選取&#x200B;**[!UICONTROL 頁面檢視]** > **[!UICONTROL 實際大小]**，並調整表格視覺效果的大小。

1. 若要劃分表格中的每個類別，請在產品類別層級選取&#x200B;**[!UICONTROL +]**。 您的Power BI案頭應該如下所示。

   ![Power BI案頭多維度排名對照表](assets/uc6-powerbi-data.png)

1. 從頂端功能表選取&#x200B;**[!UICONTROL 首頁]**，然後選取&#x200B;**[!UICONTROL 新增視覺效果]**。 新的視覺效果已新增至您的報表。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL product_category]**。
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 選取&#x200B;**[!UICONTROL purchase_revenue]**。

1. 若要修改視覺效果，請選取長條圖，然後從&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中選取&#x200B;**[!UICONTROL 樹狀圖]**。
1. 請確定&#x200B;**[!UICONTROL product_category]**&#x200B;列在&#x200B;**[!UICONTROL Category]**&#x200B;之下，而&#x200B;**[!UICONTROL product_name]**&#x200B;列在&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格的&#x200B;**[!UICONTROL 詳細資料]**&#x200B;之下。

   您的Power BI案頭應該如下所示。

   ![Power BI案頭多維度排名樹狀圖](assets/uc6-powerbi-treemap.png)

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

   ![Power BI案頭多維度排名最後](assets/uc6-powerbi-final.png)


>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選器欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 相對日期]**，選取&#x200B;**[!UICONTROL 年]**，並指定&#x200B;**[!UICONTROL 上一年]**。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](assets/uc6-tableau-filter.png)

   1. 拖曳&#x200B;**[!UICONTROL 產品類別]**，並拖曳至&#x200B;**[!UICONTROL 欄]**&#x200B;旁。
   1. 拖曳&#x200B;**[!UICONTROL Purchase Revenue]**，並放置到&#x200B;**[!UICONTROL 列]**&#x200B;旁。 值變更為&#x200B;**[!UICONTROL SUM（購買收入）]**。
   1. 將購買拖放到&#x200B;**[!UICONTROL 列]**&#x200B;旁。 值變更為&#x200B;**[!UICONTROL SUM（購買）]**。
   1. 選取&#x200B;**[!UICONTROL SUM（購買）]**，並從下拉式功能表選取&#x200B;**[!UICONTROL 雙軸]**。
   1. 選取&#x200B;**[!UICONTROL 標籤]**&#x200B;中的&#x200B;**[!UICONTROL SUM（購買）]**，並從下拉式功能表中選取&#x200B;**[!UICONTROL 行]**。
   1. 在&#x200B;**[!UICONTROL 標籤]**&#x200B;中選取&#x200B;**[!UICONTROL SUM(Purchase Revenue)]**，並從下拉式功能表中選取&#x200B;**[!UICONTROL 列]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;功能表選取&#x200B;**[!UICONTROL 整個檢視]**。
   1. 選取圖表中的&#x200B;**[!UICONTROL 購買收入]**&#x200B;標題，並確認購買收入為遞增順序。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多維度排名類別](assets/uc6-tableau-category.png)

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
   1. 從&#x200B;**&#x200B;**「符合」下拉式功能表中選取&#x200B;**[!UICONTROL 「符合寬度]**」。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多重Dimension排名資料](assets/uc6-tableau-data.png)

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

      ![Tableau案頭多重Dimension排名資料](assets/uc6-tableau-treemap.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL 類別]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視（顯示&#x200B;*將工作表拖放至此*）。
   1. 將&#x200B;**[!UICONTROL 樹狀圖]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視的&#x200B;**[!UICONTROL 類別]**&#x200B;工作表下。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視的&#x200B;**[!UICONTROL 樹狀圖]**&#x200B;工作表下。
   1. 調整檢視中的每個頁面大小。

   您的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視應如下所示。

   ![Tableau案頭儀表板1](assets/uc6-tableau-final.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
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
      1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式選單中選取&#x200B;**[!UICONTROL 小數]**，並確定`0`是以&#x200B;**[!UICONTROL 小數]**&#x200B;輸入。

         ![Looker自訂量度欄位](assets/uc5-looker-customfield.png)
      1. 選取「**[!UICONTROL 儲存]**」。
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中再次選取&#x200B;**[!UICONTROL 自訂量值]**。 在&#x200B;**[!UICONTROL 建立自訂]**&#x200B;量值對話方塊中：
      1. 從&#x200B;**[!UICONTROL 要測量]**&#x200B;的欄位下拉式功能表中選取&#x200B;**[!UICONTROL 購買]**。
      1. 從&#x200B;**[!UICONTROL 量值型別]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 總和]**。
      1. 輸入&#x200B;**[!UICONTROL 名稱]**&#x200B;的自訂欄位名稱。 例如：`Sum of Purchases`。
      1. 選取&#x200B;**[!UICONTROL 欄位詳細資料]**&#x200B;標籤。
      1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式選單中選取&#x200B;**[!UICONTROL 小數]**，並確定`0`是以&#x200B;**[!UICONTROL 小數]**&#x200B;輸入。
      1. 選取「**[!UICONTROL 儲存]**」。
   1. 這兩個欄位都會自動新增至資料檢視。
1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;區段中，選取&#x200B;**[!UICONTROL +篩選器]**。 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中。 選取‣**[!UICONTROL 自訂欄位]**，然後選取&#x200B;**[!UICONTROL 購買收入]**。
1. 選取&#x200B;**[!UICONTROL 是>]**&#x200B;並輸入`800000`以限制結果。
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;以顯示線條視覺效果。
1. 選取&#x200B;**[!UICONTROL 視覺效果]**&#x200B;中的&#x200B;**[!UICONTROL 編輯]**&#x200B;以更新視覺效果。 在快顯對話框中：
   1. 選取&#x200B;**[!UICONTROL 繪圖]**&#x200B;標籤。
   1. 向下捲動並選取&#x200B;**[!UICONTROL 編輯圖表設定]**。
   1. 修改&#x200B;**[!UICONTROL 圖表設定（覆寫）]**&#x200B;中的JSON （如下方熒幕擷圖所示），然後選取&#x200B;**[!UICONTROL 預覽]**。

      ![Looker視覺化設定](assets/uc6-looker-visualization.png)

   1. 選取&#x200B;**[!UICONTROL 「套用」]**。
   1. 選取![編輯](/help/assets/icons/CrossSize75.svg)旁的&#x200B;**[!UICONTROL CrossSize75]**&#x200B;以隱藏快顯對話方塊

您應該會看到視覺效果和類似下列的表格。

![Looker結果每日趨勢](assets/uc6-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
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

   ![Jupyter Notebook結果](assets/uc6-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

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

   ![RStudio結果](assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++


## 計算不同的維度值

在此使用案例中，您想取得2023年1月期間回報的獨特產品名稱數量。

+++ Customer Journey Analytics

若要報告產品名稱的相異計數，請在Customer Journey Analytics中設定計算量度，其名稱為&#x200B;**[!UICONTROL Title]** `Product Name (Count Distinct)`和&#x200B;**[!UICONTROL 外部ID]** `product_name_count_distinct`。

![Customer Journey Analytics產品名稱（Distincr計數）計算量度](assets/cja-calc-metric-distinct-count-product-names.png)

然後您可以在使用案例的範例&#x200B;**[!UICONTROL 計算不同Dimension值]**&#x200B;面板中使用該量度：

![Customer Journey Analytics不重複計數值](assets/cja-count-distinct-dimension-values.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 若要確保日期範圍套用至所有視覺效果，請將&#x200B;**[!UICONTROL daterangeday]**&#x200B;從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格拖放至此頁面上的&#x200B;**[!UICONTROL 篩選器]**。
   1. 從此頁面的&#x200B;**[!UICONTROL 篩選器]**&#x200B;中選取&#x200B;**[!UICONTROL daterangeday is (All)]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 在]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 在]** `2/1/2023`之前時顯示專案。
   1. 選取&#x200B;**[!UICONTROL 套用篩選器]**。

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL datarangeday]**。
   1. 選取&#x200B;**[!UICONTROL sum cm_product_name_count_distinct]**，這是Customer Journey Analytics中定義的計算量度。

1. 若要將垂直長條圖修改成表格，請確定您已選取圖表，並從&#x200B;**[!UICONTROL 視覺效果]**&#x200B;窗格中選取&#x200B;**[!UICONTROL 表格]**。

   您的Power BI案頭應該如下所示。

   ![Power BI案頭多重計數相異資料表](assets/uc7-powerbi-table.png)

1. 選取表格視覺效果。 從內容功能表中，選取&#x200B;**[!UICONTROL 複製]** > **[!UICONTROL 複製視覺效果]**。
1. 使用&#x200B;**[!UICONTROL ctrl-v]**&#x200B;貼上視覺效果。 視覺效果的精確副本會與原始副本重疊。 將其移至報告區域的右側。
1. 若要將複製的視覺效果從表格修改為卡片，請從&#x200B;**[!UICONTROL 視覺效果]**&#x200B;中選取&#x200B;**[!UICONTROL 卡片]**。

   您的Power BI案頭應該如下所示。

   ![Power BI案頭多重計數相異資料表](assets/uc7-powerbi-final.png)

或者，您也可以使用Power BI的相異計數功能。

1. 選取&#x200B;**[!UICONTROL product_name]**&#x200B;維度。
1. 在&#x200B;**[!UICONTROL 欄]**&#x200B;中的&#x200B;**[!UICONTROL product_name]**&#x200B;維度上套用&#x200B;**[!UICONTROL 計數（相異）]**&#x200B;函式。

   ![Power BI計數相異](assets/uc7-powerbi-alternative.png)



>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 資料]**&#x200B;窗格的&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架。
   1. 在&#x200B;**[!UICONTROL 篩選欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**，然後選取`01/01/2023` - `31/1/2023`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 將&#x200B;**[!UICONTROL Cm產品名稱計數Distinct]**&#x200B;拖曳至&#x200B;**[!UICONTROL 列]**。 值變更為&#x200B;**[!UICONTROL SUM(Cm Product Name Count Distinct)]**。 此欄位是您在Customer Journey Analytics中定義的計算量度。
   1. 拖曳&#x200B;**[!UICONTROL Daterangeday]**&#x200B;並放置在&#x200B;**[!UICONTROL 欄]**&#x200B;旁。 選取&#x200B;**[!UICONTROL Daterangeday]**，然後從下拉式功能表中選取&#x200B;**[!UICONTROL Day]**。
   1. 若要將線條視覺效果修改為表格，請從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表格]**。
   1. 從工具列選取&#x200B;**[!UICONTROL 交換列與欄]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭多個Dimension排名篩選器](assets/uc7-tableau-data.png)

1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 複製]**&#x200B;以建立第二個工作表。
1. 從&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Data`。
1. 從&#x200B;**[!UICONTROL 工作表1 (2)]**&#x200B;索引標籤內容功能表中選取&#x200B;**[!UICONTROL 重新命名]**，以將工作表重新命名為`Card`。

1. 確定您已選取&#x200B;**[!UICONTROL 卡片]**&#x200B;檢視。
1. 選取&#x200B;**[!UICONTROL 天(Daterangeday)]**，然後從下拉式功能表中選取&#x200B;**[!UICONTROL 月]**。 值變更為&#x200B;**[!UICONTROL MONTH(Daterangeday)]**。
1. 在&#x200B;**[!UICONTROL 標籤]**&#x200B;中選取&#x200B;**[!UICONTROL SUM（Cm產品名稱計數相異）]**，並從下拉式選單中選取&#x200B;**[!UICONTROL 格式]**。
1. 若要變更字型大小，請在&#x200B;**[!UICONTROL Format SUM(CM Product Name Count Distinct)]**&#x200B;窗格中，選取&#x200B;**[!UICONTROL 預設]**&#x200B;內的&#x200B;**[!UICONTROL 字型]**，並選取&#x200B;**[!UICONTROL 72]**&#x200B;作為字型大小。
1. 若要對齊數字，請選取&#x200B;**[!UICONTROL 對齊]**&#x200B;旁的&#x200B;**[!UICONTROL 自動]**，並將&#x200B;**[!UICONTROL 水準]**&#x200B;設定為置中。
1. 若要使用整數，請選取&#x200B;**[!UICONTROL 數字]**&#x200B;旁的&#x200B;**[!UICONTROL 123.456]**，並選取&#x200B;**[!UICONTROL 數字（自訂）]**。 將&#x200B;**[!UICONTROL 小數位數]**&#x200B;設為`0`。

   您的Tableau桌上型電腦應如下所示。

   ![Tableau案頭多個Dimension排名篩選器](assets/uc7-tableau-card.png)

1. 選取「**[!UICONTROL 新儀表板]**」索引標籤按鈕（在底部）以建立新的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。 在&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視中：
   1. 將&#x200B;**[!UICONTROL 卡片]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;擱板拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視，顯示&#x200B;*將工作表拖放到這裡*。
   1. 將&#x200B;**[!UICONTROL 資料]**&#x200B;工作表從&#x200B;**[!UICONTROL 工作表]**&#x200B;托架拖放到&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視的&#x200B;**[!UICONTROL 卡片]**&#x200B;工作表下。

   您的&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視應如下所示。

   ![Tableau案頭儀表板1](assets/uc7-tableau-final.png)


或者，您也可以使用Tableau Desktop的相異計數功能。

1. 使用&#x200B;**[!UICONTROL 產品名稱]**，而非&#x200B;**[!UICONTROL Cm產品名稱計數相異]**。
1. 在&#x200B;**[!UICONTROL 標籤]**&#x200B;中的&#x200B;**[!UICONTROL 產品名稱]**&#x200B;套用&#x200B;**[!UICONTROL 量值]** > **[!UICONTROL 計數（相異）]**。

   ![Tableau計數相異](assets/uc7-tableau-alternative.png)


>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍日期]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/02/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL 日期範圍日期]**，然後選取&#x200B;**[!UICONTROL 日期]**。
   1. 從&#x200B;**[!UICONTROL 產品名稱]**&#x200B;上的&#x200B;**⋮更多**&#x200B;內容功能表中選取&#x200B;**[!UICONTROL 彙總相異‣計數]**。

      ![Looker產品名稱內容功能表](assets/uc7-looker-count-distinct.png)
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**&#x200B;並從工具列選取6︎⃣以顯示單值視覺效果。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](assets/uc7-looker-result.png)


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT COUNT(DISTINCT(product_name)) AS `Product Name` \
      FROM cc_data_view \
      WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01';
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](assets/uc7-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

   ```R
   ## Count Distinct
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      summarise(product_name_count_distinct = n_distinct(product_name))
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](assets/uc7-rstudio-results.png)


>[!ENDTABS]

+++


## 使用日期範圍名稱進行篩選

在此使用案例中，您想使用已在Customer Journey Analytics中定義的日期範圍來篩選及報告去年的發生次數（事件）。

+++ Customer Journey Analytics

若要使用日期範圍製作報表，請在Customer Journey Analytics中設定日期範圍，並選取&#x200B;**[!UICONTROL 標題]** `Last Year 2023`。

![Customer Journey Analytics使用日期範圍名稱來篩選](assets/cja-daterange.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用日期範圍名稱以篩選使用案例的]**&#x200B;面板中使用該日期範圍：

![Customer Journey Analytics不重複計數值](assets/cja-using-date-range-filter-names-to-filter.png)

請注意，在自由表格視覺效果中定義的日期範圍會如何覆寫套用至面板的日期範圍。

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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

   ![使用日期範圍名稱篩選的Power BI案頭](assets/uc8-powerbi-final.png)

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

      ![Tableau案頭多個Dimension排名篩選器](assets/uc8-tableau-final.png)

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

![觀察者計數相異](assets/uc8-looker-result.png)


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

   ![Jupyter Notebook結果](assets/uc8-jupyter-input.png)

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

   ![Jupyter Notebook結果](assets/uc8-jupyter-results.png)


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

   ![RStudio結果](assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++



## 使用區段名稱來分段

在此使用案例中，您要將現有的區段用於「釣魚」產品類別，即您在Customer Journey Analytics中定義的類別。 對2023年1月期間的產品名稱和發生次數（事件）進行細分和報告。

+++ Customer Journey Analytics

檢查您要在Customer Journey Analytics中使用的區段。

![Customer Journey Analytics使用篩選器名稱來篩選](assets/cja-fishing-products.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用區段名稱將區段]**&#x200B;面板中針對使用案例使用該區段：

![Customer Journey Analytics不重複計數值](assets/cja-using-filter-names-to-filter.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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

   ![使用日期範圍名稱篩選的Power BI案頭](assets/uc9-powerbi-final.png)


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

      ![Tableau案頭多個Dimension排名篩選器](assets/uc9-tableau-final.png)

>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
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

![觀察者計數相異](assets/uc9-looker-result.png)



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

   ![Jupyter Notebook結果](assets/uc9-jupyter-input.png)

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

   ![Jupyter Notebook結果](assets/uc9-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。 請確定您使用適當的篩選器名稱。 例如，`Fishing Products`。

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

   ![RStudio結果](assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++


## 使用維度值劃分割槽段

您使用&#x200B;**[!UICONTROL 產品類別]**&#x200B;的動態&#x200B;**[!UICONTROL 狩獵]**&#x200B;值，從狩獵類別中劃分產品。 或者，對於不支援動態擷取產品類別值的BI工具，您可以在Customer Journey Analytics中建立新的區段，對搜尋產品類別中的產品進行區段。
然後，您想要使用新區段，報告2023年1月期間，搜尋類別中產品的產品名稱和發生次數（事件）。

+++ Customer Journey Analytics

在Customer Journey Analytics中建立具有&#x200B;**[!UICONTROL 標題]** `Hunting Products`的新區段。

![Customer Journey Analytics使用Dimension值來區段](assets/cja-hunting-products.png)

然後您可以在範例&#x200B;**[!UICONTROL 使用Dimension值來篩選使用案例的]**&#x200B;面板中使用該區段：

![Customer Journey Analytics不重複計數值](assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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

   ![使用日期範圍名稱篩選的Power BI案頭](assets/uc10-powerbi-final.png)



>[!TAB Tableau案頭]

![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop不支援從Customer Journey Analytics擷取產品類別的動態清單。 此使用案例會改用新建立的&#x200B;**[!UICONTROL 狩獵產品]**&#x200B;篩選器，並使用篩選器名稱critia。

1. 在&#x200B;**[!UICONTROL 資料Source]**&#x200B;檢視的&#x200B;**[!UICONTROL 資料]**&#x200B;下，從&#x200B;**[!UICONTROL cc_data_view(prod：cja%3FFLATTEN)]**&#x200B;上的內容功能表選取&#x200B;**[!UICONTROL 重新整理]**。 您必須重新整理連線，才能擷取您剛才在Customer Journey Analytics中定義的新篩選器。
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

      ![Tableau案頭多個Dimension排名篩選器](assets/uc10-tableau-final.png)

>[!TAB 觀察者]

1. 在1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，重新整理您的連線。 選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 清除快取並重新整理]**。
1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍日期]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/02/01]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**&#x200B;以新增另一個篩選器。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 產‣品類別]**。
1. 確定&#x200B;**[!UICONTROL 是]**&#x200B;作為篩選的選取專案。

![AlertRed](/help/assets/icons/AlertRed.svg)查閱未顯示&#x200B;**[!UICONTROL 產品類別]**&#x200B;的可能值清單。

![觀察者計數相異](assets/uc10-looker-result.png)


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

   ![Jupyter Notebook結果](assets/uc10-jupyter-input.png)

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

   ![Jupyter Notebook結果](assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。 確定您使用適當的類別。 例如，`Hunting`。

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

   ![RStudio結果](assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++



## 排序

在此使用案例中，您想要報告2023年1月期間產品名稱的購買收入和購買（以降序購買收入順序排序）。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 排序]**&#x200B;面板：

![Customer Journey Analytics排序面板](assets/cja-sort.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

1. 在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中：
   1. 選取&#x200B;**[!UICONTROL 日期範圍]**。
   1. 選取&#x200B;**[!UICONTROL product_namr]**。
   1. 選取&#x200B;**[!UICONTROL sum purchase_revenue]**。
   1. 選取&#x200B;**[!UICONTROL 總購買]**。

1. 在&#x200B;**[!UICONTROL 篩選器]**&#x200B;窗格中：
   1. 在此視覺效果&#x200B;**[!UICONTROL 上選取]**&#x200B;篩選器中的&#x200B;**[!UICONTROL 日期範圍是（全部）]**。
   1. 選取&#x200B;**[!UICONTROL 進階篩選]**&#x200B;作為&#x200B;**[!UICONTROL 篩選型別]**。
   1. 定義篩選器以&#x200B;**[!UICONTROL 當值]** **[!UICONTROL 在]** `1/1/2023` **[!UICONTROL 且]** **[!UICONTROL 在]** `2/1/2023`之前時顯示專案。

1. 在「視覺效果」窗格中：
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從資料行移除日期範圍。
   1. 將&#x200B;**[!UICONTROL Purchase_revenue]**&#x200B;的總和拖曳至&#x200B;**[!UICONTROL 欄]**&#x200B;專案的底部。

1. 在報表中，選取&#x200B;**[!UICONTROL purchase_revenue總和]**&#x200B;以購買收入遞減順序排序表格。

   您的Power BI案頭應該如下所示。

   ![使用日期範圍名稱篩選的Power BI案頭](assets/uc11-powerbi-final.png)

Power BI Desktop使用BI副檔名執行的查詢不包含`sort`陳述式。 缺少`sort`陳述式表示排序是在使用者端執行。

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
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
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Tableau案頭]

1. 選取底部的&#x200B;**[!UICONTROL 工作表1]**&#x200B;索引標籤，以從&#x200B;**[!UICONTROL 資料來源]**&#x200B;切換。 在&#x200B;**[!UICONTROL 工作表1]**&#x200B;檢視中：
   1. 從&#x200B;**[!UICONTROL 篩選器]**&#x200B;托架中的&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 日期範圍]**&#x200B;專案。
   1. 在&#x200B;**[!UICONTROL 篩選欄位\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;並選取&#x200B;**[!UICONTROL 下一步>]**。
   1. 在&#x200B;**[!UICONTROL 篩選器\[日期範圍\]]**&#x200B;對話方塊中，選取&#x200B;**[!UICONTROL 日期範圍]**，然後選取`01/01/2023` - `1/2/2023`。 選取&#x200B;**[!UICONTROL 套用]**&#x200B;及&#x200B;**[!UICONTROL 確定]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL 產品名稱]**，並將專案拖放至&#x200B;**[!UICONTROL 列]**&#x200B;旁的欄位中。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單拖曳&#x200B;**[!UICONTROL 購買]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**&#x200B;旁的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（購買）]**。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;清單中拖曳&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;專案，並將該專案拖放至&#x200B;**[!UICONTROL 欄]**、**[!UICONTROL SUM(Purchases)]**&#x200B;旁邊的欄位中。 值變更為&#x200B;**[!UICONTROL SUM（購買收入）]**。
   1. 從&#x200B;**[!UICONTROL 顯示我]**&#x200B;中選取&#x200B;**[!UICONTROL 文字表]**。
   1. 從&#x200B;**[!UICONTROL 符合]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 符合寬度]**。
   1. 選取&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;欄標題，並依遞減順序排序此欄上的表格。

      您的Tableau桌上型電腦應如下所示。

      ![Tableau案頭排序](assets/uc11-tableau-final.png)

Tableau Desktop使用BI副檔名執行的查詢不包含`sort`陳述式。 缺少此`sort`陳述式表示排序是在使用者端執行。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB 觀察者]

1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，重新整理您的連線。 選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 清除快取並重新整理]**。
1. 在Looker的&#x200B;**[!UICONTROL 瀏覽]**&#x200B;介面中，確定您已進行乾淨的設定。 如果沒有，請選取![設定](/help/assets/icons/Setting.svg) **[!UICONTROL 移除欄位和篩選器]**。
1. 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;底下的&#x200B;**[!UICONTROL +篩選器]**。
1. 在&#x200B;**[!UICONTROL 新增篩選器]**&#x200B;對話方塊中：
   1. 選取&#x200B;**[!UICONTROL ‣ Cc資料檢視]**
   1. 從欄位清單中，選取&#x200B;**[!UICONTROL 日‣期範圍日期]**&#x200B;然後&#x200B;**[!UICONTROL 日期範圍日期]**。

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍日期]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2023/02/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 產品名稱]**。
1. 從左側邊欄中的&#x200B;**[!UICONTROL ‣自訂欄位]**&#x200B;區段：
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 自訂量值]**。
   1. 在&#x200B;**[!UICONTROL 建立自訂量值]**&#x200B;對話方塊中：
      1. 從&#x200B;**[!UICONTROL 要量值]**&#x200B;的欄位下拉式功能表中選取&#x200B;**[!UICONTROL 購買收入]**。
      1. 從&#x200B;**[!UICONTROL 量值型別]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 總和]**。
      1. 輸入&#x200B;**[!UICONTROL 名稱]**&#x200B;的自訂欄位名稱。 例如：`Sum of Purchase Revenue`。
      1. 選取&#x200B;**[!UICONTROL 欄位詳細資料]**&#x200B;標籤。
      1. 從&#x200B;**[!UICONTROL 格式]**&#x200B;下拉式選單中選取&#x200B;**[!UICONTROL 小數]**，並確定`0`是以&#x200B;**[!UICONTROL 小數]**&#x200B;輸入。

         ![Looker自訂量度欄位](assets/uc5-looker-customfield.png)
      1. 選取「**[!UICONTROL 儲存]**」。
1. 請確定您在&#x200B;**[!UICONTROL Purchase Revenue↓5&rbrace;欄上選取]** 1&rbrace; （**[!UICONTROL 遞減，排序順序： 1]**）。**&#x200B;**
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](assets/uc11-looker-result.png)


Looker使用BI副檔名產生的查詢包含`ORDER BY`，這表示排序是透過Looker和BI副檔名執行。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. 在新儲存格中輸入下列陳述式。

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. 執行儲存格。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![Jupyter Notebook結果](assets/uc11-jupyter-results.png)

如Jupyter Notebook中所定義，查詢由BI擴充功能執行。


>[!TAB RStudio]

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. 執行區塊。 您應該會看到與下方熒幕擷圖類似的輸出。

   ![RStudio結果](assets/uc11-rstudio-results.png)

RStudio使用BI副檔名產生的查詢包含`ORDER BY`，這表示會透過RStudio和BI副檔名套用順序。

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++

## 限制

在此使用案例中，您想要報告2023年期間前5次出現產品名稱。

+++ Customer Journey Analytics

使用案例的範例&#x200B;**[!UICONTROL 限制]**&#x200B;面板：

![Customer Journey Analytics限制面板](assets/cja-limit.png)

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
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

   ![使用日期範圍名稱篩選的Power BI案頭](assets/uc12-powerbi-final.png)

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

         ![Tableau案頭限制](assets/uc12-tableau-final.png)

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

      ![Looker篩選器](assets/uc2-looker-filter.png)
1. 指定&#x200B;**[!UICONTROL Cc資料檢視日期範圍]**&#x200B;篩選器，因為&#x200B;**[!UICONTROL 在範圍]** **[!UICONTROL 2023/01/01]** **[!UICONTROL 到（之前）]** **[!UICONTROL 2024/01/01]**。
1. 從左側邊欄的&#x200B;**[!UICONTROL ‣ Cc資料檢視]**&#x200B;區段：
   1. 選取&#x200B;**[!UICONTROL 產品名稱]**。
   1. 在左側邊欄（底部）中選取&#x200B;**[!UICONTROL MEASURES]**&#x200B;底下的&#x200B;**[!UICONTROL 計數]**。
1. 請確定您在&#x200B;**[!UICONTROL Purchase Revenue↓5&rbrace;欄上選取]** 1&rbrace; （**[!UICONTROL 遞減，排序順序： 1]**）。**&#x200B;**
1. 請確定您在&#x200B;**[!UICONTROL Purchase Revenue↓5&rbrace;欄上選取]** 1&rbrace; （**[!UICONTROL 遞減，排序順序： 1]**）。**&#x200B;**
1. 選取&#x200B;**[!UICONTROL 執行]**。
1. 選取‣**[!UICONTROL 視覺效果]**。

您應該會看到視覺效果和類似下列的表格。

![觀察者計數相異](assets/uc12-looker-result.png)

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

   ![Jupyter Notebook結果](assets/uc12-jupyter-results.png)

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

   ![RStudio結果](assets/uc12-rstudio-results.png)

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

## 轉換

您想要瞭解各種BI工具對Customer Journey Analytics物件（例如維度、量度、篩選器、計算量度和日期範圍）的轉換。

+++ Customer Journey Analytics

在Customer Journey Analytics中，您在[資料檢視](/help/data-views/data-views.md)中定義資料集的哪些元件及如何公開為[維度](/help/components/dimensions/overview.md)和[量度](/help/components/apply-create-metrics.md)。 該維度和量度的定義會使用BI擴充功能向BI工具公開。
您將[篩選器](/help/components/segments/seg-overview.md)、[計算量度](/help/components/calc-metrics/calc-metr-overview.md)和[日期範圍](/help/components/date-ranges/overview.md)等元件用作Workspace專案的一部分。 這些元件也會透過BI擴充功能向BI工具公開。

+++

+++ BI 工具

>[!PREREQUISITES]
>
>確定您已驗證[連線成功，可以列出資料檢視，並針對您想要嘗試此使用案例的BI工具使用資料檢視](#connect-and-validate)。
>

>[!BEGINTABS]

>[!TAB Power BI案頭版]

Customer Journey Analytics物件可在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中使用，並可從您在Power BI Desktop中選取的表格擷取。 例如，**[!UICONTROL public.cc_data_view]**。 表格的名稱與您在Customer Journey Analytics中為資料檢視定義的外部ID相同。 例如，具有&#x200B;**[!UICONTROL 標題]** `C&C - Data View`和&#x200B;**[!UICONTROL 外部識別碼]** `cc_data_view`的資料檢視。

**維度**
來自Customer Journey Analytics的維度以[!UICONTROL 元件ID]識別。 [!UICONTROL 元件ID]已在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;具有[!UICONTROL 元件識別碼] **[!UICONTROL product_name]**，這是Power BI Desktop中維度的名稱。
來自Customer Journey Analytics的日期範圍維度（例如&#x200B;**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可用作&#x200B;**[!UICONTROL daterangeday]**、**[!UICONTROL daterangeweek]**、**[!UICONTROL daterangemonth]**&#x200B;等。

**個量度**
來自Customer Journey Analytics的量度以[!UICONTROL 元件ID]識別。 [!UICONTROL 元件ID]已在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有[!UICONTROL 元件識別碼] **[!UICONTROL purchase_revenue]**，這是Power BI Desktop中量度的名稱。 **[!UICONTROL ∑]**&#x200B;表示量度。 當您在任何視覺效果中使用量度時，量度會重新命名為&#x200B;**[!UICONTROL *量度的總和&#x200B;*]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為&#x200B;**[!UICONTROL filterName]**&#x200B;欄位的一部分使用。 當您在Power BI Desktop中使用&#x200B;**[!UICONTROL filterName]**&#x200B;欄位時，可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 外部ID]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;具有[!UICONTROL 外部識別碼] **[!UICONTROL product_name_count_distinct]**，並在Power BI Desktop中顯示為&#x200B;**[!UICONTROL cm_product_name_count_distinc]**&#x200B;t。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為&#x200B;**[!UICONTROL daterangeName]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL daterangeName]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Power BI Desktop提供使用[資料分析運算式(DAX)](https://learn.microsoft.com/en-us/dax/dax-overview)的自訂轉換功能。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 在報表檢視中，選取長條圖視覺效果。
1. 在[資料]窗格中選取&#x200B;**[!UICONTROL product_name]**。
1. 在工具列中選取&#x200B;**[!UICONTROL 新資料行]**。
1. 在公式編輯器中，定義名稱為`product_name_lower`的新欄，如`product_name_lower = LOWER('public.cc_data_view[product_name])`。
   ![Power BI案頭轉換至Lower](assets/uc14-powerbi-transformation.png)
1. 請確定您在&#x200B;**[!UICONTROL 資料]**&#x200B;窗格中選取新的&#x200B;**[!UICONTROL product_name_lower]**&#x200B;欄，而非&#x200B;**[!UICONTROL product_name]**&#x200B;欄。
1. 在表格視覺效果中選取&#x200B;**[!UICONTROL 更多]**&#x200B;中的![以表格](/help/assets/icons/More.svg)報告。

   您的Power BI案頭應該如下所示。
   ![Power BI案頭轉換最終版](assets/uc14-powerbi-final.png)

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
來自Customer Journey Analytics的維度以[!UICONTROL 元件名稱]識別。 已在您的Customer Journey Analytics資料檢視中定義[!UICONTROL 元件名稱]。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;有[!UICONTROL 元件名稱] **[!UICONTROL 產品名稱]**，這是Tableau中維度的名稱。 所有維度皆由&#x200B;**[!UICONTROL Abc]**&#x200B;識別。
來自Customer Journey Analytics的日期範圍維度（例如&#x200B;**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可用作&#x200B;**[!UICONTROL Daterangeday]**、**[!UICONTROL Daterangeweek]**、**[!UICONTROL Daterangemonth]**&#x200B;等。 使用日期範圍維度時，您必須從下拉式選單中選取適當的日期或時間定義，以套用至該日期範圍維度。 例如，**[!UICONTROL 年]**，**[!UICONTROL 季]**，**[!UICONTROL 月]**，**[!UICONTROL 日]**。

**個量度**
來自Customer Journey Analytics的量度由[!UICONTROL 元件名稱]識別。 已在您的Customer Journey Analytics資料檢視中定義[!UICONTROL 元件名稱]。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有[!UICONTROL 元件名稱] **[!UICONTROL Purchase Revenue]**，這是Tableau中量度的名稱。 所有量度都由&#x200B;**[!UICONTROL #]**&#x200B;識別。 當您在任何視覺效果中使用量度時，量度會重新命名為&#x200B;**[!UICONTROL Sum（*量度*）]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位的一部分使用。 當您在Tableau中使用&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位時，可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 標題]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;有[!UICONTROL 標題] **[!UICONTROL 產品名稱（相異計數）]**，並在Tableau中顯示為&#x200B;**[!UICONTROL Cm產品名稱相異計數]**。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Tableau Desktop提供使用[計算欄位](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_create.htm)的自訂轉換功能。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 從主功能表選取&#x200B;**[!UICONTROL 分析]** > **[!UICONTROL 建立計算欄位]**。
   1. 使用函式&#x200B;**[!UICONTROL 定義]**&#x200B;小寫的產品名稱`LOWER([Product Name])`。

      ![Tableau計算欄位](assets/uc14-tableau-calculated-field.png)
   1. 選取&#x200B;**[!UICONTROL 確定]**。
1. 選取&#x200B;**[!UICONTROL 資料]**&#x200B;工作表。
   1. 從&#x200B;**[!UICONTROL 表格]**&#x200B;拖曳&#x200B;**[!UICONTROL 小寫產品名稱]**，並將專案拖放至&#x200B;**[!UICONTROL 列]**&#x200B;旁的欄位中。
   1. 從&#x200B;**[!UICONTROL 列]**&#x200B;移除&#x200B;**[!UICONTROL 產品名稱]**。
1. 選取&#x200B;**[!UICONTROL 儀表板1]**&#x200B;檢視。

您的Tableau桌上型電腦應如下所示。

轉換後的![Tableau案頭](assets/uc14-tableau-final.png)

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
Customer Journey Analytics的維度會在&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;左側邊欄中列為&#x200B;**[!UICONTROL DIMENSION]**。 維度是在您的Customer Journey Analytics資料檢視中定義。 例如，Customer Journey Analytics中的維度&#x200B;**[!UICONTROL 產品名稱]**&#x200B;具有&#x200B;**[!UICONTROL DIMENSION]** **[!UICONTROL 產品名稱]**，這是Looker中維度的名稱。
來自Customer Journey Analytics的日期範圍維度（如&#x200B;**[!UICONTROL Day]**、**[!UICONTROL Week]**、**[!UICONTROL Month]**&#x200B;等）可做為&#x200B;**[!UICONTROL Daterangeday Date]**、**[!UICONTROL Daterangeweek Date]**、**[!UICONTROL Daterangemonth Date]**&#x200B;等。  使用日期範圍維度時，您必須選取適當的日期或時間定義。 例如，**[!UICONTROL 年]**，**[!UICONTROL 季]**，**[!UICONTROL 月]**，**[!UICONTROL 日期]**。

**個量度**
Customer Journey Analytics的量度在&#x200B;**[!UICONTROL Cc資料檢視]**&#x200B;左側邊欄中列為&#x200B;**[!UICONTROL DIMENSION]**。 例如，Customer Journey Analytics中的量度&#x200B;**[!UICONTROL Purchase Revenue]**&#x200B;有&#x200B;**[!UICONTROL DIMENSION]** **[!UICONTROL Purchase Revenue]**。 若要實際做為量度使用，請建立如上例所示的自訂量值欄位，或使用維度的捷徑。 例如，**[!UICONTROL ⋮]**，選取&#x200B;**[!UICONTROL 彙總]**，然後選取&#x200B;**[!UICONTROL 總計]**。

**篩選器**
您在Customer Journey Analytics中定義的篩選器可作為&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位的一部分使用。 當您在Looker中使用&#x200B;**[!UICONTROL 篩選器名稱]**&#x200B;欄位時，您可以指定要使用的篩選器。

**計算量度**
您在Customer Journey Analytics中定義的計算量度，會由您為計算量度定義的[!UICONTROL 標題]識別。 例如，計算量度&#x200B;**[!UICONTROL 產品名稱（相異計數）]**&#x200B;有[!UICONTROL 標題] **[!UICONTROL 產品名稱（相異計數）]**，並在回顧中顯示為&#x200B;**[!UICONTROL 公分產品名稱相異計數]**。

**日期範圍**
您在Customer Journey Analytics中定義的日期範圍可做為&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位的一部分。 當您使用&#x200B;**[!UICONTROL 日期範圍名稱]**&#x200B;欄位時，您可以指定要使用的日期範圍。

**自訂轉換**
Looker使用自訂欄位建置器提供自訂轉換功能，如上所示。 例如，您想要以小寫執行產品名稱排名為[的](#single-dimension-ranked)單一維度使用案例。

1. 從左側邊欄中的&#x200B;**[!UICONTROL ‣自訂欄位]**&#x200B;區段：
   1. 從&#x200B;**[!UICONTROL +新增]**&#x200B;下拉式功能表中選取&#x200B;**[!UICONTROL 自訂Dimension]**。
   1. 在`lower(${cc_data_view.product_name})`運算式&#x200B;**[!UICONTROL 文字區域中輸入]**。 當您開始輸入`Product Name`時，會以正確的語法協助您。

      ![Looker轉換範例](assets/uc14-looker-transformation.png)
   1. 輸入`product name`作為&#x200B;**[!UICONTROL 名稱]**。
   1. 選取「**[!UICONTROL 儲存]**」。

您應該會看到類似表格，如下所示。

![Looker轉換結果](assets/uc14-looker-result.png)


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

   ![Jupyter Notebook結果](assets/uc13-jupyter-results.png)

如Jupyter Notebook中所定義，查詢由BI擴充功能執行。

>[!TAB RStudio]

Customer Journey Analytics元件（維度、量度、篩選器、計算量度和日期範圍）在R語言中類似命名物件提供。 請參閱使用元件的元件。請參閱之前的範例。

**自訂轉換**

1. 在新區塊中輸入` ` ``{r} `到` `` ` `之間的下列陳述式。

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

   ![RStudio結果](assets/uc13-rstudio-results.png)

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



## 視覺效果

您想瞭解如何在Customer Journey Analytics中使用類似的方式，使用BI工具中的可用視覺效果來建立視覺效果。

+++ Customer Journey Analytics

Customer Journey Analytics有許多視覺效果。 請參閱[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)，以取得所有可能視覺效果的簡介和概觀。

+++

+++ BI 工具

>[!BEGINTABS]

>[!TAB Power BI案頭版]

### 比較

針對大多數Customer Journey Analytics視覺效果，Power BI Desktop提供同等體驗。 請參閱下表。

| 圖示 | Customer Journey Analytics視覺效果 | Power BI案頭視覺效果 |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [區域](/help/analysis-workspace/visualizations/area.md) | [區域圖、棧疊區域圖和100%區域圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#area-charts-basic-layered-and-stacked) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [條狀圖](/help/analysis-workspace/visualizations/bar.md) | [叢集柱狀圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [堆疊長條圖](/help/analysis-workspace/visualizations/bar.md) | [棧疊直條圖和100%棧疊直條圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [項目符號](/help/analysis-workspace/visualizations/bullet-graph.md) |  |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![組合](/help/assets/icons/ComboChart.svg) | [組合](/help/analysis-workspace/visualizations/combo-charts.md) | [折線圖和棧疊直條圖，以及折線圖和叢集直條圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#combo-charts) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [環形圖](/help/analysis-workspace/visualizations/donut.md) | [環形圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#doughnut-charts) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [漏斗](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#funnel-charts)。 |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [流量](/help/analysis-workspace/visualizations/c-flow/flow.md) | 分解樹？ |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [資料表](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#tables)和[矩陣](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#matrix) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [直方圖](/help/analysis-workspace/visualizations/histogram.md) |  |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [叢集長條圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [堆疊橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [棧疊長條圖和100%棧疊長條圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#bar-and-column-charts) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | [分解樹狀結構](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#decomposition-tree) |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [關鍵量度摘要](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![趨勢圖](/help/assets/icons/GraphTrend.svg) | [折線圖](/help/analysis-workspace/visualizations/line.md) | [折線圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#line-charts) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散佈圖](/help/analysis-workspace/visualizations/scatterplot.md) | [散佈圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#scatter) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [區段標題](/help/analysis-workspace/visualizations/section-header.md) | [文字方塊](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md) | [卡片](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![123](/help/assets/icons/123.svg)</p> | [摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md) | [卡片](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#cards) |
| ![Text](/help/assets/icons/Text.svg) | [文字](/help/analysis-workspace/visualizations/text.md) | [文字方塊](https://learn.microsoft.com/en-us/power-bi/paginated-reports/report-design/textbox/add-move-or-delete-a-text-box-report-builder-and-service) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [樹狀圖](/help/analysis-workspace/visualizations/treemap.md)<p> | [樹狀圖](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-types-for-reports-and-q-and-a#treemaps) |
| ![Type](/help/assets/icons/TwoDots.svg) | [文氏圖表](/help/analysis-workspace/visualizations/venn.md) | |


### 深入研究

Power BI支援[鑽研模式](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill)，以深入探索特定視覺效果的詳細資料。 在以下範例中，您會分析產品類別的購買收入。 從代表產品類別之條的內容功能表中，您可以選取&#x200B;**[!UICONTROL 向下切入]**。

![Power BI深入研究](assets/uc15-powerbi-drilldown.png)

向下展開會更新所選產品類別中產品購買收入的視覺效果。

![Power BI向上鑽研](assets/uc15-powerbi-drillup.png)

向下鑽研會在下列使用`WHERE`子句的SQL查詢中產生：

```sql
select "_"."product_category" as "c25",
    "_"."product_name" as "c26",
    "_"."a0" as "a0"
from 
(
    select "_"."product_category",
        "_"."product_name",
        "_"."a0"
    from 
    (
        select "_"."product_category",
            "_"."product_name",
            "_"."a0"
        from 
        (
            select "rows"."product_category" as "product_category",
                "rows"."product_name" as "product_name",
                sum("rows"."purchase_revenue") as "a0"
            from 
            (
                select "_"."product_category",
                    "_"."product_name",
                    "_"."purchase_revenue"
                from "public"."cc_data_view" "_"
                where ("_"."daterange" >= date '2023-01-01' and "_"."product_category" = 'Fishing') and "_"."daterange" < date '2024-01-01'
            ) "rows"
            group by "product_category",
                "product_name"
        ) "_"
        where not "_"."a0" is null
    ) "_"
) "_"
order by "_"."product_category",
        "_"."product_name"
limit 1001
```

>[!TAB Tableau案頭]

### 比較

針對大多數Customer Journey Analytics視覺效果，Tableau Desktop提供同等體驗。 請參閱下表。

| 圖示 | Customer Journey Analytics視覺效果 | Power BI案頭視覺效果 |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [區域](/help/analysis-workspace/visualizations/area.md) | [區域圖](https://help.tableau.com/current/pro/desktop/en-us/qs_area_charts.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [條狀圖](/help/analysis-workspace/visualizations/bar.md) | [長條圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [堆疊長條圖](/help/analysis-workspace/visualizations/bar.md) |  |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [項目符號](/help/analysis-workspace/visualizations/bullet-graph.md) | [項目符號圖表](https://help.tableau.com/current/pro/desktop/en-us/qs_bullet_graphs.htm) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![組合](/help/assets/icons/ComboChart.svg) | [組合](/help/analysis-workspace/visualizations/combo-charts.md) | [組合圖表](https://help.tableau.com/current/pro/desktop/en-us/qs_combo_charts.htm) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [環形圖](/help/analysis-workspace/visualizations/donut.md) | |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [流量](/help/analysis-workspace/visualizations/c-flow/flow.md) |  |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [文字資料表](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_text.htm) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [直方圖](/help/analysis-workspace/visualizations/histogram.md) | [直方圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_histogram.htm) |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [長條圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [堆疊橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [長條圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_bar.htm) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) | |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [關鍵量度摘要](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![趨勢圖](/help/assets/icons/GraphTrend.svg) | [折線圖](/help/analysis-workspace/visualizations/line.md) | [折線圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_line.htm) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散佈圖](/help/analysis-workspace/visualizations/scatterplot.md) | [散佈圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_scatter.htm) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [區段標題](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![123](/help/assets/icons/123.svg)</p> | [摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md) | |
| ![Text](/help/assets/icons/Text.svg) | [文字](/help/analysis-workspace/visualizations/text.md) | |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [樹狀圖](/help/analysis-workspace/visualizations/treemap.md)<p> | [樹狀圖](https://help.tableau.com/current/pro/desktop/en-us/buildexamples_treemap.htm) |
| ![Type](/help/assets/icons/TwoDots.svg) | [文氏圖表](/help/analysis-workspace/visualizations/venn.md) | |


### 深入研究

Tableau支援[鑽研模式](https://learn.microsoft.com/en-us/power-bi/consumer/end-user-drill)到[階層](https://help.tableau.com/current/pro/desktop/en-us/qs_hierarchies.htm)。 在以下範例中，當您在&#x200B;**[!UICONTROL 表格]**&#x200B;中選取&#x200B;**[!UICONTROL 產品名稱]**&#x200B;欄位，並將它拖曳到&#x200B;**[!UICONTROL 產品類別]**&#x200B;上時，就會建立階層。 然後，從代表產品類別之條的內容功能表中，選取&#x200B;**[!UICONTROL +向下鑽研]**。

![Tableau向下鑽研](assets/uc15-tableau-drilldown.png)

向下展開會更新所選產品類別中產品購買收入的視覺效果。

![Tableau向上鑽研](assets/uc15-tableau-drillup.png)

向下鑽研會產生下列使用GROUP BY子句的SQL查詢：

```sql
SELECT CAST("cc_data_view"."product_category" AS TEXT) AS "product_category",
  CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1,
  2
```

查詢&#x200B;**不會**&#x200B;將結果限製為所選的產品類別；只有視覺效果會顯示所選的產品類別。

![Tableau向上鑽研](assets/uc15-tableau-drillup2.png)

或者，您可以建立一個向下鑽研圖示板，其中一個視覺效果是另一個視覺效果中選取的結果。 在下列範例中，**[!UICONTROL 產品類別]**&#x200B;視覺效果已用作更新&#x200B;**[!UICONTROL 產品名稱]**&#x200B;表格的篩選條件。 此視覺效果篩選器僅供使用者端使用，不會產生額外的SQL查詢。

![Tableau視覺效果篩選器](assets/uc15-tableau-visualizationfilter.png)


>[!TAB 觀察者]

### 比較

針對大多數Customer Journey Analytics視覺效果，Looker提供同等體驗。 請參閱下表。

| 圖示 | Customer Journey Analytics視覺效果 | Power BI案頭視覺效果 |
| :---: | --- | ---| 
| ![GraphArea](/help/assets/icons/GraphArea.svg) | [區域](/help/analysis-workspace/visualizations/area.md) | [區域圖](https://cloud.google.com/looker/docs/area-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [條狀圖](/help/analysis-workspace/visualizations/bar.md) | [長條圖](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarVertical](/help/assets/icons/GraphBarVerticalStacked.svg) | [堆疊長條圖](/help/analysis-workspace/visualizations/bar.md) | [長條圖](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBullet](/help/assets/icons/GraphBullet.svg)</p> | [項目符號](/help/analysis-workspace/visualizations/bullet-graph.md) | [項目符號圖表](https://cloud.google.com/looker/docs/bullet-chart) |
| ![TextNumbered](/help/assets/icons/TextNumbered.svg) | [同類群組表格](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) |  |
| ![組合](/help/assets/icons/ComboChart.svg) | [組合](/help/analysis-workspace/visualizations/combo-charts.md) | [自訂視覺效果](https://cloud.google.com/looker/docs/creating-visualizations#customizing_visualizations_with_chart_settings) |
| ![GraphDonut](/help/assets/icons/GraphDonut.svg) | [環形圖](/help/analysis-workspace/visualizations/donut.md) | [環形圖](https://cloud.google.com/looker/docs/donut-multiples-options) |
| ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) | [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) | [漏斗](https://cloud.google.com/looker/docs/funnel-options) |
| ![GraphPathing](/help/assets/icons/GraphPathing.svg) | [流量](/help/analysis-workspace/visualizations/c-flow/flow.md) | [Sankey](https://cloud.google.com/looker/docs/sankey) |
| ![ViewTable](/help/assets/icons/ViewTable.svg)</p> | [自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) | [表格](https://cloud.google.com/looker/docs/table-options) |
| ![GraphHistogram](/help/assets/icons/Histogram.svg) | [直方圖](/help/analysis-workspace/visualizations/histogram.md) | |
| ![GraphBarHorizontal](/help/assets/icons/GraphBarHorizontal.svg) | [橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [長條圖](https://cloud.google.com/looker/docs/bar-options) |
| ![GraphBarHorizontalStacked](/help/assets/icons/GraphBarHorizontalStacked.svg) | [堆疊橫條圖](/help/analysis-workspace/visualizations/horizontal-bar.md) | [長條圖](https://cloud.google.com/looker/docs/bar-options) |
| ![Branch3](/help/assets/icons/Branch3.svg) | [歷程畫布](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) |  |
| ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) | [關鍵量度摘要](/help/analysis-workspace/visualizations/key-metric.md) |  |
| ![趨勢圖](/help/assets/icons/GraphTrend.svg) | [折線圖](/help/analysis-workspace/visualizations/line.md) | [折線圖](https://cloud.google.com/looker/docs/line-options) |
| ![GraphScatter](/help/assets/icons/GraphScatter.svg) | [散佈圖](/help/analysis-workspace/visualizations/scatterplot.md) | [散點圖](https://cloud.google.com/looker/docs/scatter-options) |
| ![PageRule](/help/assets/icons/PageRule.svg) | [區段標題](/help/analysis-workspace/visualizations/section-header.md) |  |
| ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) | [摘要變更](/help/analysis-workspace/visualizations/summary-number-change.md) | [單一值](https://cloud.google.com/looker/docs/single-value-options) |
| ![123](/help/assets/icons/123.svg)</p> | [摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md) | [單一值](https://cloud.google.com/looker/docs/single-value-options) |
| ![Text](/help/assets/icons/Text.svg) | [文字](/help/analysis-workspace/visualizations/text.md) | [單一值](https://cloud.google.com/looker/docs/single-value-options) |
| ![ModernGridView](/help/assets/icons/ModernGridView.svg) | [樹狀圖](/help/analysis-workspace/visualizations/treemap.md) | [樹狀圖](https://cloud.google.com/looker/docs/treemap) |
| ![類型](/help/assets/icons/TwoDots.svg) | [文氏圖表](/help/analysis-workspace/visualizations/venn.md) | [文氏圖表](https://cloud.google.com/looker/docs/venn) |

>[!TAB Jupyter Notebook]

比較&#x200B;**matplotlib.pyplot** （matplotlib的狀態型介面）的視覺化功能超出本文的目的。 請參閱上述範例以取得靈感和[matplotlib.pyplot](https://matplotlib.org/3.5.3/api/_as_gen/matplotlib.pyplot.html)檔案。


>[!TAB RStudio]

比較R中的資料視覺化封裝&#x200B;**ggplot2**&#x200B;的視覺化功能超出本文的目的。 請參閱上述範例以取得靈感和[ggplot2](https://ggplot2.tidyverse.org/articles/ggplot2.html)檔案。

>[!ENDTABS]




+++


## 注意事項

使用Customer Journey Analytics BI擴充功能時，每一種支援的BI工具都有一些需注意的事項。

+++ BI 工具

>[!BEGINTABS]

>[!TAB Power BI案頭版]

* Power BI Desktop進階日期範圍篩選是專屬功能。  對於結束日期，您需要選取要報告的一天之後的日期。 例如，**[!UICONTROL 位於]** `1/1/2023` **[!UICONTROL 或之後，]**&#x200B;之前`1/2/2023`。
* 建立連線時，Power BI案頭預設為&#x200B;**[!UICONTROL 匯入]**。 請確定您使用&#x200B;**[!UICONTROL 直接查詢]**。
* Power BI Desktop透過Power Query公開資料轉換。  Power Query主要用於匯入型別連線，因此許多您套用的轉換（如日期或字串函式）會擲回錯誤，指出您需要切換到匯入型別連線。  如果您需要在查詢時轉換資料，應使用衍生的維度和量度，因此Power BI不需要自行轉換。
* Power BI Desktop不瞭解如何處理日期 — 時間型別欄，所以不支援&#x200B;**[!UICONTROL daterange *X *]**&#x200B;維度，例如&#x200B;**[!UICONTROL daterangehour &#x200B;]**&#x200B;和&#x200B;**[!UICONTROL daterangeminute &#x200B;]**。
* Power BI Desktop預設會嘗試使用更多查詢服務工作階段建立多個連線。  前往專案的Power BI設定並停用平行查詢。
* Power BI Desktop會執行所有排序和限制使用者端作業。 Power BI Desktop對於前&#x200B;*X*&#x200B;個包含繫結值的篩選也有不同的語意。 因此，您無法建立與Analysis Workspace中相同的排序和限制。
* 舊版Power BI Desktop 2024年10月發行版本中斷PostgreSQL資料來源。 請確定您使用本文中提及的版本。

>[!TAB Tableau案頭]

* Tableau案頭日期範圍篩選不適用。 對於結束日期，您需要選取要報告的一天之後的日期。
* 根據預設，當您新增日期或日期時間維度（例如&#x200B;**[!UICONTROL Daterangemonth]**）至工作表的列時，Tableau Desktop會將&#x200B;**[!UICONTROL YEAR()]**&#x200B;函式中的欄位換行。  若要取得您想要的結果，您必須選取該維度，然後從下拉式選單中選取您要使用的日期函式。  例如，當您嘗試使用&#x200B;**[!UICONTROL Daterangemonth]**&#x200B;時，將&#x200B;**[!UICONTROL 年]**&#x200B;變更為&#x200B;**[!UICONTROL 月]**。
* 在Tableau Desktop中，將結果限制在前&#x200B;*X*&#x200B;是不明顯的。 您可以明確限制結果，或使用計算欄位和&#x200B;**[!UICONTROL INDEX()]**&#x200B;函式。  將Top *X*&#x200B;篩選器新增至維度，會使用不支援的內部聯結產生複雜的SQL。

>[!TAB 觀察者]

* Looker具有每個節點的最大連線數目設定，此設定必須介於5到100之間。  您無法將此值設為1。  此設定表示Looker連線一律使用至少5個可用的查詢服務工作階段。
* Looker可讓您以Customer Journey Analytics資料檢視為基礎，以檢視建立專案。 Looker接著會使用LookerML，根據資料檢視中可用的維度和量度建立模型。  此專案檢視不會自動更新以符合來源。  如果您變更或新增CJA資料檢視維度、量度、計算量度或區段，這些變更不會自動顯示在Looker中。  您必須手動更新專案檢視或建立新專案。
* 查閱者在日期或日期時間欄位（例如&#x200B;**[!UICONTROL Daterange Date]**&#x200B;或&#x200B;**[!UICONTROL Daterangeday Date]**）的使用者體驗令人困惑。
* 查閱者的日期範圍是排除而非包含。  **[!UICONTROL until （之前）]**&#x200B;為灰色，因此您可能會遺漏該外觀。  結束日期前，您必須選取要報告日期的前一天。
* Looker不會自動將您的量度視為量度。  當您選取量度時，依預設，Looker會嘗試將量度視為查詢中的維度。  若要將量度視為量度，您需要建立如上所述的自訂欄位。 作為捷徑，您可以選取&#x200B;**[!UICONTROL ⋮]**、選取&#x200B;**[!UICONTROL 彙總]**，然後選取&#x200B;**[!UICONTROL 總計]**。

>[!TAB Jupyter Notebook]

* Jupyter Notebook的主要注意事項是此工具不像其他BI工具那樣是拖放式使用者介面。 您可以建立良好的視覺效果，但您必須撰寫程式碼才能完成此操作。

>[!TAB RStudio]

* R dplyr適用於一般結構描述，因此需要&#x200B;**[!UICONTROL FLATTEN]**&#x200B;選項。
* RStudio的主要注意事項是此工具不像其他BI工具那樣是拖放式使用者介面。 您可以建立良好的視覺效果，但您必須撰寫程式碼才能完成此操作。

>[!ENDTABS]

+++
