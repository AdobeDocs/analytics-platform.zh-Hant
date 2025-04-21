---
title: Content Analytics 引導式設定
description: 如何使用上線引導式設定來進行 Content Analytics 的設定
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 46%

---

# Content Analytics 引導式設定

{{release-limited-testing}}


引導式設定可協助您快速輕鬆地設定 Content Analytics。引導式設定會使用精靈來設定要求，可為您的組織自動設定 Content Analytics。在「**[!UICONTROL 設定]**」畫面上，您可以建立新設定或編輯現有設定。

>[!IMPORTANT]
>
>您組織中每個沙箱只能有一個 Content Analytics 設定。

存取 Content Analytics 設定

* 從Customer Journey Analytics的主功能表選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL Content Analytics設定]**。

在&#x200B;**[!UICONTROL Content Analytics設定]**&#x200B;畫面中，您會看到現有Content Analytics設定的表格。

![Content Analytics 設定](../assets/aca-configuration-table.png)
每個設定都提供以下詳細資訊：

| 欄 | 說明 |
|---|---|
| **[!UICONTROL 名稱]** | 設定的名稱。 |
| **[!UICONTROL 建立者]** | 建立設定的技術帳戶。 |
| **[!UICONTROL 建立日期]** | 建立設定時的時間戳記。 |
| **[!UICONTROL 修改日期]** | 上次修改設定時的時間戳記。 |
| **[!UICONTROL 沙箱]** | 組織內的沙箱，其中已經 (預計) 設定並已經 (預計) 實施 Content Analytics。 |
| **[!UICONTROL 狀態]** | 設定的狀態。狀態可以是：<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL 草稿]**：組態已儲存以供稍後使用，但未部署。<br/>![狀態紅色](/help/assets/icons/StatusRed.svg)**[!UICONTROL 失敗]**：設定失敗。您可以選取&#x200B;**[!UICONTROL 編輯]**&#x200B;以取得失敗的相關資訊。 Adobe會主動處理任何失敗的實作。 如需詳細資訊，請聯絡客戶服務。<br/>![狀態綠色](/help/assets/icons/StatusGreen.svg)**[!UICONTROL 完成]**：設定已完成並成功實施。 |

您可以使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 來自訂表格。選取「**[!UICONTROL 自訂表格]**」對話框中顯示哪些欄，然後選取「**[!UICONTROL 套用]**」以套用變更。

在 Content Analytics **[!UICONTROL 設定]**&#x200B;畫面中，您可以建立新設定或編輯現有設定。

建立新設定：

* 選取「**[!UICONTROL 建立設定]**」。此動作會開啟[引導式設定精靈](#guided-configuration-wizard)。

編輯現有設定：

* 選取「![更多](/help/assets/icons/More.svg)」，然後選取「![編輯](/help/assets/icons/Edit.svg)」來&#x200B;**[!UICONTROL 編輯]** 現有 Content Analytics 設定。此動作會開啟[引導式設定精靈](#guided-configuration-wizard)。

## 引導式設定精靈

引導式設定精靈包含四個區段（[詳細資料](#details)、[資料檢視](#data-view)、[體驗擷取與定義](#experience-capture-and-definition)以及[資料彙集](#data-collection)），每個區段都會提示您提供正確設定和設定Content Analytics所需的詳細資料。 在轉到下一部分之前，請先完成每個部分，因為部分中的某些設定可能取決於前面部分中的配置值。

### 詳細資料 {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="詳細資料"
>abstract="請提供連線的名稱。在「**[!UICONTROL 資料視圖]**」、「**[!UICONTROL 經驗擷取與定義]**」和「**[!UICONTROL 資料收集]**」區段中，您提供更多詳細資訊以確保可以正確設定 Content Analytics。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="詳細資料"
>abstract="此指南會設定所需需求，以設定 Content Analytics。請提供此設定的名稱"

<!-- markdownlint-enable MD034 -->

每個設定都需要一個唯一的名稱。例如 `Example Content Analytics configuration`。需要名稱才能儲存或實施設定。

![Content Analytics 設定詳細資訊](../assets/aca-configuration-details.png)


### 資料檢視 {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="資料檢視"
>abstract="如要設定 Content Analytics，您需選取一個現有的資料視圖。這樣您才可以將內容分析資料與其他資料合併。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="資料檢視"
>abstract="從 Customer Journey Analytics 中選取您想要與內容分析資料合併的現有資料視圖。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="資料檢視"
>abstract="從 Customer Journey Analytics 中選取您想要與內容分析資料合併的現有資料視圖。<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="新資料檢視"
>abstract="選取新的資料視圖會導致更新該資料視圖，以包括 Content Analytics 量度和維度。若有必要，相關連線也會更新並包括 Content Analytics 資料集。目前已針對 Content Analytics 進行設定的連線和資料視圖並未修改。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="清除所選的資料檢視"
>abstract="您已選取已針對Content Analytics布建的資料檢視。 該現有Content Analytics設定會被移除，且資料檢視會布建為您的新設定。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="清除先前的資料檢視"
>abstract="您已選取一個新的資料視圖。先前選取資料檢視的Content Analytics設定已移除。"

<!-- markdownlint-enable MD034 -->

您的設定需要選擇[資料檢視](/help/data-views/data-views.md)。

1. 選取資料檢視

   * 若要選取組態的新資料檢視，請使用![資料](/help/assets/icons/Data.svg) **[!UICONTROL 選取資料檢視]**。

     資料檢視的![Content Analytics設定](../assets/aca-configuration-dataview.png)

   * 若要修改組態的資料檢視，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。

     資料檢視的![Content Analytics設定](../assets/aca-configuration-dataview-edit.png)


   在這兩種情況下，您會看到&#x200B;**[!UICONTROL 資料檢視]**&#x200B;對話方塊，您可以在其中選取您設定的資料檢視。

   ![資料檢視的Content Analytics設定 — 資料檢視表](../assets/aca-configuration-dataview-dialog.png)

   對於新設定，清單僅顯示與沒有作用中設定的沙箱關聯的資料檢視。 此外，您只會看到與您可存取的沙箱關聯的資料檢視，以及您有權修改的連線。

   如果您編輯現有設定，清單只會顯示沙箱中可用的資料檢視，而這些沙箱已與現有設定關聯。

   您可以執行下列動作：

   * 若要搜尋特定資料檢視，請使用![搜尋](/help/assets/icons/Search.svg)欄位。
   * 若要將可用資料檢視清單分段，請選取![顯示區段](/help/assets/icons/Filter.svg)。 您可以篩選[!UICONTROL 連線]、[!UICONTROL 擁有者]和[!UICONTROL 沙箱]上的清單。<br/>使用![隱藏](/help/assets/icons/Filter.svg) **[!UICONTROL 隱藏區段]**&#x200B;來隱藏區段窗格。
   * 若要定義在表格中顯示哪些欄，請選取「![欄設定](/help/assets/icons/ColumnSetting.svg)」。選取「**[!UICONTROL 自訂表格]**」對話框中顯示哪些欄，然後選取「**[!UICONTROL 套用]**」以套用變更。

1. 選取![SelectBox](/help/assets/icons/SelectBox.svg)您要使用的資料檢視。
1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以確認選取的資料檢視。 選取「**[!UICONTROL 取消]**」，即可取消。


在Customer Journey Analytics中，[資料檢視](/help/data-views/data-views.md)已繫結至Customer Journey Analytics [連線](/help/connections/overview.md)。 而且連線是以您組織內的沙箱為基礎。 儲存設定後，**[!UICONTROL 沙箱]**&#x200B;欄位會根據選取的資料檢視，自動填入沙箱的名稱。


### 經驗擷取與定義 {#onboarding-experiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="經驗擷取與定義"
>abstract="您可以選擇將體驗包含在您透過Content Analytics收集的資料中。 選取時，您必須定義一個或多個正則表達式和查詢參數的組合，以定義您想要包含的體驗 URL。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="經驗擷取與定義"
>abstract="在內容分析中收集體驗"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="經驗擷取與定義"
>abstract="指定用於判斷內容在網站上如何轉譯的參數。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_new_include_experiences"
>title="經驗擷取與定義"
>abstract="啟用後，系統會收集體驗資料、產生體驗屬性，並提供體驗報表。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_include_experiences"
>title="經驗擷取與定義"
>abstract="啟用後，系統會收集體驗資料、產生體驗屬性，並提供體驗報表。 <br><br/>使用![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]**&#x200B;修改與目前組態關聯之Tags屬性中體驗的資料收集組態。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="經驗擷取與定義"
>abstract="您必須在Adobe Content Analytics擴充功能中編輯體驗資料收集的設定。"

<!-- markdownlint-enable MD034 -->

在此區段中，您可以選取將體驗包含在您透過Content Analytics收集的資料中。  體驗是網頁上的所有內容，可以使用初始使用者造訪該網頁時使用的 URL 進行複製。

依預設，**[!UICONTROL 包含體驗]**&#x200B;為關閉狀態。選取後，您必須定義要包含體驗的 URL。

只有符合下列條件時，才考慮加入體驗：

* 網站上的頁面必須使用頁面URL可複製。
* 任何指定使用者看到的文字內容都可以使用頁面URL重現，而不取決於Cookie或其他個人化機制。

>[!IMPORTANT]
>
>實作[Content Analytics版本設定](manual.md#versioning)以收集您對體驗（頁面）所做的變更以使其遵循Content Analytics。



#### 新增設定 {#new-experiences-configuration}

若要將體驗納入新的或未實施的設定：

![Content Analytics 設定體驗擷取與定義](../assets/aca-configuration-experience.png)

1. 啟用&#x200B;**[!UICONTROL 包含體驗]**。 啟用體驗的切換會影響下列專案：

   * Content Analytics擴充功能中的資料收集
   * 從Content Analytics事件資料產生體驗屬性的程式
   * Customer Journey Analytics中的報表範本。

1. 指定在您的網站上呈現內容方式的引數。 引數是&#x200B;**[!UICONTROL 網域規則運算式]**&#x200B;和&#x200B;**[!UICONTROL 查詢引數]**&#x200B;的零個或多個組合。 查詢引數會指出哪些引數會影響頁面上的內容。 此輸入可讓Content Analytics在定義唯一體驗時，忽略不會影響頁面內容的任何引數。
   1. 輸入&#x200B;**[!UICONTROL 網域規則運算式]**，例如`/^(?!.*\b(store|help|admin)\b)/`。 使用`/`確保您逸出規則運算式。 網域規則運算式會指出這些引數適用的URL。 例如，您可能有多個網站，每個網站的不同引數會驅動內容。 如果查詢引數套用至您的所有頁面，則可以使用`.*`來指示所有頁面。
   1. 指定以逗號分隔的&#x200B;**[!UICONTROL 查詢參數清單，]**&#x200B;例如`outdoors, patio, kitchen`。
1. 如果要刪除網域規則運算式和查詢參數的組合，請選取「**[!UICONTROL 刪除]**」。
1. 如果要新增其他規則運算式和查詢參陣列合，請選取&#x200B;**[!UICONTROL 新增Regex]**。


#### 實作設定 {#implemented-experiences-configuration}

若要在實作組態中編輯現有體驗或包含新體驗：

![Content Analytics組態體驗擷取與定義](../assets/aca-configuration-experience-edit.png)

* 切換&#x200B;**[!UICONTROL 包含體驗]**&#x200B;以啟用或停用：

   * 從Content Analytics事件資料產生體驗屬性的程式
   * Customer Journey Analytics中的報表範本。

* 選取「![編輯](/help/assets/icons/Edit.svg)」**[!UICONTROL 「編輯]**」以進一步編輯Content Analytics中體驗的資料收集組態。 系統會將您重新導向至與目前設定相關聯之Tags屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。


### 資料收集 {#onboarding-data-collection}

在本節中，您將設定如何收集內容分析資料。

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="資料收集"
>abstract="定義您要使用的標記屬性，或建立一個新屬性。並且使用規則運算式定義想要包括或排除的頁面和資產。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="資料收集"
>abstract="**提供標記屬性**"

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
>abstract="您可以在頁面設定，使用目前設定相關的 Adobe Content Analytics 擴充功能設定。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="資料收集"
>abstract="您可以在資產設定，使用目前設定相關的 Adobe Content Analytics 擴充功能設定。"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tags_disabled_description "
>title="標記屬性已停用"
>abstract="Content Analytics 擴充功能已經啟用。"

<!-- markdownlint-enable MD034 -->

#### 新增設定 {#new-configuration}

在新設定中，您需要定義您是要使用現有的標籤屬性還是建立新的標籤屬性。 同時，您需要使用規則運算式定義想要包括或排除的頁面和資產。

* 若要使用現有的Tags屬性：

  ![Content Analytics 資料彙集現有標記](../assets/aca-configuration-datacollection-existingtag.png)

   1. 選取&#x200B;**[!UICONTROL 選擇現有的]**。
   2. 從&#x200B;**[!UICONTROL 標籤屬性]**&#x200B;下拉式功能表中選取現有屬性。 您可以開始輸入以搜尋並限制可用選項。 您無法選取已由其他實作Content Analytics設定使用的Tags屬性。


* 若要建立新的Tags屬性：

  ![Content Analytics 資料彙集新標記](../assets/aca-configuration-datacollection-newtag.png)

   1. 選取「**[!UICONTROL 新建]**」。
   1. 指定&#x200B;**[!UICONTROL 標籤名稱]**，例如`ACA Test for Documentation`。
   1. 指定「**[!UICONTROL 網域]**」，例如 `example.com`。

* 指示在收集Content Analytics的資料時應包含或排除哪些頁面。

  指定&#x200B;**[!UICONTROL 頁要包含/排除]**&#x200B;的規則運算式字串。 <br/>例如： `^(?!.*documentation).*`從Content Analytics排除所有檔案頁面。

* 在收集 Content Analytics 資料時，指明應包含或排除哪些資產。

  指定&#x200B;**[!UICONTROL Assets要包含/排除]**&#x200B;的規則運算式字串。 <br/>例如： `^(?!.*(logo\.jpg|\.svg)).*$`從Content Analytics排除所有標誌JPEG和SVG影像。

>[!IMPORTANT]
>
>手動從新建立的Tags屬性中移除自動包含的Web SDK擴充功能，以備您有使用[JavaScript資料庫](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/library)而非[Tags擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)的現有Web SDK實作。
>



#### 現有設定 {#existing-configuration}

若為現有設定，則無法編輯Tags屬性。 但是，您可以編輯要包含或排除的頁面和資產。

* 若要編輯在收集內容分析資料時應包含或排除哪些頁面，請在&#x200B;**[!UICONTROL 體驗]**&#x200B;下方選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。 系統會將您重新導向至與目前Adobe Content Analytics設定的Tags屬性相關聯的[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。 您可以編輯規則運算式，以包含或排除頁面。 請確定您[發佈](#publish)您的變更。

* 若要編輯在收集內容分析資料時應包含或排除哪些資產，請選取&#x200B;**[!UICONTROL 資產]**&#x200B;下方的![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。 系統會將您重新導向至與目前Adobe Content Analytics設定的Tags屬性相關聯的[Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting)。 您可以編輯規則運算式，以包含或排除資產。 請確定您[發佈](#publish)您的變更。

### 摘要 {#summary}

提供所有必要的詳細資訊後，摘要會提供已建立或修改之人工因素的詳細資訊。

* 當您實施新設定時，您會看到&#x200B;**[!UICONTROL 您幾乎已準備好實施 _Content Analytics 的設定名稱_]**&#x200B;摘要。

* 對於已實施的配置，您會看到 **[!UICONTROL 您已實施 _配置名稱_ 用於 Content Analytics]** 概括。

![Content Analytics 設定摘要](../assets/aca-configuration-summary.png)

### 動作 {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="確認實作"
>abstract="如果您選取「**[!UICONTROL 實作]**」，將會根據您在此工作流程中提供的輸入來設定 Content Analytics。系統會預設為根據一般適用於 Content Analytics 的情況選擇若干設定，但是您 (作為資料控管方) 必須檢視每個成品的設定，以確認所實作的設定均遵守您的隱私權原則、合約權利與義務，以及適用法律規定的同意要求。<br/><br/>請注意，必須先手動發佈與這個設定相關聯的標籤庫，才能開始收集資料。<br/><br/>為了衍生影像和文字的屬性，Adobe 會使用以下方式獲得屬性：<ol><li>根據已設定的資料收集設定，在使用者造訪網站時所擷取的 URL，以及</li><li>託管影像的 URL。</li></ol>您不可以標記託管在第三方網站上的影像。"

<!-- markdownlint-enable MD034 -->

當您建立或編輯組態時，您有以下選項：

* **[!UICONTROL 捨棄]**：會捨棄所有在設定中所做的變更。
* **[!UICONTROL 儲存以供稍後使用]**：已儲存對組態所做的變更。 您可在稍後階段重新造訪設定，以進一步變更或實施設定。 儲存組態只需要有[!UICONTROL Name]的值。
* **[!UICONTROL 實作]**：已儲存並實作組態的設定或變更。 所有標示為![必要](/help/assets/icons/Required.svg)的欄位都必須有適當的值。 實施包括：

   * **[!UICONTROL Customer Journey Analytics]** 設定：
      * 所選的資料檢視已更新，其中包含Content Analytics維度和量度。
      * 已修改與所選資料檢視關聯的連線，以包含Content Analytics事件和屬性資料集。
      * 「內容分析」報告範本已新增至Workspace。


   * **[!UICONTROL Adobe Experience Platform]** 設定：
      * 建立結構描述來模擬 Content Analytics 事件、設定資產屬性和 (如果已設定) 體驗屬性。
      * 建立資料集來收集 Content Analytics 事件、設定資產屬性和 (如果已設定) 體驗屬性。
      * 建立資料流，使用功能化服務從Content Analytics事件產生和更新內容屬性。


   * **[!UICONTROL 資料彙集]**&#x200B;設定
      * 新的或現有的標籤屬性已設定為支援Content Analytics資料收集。 此設定意味著包含標記的 Adob&#x200B;&#x200B;e Content Analytics 擴充功能。
      * 為 Content Analytics 事件建立資料流。
      * Adobe Content Analytics 擴充功能已設定為會確保將 Content Analytics 事件傳送至 Content Analytics 的資料流。
      * 如果沒有為標記屬性設定 Web SDK，則會建立僅傳送 Content Analytics 事件的全新 Web SDK 設定。
      * 如果針對此標籤屬性設定了網頁SDK，則不會對現有的網頁SDK設定進行任何變更。


* **[!UICONTROL 儲存]**：對已實施設定進行的變更已儲存，並且實施已更新。
* **[!UICONTROL 退出]**。退出引導式設定。對已實施設定進行的所有變更都會被捨棄。


## 發佈 {#publish}

若要開始收集您Content Analytics設定的資料，您需要[手動](manual.md)發佈在您選取&#x200B;**[!UICONTROL 實作]**&#x200B;之後建立的Tags屬性。


>[!MORELIKETHIS]
>
>[手動設定](manual.md)
>
