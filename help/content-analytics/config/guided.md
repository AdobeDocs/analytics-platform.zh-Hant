---
title: 內容分析引導式設定
description: 如何使用入門引導式設定來設定內容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: ba386bf8055498ba1cecdd49890194dd2a7d69f9
workflow-type: tm+mt
source-wordcount: '3335'
ht-degree: 13%

---

# 內容分析引導式設定

{{draft-aca}}

{{release-limited-testing}}

引導式設定可幫助您快速輕鬆地設定內容分析。 引導式設定使用精靈來設定自動為組織設定內容分析的需求。 在&#x200B;**[!UICONTROL 設定]**&#x200B;畫面中，您可以建立新設定或編輯現有設定。

>[!IMPORTANT]
>
>您組織中的每個沙箱只能有一個內容分析設定。

若要存取Content Analytics設定

* 從Customer Journey Analytics的主功能表選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 內容分析]**。

在&#x200B;**[!UICONTROL Content Analytics設定]**&#x200B;畫面中，您會看到現有Content Analytics設定的表格。

![內容分析設定](../assets/aca-configuration-table.png)
對於每個設定，都提供下列詳細資訊：

| 欄 | 說明 |
|---|---|
| **[!UICONTROL 名稱]** | 設定的名稱。 |
| **[!UICONTROL 建立者]** | 建立設定的技術帳戶。 |
| **[!UICONTROL 建立於]** | 建立組態時的時間戳記。 |
| **[!UICONTROL 修改日期]** | 上次修改設定的時間戳記。 |
| **[!UICONTROL 沙箱]** | （計畫）設定及實作Content Analytics的組織內沙箱。 |
| **[!UICONTROL 狀態]** | 設定的狀態。 狀態可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：組態已儲存以供稍後使用，但未部署。<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL 失敗]**：組態失敗。 您需要編輯設定並進行必要的變更。<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**：組態已完成並已成功實作。 |

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)來自訂表格。 選取要在&#x200B;**[!UICONTROL 自訂表格]**&#x200B;對話方塊中顯示的資料行，並選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用變更。

從Content Analytics **[!UICONTROL 設定]**&#x200B;畫面，您可以建立新設定或編輯現有設定。

若要建立新組態：

* 選取&#x200B;**[!UICONTROL 建立組態]**。 此動作會開啟[引導式設定精靈](#guided-configuration-wizard)。

若要編輯現有組態，請執行下列動作：

* 選取現有Content Analytics組態的![更多](/help/assets/icons/More.svg)，然後選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。 此動作會開啟[引導式設定精靈](#guided-configuration-wizard)。

## 引導式設定精靈

引導式設定精靈包含四個區段（[詳細資料](#details)、[資料檢視](#data-view)、[體驗擷取與定義](#experience-capture-and-definition)以及[資料彙集](#data-collection)），每個區段都會提示您提供正確設定和設定Content Analytics所需的詳細資料。 請先完成每個區段，再移至下一個區段，因為區段中的部分設定可能取決於先前區段中的設定值。

### 詳細資料 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細資料"
>abstract="請提供連線的名稱。在「**[!UICONTROL 資料視圖]**」、「**[!UICONTROL 經驗擷取與定義]**」和「**[!UICONTROL 資料收集]**」區段中，您提供更多詳細資訊以確保可以正確設定 Content Analytics。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細資料"
>abstract="本指南會設定設定Content Analytics所需的需求。 請提供此設定的名稱"

<!-- markdownlint-enable MD034 -->

每個設定都需要唯一的名稱。 例如 `Example Content Analytics configuration`。需要名稱才能儲存或實施設定。

![內容分析組態詳細資料](../assets/aca-configuration-details.png)


### 資料視圖 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="資料視圖"
>abstract="如要設定 Content Analytics，您需選取一個現有的資料視圖。這樣您才可以將內容分析資料與其他資料合併。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="資料視圖"
>abstract="從 Customer Journey Analytics 中選取您想要與內容分析資料合併的現有資料視圖。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="資料視圖"
>abstract="從 Customer Journey Analytics 中選取您想要與內容分析資料合併的現有資料視圖。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新資料視圖"
>abstract="選擇新資料檢視會更新該資料檢視，使其包含Content Analytics量度和維度。 若有必要，相關連線也會更新並包括 Content Analytics 資料集。目前已針對 Content Analytics 進行設定的連線和資料視圖並未修改。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="清除所選的資料檢視"
>abstract="您已選取已針對Content Analytics布建的資料檢視。 該現有Content Analytics設定會被移除，且資料檢視會布建為您的新設定。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="清除先前的資料檢視"
>abstract="您已選取新的資料檢視。 先前選取資料檢視的Content Analytics設定已移除。"

<!-- markdownlint-enable MD034 -->

您的設定需要選取[資料檢視](/help/data-views/data-views.md)。

1. 選取資料檢視

   * 若要為組態選取新的資料檢視，請使用![資料](/help/assets/icons/Data.svg) **[!UICONTROL 選取資料檢視]**。

     ![資料檢視的內容分析設定](../assets/aca-configuration-dataview.png)

   * 若要修改組態的資料檢視，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。

     ![資料檢視的內容分析設定](../assets/aca-configuration-dataview-edit.png)


   在這兩種情況下，您會看到&#x200B;**[!UICONTROL 資料檢視]**&#x200B;對話方塊，您可以在此選取您設定的資料檢視。

   資料檢視的![Content Analytics設定 — 資料檢視表](../assets/aca-configuration-dataview-dialog.png)

   對於新設定，清單僅顯示與沒有作用中設定的沙箱關聯的資料檢視。

   如果您編輯現有設定，清單只會顯示沙箱中現有的資料檢視（已與現有設定關聯）。

   您可以執行下列動作：

   * 若要搜尋特定資料檢視，請使用![搜尋](/help/assets/icons/Search.svg)欄位。
   * 若要篩選可用的資料檢視清單，請選取![顯示篩選器](/help/assets/icons/Filter.svg)。 您可以篩選[!UICONTROL 連線]、[!UICONTROL 擁有者]和[!UICONTROL 沙箱]上的清單。<br/>使用![隱藏](/help/assets/icons/Filter.svg) **[!UICONTROL 隱藏篩選器]**&#x200B;來隱藏篩選器窗格。
   * 若要定義要在表格中顯示哪些欄，請選取![欄設定](/help/assets/icons/ColumnSetting.svg)。 選取要在&#x200B;**[!UICONTROL 自訂表格]**&#x200B;對話方塊中顯示的資料行，並選取&#x200B;**[!UICONTROL 套用]**&#x200B;以套用變更。

1. 選取![SelectBox](/help/assets/icons/SelectBox.svg)您要使用的資料檢視。
1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以確認選取的資料檢視。 選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消。


在Customer Journey Analytics中，資料檢視已繫結至Customer Journey Analytics [連線](/help/connections/overview.md)。 而連線是以您組織內的沙箱為基礎。 儲存設定後，**[!UICONTROL 沙箱]**&#x200B;會根據選取的資料檢視，自動填入沙箱的名稱。


### 經驗擷取與定義 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="經驗擷取與定義"
>abstract="您可以選取在使用 Content Analytics 收集的資料中包含體驗。選取時，您必須定義一個或多個正則表達式和查詢參數的組合，以定義您想要包含的體驗 URL。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="經驗擷取與定義"
>abstract="收集 Content Analytics 中的體驗"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="經驗擷取與定義"
>abstract="指定決定如何在網站上呈現內容的引數。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="經驗擷取與定義"
>abstract="您可以在與目前設定相關聯的Tags屬性中，編輯Adobe Content Analytics擴充功能中的設定。"

<!-- markdownlint-enable MD034 -->

在此區段中，您可以選取將體驗包含在透過Content Analytics收集的資料中。  體驗是指網頁上的所有文字，這些文字都可以使用造訪該網頁的初始使用者所使用的URL來重現。

依預設，**[!UICONTROL 包含體驗]**&#x200B;已關閉。 選取後，您必須定義要包含體驗的URL。

只有符合下列條件時，才考慮加入體驗：

* 您只能使用公開的URL來存取網站內容。 存取網站不需要個人化的Token、Cookie或無法透過URL取得的其他機制。
* 網站上的頁面必須使用頁面URL可複製。

若要在新的或未實施的設定中包含體驗：

![Content Analytics組態體驗擷取與定義](../assets/aca-configuration-experience.png)

1. 啟用&#x200B;**[!UICONTROL 包含體驗]**。
1. 選擇性。 指定在您的網站上呈現內容的方式引數。 引數是&#x200B;**[!UICONTROL 網域規則運算式]**&#x200B;和&#x200B;**[!UICONTROL 查詢引數]**&#x200B;的零個或多個組合。
   1. 輸入&#x200B;**[!UICONTROL 網域規則運算式]**，例如`/^(?!.*\b(store|help|admin)\b)/`。 使用`/`確保您逸出規則運算式。
   1. 指定&#x200B;**[!UICONTROL 查詢引數]**&#x200B;的逗號分隔清單，例如`outdoors, patio, kitchen`。
1. 如果要移除網域規則運算式和查詢引數的組合，請選取&#x200B;**[!UICONTROL 移除]**。
1. 如果要新增其他規則運算式和查詢參陣列合，請選取&#x200B;**[!UICONTROL 新增Regex]**。

若要編輯已實作組態中的現有體驗或包含新體驗：

![Content Analytics組態體驗擷取與定義](../assets/aca-configuration-experience-edit.png)

* 選取「![編輯](/help/assets/icons/Edit.svg)」**[!UICONTROL 「編輯]**」以編輯Content Analytics中收集體驗的設定。 系統會將您重新導向至與目前設定相關聯之Tags屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。




### 資料收集 {#onboarding-data-collection}

在本節中，您將設定如何收集內容分析資料。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="資料收集"
>abstract="定義您要使用的標籤屬性，或建立新的標籤屬性。 並且使用規則運算式定義想要包括或排除的頁面和資產。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="資料收集"
>abstract="**提供Tags屬性**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="資料收集"
>abstract="**要包含/排除的頁面**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="資料收集"
>abstract="在收集 Content Analytics 資料時，指明應&#x200B;**包含**&#x200B;或&#x200B;**排除**&#x200B;哪些頁面"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="資料收集"
>abstract="**要包含/排除的資產**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="資料收集"
>abstract="在收集 Content Analytics 資料時，指明應&#x200B;**包含**&#x200B;或&#x200B;**排除**&#x200B;哪些資產"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="資料收集"
>abstract="在與目前設定相關聯的Tags屬性中，您可以在Adobe Content Analytics擴充功能中編輯頁面的設定。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="資料收集"
>abstract="您可在與目前設定相關聯的Tags屬性中，編輯Adobe Content Analytics擴充功能中的資產設定。"

<!-- markdownlint-enable MD034 -->

#### 新設定 {#new-configuration}

在新設定中，您需要定義您是要使用現有的標籤屬性還是建立新的標籤屬性。 而且您需要使用規則運算式定義要包含或排除的頁面和資產。

* 若要使用現有的Tags屬性：

  ![Content Analytics資料收集現有標籤](../assets/aca-configuration-datacollection-existingtag.png)

   1. 選取&#x200B;**[!UICONTROL 選擇現有的]**。
   2. 從&#x200B;**[!UICONTROL 標籤屬性]**&#x200B;下拉式功能表中選取現有屬性。 您可以開始輸入以搜尋並限制可用選項。

* 若要建立新的Tags屬性：

  ![Content Analytics資料收集新標籤](../assets/aca-configuration-datacollection-newtag.png)

   1. 選取&#x200B;**[!UICONTROL 新建]**。
   1. 指定&#x200B;**[!UICONTROL 標籤名稱]**，例如`ACA Test for Documentation`。
   1. 指定&#x200B;**[!UICONTROL 網域]**，例如`example.com`。

* 如果您已選取納入體驗，請指出在收集內容分析的資料時應納入或排除哪些頁面。

   * 指定&#x200B;**[!UICONTROL 頁要包含/排除]**&#x200B;的規則運算式字串。 例如： `/^(?!.*documentation).*/`從Content Analytics排除所有檔案頁面。 使用`/`確保您逸出規則運算式。

* 指示在收集內容分析的資料時應包含或排除哪些資產。

   * 指定&#x200B;**[!UICONTROL Assets要包含/排除]**&#x200B;的規則運算式字串。 例如： `/^(?!.*(logo\.jpg|\.svg)).*$/`從Content Analytics排除所有標誌JPEG和SVG影像。 使用`/`確保您逸出規則運算式。


#### 現有設定 {#existing-configuration}

若為現有設定，則無法編輯Tags屬性。 但是，您可以編輯頁面和資產以包含或排除。

* 若要編輯在收集內容分析資料時應包含或排除哪些頁面，請在&#x200B;**[!UICONTROL 體驗]**&#x200B;下方選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。 系統會將您重新導向至與目前Adobe Content Analytics設定的Tags屬性相關聯的[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以編輯規則運算式，以包含或排除頁面。 請確定您[發佈](#publish)您的變更。

* 若要編輯在收集內容分析資料時應包含或排除哪些資產，請選取&#x200B;**[!UICONTROL 資產]**&#x200B;下方的![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。 系統會將您重新導向至與目前Adobe Content Analytics設定的Tags屬性相關聯的[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering)。 您可以編輯規則運算式，以包含或排除資產。 請確定您[發佈](#publish)您的變更。

### 摘要 {#summary}

提供所有必要的詳細資訊後，摘要會提供已建立或修改之人工因素的詳細資訊。

* 當您實作新設定時，您會看到&#x200B;**[!UICONTROL 您幾乎已準備好為內容分析]**&#x200B;摘要實作&#x200B;_設定名稱_。

* 若為現有的實作組態，您會看到&#x200B;**[!UICONTROL 您已為內容分析]**&#x200B;摘要實作&#x200B;_組態名稱_。

![Content Analytics設定摘要](../assets/aca-configuration-summary.png)

### 動作 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="確認實作"
>abstract="如果您選取「**[!UICONTROL 實作]**」，將會根據您在此工作流程中提供的輸入來設定 Content Analytics。根據對Content Analytics通常有用的內容，預設會選擇數個設定，但您（作為資料控管單位）必須檢閱每個成品的設定，以確認這些設定是否根據您的隱私權原則、合約權利與義務，以及適用法律下的同意要求實施。<br/><br/>請注意，您必須先手動發佈與這個設定相關聯的標記庫，才能開始收集資料。<br/><br/>為了衍生影像和文字的屬性，Adobe會使用下列方式擷取屬性：<ol><li>根據您已設定的資料收集設定，在使用者瀏覽網站時擷取的URL，以及</li><li>託管影像的 URL。</li></ol>您不可以標記託管在第三方網站上的影像。"

<!-- markdownlint-enable MD034 -->

當您已建立或編輯組態時，可以使用下列動作。

* **[!UICONTROL 捨棄]**：建立新組態或編輯現有組態時所做的所有變更都會被捨棄。
* **[!UICONTROL 儲存以供稍後使用]**：會儲存對新的組態或現有、尚未實作的組態所做的變更。 您可在稍後階段重新造訪設定，以進一步變更或實施設定。
* **[!UICONTROL 實作]**：儲存並實作新組態或現有但尚未實作的組態的設定或變更。 實施包含：

   * **[!UICONTROL Customer Journey Analytics]**&#x200B;設定：
      * 選取的資料檢視已更新，其中包含Content Analytics維度和量度。
      * 繫結至所選資料檢視的連線已修改，以包含Content Analytics事件和屬性資料集。
      * 「內容分析」報告範本已新增至Workspace。

+++ 詳細資料

     詳細說明以下情境：

      * **標籤**&#x200B;屬性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags屬性的&#x200B;**網頁SDK**&#x200B;延伸存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag屬性的Adobe **Content Analytics**&#x200B;延伸模組存在&#x200B;**✓**，或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">情境：</th>
      </tr>
      <tr>
        <th>
          <strong>設定</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕標籤<br>✕Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td>報告範本</td>
          <td colspan="4">報表範本可供使用</td>
        </tr>
        <tr>
          <td>資料視圖</td>
          <td colspan="4">修改/建立以包含ACA維度和量度</td>
        </tr>
        <tr>
          <td>連線</td>
          <td colspan="4">修改為包含ACA資料集(ACA事件、資產屬性、體驗屬性)</td>
        </tr>
      </tbody>
    </table>

+++

   * **[!UICONTROL Adobe Experience Platform]**&#x200B;設定：
      * 建立結構描述以建立Content Analytics事件、資產屬性和（如果已設定）體驗屬性的模型。
      * 建立資料集以收集Content Analytics事件、資產屬性和（如果已設定）體驗屬性。
      * 建立資料流，使用功能化服務從Content Analytics事件產生和更新內容屬性。

+++ 詳細資料

     詳細說明以下情境：

      * **標籤**&#x200B;屬性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags屬性的&#x200B;**網頁SDK**&#x200B;延伸存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag屬性的Adobe **Content Analytics**&#x200B;延伸模組存在&#x200B;**✓**，或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">情境：</th>
      </tr>
      <tr>
        <th>
          <strong>設定</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕標籤<br>✕Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics事件結構描述</strong></td>
        </tr>
        <tr>
          <td style="margin-left: 160.0px;">名稱</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics事件資料集</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>結構描述</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
          <td>Content Analytics事件</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>標記</td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
        </tr>
        <tr>
          <td>系統資料集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>資料控管（DULE標籤）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics資產屬性結構</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Assets屬性資料集</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
        </tr>
        <tr>
          <td>結構描述</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
          <td>Content Analytics資產屬性</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>標記</td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
        </tr>
        <tr>
          <td>系統資料集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>資料控管（DULE標籤）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics體驗屬性結構</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics體驗屬性資料集</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
        </tr>
        <tr>
          <td>結構描述</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
          <td>Content Analytics體驗屬性</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
          <td><i>預先決定的待定</i></td>
        </tr>
        <tr>
          <td>標記</td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
          <td><i>空白？</i></td>
        </tr>
        <tr>
          <td>系統資料集</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>設定檔已啟用</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
          <td>否</td>
        </tr>
        <tr>
          <td>資料控管（DULE標籤）</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
      </tbody>
    </table>

+++

   * **[!UICONTROL 資料彙集]**&#x200B;組態：
      * 新的或現有的標籤屬性已設定為支援Content Analytics資料收集。 此設定表示包含標籤的Adobe Content Analytics擴充功能。
      * 系統會為內容分析事件建立資料流。
      * Adobe Content Analytics擴充功能已設定為確保Content Analytics事件傳送至Content Analytics的資料流。
      * 如果沒有為Tags屬性設定Web SDK，則會建立新的Web SDK設定，以便僅傳送Content Analytics事件。
      * 如果針對此標籤屬性設定了網頁SDK，則不會對現有的網頁SDK設定進行任何變更。

+++ 詳細資料

     詳細說明以下情境：

      * **標籤**&#x200B;屬性存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tags屬性的&#x200B;**網頁SDK**&#x200B;延伸存在&#x200B;**✓**&#x200B;或不存在&#x200B;**✕**。
      * Tag屬性的Adobe **Content Analytics**&#x200B;延伸模組存在&#x200B;**✓**，或不存在&#x200B;**✕**。

     <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">情境：</th>
      </tr>
      <tr>
        <th>
          <strong>設定</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✓Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓標籤<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕標籤<br>✕Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>資料流</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td><i>現有值</i></td>
          <td>內容分析</td>
          <td>內容分析</td>
          <td>內容分析</td>
        </tr>
        <tr>
          <td>說明</td>
          <td><i>現有值</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
        </tr>
        <tr>
          <td>對應結構描述</td>
          <td><i>現有值</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
        </tr>
        <tr>
          <td>地理位置與網路查詢</td>
          <td><i>現有值</i></td>
          <td>關閉所有選項</td>
          <td>關閉所有選項</td>
          <td>關閉所有選項</td>
        </tr>
        <tr>
          <td>裝置查詢</td>
          <td><i>現有值</i></td>
          <td>不要收集任何裝置資訊</td>
          <td>不要收集任何裝置資訊</td>
          <td>不要收集任何裝置資訊</td>
        </tr>
        <tr>
          <td>IP 模糊化</td>
          <td><i>現有值</i></td>
          <td>無</td>
          <td>無</td>
          <td>無</td>
        </tr>
        <tr>
          <td>第一方ID Cookie</td>
          <td><i>現有值</i></td>
          <td>關閉</td>
          <td>關閉</td>
          <td>關閉</td>
        </tr>
        <tr>
          <td>協力廠商ID同步</td>
          <td><i>現有值</i></td>
          <td>關閉</td>
          <td>關閉</td>
          <td>關閉</td>
        </tr>
        <tr>
          <td>存取型別</td>
          <td><i>現有值</i></td>
          <td>混合驗證</td>
          <td>混合驗證</td>
          <td>混合驗證</td>
        </tr>
        <tr>
          <td>媒體分析</td>
          <td><i>現有值</i></td>
          <td>關閉</td>
          <td>關閉</td>
          <td>關閉</td>
        </tr>
            <tr>
          <td>機器人偵測</td>
          <td><i>現有值</i></td>
          <td>關閉</td>
          <td>關閉</td>
          <td>關閉</td>
        </tr>
        <tr>
          <td>映射</td>
          <td><i>現有值</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>標籤屬性</strong><br/>現有屬性或新屬性。 名稱和網域由使用者提供。</td>
        </tr>
        <tr>
          <td>名稱</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td><i>已提供使用者</i> (預設為「Content Analytics」)</td>
        </tr>
        <tr>
          <td>網域</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td ><i>預定</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>標籤資料庫</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>
            <br/>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Web SDK擴充功能</strong></td>
        </tr>
        <tr>
          <td>名稱</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>Content Analytics — 網頁SDK</td>
          <td>Content Analytics — 網頁SDK</td>
        </tr>
        <tr>
          <td>IMS組織</td>
          <td><i>自動填入</i></td>
          <td><i>自動填入</i></td>
          <td><i>自動填入</i></td>
          <td><i>自動填入</i></td>
        </tr>
        <tr>
          <td>邊緣網域</td>
          <td><i>現有值<br/>可能需要更新以符合AppMeasurement實作</i></td>
          <td><i>現有值<br/>可能需要更新以符合AppMeasurement實作</i></td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>資料流</strong></td>
        </tr>
        <tr>
          <td>生產</td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>使用者已提供</i>？</td>
          <td><i>使用者已提供</i>？</td>
        </tr>
        <tr>
          <td>預備</td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>使用者已提供</i>？</td>
          <td><i>使用者已提供</i>？</td>
        </tr>
        <tr>
          <td>開發</td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>現有值<br/>用來傳送至不同資料流的資料流覆寫</i></td>
          <td><i>使用者已提供</i>？</td>
          <td><i>使用者已提供</i>？</td>
        </tr>
        <tr>
          <td>隱私權</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>在？</td>
          <td>在？</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>身分識別</strong></td>
        </tr>
        <tr>
          <td>移轉ECID</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>已核取</td>
          <td>已核取</td>
        </tr>
        <tr>
          <td>使用第三方Cookie</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>已核取</td>
          <td>已核取</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>個人化</strong></td>
        </tr>
        <tr>
          <td>將Target從at.js移轉至Web SDK</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>未勾選</td>
          <td>未勾選</td>
        </tr>
        <tr>
          <td>啟用個人化儲存</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>未勾選</td>
          <td>未勾選</td>
        </tr>
        <tr>
          <td>Adobe Journey Optimizer的自動點選集合</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>一律</td>
          <td>一律</td>
        </tr>
        <tr>
          <td>Adobe Target的自動點選集合</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>從不</td>
          <td>從不</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>資料收集</strong></td>
        </tr>
        <tr>
          <td>收集內部連結點按次數</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>未勾選</td>
          <td>未勾選</td>
        </tr>
        <tr>
          <td>收集外部連結點按次數</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>未勾選</td>
          <td>未勾選</td>
        </tr>
        <tr>
          <td>收集下載連結點按次數</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>未勾選</td>
          <td>未勾選</td>
        </tr>
        <tr>
          <td>傳送事件資料時，自動包含</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>所有預設內容資訊</td>
          <td>所有預設內容資訊</td>
        </tr>
        <tr>
          <td>串流媒體</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>空白值</td>
          <td>空白值</td>
        </tr>
        <tr>
          <td>資料流設定覆寫</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>符合資料流設定</td>
          <td>符合資料流設定</td>
        </tr>
        <tr>
          <td>進階設定 — Edge基本路徑</td>
          <td><i>現有值</i></td>
          <td><i>現有值</i></td>
          <td>ee</td>
          <td>ee</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics擴充功能</strong></td>
        </tr>
        <tr>
          <td>資料流</td>
          <td><i>現有值</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
          <td><i>預定</i></td>
        </tr>
        <tr>
          <td>體驗擷取與定義</td>
          <td><i>現有值</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
        </tr>
        <tr>
          <td>事件篩選</td>
          <td><i>現有值</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
          <td><i>使用者提供</i></td>
        </tr>
      </tbody>
    </table>

+++

* **[!UICONTROL 儲存]**：對實作組態所做的變更已儲存，且實作已更新。
* **[!UICONTROL 結束]**。 退出引導式設定。 會捨棄對實作組態所做的所有變更。


## 發佈 {#publish}

若要啟用您的Content Analytics設定，您必須[手動](manual.md)發佈在您選取&#x200B;**[!UICONTROL 實作]**&#x200B;之後建立的Tags屬性。


>[!MORELIKETHIS]
>
>[手動設定](manual.md)
>
