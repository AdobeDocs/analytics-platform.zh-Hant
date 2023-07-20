---
title: Customer Journey Analytics 常見問題
description: Customer Journey Analytics - 常見問題。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '2196'
ht-degree: 69%

---

# 常見問題

Adobe Customer Journey Analytics是我們新一代的分析產品。 以下是有關Customer Journey Analytics常見問題的解答。 如需詳細資訊，請參閱「[Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)」。

## 1. 先決條件 {#prerequisites}

+++**是否需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop] 才能使用 [!UICONTROL Customer Journey Analytics]？**

否，使用 [!UICONTROL Customer Journey Analytics] 不需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop]。事實上，目前系統尚未支援這兩項功能。

+++


+++**是否需要 [!UICONTROL Experience Cloud ID] (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？**

否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的其他任何 ID 皆可使用。

+++


+++**如果我需要在使用 [!UICONTROL Customer Journey Analytics] 之前對我的資料執行 ETL 作業 (擷取、轉換、載入)，該怎麼辦？**

Customer Journey Analytics 包含[資料準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-Hant)功能，以協助您先轉換資料，然後再將資料放到 Adobe Experience Platform Data Lake 中。如果您在擷取資料後需要 ETL，[Adobe Experience Platform 查詢服務](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-Hant#queries)會提供一些有限的選項，但這些選項可能需要額外付費。

+++


## 2.彙整資料 {#stitching}

+++**[!UICONTROL Customer Journey Analytics] 是否可以在裝置或資料集之間「拼接」(彙整) 資料嗎？**

是。[!UICONTROL Customer Journey Analytics] 有 [拼接](../stitching/overview.md) 可在資料集內已驗證和未驗證事件間運作的功能。 這樣可將不同的記錄解析為單一拼接ID，以在人員層級進行跨裝置分析。
此外，在中跨資料集使用通用名稱空間ID （人員ID）時， [連線](/help/connections/overview.md)，您將能夠對多個資料集的無縫組合執行分析，並在人員層級「拼接」。

+++


+++**是否支援拼接匿名行為與已驗證的行為？**

是。[拼接](../stitching/overview.md) 會檢視已驗證和未驗證工作階段的使用者資料，以產生拼接ID。

+++


+++**「重播」在彙整中如何運作？**

根據所掌握的唯一識別碼拼接「重播」資料。 重播旨在拼接來自同時已識別之裝置的初始未驗證事件。 [了解更多](../stitching/explained.md)

+++


+++**拼接歷史資料（回填）如何運作？**

初次開啟此功能時，Adobe 將提供回填的拼接資料，其回溯時間可追溯到上個月初 (最長 60 天)。為了執行此回填，當時的未拼接資料中必須存在暫時性 ID。[了解更多](../stitching/explained.md)

+++


+++**非拼接設定檔資料集記錄的預期行為是什麼？**

**範例情境**：您使用在Customer Journey Analytics連線中聯結2個資料集 `CRMid` 作為個人ID。 一種是在所有記錄中具有 `CRMid`的 Web 事件資料集。另一個資料集是 CRM 設定檔資料集。40% 的 CRM 資料集在 Web 事件資料集中存在 `CRMid`。其他 60% 不存在於 Web 事件資料集中 - 這些記錄是否出現在 Analysis Workspace 的報告中？<p> **答案**：沒有事件關聯的設定檔列會以Customer Journey Analytics儲存。 但是，在與該 ID 關聯的事件出現之前，您無法在 Analysis Workspace 中查看它們。

+++

## 3. 將資料帶入 [!UICONTROL Customer Journey Analytics] {#ingest}

+++**我可以合併同一個 [!UICONTROL Customer Journey Analytics] 連線中不同 [!UICONTROL Adobe Experience Platform] 沙箱的資料嗎？**

不可以，您無法一次存取多個沙箱內的資料，只能合併同一個沙箱中的資料集。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#select-sandbox-and-datasets)

+++


+++**如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？**

只要資料集之間的個人 ID 相符，[!UICONTROL Customer Journey Analytics] 就可連接篩選器、歸因、流量、流失等。。

+++


+++**如何將離線資料帶入 [!UICONTROL Customer Journey Analytics]？**

您對 Customer Journey Analytics 的權益可讓您將資料擷取到 Experience Platform。然後您可以在 [!UICONTROL Customer Journey Analytics] 中建立與該資料和資料檢視的連線，以便在 Analysis Workspace 中報告。如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。

+++


+++**如何將 [!UICONTROL Adobe Analytics] 資料帶入 [!UICONTROL Customer Journey Analytics]？**

[!UICONTROL Adobe Analytics] 資料可透過以下連結至Experience Platform： [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant). 大部分的 [!UICONTROL Adobe Analytics] 欄位都會以 XDM 格式帶入，但其他欄位則尚未開放使用。

+++


+++**將資料集元素組合成資料檢視需要多久時間？**

需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。

+++


+++**是否需要帶入 PII 資料來建立資料之間的連結？**

否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。

+++


+++**擷取過去或未來的日期/時間戳記至Customer Journey Analytics事件資料集的限制有哪些？**

<ul><li>在過去日期/時間戳記方面：事件資料最久為 10 年。</li><li>在未來日期/時間戳記方面：事件資料 (預測性) 最久為未來 1 個月。</li></ul>

+++


## 4. 延遲的注意事項 {#latency}

>[!NOTE]
>Customer Journey Analytics中沒有固定的資料大小，因此Adobe無法指定標準擷取時間。 我們正在積極努力透過新的更新和擷取最佳化，減少這些延遲。

<ul><li>即時資料或事件：當資料可在Adobe Experience Platform中使用時，在90分鐘內處理和擷取。 (批次大小 &gt; 5 千萬列：90 分鐘以上。)</li><li>小型回填：7天內<li>大型回填：30天內</li></ul>

我們最近變更了處理Customer Journey Analytics中資料的方式：

<ul><li>任何時間戳記不到 24 小時的事件資料都會串流進入。</li><li>任何時間戳記超過 24 小時的事件資料 (即使與較新的資料屬於同一批次) 都視為回填，並將以較低的優先順序擷取。</li></ul>

## 5. 設定[!UICONTROL 連線]資料保留的滾動時段 {#data-retention}

此 [**[!UICONTROL 啟用滾動資料時段&#x200B;]**設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#create-connection) 可讓您將Customer Journey Analytics資料保留定義為單位為月數的滾動時段（3個月、6個月等）。 這是在[!UICONTROL 連接]層級設定，而不是[!UICONTROL 資料集]層級。資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此基本資料或查詢資料集不存在資料保留設定。

主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。

## 6. 刪除資料元件的影響 {#deletion}

關於資料的刪除，我們會考慮 6 種元件：沙箱、結構描述、資料集、連線、資料檢視和「工作區」專案。以下是刪除上述任何元件後的一些可能情況：

| 若您... | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的沙箱 | 刪除沙箱時，將會讓資料停止流向該沙箱中資料集的任何 [!UICONTROL Customer Journey Analytics] 連線。目前， [!UICONTROL 連線] 不會自動刪除與被刪除的沙箱繫結的Customer Journey Analytics中。 |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的結構描述，但不刪除與此結構描述相關聯的資料集 | [!UICONTROL Adobe Experience Platform] 不允許刪除與一或多個[!UICONTROL 資料集]相關聯的[!UICONTROL 結構描述]。不過，擁有適當權限的管理員可以先刪除資料集，再刪除結構描述。 |
| 刪除 [!UICONTROL Adobe Experience Platform] Data Lake 中的資料集 | 刪除Adobe Experience Platform Data Lake中的資料集，會使該資料集的資料停止流向包含該資料集的任何Customer Journey Analytics連線。 系統會從關聯的Customer Journey Analytics連線中自動刪除該資料集中的任何資料。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 請聯絡您的Adobe客戶團隊，以啟動刪除已儲存連線中的資料集的程式。 |
| 從資料集中刪除批次 (在 [!UICONTROL Adobe Experience Platform] 中) | 如果從「 」中刪除批次 [!UICONTROL Adobe Experience Platform] 該批次會從包含該特定批次的任何Customer Journey Analytics連線中移除。  Customer Journey Analytics會收到批次刪除的通知 [!UICONTROL Adobe Experience Platform]. |
| 當批次&#x200B;**正要擷取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中時將它刪除 | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有5筆批次資料，其中3筆在資料集遭刪除前就已匯入完成，則該3筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]. |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何「工作區」專案與所刪除連線中的資料檢視相依，也將停止運作。</li></ul> |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視 | 錯誤訊息會指出，與這個已刪除的資料檢視相依的任何Workspace專案都將停止運作。 |

## 7.以Customer Journey Analytics合併報表套裝時的注意事項 {#merge-reportsuite}

如果您計劃透過 [Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)擷取 Adobe Analytics 資料，請在合併 2 個或多個 Adobe Analytics 報表套裝時考慮這些後果。

| 問題 | 考量事項 |
| --- | --- |
| 變數 | [!UICONTROL eVars] 等變數可能不會跨報表套裝排列。例如，報表套裝 1 中的 eVar1 可能指向&#x200B;**[!UICONTROL 頁面]**。在報表套裝 2 中，eVar1 可能指向&#x200B;**[!UICONTROL 內部行銷活動]**，因而導致混合和不準確的報表。 |
| [!UICONTROL 工作階段]和[!UICONTROL 人員]計數 | 它們會跨報表套裝進行重複資料刪除。因此，計數可能不相符。 |
| 量度重複資料刪除 | 如果多列具有相同的交易 ID (例如，[!UICONTROL 購買 ID])，則對量度的實例 (例如[!UICONTROL 訂單]) 進行重複資料刪除。這可以防止過度計算關鍵量度。因此，像[!UICONTROL 訂單]這樣的量度可能不會跨報表套裝累加。 |
| 貨幣 | Customer Journey Analytics尚不支援貨幣轉換。 如果您嘗試合併的報表套裝使用不同的基礎貨幣，則可能會出現問題。 |
| [!UICONTROL 持續性] | [持續性](../data-views/component-settings/persistence.md)跨報表套裝擴展，這會影響[!UICONTROL 篩選]、[!UICONTROL 歸因]等。數字可能無法正確相加。 |
| [!UICONTROL 分類] | 合併報表套裝時，[!UICONTROL 分類]不會自動進行重複資料刪除。將多個分類檔案合併為單一時 [!UICONTROL 查詢] 資料集，您可能會遇到問題。 |

## 8. [!UICONTROL Adobe Analytics] 元件

+++**我可以共用/發佈嗎 [!UICONTROL 篩選器] 從 [!DNL Customer Journey Analytics] Experience PlatformReal-Time CDP或其他Experience Cloud應用程式？**

還不行，我們正在積極努力地提供這項功能。

+++

+++**我的舊 [!UICONTROL eVar] 設定發生了什麼事？**

[!UICONTROL eVar]， [!UICONTROL prop]、和 [!UICONTROL 事件] 在Adobe Analytics中，已不存在於 [!UICONTROL Customer Journey Analytics]. 您有不限數量的結構描述元素 (維度、量度、清單欄位)。因此，您曾在資料收集流程期間套用的所有歸因設定，現在都會在查詢時套用。

+++

+++**我所有的工作階段和變數持續性設定現在位於何處？**

[!UICONTROL Customer Journey Analytics] 會在報告時套用這些設定，而這些設定現在會顯示在資料檢視中。 對這些設定的變更現在可回溯，您可以使用多個資料檢視擁有多個版本！

+++

+++**我們現有的區段/計算量度有何改變？**

[!UICONTROL Customer Journey Analytics] 不再使用eVar、prop或事件，而是使用Adobe Experience Platform結構描述。 換句話說，現有的區段或計算量度都會與 [!UICONTROL Customer Journey Analytics] 不相容。

+++

+++**[!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？**

[!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！]

+++

+++**如果我是現有 [!DNL Data Workbench]客戶，現在是否可以改用 Customer Journey Analytics？**

這取決於您的使用案例 - 請與您的 Adobe 帳戶團隊合作。您目前的使用案例可能已經很適合使用 Customer Journey Analytics！

+++

## 9. 估算連線規模 {#estimate-size}

請參閱[估計和管理使用情況](/help/admin/estimate-usage.md)。

## 10. 關於使用超額 {#overage}

Adobe 會定期監控和執行使用量限額。「資料列」指可用於 Customer Journey Analytics 中分析的每日平均資料列。

例如，如果您的合約讓您有權使用 100 萬筆資料列。假設在使用 Customer Journey Analytics 的第 1 天，您可以上傳 200 萬筆資料列。您要在第 2 天刪除 100 萬筆資料列，並在剩餘的授權期限內將使用量維持在最大使用量 (即 100 萬筆資料列) 以內。根據您的合約條款，由於您超出了「資料列」授權權利，您仍然可能需支付按比例計算的第 1 天超額使用費。

## 11. 診斷資料差異 {#discrepancies}

在部分情況下，您可能會發現連線所擷取的事件總數與 [!UICONTROL Adobe Experience Platform] 資料集中的列數不同。在此範例中，資料集「B2B Impression」有 7,650 列，但資料集在 [!UICONTROL Adobe Experience Platform] 中僅有 3,830 列。數據不一致有幾個原因，您可採取下列步驟加以診斷：

1. 此維度的劃分依據 **[!UICONTROL 平台資料集ID]** 而且您會發現兩個大小相同但大小不同的資料集 **[!UICONTROL 平台資料集ID]**. 每個資料集有 3,825 筆記錄，表示有 5 筆記錄缺少人員 ID 或時間戳記，導致 [!UICONTROL Customer Journey Analytics] 忽略了這些記錄：

   ![劃分](assets/data-size2.png)

1. 此外，如果我們簽入 [!UICONTROL Adobe Experience Platform]，沒有ID為「5f21c12b732044194bffc1d0」的資料集，因此有人將此特定資料集從「 」中刪除 [!UICONTROL Adobe Experience Platform] 建立初始連線的時間。 稍後，系統再次將其新增至Customer Journey Analytics，但新增了其他專案 [!UICONTROL 平台資料集ID] 產生者： [!UICONTROL Adobe Experience Platform].

深入了解在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[刪除資料集和連線可能造成的後果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
