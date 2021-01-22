---
title: Customer Journey Analytics 常見問題集
description: Customer Journey Analytics - 常見問題集。
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '1235'
ht-degree: 100%

---


# 常見問題集

## 先決條件

| 問題 | 回答 |
| --- | --- |
| 是否需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop] 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，使用 [!UICONTROL Customer Journey Analytics] 不需要 [!UICONTROL Private Device Graph] 或 [!UICONTROL Device Coop]。事實上，目前系統尚未支援這兩項功能。 |
| 是否需要 [!UICONTROL Experience Cloud ID] (ECID) 才能使用 [!UICONTROL Customer Journey Analytics]？ | 否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的其他任何 ID 皆可使用。 |
| 如果我需要在使用 [!UICONTROL Customer Journey Analytics] 之前對我的資料執行 ETL 作業 (擷取、轉換、載入)，該怎麼辦？ | 現在，如果您需要在將資料放入 AEP 前先行轉換資料，您必須與 ETL 合作夥伴 (Unifi 或 Informatica) 合力處理。如果您需要在資料匯入後執行 ETL 作業，[!UICONTROL Adobe Experience Platform Query Services] 僅會提供幾個選項。 |

## 彙整資料

| 問題 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 可以在裝置或資料集之間「拼接」(彙整) 資料嗎？ | 可以。[!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。我們已在 2020 年 11 月發佈彙整作業的解決方案。深入了解。 |
| 是否支援彙整匿名行為與已驗證的行為？ | 否，系統尚未支援此功能。 |

## 將資料帶入 [!UICONTROL Customer Journey Analytics]

| 問題 | 回答 |
| --- | --- |
| 我可以合併同一個 [!UICONTROL Customer Journey Analytics] 連線中不同 [!UICONTROL Adobe Experience Platform] 沙箱的資料嗎？ | 不可以，您無法一次存取多個沙箱內的資料，只能合併同一個沙箱中的資料集。[深入了解...](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform] 上 [!UICONTROL Customer Journey Analytics] 的延遲時間預計會多久？ | <ul><li>正常負載下：小於 60 分鐘&#x200B;<br>**注意：**&#x200B;如果通過管道的資料流量特別多，則最多可能需要 24 小時。</li><li>回填資料 (無論大小，最多 13 個月的資料)：小於 4 週</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？ | [!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。只要人員 ID 在資料集之間相符，[!UICONTROL Customer Journey Analytics] 就可以在資料集之間連結區段、歸因、流量、流失等等。 |
| 如何將離線資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您必須先將資料帶入 Experience Platform，才能透過 [!UICONTROL Customer Journey Analytics] 使用。如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。 |
| 如何將 [!UICONTROL Adobe Analytics] 資料帶入 [!UICONTROL Customer Journey Analytics]？ | 您可透過 [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/connectors/adobe-applications/analytics.html)，將 [!UICONTROL Adobe Analytics] 資料連結至 Experience Platform。大部分的 [!UICONTROL Adobe Analytics] 欄位都會以 XDM 格式帶入，但其他欄位尚未開放使用 (例如[!UICONTROL 「行銷管道」]維度)。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |

## 舊版 [!UICONTROL Adobe Analytics] 元件

| 問題 | 回答 |
| --- | --- |
| 這對舊版的 [!UICONTROL Adobe Analytics] 產品有何意義？ | [!UICONTROL Customer Journey Analytics 是我們新一代的分析產品。]從我們目前的產品改用 [!UICONTROL Customer Journey Analytics] 需要數年時間，且需大量的協調工作。如需詳細資訊，請參閱 [Customer Journey Analytics 功能支援](/help/getting-started/cja-aa.md)。 |
| 我可不可以將區段從 [!UICONTROL Customer Journey Analytics] 分享至 AEP 或其他解決方案？ | 還不可以。我們正在研究新的創新方法，以便能在日後將區段從 [!UICONTROL Customer Journey Analytics] 分享至 AEP，同時縮短延遲時間。也就是說，您可以將 Query Service 的輸出分享至整合設定檔，作為可能的因應措施。 |
| 我的舊 eVar 設定有什麼改變？ | [!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 eVar、prop 和事件。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | [!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會顯示於「資料檢視」。]這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]換句話說，現有的區段或計算量度都會與 [!UICONTROL Customer Journey Analytics] 不相容。 |
| [!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！] |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 視情況而定。如果您重度依賴整合客戶流程 (UCP)，建議您等到我們實作彙整功能後再改用。如果您已有高客戶驗證率、想將所有資料集中在一處，或是想要移除 eVar，Customer Journey Analytics 可能非常適合您。 |

## 刪除資料元件可能的後果

刪除時，我們會考慮 6 個元件：沙箱、結構描述、資料集、連線、資料檢視和 Analysis Workspace 專案。刪除其中任一元件的部分可能情況如下：

| 如果我… | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的沙箱？ | 刪除沙箱會讓傳送到任一 [!UICONTROL Customer Journey Analytics] 連線的資料停止傳輸至該沙箱中的資料集。目前，系統不會自動刪除與該沙箱繫結的 CJA 連線。 |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的結構描述，但不刪除與此結構描述相關聯的資料集？ | [!UICONTROL Adobe Experience Platform] 不允許刪除與一或多個資料集相關聯的結構描述。不過，擁有適當權限的管理員可以先刪除資料集，再刪除結構描述。 |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的資料集？ | 如果刪除 AEP 中的資料集，該資料集的資料將不再傳輸至包含該資料集的任何連線。該資料集中的任何資料不會從關聯的 CJA 連線中自動刪除。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集？ | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(不過您可以刪除 [!UICONTROL Adobe Experience Platform] 中的資料集)。 |
| (在 [!UICONTROL Adobe Experience Platform] 中) 從資料集刪除批次資料？ | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 CJA 連線中移除。[!UICONTROL Adobe Experience Platform] 中的批次資料刪除後，CJA 會收到相關通知。 |
| 將&#x200B;**匯入** [!UICONTROL Customer Journey Analytics] 的批次資料刪除？ | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線？ | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何 Analysis Workspace 專案需仰賴所刪除連線中的資料檢視，也將停止運作。</li></ul> |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視？ | 錯誤訊息會指出，仰賴這個已刪除資料檢視的 Analysis Workspace 專案會停止運作。 |
