---
title: 將Adobe Analytics資料摘要欄對應至Customer Journey Analytics
description: 決定如何取用指定的Adobe Analytics資料摘要欄，並決定其在您Customer Journey Analytics實作中的大致相等值。
feature: Components
hide: true
hidefromtoc: true
exl-id: 81d6e79e-8324-4726-9a48-10177b0a91b1
source-git-commit: af5b30cd71ebe46e2af584ee502ef631c829f5ea
workflow-type: tm+mt
source-wordcount: '3356'
ht-degree: 57%

---

# 將Adobe Analytics資料摘要欄對應至Customer Journey Analytics

Adobe Analytics與Customer Journey Analytics資料摘要欄之間不可能有真正的1:1對應。 這兩種產品有根本的不同，每個組織的實施作業也可能大不相同。

此參考資料可協助資料工程師評估Adobe Analytics資料摘要欄，並針對其工作流程找出最接近的Customer Journey Analytics對應專案。

>[!NOTE]
>
>此參考僅包含Adobe根據[Analytics資料摘要資料行參考](https://experienceleague.adobe.com/zh-hant/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference)視為目前的資料行。 如果您的Analytics資料摘要欄位未在此表格中列出，且您主動使用，請參閱貴組織的解決方案設計檔案，以判斷其在Customer Journey Analytics中的最佳對應專案。

+++**`accept_language`**

列出所有接受的語言，如影像要求中的 Accept-Language HTTP 標頭所示。

+++

+++**`adload`**

媒體廣告載入

{{cja-df-post}}

+++

+++**`aemassetid`**

對應於一組 Adobe Experience Manager Assets 的資產 ID (GUID) 的多值變數。增加曝光事件。

{{cja-df-post}}

+++

+++**`aemassetsource`**

確認資產事件的來源。用於 Adobe Experience Manager。

{{cja-df-post}}
+++

+++**`aemclickedassetid`**

Adobe Experience Manager 資產的資產 ID。增加點按事件。

{{cja-df-post}}

+++

+++**`amo_cid`**

AMO ID維度，用於Adobe Advertising整合。

{{cja-df-post}}

+++

+++**`amo_ef_id`**

AMO EF ID維度，用於Adobe Advertising整合。

{{cja-df-post}}

+++

+++**`browser`**

表示瀏覽器的數值ID。

{{cja-df-lookup}}

+++

+++**`browser_height`**

瀏覽器高度維度。

{{cja-df-post}}

+++

+++**`browser_width`**

瀏覽器寬度

{{cja-df-post}}

+++

+++**`campaign`**

追蹤代碼維度。

{{cja-df-post}}

+++

+++**`carrier`**

Adobe Advertising 整合變數。指定行動電信業者。

{{cja-df-lookup}}

+++

+++**`channel`**

網站區段維度。

{{cja-df-post}}

+++

+++**`ch_hdr`**

透過 HTTP 請求標頭收集的用戶端提示。

+++

+++**`ch_js`**

透過使用者代理用戶端提示 JavaScript API 收集的用戶端提示。

+++

+++**`clickmaplink`**

Activity Map連結維度。

{{cja-df-post}}

{{cja-df-na}}

此欄不適用，因為Customer Journey Analytics尚不支援Activity Map。

+++

+++**`clickmaplinkbyregion`**

Activity Map連結（依地區）維度。

{{cja-df-post}}

{{cja-df-na}}

此欄不適用，因為Customer Journey Analytics尚不支援Activity Map。

+++

+++**`clickmappage`**

Activity Map頁面維度。

{{cja-df-post}}

{{cja-df-na}}

此欄不適用，因為Customer Journey Analytics尚不支援Activity Map。

+++

+++**`clickmapregion`**

Activity Map區域維度。

{{cja-df-post}}

{{cja-df-na}}

此欄不適用，因為Customer Journey Analytics尚不支援Activity Map。

+++

+++**`code_ver`**

用於編譯及傳送影像要求的 API 或客戶端 SDK 版本。

+++

+++**`color`**

以`c_color`欄的值為基礎的色階ID。

{{cja-df-lookup}}

+++

+++**`connection_type`**

表示連線型別維度的數值ID。

{{cja-df-lookup}}

+++

+++**`cookies`**

Cookie支援維度。<br>Y：啟用<br>N：停用<br>U：未知

{{cja-df-post}}

+++

+++**`country`**

代表訪客所屬國家的數值 ID。請參考`country.tsv`查詢表。

{{cja-df-lookup}}

+++

+++**`currency`**

交易期間使用的貨幣代碼。使用 `currencyCode` 設定。

`xdm.commerce.order.currencyCode`

{{cja-df-post}}

+++

+++**`ct_connect_type`**

和`connection_type`欄相關。最常見的值是 LAN/Wifi、行動電信業者和數據機。

+++

+++**`curr_factor`**

決定貨幣的小數位數。 用於貨幣轉換。 例如，美元使用兩位小數，因此此欄的值為 `2`。

+++

+++**`curr_rate`**

交易發生時的匯率。Adobe 與 XE 合作，以確定當日的匯率。

+++

+++**`customer_perspective`**

判斷點選是否為行動背景點選。

{{cja-df-post}}

+++

+++**`cust_hit_time_gmt`**

僅限啟用時間戳記的報告套裝。時間戳記根據 UNIX® 時間隨點擊傳送。

{{cja-df-post}}

+++

+++**`cust_visid`**

自訂的訪客 ID，如果使用 `visitorID` 設定。

{{cja-df-post}}

+++

+++**`c_color`**

調色盤的位元深度。用於計算色彩深度維度的一部分。 AppMeasurement 使用 JavaScript 函數`screen.colorDepth()`。

+++

+++**`daily_visitor`**

一個標幟，用來判斷該點擊是否為新的每日訪客。

+++

+++**`dataprivacyconsentoptin`**

同意管理選擇加入維度。 每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `DMP` 和 `SELL`。

{{cja-df-na}}

此欄不適用，因為Customer Journey Analytics不???。

+++

+++**`dataprivacyconsentoptout`**

同意管理選擇退出維度。 每個點擊可以有多個值，以垂直號 (`\|`) 分隔。有效值包括 `SSF`、`DMP` 和 `SELL`。

+++

+++**`date_time`**

可讀格式的點擊時間，根據報告套裝的時區而定。

+++

+++**`domain`**

網域維度。 根據訪客的網路存取點。

+++

+++**`duplicated_from`**

僅用於包含點擊複製 VISTA 規則的報告套裝。指出從中複製點擊的報告套裝。

+++

+++**`duplicate_events`**

列出每個被視為重複的事件。

+++

+++**`duplicate_purchase`**

一個標幟，用來判斷此點擊的購買事件是否因為重複而被忽略。

+++

+++**`ef_id`**

EF ID，用於Adobe Advertising整合。

{{cja-df-post}}

+++

+++**`evar1 - evar250`**

自訂變數 1-250。用於eVar維度。 每個組織使用 eVar 的方式不同。若要進一步瞭解貴組織如何填入個別eVar，最佳選擇是貴組織專屬的解決方案設計檔案。

{{cja-df-post}}

+++

+++**`event_list`**

用逗號分隔的數值 ID 列表，代表在該點擊上觸發的事件。包含商務事件和自訂事件1-1000。 使用`event.tsv`查詢。

此欄可能會對應至數十種不同的量度，端視您的實施而定。 Adobe建議依照下列程式，將Customer Journey Analytics中的各個量度對應至顯示在此Analytics資料摘要欄中的數值：

1. 使用`event.tsv`查詢將每個數值對應至其量度名稱。
1. 使用您的解決方案設計檔案，將每個Analytics事件名稱對應到Customer Journey Analytics中對應的量度名稱。
1. 在資料檢視UI中選取對應的元件，並記下其元件ID。 如果元件ID太笨重，您可以填入資料摘要別名ID欄位，然後改用。
1. 對您的組織使用的每個量度重複此步驟。

{{cja-df-post}}

如果您的結構描述使用[[!UICONTROL Commerce詳細資料]](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/field-groups/event/commerce-details)欄位群組，部分量度可能會直接對應到下列XDM欄位：

* **結帳**： `xdm.commerce.checkouts.value`
* **購物車新增次數**： `xdm.commerce.productListAdds.value`
* **購物車開啟**： `xdm.commerce.productListOpens.value`
* **購物車移除**： `xdm.commerce.productListRemovals.value`
* **購物車檢視**： `xdm.commerce.productListViews.value`
* **產品檢視**： `xdm.commerce.productViews.value`
* **訂單**： `xdm.commerce.purchases.value`

有些量度可能會使用事件序列化，因此Adobe Analytics可完全控制重複資料刪除。 您可以使用[量度重複資料刪除](/help/data-views/component-settings/metric-deduplication.md)元件設定來達成重複資料刪除同位檢查。

* 如果您的量度在Adobe Analytics中依造訪進行重複資料刪除，您可以在該量度的元件設定中，將重複資料刪除範圍設定為工作階段。
* 如果您的量度在Adobe Analytics中依事件ID進行重複資料刪除，則該量度的XDM物件可能同時包含`value`和`id`欄位。 如果您的結構描述使用[[!UICONTROL Commerce詳細資料]](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/field-groups/event/commerce-details)欄位群組，這些量度可能位於這些XDM欄位中，您可以在量度的元件設定中設定&#x200B;**[!UICONTROL 重複資料刪除ID]**&#x200B;欄位：

   * **結帳**： `xdm.commerce.checkouts.id`
   * **購物車新增次數**： `xdm.commerce.productListAdds.id`
   * **購物車開啟**： `xdm.commerce.productListOpens.id`
   * **購物車移除**： `xdm.commerce.productListRemovals.id`
   * **購物車檢視**： `xdm.commerce.productListViews.id`
   * **產品檢視**： `xdm.commerce.productViews.id`
   * **訂單**： `xdm.commerce.purchases.id`

+++

+++**`exclude_hit`**

一個標幟，用來判斷該點擊是否被排除在報告之外。此`visit_num`欄不會因排除的點擊而遞增。<br>1：未使用。屬於已報廢功能。<br>2：未使用。屬於已報廢功能。<br>3：已不再使用。用戶代理排除<br>4：依據 IP 位址的排除<br>5：遺失重要點擊資訊，例如`page_url`、`pagename`、`page_event`、或者`event_list`<br>6：JavaScript 沒有正確處理點擊<br>7：特定帳戶的排除，例如在 Vista 規則中<br>8：未使用。替代帳戶特定排除。<br>9：未使用。屬於已報廢功能。<br>10：無效的貨幣代碼<br>11：僅時間戳記報告套裝上遺失時間戳記的點擊，或非時間戳記報告套裝上包含時間戳記的點擊<br>12：未使用。屬於已報廢功能。<br>13：未使用。屬於已報廢功能。<br>14：不符合 Analytics 點擊的 Target 點擊<br>15：目前未使用。<br>16：不符合 Analytics 點擊的 Advertising Cloud 點擊

+++

+++**`first_hit_pagename`**

登入頁面原始維度。 訪客的原始進入頁面名稱。

+++

+++**`first_hit_page_url`**

訪客的第一個 URL。

+++

+++**`first_hit_referrer`**

訪客的第一個反向連結 URL。

+++

+++**`first_hit_ref_domain`**

原始反向連結網域維度。 根據`first_hit_referrer`而定。訪客的第一個反向連結網域。

+++

+++**`first_hit_ref_type`**

表示訪客第一個反向連結的反向連結型別數值ID。

{{cja-df-lookup}}

+++

+++**`first_hit_time_gmt`**

訪客初次點擊的時間戳記 (根據 UNIX® 時間)。

+++

+++**`geo_city`**

點擊的來源城市名稱，以 IP 為準。用於城市維度。

+++

+++**`geo_country`**

點擊的來源國家/地區縮寫，以 IP 為準。用於國家/地區維度。

+++

+++**`geo_dma`**

點擊的來源人口統計區域的數值 ID，以 IP 為準。用於美國DMA維度。

+++

+++**`geo_region`**

點擊的來源州或地區名稱，以 IP 為準。用於地區維度。

+++

+++**`geo_zip`**

點擊來源的郵遞區號 (根據 IP 位址)。協助填入郵遞區號維度。 另請參閱`zip`。

+++

+++**`hitid_high`**

搭配 `hitid_low` 使用來識別點擊。

+++

+++**`hitid_low`**

搭配 `hitid_high` 使用來識別點擊。

+++

+++**`hit_source`**

該點擊的來源。點選來源1和2需計費。 <br>1：沒有時間戳記的標準影像要求<br>2：具有時間戳記的標準影像要求<br>3：具有時間戳記的即時資料來源上傳<br>4：未使用<br>5：通用資料來源上傳<br>6：不再使用；完整處理資料來源上傳<br>7： TransactionID資料來源上傳<br>8：已不再使用；舊版Adobe Advertising資料來源<br>9：已不再使用；Adobe Social摘要量度<br>10：使用了Audience Manager伺服器端轉送

+++

+++**`hit_time_gmt`**

Adobe 資料收集伺服器收到點擊的時間戳記 (根據 UNIX® 時間)。

+++

+++**`hourly_visitor`**

一個標幟，用來判斷該點擊是否來自新的每小時訪客。

+++

+++**`ip`**

IPv4 位址，根據影像請求 HTTP 標頭。與 `ipv6` 互斥；如果此欄包含非模糊 IP 位址，`ipv6` 為空白。

+++

+++**`ipv6`**

壓縮的 IPv6 位址 (若有)。與 `ip` 互斥；如果此欄包含非模糊 IP 位址，`ip` 為空白。

+++

+++**`javascript`**

JavaScript版本的查詢識別碼，根據`j_jscript`。

{{cja-df-lookup}}

+++

+++**`java_enabled`**

Java已啟用維度。 <br>Y：啟用 <br>N：停用 <br>U：未知

{{cja-df-post}}

+++

+++**`j_jscript`**

瀏覽器支援的 JavaScript 版本。

+++

+++**`language`**

代表訪客語言的數值ID。

{{cja-df-lookup}}

+++

+++**`last_hit_time_gmt`**

先前點擊的時間戳記 (根據 UNIX® 時間)。用於計算上次造訪間隔天數維度。

+++

+++**`last_purchase_num`**

客戶忠誠度維度。 訪客之前已購買的次數。<br>0：沒有先前購買 (非客戶) <br>1：先前購買 1 次 (新客戶) <br>2：先前購買 2 次 (回頭客戶) <br>3：先前購買 3 次以上 (忠實客戶)

+++

+++**`last_purchase_time_gmt`**

用於和上次購買間隔天數維度。 上次進行購買的時間戳記 (根據 UNIX® 時間)。對於首次購買和之前未購買的訪客，此值為 `0`。

+++

+++**`latlon1`**

位置 (10 公里以內)

+++

+++**`latlon23`**

位置 (100 公尺以內)

+++

+++**`latlon45`**

位置 (1 公尺以內)

+++

+++**`mcvisid`**

Experience Cloud 訪客 ID。由兩個連接的 64 位數組成，並填入至 19 位的 128 位數。

+++

+++**`mc_audiences`**

訪客所屬的 Audience Manager 區段 ID 清單。`post_mc_audiences` 欄會將分隔符號變更為 `--**--`。

{{cja-df-post}}

+++

+++**`mobileaction`**

行動動作。在行動裝置實施中呼叫 `trackAction` 時自動收集。允許應用程式中的自動動作路徑。

{{cja-df-post}}

+++

+++**`mobileappid`**

行動應用程式 ID。以下列格式儲存應用程式名稱和版本：`[AppName] [BundleVersion]`

`xdm.application.name` + `xdm.application.version`

{{cja-df-post}}

+++

+++**`mobileappperformanceappid`**

用於 Apteligent 資料連接器。Apteligent 中使用的應用程式 ID。

+++

+++**`mobileappperformancecrashid`**

用於 Apteligent 資料連接器。Apteligent 中使用的當機 ID。

+++

+++**`mobileappstoreobjectid`**

用於 [!DNL Appfigures] 資料連接器。應用程式商店物件 ID。

+++

+++**`mobilebeaconmajor`**

行動服務主要信標

+++

+++**`mobilebeaconminor`**

行動服務次要信標

+++

+++**`mobilebeaconproximity`**

行動服務鄰近地區信標

+++

+++**`mobilebeaconuuid`**

行動服務信標 UUID

+++

+++**`mobilecampaigncontent`**

顯示連結之內容的名稱或 ID。由「行動應用程式贏取」填入。

{{cja-df-post}}

+++

+++**`mobilecampaignmedium`**

行銷媒體，例如橫幅或電子郵件。由「行動應用程式贏取」填入。

{{cja-df-post}}

+++

+++**`mobilecampaignname`**

行銷活動名稱，亦儲存於行銷活動變數中。由「行動應用程式贏取」填入。

{{cja-df-post}}

+++

+++**`mobilecampaignsource`**

原始反向連結，例如電子報或社交媒體網路。由「行動應用程式贏取」填入。

{{cja-df-post}}

+++

+++**`mobilecampaignterm`**

您要對此贏取追蹤的付費關鍵字或其他詞語。由「行動應用程式贏取」填入。

{{cja-df-post}}

+++

+++**`mobiledayofweek`**

應用程式啟動的工作日數。

{{cja-df-post}}

+++

+++**`mobiledayssincefirstuse`**

自應用程式初次執行以來的天數。

{{cja-df-post}}

+++

+++**`mobiledayssincelastuse`**

自應用程式上次執行以來的天數。

{{cja-df-post}}

+++

+++**`mobiledeeplinkid`**

從內容資料變數`a.deeplink.id`中收集。用於贏取報表中，作為行動贏取連結的識別碼。

+++

+++**`mobiledevice`**

行動裝置名稱。在 iOS 上，儲存為以逗號分隔的兩碼字串。第一個數字代表裝置世代，第二個數字代表裝置系列。

{{cja-df-post}}

+++

+++**`mobilehourofday`**

定義一天當中啟動應用程式的時段。請依照 24 小時數字格式。

{{cja-df-post}}

+++

+++**`mobileinstalldate`**

Mobile 安裝日期。提供使用者初次開啟行動應用程式的日期。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilelaunchnumber`**

每次啟動行動應用程式時增加 1。

{{cja-df-lookback}}

{{cja-df-post}}

+++

+++**`mobilemessagebuttonname`**

從內容資料變數`a.message.button.id`中收集。用於應用程式內傳訊，以識別關閉訊息的按鈕。

{{cja-df-post}}

+++

+++**`mobilemessageid`**

應用程式內訊息 ID

{{cja-df-post}}

+++

+++**`mobilemessageonline`**

線上應用程式內訊息

{{cja-df-post}}

+++

+++**`mobilemessagepushoptin`**

從內容資料變數`a.push.optin`中收集。當使用者選擇加入推播訊息時，設為「true」；否則，值為「false」。

{{cja-df-post}}

+++

+++**`mobilemessagepushpayloadid`**

從內容資料變數`a.push.payloadid`中收集。用於推播訊息中，作為裝載識別碼。

{{cja-df-post}}

+++

+++**`mobileosversion`**

行動服務作業系統版本

{{cja-df-post}}

+++

+++**`mobileplaceaccuracy`**

從內容資料變數`a.loc.acc`中收集。指出 GPS 在採集時的準確度 (以公尺為單位)。

+++

+++**`mobileplacecategory`**

從內容資料變數`a.loc.category`中收集。說明特定位置的類別。

+++

+++**`mobileplaceid`**

從內容資料變數`a.loc.id`中收集。指定興趣點的識別碼。

+++

+++**`mobilepushoptin`**

行動服務推送選擇加入

{{cja-df-post}}

+++

+++**`mobilepushpayloadid`**

Mobile Services 推送承載 ID

{{cja-df-post}}

+++

+++**`mobilerelaunchcampaigncontent`**

行動服務上市內容

+++

+++**`mobilerelaunchcampaignmedium`**

行動服務上市媒體

+++

+++**`mobilerelaunchcampaignsource`**

行動服務上市來源

+++

+++**`mobilerelaunchcampaignterm`**

行動服務上市條件

+++

+++**`mobilerelaunchcampaigntrackingcode`**

從內容資料變數`a.launch.campaign.trackingcode`中收集。用於贏取中，作為上市促銷活動的追蹤代碼。

+++

+++**`mobileresolution`**

行動裝置的解析度。`[Width] x [Height]` 像素。

{{cja-df-post}}

+++

+++**`mobile_id`**
如果使用者使用行動裝置，則為裝置的數值 ID。

{{cja-df-lookup}}

+++

+++**`monthly_visitor`**

一個標幟，用來判斷該點擊是否為當月的不重複訪客。

+++

+++**`mvvar1`** - **`mvvar3`**

清單變數值。根據實施包含使用分隔符號的自訂值清單。`post_mvvar1` - `post_mvvar3` 欄會以 `--**--` 取代原始的分隔符號。

{{cja-df-post}}

+++

+++**`mvvar1_instances`** - **`mvvar3_instances`**

在目前點擊上設定的清單變數值。以 `--**--` 取代原始的分隔符號。`post` 欄位通常不包含資料。

{{cja-df-post}}

+++

+++**`new_visit`**

一個標幟，用來判斷目前的點擊是否為新造訪。在造訪閒置長達 30 分鐘後，由 Adobe 設定此值。

+++

+++**`os`**

代表訪客作業系統的數值 ID。依據 `user_agent` 欄而定。

{{cja-df-lookup}}

+++

+++**`pagename`**

頁面維度。 如果`pagename`變數為空白，Analytics 會改用`page_url`。

{{cja-df-post}}

+++

+++**`pagename_no_url`**

與 `pagename` 類似，但不會回復到 `page_url`。只有 `post` 列適用。

{{cja-df-post}}

+++

+++**`page_event`**

影像要求中傳送的點選型別（標準點選、下載連結、自訂連結、退出連結）。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`page_event_var1`**

僅用於連結追蹤影像要求。所點按的下載連結、退出連結或自訂連結的 URL。

{{cja-df-post}}

+++

+++**`page_event_var2`**

僅用於連結追蹤影像要求。連結的自訂名稱 (若有指定)。根據`page_event`中的值設定自訂連結、下載連結或退出連結。

{{cja-df-post}}

+++

+++**`page_type`**

找不到頁面維度，通常用於404頁。

{{cja-df-post}}

+++

+++**`page_url`**

**`page_url`**：點選的網址。 使用文字的資料型別。<br>**`post_page_url`**：連結追蹤影像要求(`tl()`)已移除。

{{cja-df-post}}

+++

+++**`paid_search`**

一個標幟，用來判斷該點擊是否符合付費搜尋偵測。

+++

+++**`persistent_cookie`**

用於永久性Cookie支援維度。 指示訪客是否支援不會在每次點擊後被捨棄的 cookie。

{{cja-df-post}}

+++

+++**`pointofinterest`**

行動服務興趣點名稱

{{cja-df-post}}

+++

+++**`pointofinterestdistance`**

行動服務與興趣點中心的距離

{{cja-df-post}}

+++

+++**`product_list`**

`products` 頁面變數。有助於填入數個維度和量度，包括類別、產品、件數和收入。

{{cja-df-post}}

+++

+++**`prop1`** - **`prop75`**

自訂流量變數 1 - 75。用於Prop維度。

{{cja-df-post}}

+++

+++**`purchaseid`**

使用`purchaseID`變數設定之購買的唯一識別碼。由`duplicate_purchase`欄使用。

`xdm.commerce.order.purchaseID`

{{cja-df-post}}

+++

+++**`quarterly_visitor`**

一個標幟，用來判斷該點擊是否為每季的新訪客。

+++

+++**`referrer`**

反向連結維度。 請注意，雖然 `referrer` 使用 varchar(255) 資料類型，但 `post_referrer` 是使用 varchar(244) 資料類型。

{{cja-df-post}}

+++

+++**`ref_domain`**

反向連結網域維度。 依據 `referrer` 欄而定。

+++

+++**`ref_type`**


代表點擊的反向連結類型的數值 ID。用於反向連結型別維度。<br>1：網站內<br>2：其他網站<br>3：搜尋引擎<br>4：硬碟<br>5：USENET<br>6：分類/建立書籤（無反向連結）<br>7：電子郵件<br>8：無JavaScript<br>9：社交網路<br>10：對話式AI工具

+++

+++**`resolution`**

代表螢幕解析度的數值 ID。用於熒幕解析度維度。

{{cja-df-lookup}}

+++

+++**`search_engine`**

代表將訪客反向連結至您的網站的搜尋引擎的數值 ID。用於搜尋引擎維度。

{{cja-df-post}}

{{cja-df-lookup}}

+++

+++**`search_page_num`**

供所有搜尋頁面排名維度使用。 在使用者點進您的網站之前，指示您的網站要顯示哪個搜尋結果頁面。

+++

+++**`secondary_hit`**

一個標幟，用來判斷該點擊是否為次要點擊。這個標幟通常來自多套裝標記和複製點擊的 VISTA 規則。

+++

+++**`sourceid`**

來源 ID

+++

+++**`stats_server`**

未使用。處理點擊的 Adobe 內部伺服器。

+++

+++**`s_kwcid`**

用於 Adobe Advertising 整合的關鍵字 ID。

{{cja-df-post}}

+++

+++**`s_resolution`**

原始螢幕解析度值。使用 JavaScript 函數`screen.width x screen.height`收集。

+++

+++**`tnt`**

用於 Adobe Target 整合。 代表目前符合條件的所有測試。 格式為：`TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`。

{{cja-df-post}}

+++

+++**`tnt_action`**

用於 Adobe Target 整合。 代表點擊合格的所有測試。

{{cja-df-post}}

+++

+++**`tnt_instances`**

用於 Adobe Target 整合。 Target 執行個體變數。

+++

+++**`transactionid`**

唯一識別碼，日後可透過資料來源上傳各種資料點。 使用`transactionID`變數收集。

`xdm.commerce.order.payments[0].transactionID`

{{cja-df-post}}

+++

+++**`truncated_hit`**

表示影像要求已截斷（收到部分點選）的旗標。 <br>Y：點擊遭截斷；收到部分點擊 <br>N：點擊未截斷；收到完整點擊

+++

+++**`t_time_info`**

訪客的當地時間。格式為：`M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)`

{{cja-df-post}}

+++

+++**`userid`**

未使用。報告套裝 ID 的數值 ID。請改用 `username`。

+++

+++**`username`**

點擊的報告套裝 ID。

+++

+++**`user_agent`**

在影像要求的 HTTP 標頭中發送的使用者代理字串。

+++

+++**`user_hash`**

未使用。報告套裝 ID 上的雜湊.請改用 `username`。

+++

+++**`user_server`**

用於伺服器維度。

{{cja-df-post}}

+++

+++**`va_closer_detail`**

上次接觸詳情維度。

+++

+++**`va_closer_id`**

可識別上次接觸管道維度的數值ID。

{{cja-df-lookup}}

+++

+++**`va_finder_detail`**

首次接觸詳情維度。

+++

+++**`va_finder_id`**

可識別首次接觸管道維度的數值ID。

{{cja-df-lookup}}

+++

+++**`va_instance_event`**

可識別行銷管道執行個體的旗標。

+++

+++**`va_new_engagement`**

可識別行銷管道新增參與的旗標。

+++

+++**`video`**

內容串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoad`**

廣告串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadinpod`**

Pod中的廣告定位串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadlength`**

廣告長度（變數）串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadname`**

廣告名稱（變數）串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadplayername`**

廣告播放器名稱串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadpod`**

廣告Pod串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoadvertiser`**

廣告商串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoaudioalbum`**

相簿串流媒體服務維度。

+++

+++**`videoaudioartist`**

藝人串流媒體服務維度。

+++

+++**`videoaudioauthor`**

作者串流媒體服務維度。

+++

+++**`videoaudiolabel`**

「標示串流媒體服務」維度。

+++

+++**`videoaudiopublisher`**

Publisher串流媒體服務維度。

+++

+++**`videoaudiostation`**

站台串流媒體服務維度。

+++

+++**`videocampaign`**

促銷活動ID串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videochannel`**

內容頻道串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videochapter`**

章節串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videocontenttype`**

內容型別串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videodaypart`**

日時段串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoepisode`**

劇集串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videofeedtype`**

媒體摘要型別串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videogenre`**

串流媒體服務維度。 此維度允許在同一個點擊中包含多個值，並以逗號分隔。

{{cja-df-post}}

+++

+++**`videolength`**

串流媒體服務維度的內容長度（變數）。

{{cja-df-post}}

+++

+++**`videomvpd`**

MVPD串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoname`**

內容名稱（變數）串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videonetwork`**

網路串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videopath`**

媒體路徑串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoplayername`**

內容播放器名稱串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoqoebitrateaverageevar`**

平均位元速率串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoqoebitratechangecountevar`**

位元速率會變更串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoqoebuffercountevar`**

緩衝事件串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoqoebuffertimeevar`**

串流媒體服務維度的總緩衝期間。

{{cja-df-post}}

+++

+++**`videoqoedroppedframecountevar`**

串流媒體服務掉格維度。

{{cja-df-post}}

+++

+++**`videoqoeerrorcountevar`**

串流媒體服務維度錯誤。

+++
{{cja-df-post}}


+++**`videoqoeextneralerrors`**

外部錯誤ID串流媒體服務維度。 此維度允許在同一個點擊中包含多個值。

+++

+++**`videoqoeplayersdkerrors`**

播放器SDK錯誤ID串流媒體服務維度。 此維度允許在同一個點擊中包含多個值。

{{cja-df-post}}

+++

+++**`videoqoetimetostartevar`**

開始串流媒體服務的時間維度。

{{cja-df-post}}

+++

+++**`videoseason`**

季節串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videosegment`**

串流媒體服務維度內容區段。

{{cja-df-post}}

+++

+++**`videosessionid`**

媒體工作階段ID串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoshow`**

顯示串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videoshowtype`**

顯示型別串流媒體服務維度。

{{cja-df-post}}

+++

+++**`videostreamtype`**

串流型別串流媒體服務維度。

+++

+++**`visid_high`**

搭配 `visid_low` 使用，以唯一碼來識別一位訪客。

{{cja-df-post}}

+++

+++**`visid_low`**

搭配 `visid_high` 使用，以唯一碼來識別一位訪客。

{{cja-df-post}}

+++

+++**`visid_new`**

一個標幟，用來判斷該點擊是否包含新生成的訪客 ID。

+++

+++**`visid_timestamp`**

如果是新產生的訪客 ID，則提供該訪客 ID 生成的 UNIX® 時間戳記。

+++

+++**`visid_type`**

不供外部使用；供 Adobe 在內部用來處理最佳化。代表用來識別訪客的方法的數值 ID。<br>`0`：自訂訪客 ID 或未知/不適用<br>`1`：IP 和用戶代理備援<br>`2`：HTTP 行動訂閱者標題<br>`3`：舊版 Cookie 值 (`s_vi`) <br>`4`：備援 Cookie 值 (`s_fid`) <br>`5`：身分識別服務

{{cja-df-post}}

+++

+++**`visit_keywords`**

搜尋關鍵字維度。 此欄使用非標準字元限制varchar(244)來容納Adobe使用的後端邏輯。 後續處理的資料行是`**post_keywords**`，而非`**post_visit_keywords**`。

{{cja-df-post}}

+++

+++**`visit_num`**

造訪次數維度。 從 1 開始，隨著每次訪客開始新的造訪而遞增。

+++

+++**`visit_page_num`**

點選深度維度。 每當訪客產生一次點擊，該數值增加 1。每次造訪都重設。

+++

+++**`visit_referrer`**

造訪的第一個反向連結。

+++

+++**`visit_ref_domain`**

依據`visit_referrer`欄而定。造訪的第一個反向連結網域。

+++

+++**`visit_ref_type`**

表示造訪的第一個反向連結的反向連結型別數值ID。

{{cja-df-lookup}}

+++

+++**`visit_search_engine`**

表示造訪的第一個搜尋引擎數值ID。

{{cja-df-lookup}}

+++

+++**`visit_start_pagename`**

造訪首次點選的頁面。

+++

+++**`visit_start_page_url`**

造訪之第一次點選的URL。

+++

+++**`visit_start_time_gmt`**

造訪的第一次點擊時間戳記 (根據 UNIX® 時間)。

+++

+++**`weekly_visitor`**

一個標幟，用來判斷該點擊是否為每週的新訪客。

+++

+++**`yearly_visitor`**

一個標幟，用來判斷該點擊是否為每年的新訪客。

+++

+++**`zip`**

協助填入郵遞區號維度。 另請參閱`geo_zip`。

{{cja-df-post}}

+++
