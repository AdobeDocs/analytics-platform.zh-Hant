---
title: 在Customer Journey Analytics中將付費媒體資料與Web資料結合
description: 在Adobe Customer Journey Analytics中結合付費媒體摘要資料與網站活動，比較廣告支出、點按數、訂購、收入和廣告支出回報率。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 62a6bb436d59ab7a5a7be515afbe1f5f0f7817ee
workflow-type: tm+mt
source-wordcount: '3912'
ht-degree: 3%
---
# 使用網頁資料加入付費媒體資料

此使用案例指南說明如何在[!DNL Adobe Customer Journey Analytics]中將付費媒體摘要資料與網站行為事件資料聯結。


將您的廣告帳戶（Meta、Google Ads等）連結至Experience Platform可在Customer Journey Analytics中提供付費媒體摘要資料：每個帳戶、行銷活動、廣告群組、廣告、體驗和資產的每日曝光數、點按數、支出和廣告網路回報的轉換次數。 使用Customer Journey Analytics，您可以使用Web SDK收集您自己的站上行為事件資料：頁面檢視次數、訂購、收入。

在單一Workspace自由表格中聯結兩種型別的資料時，您可以將廣告效能與網站上的活動進行比較。 在[!DNL Analysis Workspace]中使用共用的行銷活動、廣告群組和廣告ID來報告曝光數、點按數，以及付費登陸、訂購和收入的相關支出。

| 資料來源 | 量度範例 |
|---|---|
| 付費媒體摘要資料 | 廣告網路所報告的曝光數、點按數、支出、轉換和轉換值。 |
| 網站行為事件 | 在您的網站上測量的付費登陸頁面、頁面檢視、訂單和收入 |
| 計算量度 | 登陸頁面率、網頁轉換率、網頁廣告投資報酬率、每個網頁訂單的成本，以及網路與網頁轉換的差距 |

這兩種資料型別的組合，可讓您比較點按前的資料（來自廣告）和點按後的資料（來自網站）。

本指南涵蓋以您自行設定的[!DNL Adobe Content Analytics]設定和連線所管理的連線為基礎的情況。

## 運作方式

下圖說明如何透過Customer Journey Analytics連線擷取付費媒體摘要資料和網站行為事件資料。

資料檢視負責剖析及對齊資料，因此您可以使用Workspace正確報告資料。

![付費媒體加入](./assets/paid-media-web-join.png){zoomable="yes"}

付費媒體摘要資料集包含沒有個人ID的每日量度。 網站事件資料集包含時間戳記行為事件和個人識別碼。 摘要資料群組會將維度與這些資料集建立關聯，好讓相同的維度值會出現在相同的報表列中。

>[!IMPORTANT]
>
>此聯結會對齊彙總的摘要資料與報表的Web事件。 它不會將廣告曝光或點按連結至個人。 廣告網路轉換會保留網路的報告方法。 網站訂購和收入會使用您在本指南中設定的歸因設定。

## 瞭解報表加入

您只能在ID出現在登陸頁面URL或現有事件欄位中的層級加入。 例如，僅限促銷活動標籤支援促銷活動報告，但不支援廣告層級報告。

>[!NOTE]
>
>Content Analytics體驗層級和資產層級結合需要額外的URL引數，並且不在本指南的範圍之內。


如需參考，請參閱[摘要資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/summary-data)和[摘要資料群組元件設定](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/component-settings/summary-data-group)。

### 選擇聯結索引鍵

付費媒體資料集提供原始網路ID和Adobe產生的全域唯一識別碼(GUID)。

| 識別碼 | 範例 | 用途 |
|---|---|---|
| 網路識別碼 | 行銷活動ID `123456789` | 比對從登陸頁面URL擷取的ID與付費媒體摘要維度 |
| GUID | `meta_111111111_123456789` | 使用網路、帳戶和實體階層識別付費媒體實體 |

GUID結構是`{adNetwork}_{accountID}[_{campaignID}[_{adGroupID}[_{adID}]]]`。 由[!DNL Adobe Content Analytics]管理的付費媒體元件會使用這些GUID。

本指南使用網路ID進行網路聯結，因為行銷活動、廣告群組和廣告URL巨集未提供重建GUID所需的所有資訊。 使用這些摘要欄位：

| 報告層級 | 網路識別碼欄位 | GUID欄位 |
|---|---|---|
| 促銷活動 | `paidMedia.campaignID` | `paidMedia.campaignGUID` |
| 廣告群組 | `paidMedia.adGroupID` | `paidMedia.adGroupGUID` |
| 廣告 | `paidMedia.adID` | `paidMedia.adGUID` |

網路欄位是`paidMedia.adNetwork`。 範例值包括`meta`和`google_ads`。 衍生欄位輸出必須與資料集中的值完全相符。

>[!NOTE]
>
>摘要資料群組符合維度值，而非表格中所有維度的組合。 確認您選擇的ID可明確識別您報告之帳戶和網路中的實體。 以名稱為基礎的群組可以結合共用名稱的不同實體。

## 先決條件

確認您已擁有：

* [!DNL Customer Journey Analytics] Select或更新版本，可存取此處使用的衍生欄位函式： [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse)、[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)、[Regex Replace](/help/data-views/derived-fields/derived-fields.md#regex-replace)，以及針對名稱擴充，[Lookup](/help/data-views/derived-fields/derived-fields.md#lookup)。
* [!DNL Adobe Experience Platform]許可權可管理目標沙箱中的結構描述、資料集和資料流，以及存取資料集和查詢服務以進行驗證。
* [!DNL Customer Journey Analytics]編輯目標連線和資料檢視的許可權。
* 付費媒體來源聯結器已設定在相同沙箱中，並擷取摘要和查詢資料集。 如需聯結器範例，請參閱[Meta Ads來源](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/advertising/meta-ads)。
* 擷取完整登陸頁面URL （包括其查詢字串）或包含網路ID的同等欄位的網站事件。


### 廣告標籤

識別包含行銷活動、廣告群組和廣告ID的查詢引數。 您可以使用現有的ID型標籤，而不需變更廣告平台。

| 標籤模式 | 促銷活動引數 | 廣告群組引數 | 廣告引數 |
|---|---|---|---|
| 網站URL中的Meta ID | <code>campaign_id={{campaign.id}}</code> | <code>adset_id={{adset.id}}</code> | <code>ad_id={{ad.id}}</code> |
| UTM引數中的Meta ID | <code>utm_campaign={{campaign.id}}</code> | <code>utm_term={{adset.id}}</code> | <code>utm_content={{ad.id}}</code> |
| UTM引數中的Google Ads ID | <code>utm_campaign={{campaignid}}</code> | <code>utm_term={{adgroupid}}</code> | <code>utm_content={{creative}}</code> |

對於Meta UTM標籤，`utm_source=fb`之類的來源值可以識別網路。 對於Google Ads UTM標籤，請使用來源值，例如`utm_source=google`。

某些[!DNL Adobe Advertising]整合會將`s_kwcid`值與此配置搭配使用：

```text
AL!<id>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}!{campaignid}!{adgroupid}
```

本指南後面章節的剖析規則僅適用於此版面。 在使用實際登陸URL之前，請先檢查這些URL。

如果您無法存取廣告平台，請檢查網站資料集中的登陸URL。 您也可以檢查這些付費媒體查閱欄位：

* Google Ads帳戶查閱：名為`google_ads_tracking_url_template`和`google_ads_final_url_suffix`的`additionalDetails`專案。
* Meta廣告查閱： `paidMedia.adDetails.creative.paidMediaCreative.destinationURL`。

儲存的目的地URL中的巨集可以採用百分比編碼。 驗證實際網站事件中的擴充ID，而非假設儲存的URL代表最終登陸URL。

>[!IMPORTANT]
>
>促銷活動名稱（例如`utm_campaign=fall_sale`）與促銷活動ID不符。 只在包含實際ID的層級加入。 如果ID不存在，請與您的廣告營運團隊合作，針對未來流量更新標籤；此設定無法重新建構歷史造訪中遺失的ID。

### 起點

開啟您打算使用的資料檢視，並檢查元件以判斷起點。

| | 起點 | 現有設定 | 需要進行的步驟 |
|---|---|---|---|
| A | Content Analytics搭配Web或行動與付費媒體 | [付費媒體資料集和元件](/help/content-analytics/config/paid-media.md)，加上Content Analytics事件和查詢資料集。 | 如有需要，可新增您的網站事件資料集，然後設定Web衍生的欄位和報告群組。 |
| B | 僅含付費媒體的Content Analytics | [付費媒體資料集和元件](/help/content-analytics/config/paid-media.md)；也可以出現共用內容查詢資料集。 | 新增您的網站事件資料集，然後設定Web衍生的欄位和報告群組。 |
| C | 不含Content Analytics布建的付費媒體 | 付費媒體資料集存在於Experience Platform中，但連線和資料檢視不包含付費媒體設定。 | 新增網站和付費媒體資料集，然後建立付費媒體和Web元件。 |
| D | Content Analytics （不含付費媒體） | 僅限Content Analytics元件。 | 在Content Analytics設定中啟用付費媒體頻道，然後遵循現有設定路徑。 |

延伸Content Analytics管理的連線時，請勿移除或修改系統布建的資料集或唯讀元件。

## 收集網站行為事件

如果您的網站已將所需事件傳送至Customer Journey Analytics中使用的資料集，請略過結構、資料集和資料串流建立。 確認`web.webPageDetails.URL`包含登入頁面查詢字串。

### 建立結構和資料集

1. 在Experience Platform中，選取目標沙箱。
1. 移至&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 結構描述]**，然後選取&#x200B;**[!UICONTROL 建立結構描述]**。
1. 選擇&#x200B;**[!UICONTROL 手動]**&#x200B;和`XDM ExperienceEvent`類別。
1. 為結構描述命名，例如`Web Behavioral Events`。
1. 新增實施所需的欄位群組。

   | 欄位群組 | 必要資料 |
   |---|---|
   | AEP Web SDK體驗事件 | 頁面URL、頁面檢視、反向連結和其他網頁內容。 |
   | Commerce詳細資料 | 購買計數、訂單值、貨幣、購買ID和產品詳細資料。 |
   | 行銷活動行銷細節，選用 | 如果您的實作會分別擷取追蹤程式碼，則請追蹤程式碼。 |
   | IdentityMap （如果尚未出現） | 個人識別碼，例如ECID。 |

1. 儲存結構。 此報告使用案例不需要啟用設定檔。
1. 移至&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料集]** > **[!UICONTROL 建立資料集]** > **[!UICONTROL 從結構描述建立資料集]**。
1. 選取結構描述並建立名為的資料集，例如`Web Behavioral Events`。 保留&#x200B;**[!UICONTROL 設定檔]**&#x200B;停用，除非其他使用案例需要它。

### 設定資料流和網頁SDK

1. 移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 資料串流]** > **[!UICONTROL 新增資料串流]**。
1. 為資料流命名，並選取您的事件結構描述作為對應結構描述。
1. 儲存，然後選取&#x200B;**[!UICONTROL 新增服務]** > **[!UICONTROL Adobe Experience Platform]**。
1. 選取沙箱和事件資料集，然後&#x200B;**[!UICONTROL 儲存]**。
1. 使用資料串流識別碼來設定[Experience Platform Web SDK](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/js-overview)。

擷取下列專案：

* 擷取每個頁面上的頁面檢視，並將`web.webPageDetails.URL`和`web.webPageDetails.pageViews.value`中的完整URL設為`1`。
* 購買`commerce.purchases.value`設定為`1`，加上`commerce.order.priceTotal`、`commerce.order.currencyCode`和`commerce.order.purchaseID`的事件。
* 適用於您Customer Journey Analytics連線的個人識別碼。

您不需要剖析網站程式碼中的UTM引數。 本指南中的衍生欄位會在報表時間剖析URL。 如果您的實作已擷取專用欄位中的ID，請改用這些欄位。

### 驗證內嵌

檢查資料集活動是否成功擷取。 在查詢服務中，執行下列查詢，將`web_behavioral_events`取代為您資料集的SQL資料表名稱：

```sql
SELECT timestamp, eventType, web.webPageDetails.URL
FROM web_behavioral_events
WHERE web.webPageDetails.URL RLIKE '[?&](campaign_id|utm_campaign|s_kwcid)='
ORDER BY timestamp DESC
LIMIT 20;
```

確認傳回的URL包含展開的網路ID。 如果付費流量存在，但查詢未傳回任何列，請檢查最近的登陸URL，並調整引數模式以符合您的標籤。

## 設定連線

若要將網頁事件資料集擷取至Customer Journey Analytics，您需要將資料集新增至相關連線。 這可確保網頁行為事件可與您的付費媒體資料集一併使用以進行分析。

### 新增網站事件資料集

1. 在Customer Journey Analytics中，移至&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 連線]**。
1. 編輯包含付費媒體資料集的連線。
1. 選取&#x200B;**[!UICONTROL 新增資料集]**&#x200B;並選擇網站事件資料集。
1. 設定資料集：

   | 設定 | 值 |
   |---|---|
   | 人員 ID | `identityMap`具有ECID名稱空間，或您實作的人員ID欄位。 |
   | 時間戳記 | `timestamp` |
   | 資料來源類型 | 網頁資料 |
   | 匯入所有新資料 | 已啟用 |
   | 回填所有現有資料 | 已針對您需要的歷史期間啟用。 |

1. 新增資料集並儲存連線。

### 新增付費媒體資料集（如果尚未設定）

>[!IMPORTANT]
>
>有關Content Analytics管理付費媒體資料集的連線，請略過本節。


至少新增付費媒體廣告摘要和付費媒體帳戶、付費媒體行銷活動、付費媒體廣告群組和付費媒體廣告查詢資料集。

| 資料集 | 類型 | 金鑰組態 |
|---|---|---|
| 付費媒體廣告摘要 | 摘要 | 使用結構的每日時間戳記設定；啟用新資料匯入和必要的回填。 |
| 付費媒體帳戶查閱 | 查詢 | 索引鍵： `paidMedia.accountGUID`；廣告摘要中的相符欄位： `paidMedia.accountGUID`。 |
| 付費媒體促銷活動查閱 | 查詢 | 索引鍵： `paidMedia.campaignGUID`；廣告摘要中的相符欄位： `paidMedia.campaignGUID`。 |
| 付費媒體廣告群組查閱 | 查詢 | 索引鍵： `paidMedia.adGroupGUID`；廣告摘要中的相符欄位： `paidMedia.adGroupGUID`。 |
| 付費媒體廣告查閱 | 查詢 | 索引鍵： `paidMedia.adGUID`；廣告摘要中的相符欄位： `paidMedia.adGUID`。 |

在儲存之前，請確認連線編輯器公開預期的相符欄位。 本指南稍後章節的名稱擴充會明確使用衍生欄位查詢規則。

只有在您需要劃分其他可用的摘要資料集時（例如地理位置、人口統計、位置或效能），才能新增這些資料集。

## 設定資料檢視

開啟&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 資料檢視]**，然後選取您的資料檢視。 如有需要，請使用您設定的連線建立資料檢視。

對於新資料檢視，使用GMT將網站事件與UTC付費媒體天數保持一致，並保持預設的30分鐘工作階段逾時，除非您的報告要求不同。 變更現有資料檢視的時區會影響其他報表；請先評估影響，然後再進行變更。

### 新增付費媒體量度（如果尚未設定）

如果這些量度或維度已存在，請略過此步驟。 從&#x200B;**[!UICONTROL 付費媒體廣告摘要]**&#x200B;新增下列欄位：

| 元件名稱 | 結構描述欄位 | 格式 |
|---|---|---|
| **量度** | | |
| 曝光數\|廣告摘要 | `paidMedia.metrics.impressions` | 小數 |
| 點選次數\|廣告摘要 | `paidMedia.metrics.clicks` | 小數 |
| 支出\|廣告摘要 | `paidMedia.metrics.spend` | 貨幣 |
| 轉換\|廣告摘要 | `paidMedia.metrics.conversions` | 小數 |
| 轉換值\|廣告摘要 | `paidMedia.metrics.conversionValue` | 貨幣 |
| **維度** | | |
| 廣告網路 | `paidMedia.adNetwork` | 字串 |
| 帳戶 GUID | `paidMedia.accountGUID` | 字串 |
| 行銷活動 GUID | `paidMedia.campaignGUID` | 字串 |
| 廣告群組 GUID | `paidMedia.adGroupGUID` | 字串 |
| 廣告 GUID | `paidMedia.adGUID` | 字串 |

幣別格式本身不會調節不同的來源幣別。 在比較支出和收入之前確認貨幣基準。

使用衍生欄位來建立GUID維度的描述性名稱。 使用[查詢](/help/data-views/derived-fields/derived-fields.md#lookup)規則為GUID維度套用描述性名稱。  例如：查詢&#x200B;**[!UICONTROL paidMedia.accountGUID （付費媒體廣告摘要）]**&#x200B;使用查詢資料集&#x200B;**[!UICONTROL 付費媒體帳戶查詢]**，並搭配比對索引鍵`paidMedia.accountGUID`和要傳回的值： `paidMedia.accountDetails.accountName`。


### 建立Web網路衍生欄位

選取&#x200B;**[!UICONTROL 建立衍生欄位]**&#x200B;並命名欄位`PM Network (Web)`。 以下的所有[URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse)規則都會讀取網站資料集的`web.webPageDetails.URL`欄位，此處稱為頁面URL。

依下列順序新增規則：

| 規則 | 函數 | 設定 |
|---|---|---|
| 1 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 頁面URL。 取得`utm_source`的查詢字串值。 |
| 2 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 頁面URL。 取得`s_kwcid`的查詢字串值。 |
| 3 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 頁面URL。 取得`gclid`的查詢字串值。 |
| 4 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 頁面URL。 取得`fbclid`的查詢字串值。 |
| 5 | [案例時間](/help/data-views/derived-fields/derived-fields.md#case-when) | 套用下列條件。 |

設定[&#128279;](/help/data-views/derived-fields/derived-fields.md#case-when)規則時的最終案例：

1. 如果已設定規則2或規則3，則傳回`google_ads`。
1. 否則，如果規則4已設定或規則1等於`fb`、`facebook`、`ig`、`instagram`或`meta`，則會傳回`meta`。
1. 否則，如果規則1等於`google`，則傳回`google_ads`。
1. 在`paidMedia.adNetwork`中確認其他網路的值之後，才為其他網路新增對應。
1. 否則，不會傳回任何值。

若要輸入固定輸出，請開啟值選擇器，選取&#x200B;**[!UICONTROL 自訂字串值]**，然後輸入字串。

這些分類規則是以標籤為基礎，而不是證明造訪來自付費廣告。 例如，來源引數本身也可以出現在非付費連結上。 在將該欄位用作付費流量分類器之前，請根據您的標籤慣例調整條件。

### 建立網頁ID衍生欄位

為每個報告層級建立一個衍生欄位。 下列結構會處理先前所述的三種標籤模式：

| 規則 | 函數 | 設定 |
|---|---|---|
| 1 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 從頁面URL讀取層級特定的Meta引數。 |
| 2 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 從頁面URL中讀取層級特定的UTM引數。 |
| 3 | [URL剖析](/help/data-views/derived-fields/derived-fields.md#url-parse) | 從頁面URL讀取`s_kwcid`。 |
| 4 | [Regex取代](/help/data-views/derived-fields/derived-fields.md#regex-replace) | 套用層次特定運算式至規則3；輸出`$1`。 |
| 5 | [案例時間](/help/data-views/derived-fields/derived-fields.md#case-when) | 若已設定規則3，則傳回規則4；否則，若已設定規則1，則傳回規則1；否則，傳回規則2。 |

請使用下列值：

| 衍生欄位 | Meta引數 | UTM引數 | 規則運算式 |
|---|---|---|---|
| **下午Campaign ID （網頁）** | `campaign_id` | `utm_campaign` | `^.*!([^!]*)![^!]*$` |
| **PM廣告群組ID （網頁）** | `adset_id` | `utm_term` | `^.*!([^!]*)$` |
| **PM廣告ID （網頁）** | `ad_id` | `utm_content` | `^[^!]*![^!]*![^!]*!([^!]*)!.*$` |

在最終的[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)規則中，從值選擇器選取較早的規則輸出，而不是以常值字串輸入它們。

行銷活動運算式會擷取第二個到最後一個`s_kwcid`值，廣告群組運算式會擷取最後一個值，而廣告運算式則會擷取第四個值。 這些位置取決於先前顯示的確切版面配置。

使用&#x200B;**[!UICONTROL 最終輸出]**&#x200B;確認結果符合付費媒體廣告摘要中的識別碼。 如果您的URL使用不同的配置，請勿保留`s_kwcid`剖析分支。 如果您的URL僅使用UTM引數，請忽略未使用的規則並相應地更新後續規則參照。

每個衍生欄位最多支援五個[URL剖析規則](/help/data-views/derived-fields/derived-fields.md#url-parse)和一個[Regex取代規則](/help/data-views/derived-fields/derived-fields.md#regex-replace)。 每個衍生欄位請保留一個ID。

### 建立付費登陸量度

使用`PM Campaign ID (Web)`作為輸入建立名為`Paid Media Landings (Web)`的衍生欄位。

產生器將輸入欄位的規則展開至新欄位。 在這些規則之後，新增[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)規則，當行銷活動ID輸出已設定時，該規則會傳回自訂數值`1`，否則不會傳回值。 將結果新增為量度。

此量度會計算攜帶行銷活動ID的事件。 此量度只會在您的實作在登陸事件上傳送該ID承載URL時代表登陸，而不會在重複或不相關的事件上傳送。

>[!NOTE]
>
>展開的衍生欄位規則為副本。 如果您變更ID欄位，請一併檢查並更新對應的登入和名稱欄位。 如果您省略剖析規則，請參考實際的最終ID規則，而非假設其為規則5。

### 新增選用的網頁名稱欄位

若要依名稱報告，請在展開的Web ID規則之後，使用[查閱規則](/help/data-views/derived-fields/derived-fields.md#lookup)建立下列衍生欄位：

| 衍生欄位 | 輸入 | 查詢資料集 | 相符的欄位 | 傳回欄位 |
|---|---|---|---|---|
| PM行銷活動名稱（網頁） | PM Campaign ID （網頁）的最終輸出 | 付費媒體促銷活動查閱 | `paidMedia.campaignID` | `paidMedia.metadata.name` |
| PM廣告群組名稱（網頁） | PM廣告群組ID （網頁）的最終輸出 | 付費媒體廣告群組查閱 | `paidMedia.adGroupID` | `paidMedia.metadata.name` |
| PM廣告名稱（網頁） | PM廣告ID （網頁）的最終輸出 | 付費媒體廣告查閱 | `paidMedia.adID` | `paidMedia.metadata.name` |

選取最終ID規則作為套用查閱的欄位。 在將欄位新增為維度之前，驗證最終輸出預覽中的名稱。 如果必要的相符欄位無法使用，請改用ID型報表。

名稱會比對為文字。 當不同的實體共用一個名稱時，請使用ID維度。

### 新增Web元件並設定歸因

將網頁ID和網路衍生欄位新增為維度。 如果您已建立選用名稱欄位，請新增它們。 將元件設定維持在預設值，以便符合您新增至其群組的摘要維度。

確認您的資料檢視包含您需要的網頁元件：

| 元件 | 類型 | 結構描述欄位 |
|---|---|---|
| 頁面 URL | 維度 | `web.webPageDetails.URL` |
| 頁面名稱 | 維度 | `web.webPageDetails.name` |
| 反向連結URL | 維度 | `web.webReferrer.URL` |
| 事件類型 | 維度 | `eventType` |
| 產品 SKU | 維度 | `productListItems.SKU` |
| 產品名稱 | 維度 | `productListItems.name` |
| 頁面檢視 | 量度 | `web.webPageDetails.pageViews.value` |
| 新增至購物車 | 量度 | `commerce.productListAdds.value` |
| 訂購 | 量度 | `commerce.purchases.value` |
| 收入 | 量度 | `commerce.order.priceTotal` |

將付費登陸衍生欄位新增為量度，然後設定個別的訂單和收入量度：

1. 複製&#x200B;**[!UICONTROL 訂單]**&#x200B;並命名復本`Orders (Web)`。 如果&#x200B;**[!UICONTROL 訂單]**&#x200B;不存在，請直接新增`commerce.purchases.value`。
1. 複製&#x200B;**[!UICONTROL 收入]**&#x200B;並命名復本`Revenue (Web)`。 如果&#x200B;**[!UICONTROL 收入]**&#x200B;不存在，請直接新增`commerce.order.priceTotal`。
1. 將&#x200B;**[!UICONTROL 訂單（網頁）]**&#x200B;格式化為小數，小數位數為零，並將&#x200B;**[!UICONTROL 收入（網頁）]**&#x200B;格式化為貨幣。
1. 針對這兩個量度，開啟&#x200B;**[!UICONTROL 歸因]**&#x200B;並啟用&#x200B;**[!UICONTROL 覆寫預設歸因]**。
1. 選取&#x200B;**[!UICONTROL 上次接觸]**&#x200B;模型和&#x200B;**[!UICONTROL 工作階段]**&#x200B;容器。

保持原始&#x200B;**[!UICONTROL 訂單]**&#x200B;和&#x200B;**[!UICONTROL 收入]**&#x200B;量度不變，以保留現有報表。 此設定需要明確啟用覆寫，即使顯示的預設值似乎相符。

若要計算回訪間的轉換點數，請改為考慮&#x200B;**[!UICONTROL 人員]**&#x200B;容器和適當的回顧期間。 檢視[摘要資料使用案例](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-usecases/data-views/summary-data)。

使用量度歸因，而非將持續性新增至網頁ID維度。 為避免誇大解譯為著陸的計數，請勿將ID保留給之後的事件，因為這會變更哪些事件會出現在促銷活動列下。

### 建立摘要端結合維度

從付費媒體廣告摘要新增個別維度以用於網頁聯結：

| 元件名稱 | 結構描述欄位 |
|---|---|
| 廣告網路（已加入） | `paidMedia.adNetwork` |
| 行銷活動ID （網路） | `paidMedia.campaignID` |
| 廣告群組ID （網路） | `paidMedia.adGroupID` |
| 廣告ID （網路） | `paidMedia.adID` |

請勿編輯或複製唯讀、範本管理的付費媒體元件。 從結構欄位建立上述的個別元件。

如果您已建立選用的Web名稱欄位，請一併建立這些摘要端的「查詢」衍生欄位：

| 元件名稱 | 從廣告摘要輸入 | 查詢資料集 | 相符的欄位 | 傳回欄位 |
|---|---|---|---|---|
| 行銷活動名稱（已加入） | `paidMedia.campaignGUID` | 付費媒體促銷活動查閱 | `paidMedia.campaignGUID` | `paidMedia.metadata.name` |
| 廣告群組名稱（已加入） | `paidMedia.adGroupGUID` | 付費媒體廣告群組查閱 | `paidMedia.adGroupGUID` | `paidMedia.metadata.name` |
| 廣告名稱（已加入） | `paidMedia.adGUID` | 付費媒體廣告查閱 | `paidMedia.adGUID` | `paidMedia.metadata.name` |

使用摘要資料集中的GUID作為每個查詢的輸入。 直接從查詢資料集中取得的維度不符合摘要資料群組中摘要維度的需求。

### 建立摘要資料群組

在您計畫用於報表的Web維度上建立每個群組。 新增對應的摘要維度，並將新增的成員隱藏在報表中。

| 網頁維度：在此處建立群組 | 摘要維度：新增為隱藏成員 |
|---|---|
| PM網路（網頁） | 廣告網路（已加入） |
| PM促銷活動ID （網頁） | 行銷活動ID （網路） |
| PM廣告群組ID （網頁） | 廣告群組ID （網路） |
| PM廣告ID （網頁） | 廣告ID （網路） |
| PM促銷活動名稱（網頁），選用 | 行銷活動名稱（已加入） |
| PM廣告群組名稱（網頁），選填 | 廣告群組名稱（已加入） |
| PM廣告名稱（網頁），選填 | 廣告名稱（已加入） |

每一列：

1. 選取網頁維度。
1. 開啟&#x200B;**[!UICONTROL 摘要資料群組]**&#x200B;並啟用&#x200B;**[!UICONTROL 建立群組]**。
1. 新增摘要維度。
1. 為新增的摘要成員啟用&#x200B;**[!UICONTROL 在報表中隱藏]**。 維持網頁維度可見。
1. 確認元件設定（包括小寫、子字串和包含/排除規則）在各個成員間相符。

每個群組最多可支援10個維度。 若要包含其他摘要資料集的量度，請將該資料集的對等摘要維度新增至與隱藏成員相同的群組。

>[!IMPORTANT]
>
>使用網頁維度作為報表維度，並在此維度上建立群組。 反向排列可以顯示摘要量度，但沒有對應的網頁量度。

儲存資料檢視。

### 建立計算量度

在Workspace中，前往&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 計算量度]**，並使用設定的資料檢視建立下列量度：

| 名稱 | 定義 | 格式 |
|---|---|---|
| 登陸率 | 付費媒體上線（網頁） /點按\|廣告摘要 | 百分比 |
| 網頁轉換率 | 訂購（網頁）/付費媒體上線（網頁） | 百分比 |
| Web ROAS | 收入（網頁） /支出\|廣告摘要 | 小數，兩位 |
| 每個網頁訂單的成本 | 支出\|廣告摘要/訂單（網頁） | 貨幣 |
| 網路與網頁轉換間隙 | 轉換\|廣告摘要 — 訂單（網頁） | 小數，零位數 |

在解譯比率量度之前，請先檢閱零分母的列。 網路與網頁轉換間隙本身並不表示錯誤：這兩個來源在歸因、測量和報告時段中可能不同。

## 建置及驗證報告

1. 使用已設定的資料檢視建立Workspace專案。
1. 選擇包含兩個來源資料的日期範圍。 允許付費媒體擷取延遲；摘要資料可能會將網站事件延遲一天。
1. 新增含有&#x200B;**[!UICONTROL PM促銷活動識別碼（網頁）]**&#x200B;作為列維度的自由表格，或如果您已設定名稱群組，則新增&#x200B;**[!UICONTROL PM促銷活動名稱（網頁）]**。
1. 新增&#x200B;**[!UICONTROL 曝光數 |廣告摘要]**，**[!UICONTROL 點按 |廣告摘要]**，**[!UICONTROL 支出 |廣告摘要]**，**[!UICONTROL 轉換 |廣告摘要]**，**[!UICONTROL 付費媒體登陸 |廣告摘要]**、**[!UICONTROL 訂單（網頁）]**、**[!UICONTROL 收入（網頁）]**&#x200B;和計算量度。
1. 依網頁廣告群組和廣告維度劃分促銷活動列。 確認摘要和Web度量會填入每個已設定的層級。
1. 使用&#x200B;**[!UICONTROL PM Network (Web)]**&#x200B;新增第二個資料表，以檢閱網路層級總計和無值資料列。

   ![付費媒體和Web資料工作區專案](./assets/paid-media-and-web-data-workspace.png)

   ![付費媒體和Web資料工作區專案無資料](./assets/paid-media-and-web-data-workspace-no-value.png)

共用報表前請先檢查下列專案：

* 登陸事件ID符合付費媒體廣告摘要ID。
* 付費媒體量度和網頁量度會填入相同的列。
* 訂單和收入會收到預期的作業階段或人員歸因。
* 瞭解無值列。 它們可以包含不相符的摘要資料或沒有付費媒體識別碼的網頁活動。
* 登陸至點按的差異與您的收集設定、同意處理和報告視窗一致。 沒有普遍預期的符合率。

### 疑難排解不相符專案

| 症狀 | 檢查與更正動作 |
|---|---|
| 摘要量度會填入，但所有網路量度皆為零 | 確認列使用網頁維度，且群組已建立在這些維度上。 然後檢查登陸URL中的實際ID，而非名稱。 |
| 網路量度會填入，但摘要層級為空白 | 確認層級的摘要維度位於對應的群組中，並且所選日期存在相符的付費媒體資料。 |
| 網頁列上缺少名稱 | 檢查最終輸出預覽中的查閱輸入和比對欄位。 如果無法使用名稱擴充，請使用識別碼群組。 |
| 網頁ID包含常值或編碼的巨集 | 要求廣告營運團隊檢查目的地URL，並確認網路在登陸前會展開巨集。 |
| Google Ads ID不相符 | 檢查實際`s_kwcid`配置或UTM引數，並更新剖析規則。 |
| 網路值已分割，例如`facebook`和`meta` | 讓網路衍生欄位輸出完全符合`paidMedia.adNetwork`。 |
| ID會顯示在個別的列中 | 確認所有分組的維度間的設定相符，並檢查基礎字串值。 |
| 網站活動似乎已移動一天 | 比較資料檢視時區與UTC摘要日期邊界。 |
| 行銷活動中的訂單或收入為零或意外地低 | 明確啟用量度歸因覆寫，並確認其模型、容器和回顧設定。 |
| 付費登陸次數出乎意料地高 | 確認只有登陸事件會攜帶已計數的行銷活動引數。 重複的ID攜帶事件也會影響此量度。 |
| 不同的行銷活動會共用一個名稱列 | 使用以ID為基礎的報表，區分名稱相同的實體。 |
