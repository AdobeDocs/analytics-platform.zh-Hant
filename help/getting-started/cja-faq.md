---
title: Customer Journey Analytics 常見問答
description: Customer Journey Analytics - 常見問答。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: 719b67049456be857431ee1a7ca97e9f0fd881ee
workflow-type: ht
source-wordcount: '1646'
ht-degree: 100%

---

# 常見問答

[!UICONTROL Customer Journey Analytics] (CJA) 是我們新一代的分析產品。 以下是有關 CJA 常見問題的解答。 如需詳細資訊，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/cja-aa.md)」。

## 1. 先決條件

| 問題 | 回答 |
| --- | --- |
| 是否需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop] 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，使用 [!UICONTROL Customer Journey Analytics] 不需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop]。事實上，目前系統尚未支援這兩項功能。 |
| 是否需要 [!UICONTROL Experience Cloud ID] (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的其他任何 ID 皆可使用。 |
| 如果我需要在使用 [!UICONTROL Customer Journey Analytics] 之前對我的資料執行 ETL 作業 (擷取、轉換、載入)，該怎麼辦？ | Customer Journey Analytics 包含[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-Hant)功能，以協助您先轉換資料，然後再將資料放到 Adobe Experience Platform Data Lake 中。 如果您在擷取資料後需要 ETL，[Adobe Experience Platform 查詢服務](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-Hant#queries)會提供一些有限的選項，但這些選項可能需要額外付費。 |

{style=&quot;table-layout:auto&quot;}

## 2. 拼接資料 (跨管道分析)

| 問題 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否可以在裝置或資料集之間「拼接」(彙整) 資料嗎？ | 是。 [!UICONTROL Customer Journey Analytics] 有一個稱為[跨管道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hant) (CCA) 的拼接解決方案。 它可讓您重新輸入資料集的人員 ID，好讓您順暢地合併多個資料集。 |
| 是否支援拼接匿名行為與已驗證的行為？ | 是。 [跨管道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hant)會檢視已驗證和未驗證工作階段的使用者資料，以產生拼接 ID。 |
| CCA 中的「重播」是如何運作的？ | CCA 會根據所掌握的唯一識別碼來「重播」資料。 重播會使得連線的新裝置被拼接。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=zh-Hant#step-1%3A-live-stitching) |
| CCA 中的拼接歷史 (回填) 資料是如何運作的？ | 初次開啟此功能時，Adobe 將提供回填的拼接資料，其回溯時間可追溯到上個月初 (最長 60 天)。 為了執行此回填，當時的未拼接資料中必須存在暫時性 ID。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hant#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. 將資料帶入 [!UICONTROL Customer Journey Analytics]

| 問題 | 回答 |
| --- | --- |
| 我可以合併同一個 [!UICONTROL Customer Journey Analytics] 連線中不同 [!UICONTROL Adobe Experience Platform] 沙箱的資料嗎？ | 不可以，您無法一次存取多個沙箱內的資料，只能合併同一個沙箱中的資料集。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#select-sandbox-and-datasets) |
| 如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？ | 只要資料集之間的個人 ID 相符，[!UICONTROL Customer Journey Analytics] 就可連接篩選器、歸因、流量、流失等。。 |
| 如何將離線資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您對 Customer Journey Analytics 的權益可讓您將資料擷取到 Experience Platform。 然後您可以在 [!UICONTROL Customer Journey Analytics] 中建立與該資料和資料檢視的連線，以便在 Analysis Workspace 中報告。 如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。 |
| 如何將 [!UICONTROL Adobe Analytics] 資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您可透過 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)，將 [!UICONTROL Adobe Analytics] 資料連結至 Experience Platform。大部分的 [!UICONTROL Adobe Analytics] 欄位都會以 XDM 格式帶入，但其他欄位則尚未開放使用。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |
| 擷取過去或未來的日期/時間戳記至 CJA 事件資料集的限制有哪些？ | <ul><li>在過去日期/時間戳記方面：事件資料最久為 10 年。</li><li>在未來日期/時間戳記方面：事件資料 (預測性) 最久為未來 1 個月。</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 4. 延遲的注意事項

>[!NOTE]
>CJA 中沒有固定的資料大小，因此 Adobe 無法指定標準的擷取時間。我們正在積極努力透過新的更新和擷取最佳化，減少這些延遲。

| 問題 | 回答 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform] 上的 [!UICONTROL Customer Journey Analytics] 延遲時間預計會多久？ | <ul><li>即時資料或事件：資料在 AEP 上可供使用時，在 90 分鐘內完成處理和擷取。(批次大小 > 5 千萬列：90 分鐘以上。)</li><li>小型回填 - 例如，1 千萬列的查詢資料集：24 小時以內<li>大型回填 - 例如，5 百億列：30 天</li></ul> |


## 5. 傳統 [!UICONTROL Adobe Analytics] 元件

| 問題 | 回答 |
| --- | --- |
| 我可以將 [!DNL Customer Journey Analytics] 中的[!UICONTROL 篩選器] ([!UICONTROL 區段]) 共用/發佈到 Experience Platform Unified Profile 或其他 Experience Cloud 應用程式嗎？ | 還不行，我們正在積極努力地提供這項功能。 |
| 我的舊 [!UICONTROL eVar] 設定發生了什麼事？ | [!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 [!UICONTROL eVar]、[!UICONTROL prop] 和 [!UICONTROL event]。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | [!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會顯示於「資料檢視」。]這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]換句話說，現有的區段或計算量度都會與 [!UICONTROL Customer Journey Analytics] 不相容。 |
| [!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！] |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 這取決於您的使用案例 - 請與您的 Adobe 帳戶團隊合作。 您目前的使用案例可能已經很適合使用 Customer Journey Analytics！ |

{style=&quot;table-layout:auto&quot;}

## 6. 刪除資料元件的影響

關於資料的刪除，我們會考慮 6 種元件：沙箱、結構描述、資料集、連線、資料檢視和「工作區」專案。 以下是刪除上述任何元件後的一些可能情況：

| 若您... | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的沙箱 | 刪除沙箱時，將會讓資料停止流向該沙箱中資料集的任何 [!UICONTROL Customer Journey Analytics] 連線。 目前，系統不會自動刪除與被刪除的沙箱繫結的 CJA [!UICONTROL 連線]。 |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的結構描述，但不刪除與此結構描述相關聯的資料集 | [!UICONTROL Adobe Experience Platform] 不允許刪除與一或多個[!UICONTROL 資料集]相關聯的[!UICONTROL 結構描述]。不過，擁有適當權限的管理員可以先刪除資料集，再刪除結構描述。 |
| 刪除 [!UICONTROL Adobe Experience Platform] Data Lake 中的資料集 | 如果刪除 AEP Data Lake 中的資料集，該資料集的資料將停止流向包含該資料集的任何 CJA 連線。 系統不會從關聯的 CJA 連線中自動刪除該資料集中的任何資料。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(然而，已購買 CJA SKU 的客戶可以在 [!UICONTROL Adobe Experience Platform] 使用者介面中刪除資料集。) |
| 從資料集中刪除批次 (在 [!UICONTROL Adobe Experience Platform] 中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 CJA 連線中移除。[!UICONTROL Adobe Experience Platform] 中的批次資料刪除後，CJA 會收到相關通知。 |
| 當批次&#x200B;**正要擷取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中時將它刪除 | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何「工作區」專案與所刪除連線中的資料檢視相依，也將停止運作。</li></ul> |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視 | 錯誤訊息會指出，與這個已刪除的資料檢視相依的任何「工作區」專案都將停止運作。 |

## 7. 在 CJA 中合併報表套裝時的注意事項

如果您計劃透過 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)擷取 Adobe Analytics 資料，請在合併 2 個或多個 Adobe Analytics 報表套裝時考慮這些後果。

| 問題 | 考量事項 |
| --- | --- |
| 變數 | [!UICONTROL eVars] 等變數可能不會跨報表套裝排列。例如，報表套裝 1 中的 eVar1 可能指向&#x200B;**[!UICONTROL 頁面]**。在報表套裝 2 中，eVar1 可能指向&#x200B;**[!UICONTROL 內部行銷活動]**，因而導致混合和不準確的報表。 |
| [!UICONTROL 工作階段]和[!UICONTROL 人員]計數 | 它們會跨報表套裝進行重複資料刪除。因此，計數可能不相符。 |
| 量度重複資料刪除 | 如果多列具有相同的交易 ID (例如，[!UICONTROL 購買 ID])，則對量度的實例 (例如[!UICONTROL 訂單]) 進行重複資料刪除。這可以防止過度計算關鍵量度。因此，像[!UICONTROL 訂單]這樣的量度可能不會跨報表套裝累加。 |
| 貨幣 | CJA 尚不支援貨幣轉換。如果您嘗試合併的報表套裝使用不同的基礎貨幣，則可能會出現問題。 |
| [!UICONTROL 持續性] | [持續性](../data-views/component-settings/persistence.md)跨報表套裝擴展，這會影響[!UICONTROL 篩選]、[!UICONTROL 歸因]等。數字可能無法正確相加。 |
| [!UICONTROL 分類] | 合併報表套裝時，[!UICONTROL 分類]不會自動進行重複資料刪除。將多個分類檔案合併為單一[!UICONTROL 查閱]資料集時，您可能會遇到問題。 |