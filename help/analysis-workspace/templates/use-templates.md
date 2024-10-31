---
description: 概述如何使用Analysis Workspace中的預設範本。
title: 使用範本
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 4927fbcaa8d0d0ea251c2827fd6c17c2d55c9f11
workflow-type: tm+mt
source-wordcount: '10210'
ht-degree: 4%

---

# 使用範本

Analysis Workspace中的範本（或公司範本）可快速深入分析最常見的報表案例。 以下是您可以使用範本回答的一些問題範例：

* 多少訪客瀏覽您的網站
* 多少訪客是獨特訪客 (僅計算一次)
* 他們如何來到站點 (例如跟隨連結到達站點，或直接到達)
* 搜尋站點內容時所用的關鍵字
* 在指定網頁或整個站點上逗留的時間
* 訪客點按的連結，以及離開網站的時間
* 產生收入或轉換事件的最有效行銷管道
* 訪客花費在觀看視訊的時間
* 他們用來造訪網站的瀏覽器和裝置

下列資訊說明如何從Analysis Workspace的[!UICONTROL 範本]索引標籤存取及使用範本。

## 存取並執行範本

1. 在 Analysis Workspace 中，選取「[!UICONTROL **工作區**]」標籤。

1. 選取&#x200B;[!UICONTROL **範本**]。

   ![「報告」標籤](assets/view-prebuilt-reports.png)

1. 在搜尋欄位中，開始輸入您要尋找的範本名稱，然後從範本清單中選取它。

   或

   選取您要檢視的範本類別，然後從範本清單中選取範本。

   >[!TIP]
   >
   >若要使用方向鍵瀏覽選單，請按正斜線鍵 (/)，然後按向下鍵。按Enter載入選取的範本。

   如需可用的範本清單，請參閱下方的[可用的範本](#available-templates)區段。

1. （選用）檢視並使用包含資料檢視中無法使用之元件的範本。 （依預設，只會顯示使用資料檢視中可用元件的範本。）

   1. 選取（篩選器選項的名稱？） 來顯示需要其他元件的範本。

      <!-- add screenshot -->

   1. 選取您要使用的範本。

   1. 如果範本包含資料檢視中不可用的元件，則會顯示訊息，指出缺少哪些元件。 按一下（按鈕？） 前往資料檢視，您可在其中自動建立它們。<!--how do you do this? Walk through the process -->

1. 選取要根據所選範本建立報告的範本。

## 自訂並儲存範本 {#use-reports}

範本可能並不完全符合您的需求，但可讓您關閉。 在這些情況下，您可以使用範本作為起點，然後進行自訂以最符合您的特定目的。

如果您在進行變更後離開範本，系統會提示您儲存或捨棄變更。 將變更儲存到範本會將範本儲存為新專案。

若要自訂並儲存範本：

1. 在 Adobe Analytics 中，選取「[!UICONTROL **工作區**]」索引標籤。

1. 選取&#x200B;[!UICONTROL **範本**]&#x200B;索引標籤。

1. 選取您要檢視的範本。 例如，在「[!UICONTROL **最常用**]」底下，選取「[!UICONTROL **頁面**]」報告。

   Analysis Workspace中顯示的「頁面」範本會顯示兩個[視覺效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) （[橫條圖](/help/analysis-workspace/visualizations/bar.md)和[摘要數字](/help/analysis-workspace/visualizations/summary-number-change.md)）以及一個[自由表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 使用的量度為發生次數。

   ![頁面範本](assets/pages-report.png)

1. 執行以下任一操作：

   * 檢視範本。
   * 將一或多個區段拖曳到頂部的「區段」放置區。例如，拖曳「[!UICONTROL **Mobile 客戶**]」區段，然後檢視結果。
   * 前往右上方的行事暦，變更日期範圍。
   * 新增維度劃分、拖曳其他量度，且通常會根據您的需求自訂範本。

1. （選擇性）選取&#x200B;[!UICONTROL **專案**] > [!UICONTROL **儲存**]，將範本儲存為專案。

   範本會儲存為新專案，不會修改現有報告。 有關將報告另存為專案的詳細資訊，請參閱「[儲存專案](/help/analysis-workspace/build-workspace-project/save-projects.md)」。

## 可用的範本

若要存取所有可用的預先建立範本：

1. 在Adobe Analytics中，選取&#x200B;[!UICONTROL **Workspace**]&#x200B;標籤，然後選取&#x200B;[!UICONTROL **範本**]&#x200B;標籤。

   預先建立的範本會依類別組織。

   <!--add screenshot-->

1. 選取類別以檢視其中的範本。

   以下各節對應於可用的類別，並提供每個範本的相關資訊。

   * [[！UICONTROL ](#most-popular)

   * [[！UICONTROL ](#engagement)

   * [[！UICONTROL ](#web-conversion)

   * [[！UICONTROL ](#web-audience)

   * [[！UICONTROL ](#web-acquisition)

   * [[！UICONTROL ](#mobile-mobile-app)

   * [[！UICONTROL ](#mobile-mobile-device-information)

   * [[！UICONTROL ](#time-parting)

   * [[！UICONTROL ](#cross-channel)

   * [[！UICONTROL ](#other-channels)

   * [[！UICONTROL ](#ajo)

### 最受歡迎 {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_training_tutorial"
>title="培訓教學課程範本"
>abstract="瞭解常用的Analysis Workspace術語和建立第一個分析的步驟。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_pages"
>title="識別最受歡迎和最不受歡迎的頁面。"
>abstract="**這可協助您**&#x200B;更瞭解您的對象以及他們最感興趣的資訊型別。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整頁面中繼資料以增加檢視次數較少的頁面上的可見度，或是花時間改善檢視次數最多的頁面的內容。<br/>此範本使用頁面維度和頁面檢視量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_page_views"
>title="檢視頁面檢視總數。 會顯示一段時間的資料，並與之前的時段進行比較。 "
>abstract="**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。<br/>此範本使用日維度和頁面檢視量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_web_visits"
>title="檢視造訪總數。 會顯示一段時間的資料，並與之前的時段進行比較。"
>abstract="**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。<br/>此範本使用日維度和造訪量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_multi_channel_overview"
>title="多管道概觀範本"
>abstract=" "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_multi_channel_comparison"
>title="多管道比較範本"
>abstract=" "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_key_metrics"
>title="檢視可並排顯示頁面檢視、造訪和不重複訪客量度的報表。 會顯示一段時間的資料，並與之前的時段進行比較。"
>abstract="**這可協助您**&#x200B;比較這些重要量度，以更完整瞭解造訪網站的不重複使用者人數、造訪頁面次數和工作階段數量。<br/>**根據您所瞭解的情況，您可**&#x200B;執行任何數量的工作，例如評估每個人在指定的一週或一個月內造訪網站時檢視的平均頁數，以及在一年中的特定時間或在執行行銷活動之前和之後的變化。 <br/>此範本使用日維度、頁面檢視量度、造訪量度和不重複訪客量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_site_sections"
>title="檢視網站中最受歡迎或成效最高的區段。"
>abstract="**這可協助您**&#x200B;更瞭解您網站的哪些區段最常造訪。<br>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如評估您提供的產品或服務會產生最大的興趣。<br/>此範本使用網站區段維度和造訪量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_next_previous_page"
>title="檢視訪客在造訪後或造訪特定地點前最常前往的地方。"
>abstract="**這可協助您**&#x200B;瞭解流量如何從指定頁面移動到網站的其他部分，並瞭解人們進入指定頁面的路徑。<br/>**根據您瞭解的情況，您可**&#x200B;執行許多操作，例如評估頁面設計或版面配置是否可最佳化，以將使用者導向到更理想的頁面，例如購買或留下評論的頁面。 或者，評估目前頁面上的資訊是否可能提供使用者從先前頁面到達時所尋找的方向或動作。 或者，您可以評估未顯示為先前頁面的頁面是否需要指向目前頁面的更顯眼連結。<br/>此範本使用下一個或上一個專案面板。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_campaigns"
>title="檢視最成功吸引流量進入網站的連結。"
>abstract="**這可協助您**&#x200B;更清楚瞭解哪些追蹤程式碼（及其關聯的連結）最常用於存取您的網站。<br/>**根據您學到的內容，您可能**&#x200B;會做許多事情，例如調整您新增連結至網站的策略。<br/>此範本使用追蹤代碼維度和造訪量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_products"
>title="依產品檢視訂單數。 會顯示一段時間的資料。"
>abstract="**這可以協助您**&#x200B;瞭解哪些產品的需求最高或最低。<br/>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如調整行銷策略以促銷高績效的產品，或是改善或停止表現不佳的產品。 您也可以根據資料分析調整產品詳細目錄。<br/>此範本使用「產品」維度和「訂單」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_last_touch"
>title="檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。"
>abstract="**這可協助您**&#x200B;瞭解哪些行銷管道最能有效吸引人們進入您的網站，進而帶來轉換。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如將更多資源配置給表現優異的管道，或將較少資源配置給表現不佳的管道。<br/>此範本使用「上次接觸管道」維度和「不重複訪客」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_last_touch_detail"
>title="檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道的詳細資料。"
>abstract="**這可協助您**&#x200B;不僅瞭解哪些行銷管道最能有效吸引人們進入您的網站並帶來轉換，還可瞭解這些行銷管道的詳細資訊。 例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如將更多資源配置給表現優異的管道，或將較少資源配置給表現不佳的管道。<br/>此範本使用上次接觸管道詳細資料維度和不重複訪客量度。 "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_revenue"
>title="檢視所有訂單中購買產品的金額。 會顯示一段時間的資料，並與之前的時段進行比較。"
>abstract="**這可協助您**&#x200B;瞭解收入如何隨著時間增加或減少。 您可以將此量度與任何維度結合，瞭解哪些維度專案對收入有貢獻。<br/>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如根據先前的趨勢預測專案未來的收入。 您也可以新增另一個維度（例如追蹤代碼維度），以瞭解哪些行銷活動產生最多收入。<br/>此範本使用日維度和收入量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_desc_orders"
>title="檢視購買事件的總數。 會顯示一段時間的資料，並與之前的時段進行比較。"
>abstract="**這可以協助您**&#x200B;更瞭解您的產品和服務在一段時間內如何增加或減少興趣。 您可以套用區段，以瞭解哪些客戶或地理區域下的訂單最多，以及這些訂單在一段時間內的趨勢如何。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如透過比較行銷活動啟動前後的訂單，來評估最近啟動行銷活動的有效性。 或者，您也可以比較逐年比較假期訂單。<br/>此範本使用「日」維度和「訂單」量度。"

<!-- markdownlint-enable MD034 -->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **訓練教學課程**] | 瞭解常用的Analysis Workspace術語和建立第一個分析的步驟 |
| [!UICONTROL **頁面**] | <!--duplicated in Engagement section--> 識別最受歡迎和最不受歡迎的頁面。 <p>**這可協助您**&#x200B;更瞭解您的對象以及他們最感興趣的資訊型別。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整頁面中繼資料以增加檢視次數較少的頁面上的可見度，或是花時間改善檢視次數最多的頁面的內容。</p><p>此範本使用頁面維度和頁面檢視量度。</p> |
| [!UICONTROL **頁面瀏覽數**] | <!--duplicated in Engagement section--> 檢視頁面檢視總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。</p><p>此範本使用日維度和頁面檢視量度。</p> |
| [!UICONTROL **網站造訪**] | <!--duplicated in Engagement section--> 檢視造訪總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。</p><p>此範本使用日維度和造訪量度。</p> |
| [!UICONTROL **網頁訪客**] | <!--duplicated in Engagement section--> 檢視不重複訪客的總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更清楚瞭解您網站的觸及範圍和對象人數如何隨著時間增加或減少，或與之前時段相比。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如評估最近啟動的行銷活動是否成功吸引新人加入網站，方法是比較行銷活動啟動前後的不重複訪客。 或者，您可能會比較假日期間和全年造訪網站的人數。</p><p>此範本使用日維度和不重複訪客量度。</p> |
| **[!UICONTROL 多管道概觀]** |  |
| **[!UICONTROL 跨管道比較]** |  |
| [!UICONTROL **關鍵量度**] | <!--duplicated in Engagement section--> 檢視可並排顯示頁面檢視、造訪和不重複訪客量度的報表。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;比較這些重要量度，以更完整瞭解造訪網站的不重複使用者人數、造訪頁面次數和工作階段數量。</p><p>**根據您所瞭解的情況，您可**&#x200B;執行任何數量的工作，例如評估每個人在指定的一週或一個月內造訪網站時檢視的平均頁數，以及在一年中的特定時間或在執行行銷活動之前和之後的變化。 </p><p>此範本使用日維度、頁面檢視量度、造訪量度及不重複訪客量度。</p> |
| [!UICONTROL **網站區域**] | 檢視網站中最受歡迎或成效最高的區段。 <p>**這可協助您**&#x200B;更瞭解您網站的哪些區段最常造訪。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如評估您提供的產品或服務會產生最大的興趣。</p> <p>此範本使用網站區段維度和造訪量度。</p> |
| [!UICONTROL **下一頁和上一頁**] | 檢視訪客在造訪後或造訪特定地點前最常前往的地方。 <p>**這可協助您**&#x200B;瞭解流量如何從指定頁面移動到網站的其他部分，並瞭解人們進入指定頁面的路徑。</p><p>**根據您瞭解的情況，您可**&#x200B;執行許多操作，例如評估頁面設計或版面配置是否可最佳化，以將使用者導向到更理想的頁面，例如購買或留下評論的頁面。 或者，評估目前頁面上的資訊是否可能提供使用者從先前頁面到達時所尋找的方向或動作。 或者，您可以評估未顯示為先前頁面的頁面是否需要指向目前頁面的更顯眼連結。</p><p>此範本使用「下一個專案」或「上一個專案」面板。</p> |
| [!UICONTROL **行銷活動（追蹤代碼）**] | 檢視最成功吸引流量進入網站的連結。 <p>**這可協助您**&#x200B;更清楚瞭解哪些追蹤程式碼（及其關聯的連結）最常用於存取您的網站。</p><p>**根據您學到的內容，您可能**&#x200B;會做許多事情，例如調整您新增連結至網站的策略。</p><p>此範本使用追蹤代碼維度和造訪量度。</p> |
| [!UICONTROL **產品**] | 依產品檢視訂單數。 會顯示一段時間的資料。 <p>**這可以協助您**&#x200B;瞭解哪些產品的需求最高或最低。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如調整行銷策略以促銷高績效的產品，或是改善或停止表現不佳的產品。 您也可以根據資料分析調整產品詳細目錄。</p><p>此範本使用產品維度和訂單量度。</p> |
| [!UICONTROL **上次接觸行銷管道**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。<p>**這可協助您**&#x200B;瞭解哪些行銷管道最能有效吸引人們進入您的網站，進而帶來轉換。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如將更多資源配置給表現優異的管道，或將較少資源配置給表現不佳的管道。</p><p>此範本使用「上次接觸管道」維度和獨特訪客量度。</p> |
| [!UICONTROL **上次接觸行銷管道詳細資料**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道的詳細資料。<p>**這可協助您**&#x200B;不僅瞭解哪些行銷管道最能有效吸引人們進入您的網站並帶來轉換，還可瞭解這些行銷管道的詳細資訊。 例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如將更多資源配置給表現優異的管道，或將較少資源配置給表現不佳的管道。</p><p>此範本使用「上次接觸管道詳細資料」維度和「不重複訪客」量度。</p> |
| [!UICONTROL **收入**] | <!--duplicated in Web Conversion section-->檢視所有訂單中購買產品的金額。 會顯示一段時間的資料，並與之前的時段進行比較。<p>**這可協助您**&#x200B;瞭解收入如何隨著時間增加或減少。 您可以將此量度與任何維度結合，瞭解哪些維度專案對收入有貢獻。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如根據先前的趨勢預測專案未來的收入。 您也可以新增另一個維度（例如追蹤代碼維度），以瞭解哪些行銷活動產生最多收入。</p><p>此範本使用日維度和收入量度。</p> |
| [!UICONTROL **訂購**] | <!--duplicated in Web Conversion section-->檢視購買事件的總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可以協助您**&#x200B;更瞭解您的產品和服務在一段時間內如何增加或減少興趣。 您可以套用區段，以瞭解哪些客戶或地理區域下的訂單最多，以及這些訂單在一段時間內的趨勢如何。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如透過比較行銷活動啟動前後的訂單，來評估最近啟動行銷活動的有效性。 或者，您也可以比較逐年比較假期訂單。</p><p>此範本使用日維度和訂單量度。</p> |

### 網路：參與 {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="檢視訪客每次造訪時花在您的網站上的平均時間，以及使用者在成功事件之前花的平均時間。 會顯示一段時間的資料，並與之前的時段進行比較。"
>abstract="**這可協助您**&#x200B;更瞭解訪客參與層級，以及訪客執行所需動作（例如購買）所花費的時間。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如評估您網站的變更是否可改善訪客快速達成成功事件的能力。<br/>此範本使用「日」維度和「每次造訪逗留時間（秒）」量度、「日」維度和「每次造訪逗留時間（秒）」量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_web_content_consumption"
>title="檢視使用者最常使用且受到哪些網站內容吸引。"
>abstract="**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的目的地、使用者最常造訪的網站區域，以及哪些頁面最有可能將使用者帶離網站。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至網站之外。<br/>此範本使用「頁面」維度和「頁面檢視」量度、「造訪」量度、「不重複訪客」量度、「登入率」量度、「跳出率」量度、「退出率」量度和「內容速度」量度。 它也會對登入、退出和頂端區段使用「流量」視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_media_content_consumption"
>title="檢視最常使用且吸引使用者的媒體內容。"
>abstract="**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的目的地、使用者最常造訪的網站區域，以及哪些頁面最有可能將使用者帶離網站。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至網站之外。<br/>此範本使用「頁面」維度和「頁面檢視」量度、「造訪」量度、「不重複訪客」量度、「登入率」量度、「跳出率」量度、「退出率」量度和「內容速度」量度。 此外也針對登入、退出和頂端區段使用「流量」視覺效果；顯示最常見頁面檢視次數的「起點」視覺效果；依分段時間顯示頁面檢視次數的「長條」視覺效果；以及顯示網站平均逗留時間趨勢檢視的「線條」視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_page_summary"
>title="檢視屬性中任何頁面的相關重要資訊。 顯示頁面檢視、趨勢線、流量視覺效果等。"
>abstract="**這可協助您**&#x200B;更瞭解人們如何與指定頁面互動。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如分析一段時間內的頁面效能，或更瞭解哪些因素會導致流量進入頁面。<br/>此範本使用頁面檢視量度。 它也會使用線條視覺效果和流量視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_entry_pages"
>title="檢視訪客首次造訪您的網站時存取的最上層頁面。"
>abstract="**這可協助您**&#x200B;更瞭解哪些頁面為您的網站帶來最多流量，或進一步瞭解訪客在您網站上的第一印象。<br/>**根據您所瞭解的情況，您可能**&#x200B;會執行許多動作，例如最佳化使用者在網站上的初始體驗，或確保使用者在進入網站時首先看到的頁面是歡迎的，並提供您網站其他區域的必要連結。<br/>此範本使用工作階段量度。 它也會使用長條圖視覺效果和自由格式表格視覺效果。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_exit_pages"
>title="檢視訪客在離開您的網站前立即存取的最上層頁面。"
>abstract="**這可以協助您**&#x200B;更瞭解哪些頁面正在將人們帶離網站。 <br/>**根據您所學到的內容，您可以**&#x200B;執行許多操作，例如更新常見的退出頁面以最佳化使用者離開之前的體驗，或包含內容或連結以鼓勵使用者留在您的網站上。<br/>此範本使用工作階段量度。 它也會使用長條圖視覺效果和自由格式表格視覺效果。"

<!-- markdownlint-enable MD034 -->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **關鍵量度**] | <!--duplicated in Most popular section--> 檢視可並排顯示頁面檢視、造訪和不重複訪客量度的報表。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;比較這些重要量度，以更完整瞭解造訪網站的不重複使用者人數、造訪頁面次數和工作階段數量。</p><p>**根據您所瞭解的情況，您可**&#x200B;執行任何數量的工作，例如評估每個人在指定的一週或一個月內造訪網站時檢視的平均頁數，以及在一年中的特定時間或在執行行銷活動之前和之後的變化。 </p><p>此範本使用日維度、頁面檢視量度、造訪量度及不重複訪客量度。</p> |
| [!UICONTROL **頁面瀏覽數**] | <!--duplicated in Most popular section-->檢視頁面檢視總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。</p><p>此範本使用日維度和頁面檢視量度。</p> |
| [!UICONTROL **頁面**] | <!--duplicated in Most popular section-->識別最受歡迎和最不受歡迎的頁面。 <p>**這可協助您**&#x200B;更瞭解您的對象以及他們最感興趣的資訊型別。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整頁面中繼資料以增加檢視次數較少的頁面上的可見度，或是花時間改善檢視次數最多的頁面的內容。</p><p>此範本使用頁面維度和頁面檢視量度。</p> |
| [!UICONTROL **造訪數**] | <!--duplicated in Most popular section-->檢視造訪總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更瞭解您網站上的流量如何隨著時間增加或減少。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如比較最近推出的行銷活動推出前後的網站流量，以評估行銷活動的成效。 或者，您也可以比較逐年比較假期流量。</p><p>此範本使用日維度和造訪量度。</p> |
| [!UICONTROL **訪客**] | <!--duplicated in Most popular section-->檢視不重複訪客的總數。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更清楚瞭解您網站的觸及範圍和對象人數如何隨著時間增加或減少，或與之前時段相比。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如評估最近啟動的行銷活動是否成功吸引新人加入網站，方法是比較行銷活動啟動前後的不重複訪客。 或者，您可能會比較假日期間和全年造訪網站的人數。</p><p>此範本使用日維度和不重複訪客量度。</p> |
| [!UICONTROL **逗留時間**] | 檢視訪客每次造訪時花在您的網站上的平均時間，以及使用者在成功事件之前花的平均時間。 會顯示一段時間的資料，並與之前的時段進行比較。 <p>**這可協助您**&#x200B;更瞭解訪客參與層級，以及訪客執行所需動作（例如購買）所花費的時間。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如評估您網站的變更是否可改善訪客快速達成成功事件的能力。</p><p>此範本使用「日」維度和「每次造訪逗留時間（秒）」量度、「日」維度和「每次造訪逗留時間（秒）」量度。</p> |
| [!UICONTROL **網站區域**] | <!--duplicated in Most popular section-->檢視網站中最受歡迎或成效最高的區段。 <p>**這可協助您**&#x200B;更瞭解您網站的哪些區段最常造訪。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如評估您提供的產品或服務會產生最大的興趣。</p> <p>此範本使用網站區段維度和造訪量度。</p> |
| [!UICONTROL **網頁內容使用量**] | 檢視使用者最常使用且受到哪些網站內容吸引。<p>**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的目的地、使用者最常造訪的網站區域，以及哪些頁面最有可能將使用者帶離網站。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至遠離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用「頁面」維度和「頁面檢視」量度、「造訪」量度、「不重複訪客」量度、「登入率」量度、「跳出率」量度、「退出率」量度和「內容速度」量度。 它也會對登入、退出和頂端區段使用「流量」視覺效果。</p> |
| [!UICONTROL **媒體內容使用量**] | 檢視最常使用且吸引使用者的媒體內容。<p>**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的目的地、使用者最常造訪的網站區域，以及哪些頁面最有可能將使用者帶離網站。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何數量的操作，例如評估網站上的哪些路徑會將人們引導至最重要的頁面，以及哪些頁面更可能將人們引導至遠離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用「頁面」維度和「頁面檢視」量度、「造訪」量度、「不重複訪客」量度、「登入率」量度、「跳出率」量度、「退出率」量度和「內容速度」量度。 此外也針對登入、退出和頂端區段使用「流量」視覺效果；顯示最常見頁面檢視次數的「起點」視覺效果；依分段時間顯示頁面檢視次數的「長條」視覺效果；以及顯示網站平均逗留時間趨勢檢視的「線條」視覺效果。</p> |
| [!UICONTROL **下一頁和上一頁**] | <!--duplicated in Most popular section-->檢視訪客造訪特定地點之前或之後最常前往的地方。<p>**這可協助您**&#x200B;更清楚瞭解使用者第一次進入網站時的所在位置、使用者最常造訪的網站區域，以及離開網站前最有可能造訪的頁面。</p><p>**根據您所瞭解的情況，您可能**&#x200B;會執行任何數量的動作，例如評估網站上的哪些路徑將人們帶往最重要的頁面，以及哪些頁面更可能將人們帶離網站<!-- not sure about these takeaways... -->。</p> <p>此範本使用「頁面」維度、「頁面檢視」量度、「造訪」量度、「不重複訪客」量度、「登入率」量度、「跳出率」量度、「退出率」量度和「內容速度」量度。 此外也針對登入、退出和頂端區段使用流量視覺效果；顯示最常見頁面檢視的散佈圖視覺效果；依分段時間顯示頁面檢視的橫條圖視覺效果；以及顯示網站平均逗留時間趨勢檢視的線條圖視覺效果。</p> |
| **頁面摘要** | 檢視屬性中任何頁面的相關重要資訊。 顯示頁面檢視、趨勢線、流量視覺效果等。  <p>**這可協助您**&#x200B;更瞭解人們如何與指定頁面互動。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如分析一段時間內的頁面效能，或更瞭解哪些因素會導致流量進入頁面。</p><p>此範本使用頁面檢視量度。 它也會使用線條視覺效果和流量視覺效果。</p> |
| **登入頁面** | 檢視訪客首次造訪您的網站時存取的最上層頁面。 <p>**這可協助您**&#x200B;更瞭解哪些頁面為您的網站帶來最多流量，或進一步瞭解訪客在您網站上的第一印象。</p><p>**根據您所瞭解的情況，您可能**&#x200B;會執行許多動作，例如最佳化使用者在網站上的初始體驗，或確保使用者在進入網站時首先看到的頁面是歡迎的，並提供您網站其他區域的必要連結。</p><p>此範本使用工作階段量度。 它也會使用長條圖視覺效果和自由格式表格視覺效果。</p> |
| **退出頁面** | 檢視訪客在離開您的網站前立即存取的最上層頁面。<p>**這可以協助您**&#x200B;更瞭解哪些頁面正在將人們帶離網站。 </p><p>**根據您所學到的內容，您可以**&#x200B;執行許多操作，例如更新常見的退出頁面以最佳化使用者離開之前的體驗，或包含內容或連結以鼓勵使用者留在您的網站上。</p><p>此範本使用工作階段量度。 它也會使用長條圖視覺效果和自由格式表格視覺效果。</p> |

### 網頁：轉換 {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_product_conversion_funnel"
>title="產品轉換漏斗"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_product_performance"
>title="檢視哪些產品成效最高。"
>abstract="**這可協助您**&#x200B;更清楚瞭解哪些產品最成功。<br/>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如增加對成功產品的資助，並減少對不成功產品的資助。<br/>此範本使用產品檢視、購物車新增、訂購、收入和件數等量度。 它也會使用產品維度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_conversion_funnels"
>title="檢視人員執行重要結帳事件的次數，例如將商品新增至購物車、檢視購物車、從購物車移除商品以及結帳。"
>abstract="**這可協助您**&#x200B;更清楚瞭解哪些結帳程式漏斗部分會導致轉換，以及哪些部分更容易遭到購物車放棄。<br/>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如在結帳程式的某些步驟減少摩擦。<br/>此範本使用"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_carts"
>title="檢視將產品新增至購物車的使用者人數。"
>abstract="**這可協助您**&#x200B;更瞭解將產品加入購物車的人數，而非加入購物車的產品總數。<br/>**根據您瞭解的情況，您可能**&#x200B;會執行任何工作，例如測量產品頁面的效益。<br/>此範本使用購物車量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_views"
>title="檢視人們檢視其購物車的次數。"
>abstract="**這可協助您**&#x200B;更瞭解結帳體驗，以降低購物車放棄率，或分析不同產品之間購物車新增與結帳之間的時間。<br/>**根據您所掌握的資訊，您可能**&#x200B;會做許多事情，例如針對在購物車中停留時間最長，且最容易被放棄的產品提供促銷活動。<br/>此範本使用購物車檢視量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_additions"
>title="檢視人們在購物車中新增商品的次數。"
>abstract="**這可協助您**&#x200B;更瞭解客戶對產品有足夠高的興趣而將其新增到購物車的轉換漏斗部分。<br/>**根據您瞭解的情況，您可以**&#x200B;執行許多操作，例如改善所有客戶的產品建議。 您可以透過分析哪些產品經常新增到相同的購物車，並根據購物車中已有的專案建議相關產品來完成這項操作。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_cart_removals"
>title="檢視人們從購物車中移除商品的次數。"
>abstract="**這可協助您**&#x200B;更瞭解客戶對產品已不感興趣的轉換漏斗部分，或可協助您瞭解結帳過程中可能存在的問題。<br/>**根據您所學到的內容，您可能**&#x200B;會執行許多操作，例如移除結帳過程中可能存在的任何潛在障礙，例如複雜的使用者體驗。<br/>此範本使用購物車移除量度。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_purchase_conversion_funnel"
>title="購買轉換漏斗範本"
>abstract=""

<!-- markdownlint-enable MD034 -->

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **產品轉換漏斗**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **產品** | 檢視帶動關鍵量度的產品，例如最暢銷商品或最常檢視的商品。 <p>**這可協助您**&#x200B;更清楚瞭解哪些產品最成功。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如增加對成功產品的資助，並減少對不成功產品的資助。</p><p>此範本使用訂單量度和產品維度。 |
| **產品績效** | 檢視哪些產品成效最高。<p>**這可協助您**&#x200B;更清楚瞭解哪些產品最成功。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如增加對成功產品的資助，並減少對不成功產品的資助。</p><p>此範本使用產品檢視、購物車新增、訂單、收入和件數等量度。 它也會使用產品維度。 |
| **購物車轉換漏斗** | 檢視人員執行重要結帳事件的次數，例如將商品新增至購物車、檢視購物車、從購物車移除商品以及結帳。 <p>**這可協助您**&#x200B;更清楚瞭解哪些結帳程式漏斗部分會導致轉換，以及哪些部分更容易遭到購物車放棄。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如在結帳程式的某些步驟減少摩擦。</p><p>此範本使用 |
| **購物車** | 檢視將產品新增至購物車的使用者人數。<p>**這可協助您**&#x200B;更瞭解將產品加入購物車的人數，而非加入購物車的產品總數。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何工作，例如測量產品頁面的效益。</p><p>此範本使用購物車量度。 |
| **購物車檢視** | 檢視人們檢視其購物車的次數。 <p>**這可協助您**&#x200B;更瞭解結帳體驗，以降低購物車放棄率，或分析不同產品之間購物車新增與結帳之間的時間。</p><p>**根據您所掌握的資訊，您可能**&#x200B;會做許多事情，例如針對在購物車中停留時間最長，且最容易被放棄的產品提供促銷活動。</p><p>此範本使用購物車檢視量度。 |
| **購物車新增** | 檢視人們在購物車中新增商品的次數。 <p>**這可協助您**&#x200B;更瞭解客戶對產品有足夠高的興趣而將其新增到購物車的轉換漏斗部分。</p><p>**根據您瞭解的情況，您可以**&#x200B;執行許多操作，例如改善所有客戶的產品建議。 您可以透過分析哪些產品經常新增到相同的購物車，並根據購物車中已有的專案建議相關產品來完成這項操作。 |
| **購物車移除** | 檢視人們從購物車中移除商品的次數。<p>**這可協助您**&#x200B;更瞭解客戶對產品已不感興趣的轉換漏斗部分，或可協助您瞭解結帳過程中可能存在的問題。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多操作，例如移除結帳過程中可能存在的任何潛在障礙，例如複雜的使用者體驗。</p><p>此範本使用購物車移除量度。 |
| **購買轉換漏斗** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **收入** | <!--duplicated in Most popular section-->檢視所有訂單中購買產品的金額。<p>**這可協助您將「收入」量度與任何維度結合，以**&#x200B;更能瞭解哪些維度專案對收入有貢獻。 例如，您可以看到對收入最有貢獻的前幾項行銷活動（使用追蹤代碼維度）。 </p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整未達到您預期收入目標的行銷活動。</p><p>此範本使用收入量度。 |
| **訂購** | <!--duplicated in Most popular section-->檢視您的網站上發生的購買事件總數。 <p>**這可協助您**&#x200B;結合訂單量度與任何維度，以更清楚瞭解哪些維度專案對訂單有貢獻。 例如，您可以看到對購買最有貢獻的前幾項行銷活動（使用追蹤代碼維度）。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如調整未達到您預期購買目標的行銷活動。 </p><p>此範本使用訂單量度。 |

### 網路：對象

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **第一個與重複使用者**] | 檢視首次訪客與重複訪客的比較。 <p>**這可協助您**&#x200B;更瞭解您的網站在維持客戶忠誠度方面的成效，或您獲得新客戶的比率。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行任何動作，例如為首次訪客購買產品提供獎勵，以吸引他們回訪。</p><p>此範本使用 |
| **人員Id/名稱空間** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **位置概述** | 在地圖視覺效果中檢視訪客位置概觀。<p>**這可協助您**&#x200B;更清楚瞭解造訪您網站的訪客所在位置。 </p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如將行銷資源集中在您最感興趣和機會的地方。</p><p>此範本使用 |
| **地理國家/地區** | 檢視造訪網站的訪客所在的國家/地區。<p>**這可協助您**&#x200B;更瞭解訪客最常來自哪些國家/地區造訪您的網站。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用資料來專注於這些國家/地區的行銷工作，或確保您的網站體驗在主要語言不同的國家/地區中是最佳的。</p><p>此範本使用國家/地區維度。 |
| **美國地理州** | 檢視造訪網站的訪客所來自的州（美國）。 此範本與地理區域範本類似，差別在於此範本是美國特有範本。<p>**這可協助您**&#x200B;更瞭解最受歡迎的美國州訪客來自造訪您網站的訪客。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用這些資料來專注在這些狀態下的行銷工作。</p><p>此範本使用美國州維度。 |
| **地理區域** | 檢視造訪網站的人所來自的地理區域。 區域是小於國家/地區、大於城市的地理區域。 在某些國家，區域是指一個州、省或府/州。在其他區域，它是一個組成國家、部門或大都會區域。 <p>**這可協助您**&#x200B;更清楚瞭解造訪您網站之訪客最常來自的地區。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用資料來集中在這些地區的行銷工作，或確保您的網站體驗在主要語言不同的地區是最佳的。 </p><p>此範本使用ID（變數/地理國家）與地區維度。 |
| **地理城市** | 檢視造訪網站的人所來自的城市。 <p>**這可協助您**&#x200B;更清楚瞭解訪客從造訪您網站的人中最常造訪的城市。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用這些資料來專注於這些城市的行銷工作。 </p><p>此範本使用 |
| **美國DMA** | 檢視造訪網站訪客所在的美國指定行銷區域(DMA)。<p>**這可協助您**&#x200B;更清楚瞭解造訪您網站之訪客最常來自的地區。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如使用資料專注於最成功地區的行銷工作。 </p><p>此範本使用 |
| **語言** | 檢視訪客最常用來檢視內容的語言。 <p>**這可協助您**&#x200B;更瞭解訪客最常使用的語言。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如針對最熱門的語言進行重點本地化或行銷工作。</p><p>此範本使用語言維度。 |
| **技術概覽** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **瀏覽器** | 檢視訪客用來存取您網站的主要瀏覽器名稱和版本。<p>**這可協助您**&#x200B;更瞭解訪客最常使用的瀏覽器。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如使用最熱門的瀏覽器測試您網站的新版本，以改善網站品質。 這麼做可讓品質控制的工作發揮最大效用。</p><p>此範本使用瀏覽器維度。 |
| **瀏覽器類型** | 檢視組織名稱，這些組織是製作訪客用來存取您網站的主要瀏覽器。 這與瀏覽器範本的不同之處在於，它不會將相同瀏覽器的不同版本列為單獨的維度專案。<p>**這可協助您**&#x200B;更瞭解訪客最常使用的瀏覽器</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如使用最熱門的瀏覽器測試您網站的新版本，以改善網站品質。 這麼做可讓品質控制的工作發揮最大效用。 </p><p>此範本使用瀏覽器型別維度。 |

### Web：贏取

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行銷管道**] > [!UICONTROL **行銷管道概觀報表**] | 使用自訂歸因時，此範本會顯示訪客如何到達您的網站。<p>**這可協助您**&#x200B;更清楚瞭解哪些行銷管道最有效。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如，在有效的行銷管道上投入更多資金，並從影響較小的行銷管道中抽身。</p><p>此範本使用ID（變數/行銷管道）維度和收入量度。 |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸行銷管道**] | 檢視訪客在其參與期間（預設為30天）遇到的第一個相符行銷管道。 <p>**這可協助您**&#x200B;更清楚瞭解哪些行銷管道促進網站的初始流量。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如在最有效的領域集中行銷工作。</p><p>此範本使用首次接觸管道維度。 |
| [!UICONTROL **行銷管道**] > [!UICONTROL **首次接觸行銷管道詳細資料**] | 檢視訪客在其參與期間（預設為30天）遇到的第一個相符行銷管道的詳細資料。<p>**這可協助您**&#x200B;更瞭解促使點選符合行銷管道的原因。 例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如在最有效的領域集中行銷工作。</p><p>此範本使用首次接觸管道詳細資料維度。 |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸行銷管道**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道。<p>**這可協助您**&#x200B;更清楚瞭解哪些行銷管道促進您網站的流量進而產生轉換。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如在最有效的領域集中行銷工作。</p><p>此範本使用「上次接觸管道」維度。 |
| [!UICONTROL **行銷管道**] > [!UICONTROL **上次接觸行銷管道詳細資料**] | 檢視訪客在其參與期間（預設為30天）遇到的最新相符行銷管道的詳細資料<p>**這可協助您**&#x200B;更瞭解促使點選符合行銷管道的原因。 例如，當訪客進入您的網站，並找到相符的「付費搜尋」行銷管道時，您可以使用管道詳細資料來瞭解他們使用了哪個搜尋引擎，或搜尋了哪個關鍵字。</p><p>**根據您所學到的內容，您可能**&#x200B;會做許多事情，例如在最有效的領域集中行銷工作。 </p><p>此範本使用「上次接觸管道詳細資料」維度。 |
| [!UICONTROL **行銷活動**] > [!UICONTROL **行銷活動（追蹤代碼）**] | 檢視您網站上的追蹤程式碼名稱。 您可以在網際網路中的不同位置放置具有不同查詢字串引數值的連結。<p>**這可協助您**&#x200B;更瞭解哪些連結最能成功吸引流量進入您的網站。 附加追蹤程式碼查詢字串在電子郵件、廣告、社群媒體貼文及您的組織使用的其他行銷工作中很常見</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如將行銷工作重點放在帶來最多收入的行銷活動中。</p><p>此範本使用追蹤代碼維度。 |
| [!UICONTROL **促銷活動**] > [!UICONTROL **促銷活動轉換漏斗**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| [!UICONTROL **行銷活動**] > [!UICONTROL **行銷活動績效**] | 檢視行銷活動成效的詳細資訊。<p>**這可協助您**&#x200B;更深入瞭解與行銷活動相關的各種成功指標，例如收入、產品檢視、訂購等。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如將行銷工作重點放在帶來最多收入的行銷活動中。 </p><p>此範本使用「收入」量度、「產品檢視」量度、「購物車新增」量度、「訂單」量度和「件數」量度。 此維度也會使用追蹤代碼維度和反向連結網域維度。 |
| **網頁贏取** | 檢視您的網站如何取得訪客。<p>**這可協助您**&#x200B;進一步瞭解導致贏取的各種因素，例如搜尋關鍵字、反向連結網域等。</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用「跳出率」量度和「跳出」量度。 它也會使用搜尋引擎維度、搜尋關鍵字維度、登入頁面維度、反向連結網域維度、追蹤代碼維度以及反向連結維度。 |
| **搜尋關鍵字 — 全部** | 檢視訪客用來存取您的網站的搜尋關鍵字，無論是付費還是免費。 <p>**這可以協助您**&#x200B;更瞭解使用者在搜尋中導致網站流量的關鍵字。 </p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多作業，例如識別並填滿所使用的關鍵字與造成網站流量之關鍵字之間的SEO差距。</p><p>此範本使用「搜尋關鍵字」維度。 |
| **搜尋付費關鍵字** | 檢視訪客用來存取您的網站的搜尋關鍵字（符合付費搜尋偵測）。<p>**這可以協助您**&#x200B;更瞭解使用者在搜尋中導致網站流量的關鍵字。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多作業，例如識別並填滿所使用的關鍵字與造成網站流量之關鍵字之間的SEO差距。 </p><p>此範本使用搜尋關鍵字 — 付費維度。 |
| **搜尋關鍵字 — 免費** | 檢視訪客用來存取您的網站的搜尋關鍵字（不符合付費搜尋偵測）。<p>**這可以協助您**&#x200B;更瞭解使用者在搜尋中導致網站流量的關鍵字。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多作業，例如識別並填滿所使用的關鍵字與造成網站流量之關鍵字之間的SEO差距。</p><p>此範本使用「搜尋關鍵字 — 免費」維度。 |
| **搜尋引擎 — 全部** | 檢視訪客用來存取您的網站的搜尋引擎，無論是付費還是免費。 <p>**這可協助您**&#x200B;更清楚瞭解使用者用來產生網站流量的搜尋引擎。 </p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如將SEO工作集中在為網站帶來最多流量的搜尋引擎上。</p><p>此範本使用搜尋引擎維度。 |
| **搜尋引擎付費** | 檢視訪客用來存取您的網站的搜尋引擎（符合付費搜尋偵測）。<p>**這可協助您**&#x200B;更清楚瞭解使用者用來產生網站流量的搜尋引擎。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如將SEO工作集中在為網站帶來最多流量的搜尋引擎上。 </p><p>此範本使用搜尋引擎 — 付費維度。 |
| **搜尋引擎 — 免費** | 檢視訪客用來存取您的網站的搜尋關鍵字（不符合付費搜尋偵測）。<p>**這可協助您**&#x200B;更清楚瞭解使用者用來產生網站流量的搜尋引擎。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多作業，例如將SEO工作集中在為網站帶來最多流量的搜尋引擎上。</p><p>此範本使用「搜尋引擎 — 免費」維度。 |
| **反向連結網域** | 檢視訪客點進哪些網域以存取您的網站。<p>**這可協助您**&#x200B;更瞭解哪些協力廠商網站為您帶來最多流量。 （外部網站上必須有連結，且訪客必須點按該連結，才會顯示維度專案。）</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行許多操作，例如建立或調整內容，以更符合來自頂級反向連結網域的訪客的興趣。 </p><p>此範本使用反向連結網域維度。 |
| **原始反向連結網域** | 檢視訪客點進您的網站的第一個反向連結網域。 （設定後，該訪客ID的整個存留期都會包含相同的值。）<p>**這可協助您**&#x200B;更瞭解哪些協力廠商網站原本會將流量帶往您的網站。</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行任意數量的操作，例如建立或調整內容，以更符合來自最佳原始反向連結網域的訪客的興趣。 </p><p>此範本使用原始反向連結網域維度。 |
| **反向連結** | 檢視訪客點進您的網站時所在的URL。 （外部URL上必須有連結，且訪客必須點按該連結，才會顯示維度專案。）  <p>**這可協助您**&#x200B;更瞭解哪些特定URL為您的網站帶來最多流量。</p><p>**根據您瞭解到的內容，您可能**&#x200B;會執行許多操作，例如建立或調整內容，以更符合來自頂層URL之訪客的興趣。 </p><p>此範本使用反向連結網域維度 </p><p>此範本使用反向連結維度。 |
| **反向連結型別** | 檢視訪客點進哪些通用管道後到達您的網站。 Adobe會維護每個頻道的規則。 可能的管道包括搜尋引擎、社交網路、其他網站、硬碟或電子郵件。<p>**這可協助您**&#x200B;更瞭解哪些型別的反向連結為您的網站帶來最多流量。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行任何動作，例如建立或調整內容，以更符合來自特定頻道的訪客的興趣。</p><p>此範本使用反向連結型別維度。 |

### 行動：行動應用程式

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行動應用程式Screens**] | 檢視訪客存取您的網站時，所使用的行動熒幕資訊，例如熒幕大小、熒幕寬度和熒幕高度。 <p>**這可協助您**&#x200B;更瞭解人們如何體驗您的網站。</p><p>**根據您瞭解的情況，您可**&#x200B;執行任意數量的操作，例如針對最常見的熒幕大小最佳化網站的呈現。</p><p>此範本使用 |
| **行動應用程式動作** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式使用情形** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式歷程** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式量度** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式訊息** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式效能** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **行動應用程式保留率** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |

### 行動：行動裝置資訊

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **行動電信業者**] | 檢視人們用來存取您的網站的行動電信業者。<p>**這可協助您**&#x200B;更清楚瞭解哪些行動電信業者最受您的使用者群歡迎。</p><p>**根據您瞭解的情況，您可以**&#x200B;執行任何動作，例如根據不同電信業者的網路功能量身打造您的內容傳遞，以確保順暢的使用者體驗。</p><p>此範本使用行動電信業者維度。 |
| **行動裝置** | 檢視人們用來存取您的網站的行動裝置。<p>**這可協助您**&#x200B;更清楚瞭解哪些行動裝置最受您的使用者群歡迎。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如針對最常見的行動裝置最佳化您網站的轉譯。</p><p>此範本使用行動裝置名稱維度。 |
| **行動裝置型別** | 檢視人們用來存取您的網站的行動裝置型別，例如手機和平板電腦。<p>**這可協助您**&#x200B;更清楚瞭解用來存取您網站的各種行動裝置。</p><p>**根據您瞭解的情況，您可能**&#x200B;會執行許多動作，例如針對最常使用的行動裝置型別最佳化您的網站。</p><p>此範本使用行動裝置型別維度。 |
| **製造商** | 檢視哪些製造商生產供使用者存取網站的行動裝置，例如Apple和Samsung。<p>**這可以協助您**&#x200B;更清楚瞭解哪些製造商最受您的使用者群歡迎。</p><p>**根據您瞭解到的內容，您可以**&#x200B;做許多事情，例如根據不同製造商的能力量身打造您的內容傳遞，以確保順暢的使用者體驗。</p><p>此範本使用行動製造商維度。 |

### 時間分段

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **分鐘小時**] | 檢視指定量度發生的分鐘（無條件舍去）。 第一個維度項目是日期範圍中的第一分鐘，最後一個維度項目是日期範圍中的最後一分鐘。 <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **小時** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **上午/下午** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **星期** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **日期** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **一年當中的第幾天** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **平日/週末** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **年周** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **月份** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **季別** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |

### 跨管道

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **多管道概觀**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **跨管道比較** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **呼叫中心偏轉（Web+呼叫中心）** | 檢視網路流量如何影響客服中心流量。<p>**這可協助您**&#x200B;更瞭解網站上的自助服務內容如何成功將流量導向您的客服中心。</p><p>**根據您所學到的內容，您可能**&#x200B;會執行許多動作，例如增強自助服務內容以降低客服中心的流量，或透過減少支援電話的節省金額來衡量自助服務內容的ROI。</p><p>此範本使用 |
| **網頁+應用程式** | 一起檢視網站流量和行動流量。<p>**這可協助您**&#x200B;更清楚瞭解您網站的網頁和行動流量分佈。</p><p>**根據您瞭解的情況，您可能**&#x200B;會做許多事情，例如當您的行動應用程式達到特定流量等級時，為您的行動應用程式體驗投入更多資源。</p><p>此範本使用 |
| **線上/離線** | 同時檢視線上和離線流量。<p>**這可協助您**&#x200B;更清楚瞭解您網站的線上和離線流量分佈。</p><p>**根據您的瞭解，您可能**&#x200B;會做許多事情，例如當您的線上體驗達到特定流量等級時，將更多資源專用於該體驗。</p><p>此範本使用 |

### 其他管道

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **客服中心儀表板**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **POS/離線** | 檢視銷售點(POS)和離線交易資料。<p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **電子郵件/AJO** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **調查** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |

### AJO

下列範本可供使用：

| 範本名稱 | 為何使用此範本<!-- What do you do with it? What can it help you learn? and What are the potential actions? --> |
| --- | --- | 
| [!UICONTROL **AJO行銷活動**] | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **AJO歷程** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **AJO登陸頁面** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **AJO概觀報告** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |
| **AJO訂閱** | <p>**這能協助您**&#x200B;更清楚瞭解</p><p>**根據您學到的內容，您可以**&#x200B;做任何事情，例如 </p><p>此範本使用 |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->
