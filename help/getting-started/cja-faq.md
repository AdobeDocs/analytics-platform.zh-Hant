---
title: Customer Journey Analytics 常見問題集
description: Customer Journey Analytics - 常見問題集。
translation-type: tm+mt
source-git-commit: 3b3d0b0858d559e94f1bed6a31a63b018ed32a23
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 40%

---


# 常見問題集

## 必要條件

| 問題 | 回答 |
| --- | --- |
| 我需要 [!UICONTROL 專用設備圖] 或 [!UICONTROL 裝置合作基金] for [!UICONTROL 客戶歷程分析]? | 不， [!UICONTROL 專用設備圖] 或 [!UICONTROL 裝置合作基金] 不需要 [!UICONTROL 客戶歷程分析]. 事實上，目前尚未支援這兩項功能。 |
| 我需要 [!UICONTROL Experience Cloud ID] (ECID) [!UICONTROL 客戶歷程分析]? | 否，[!UICONTROL Customer Journey Analytics] 支援資料集中的任何 ID，不論是 ECID 或您選擇的任何其他 ID。 |
| 如果我需要在 [!UICONTROL 客戶歷程分析]? | 現在，如果您需要在將資料放入 AEP 之前先轉換資料，您必須與 ETL 合作夥伴 (Unifi 或 Informatica) 合作。如果您在資料已收錄後需要ETL, [!UICONTROL Adobe Experience Platform查詢服務] 提供一些有限的選項。 |

## 拼接資料

| 問題 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 可以在裝置或資料集之間「拼接」嗎？ | 是。[!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。2020年11月，我們發佈了一個縫合解決方案。 更多詳情. |
| 是否支援拼接匿名行為與已驗證的行為？ | 否，尚未支援。 |

## 將資料帶入 [!UICONTROL Customer Journey Analytics]

| 問題 | 回答 |
| --- | --- |
| 我是否可結合不同資料 [!UICONTROL Adobe Experience Platform] 單一沙盒 [!UICONTROL 客戶歷程分析] 連線？ | 否，您無法一次存取多個沙箱內的資料。您只能合併位於同一個沙箱中的資料集。[深入了解...](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 預期延遲的時間 [!UICONTROL 客戶歷程分析] on [!UICONTROL Adobe Experience Platform]? | <ul><li>正常負載下：小於 60 分鐘&#x200B;<br>**注意：**&#x200B;如果通過管道的資料流量特別多，則最多可能需要 24 小時。</li><li>回填資料 (無論大小，最多 13 個月的資料)：小於 4 週</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中將線上資料連結至離線資料？ | [!UICONTROL Customer Journey Analytics] 是「自攜 ID」的分析系統。只要人員 ID 在資料集之間相符，[!UICONTROL Customer Journey Analytics] 就可以在資料集之間連結區段、歸因、流量、流失等等。 |
| 如何將離線資料帶入 [!UICONTROL 客戶歷程分析]? | 您必須先將任何資料帶入Experience Platform，才能將其與 [!UICONTROL 客戶歷程分析]. 如有需要，Experience Platform 的資料入門團隊可為您提供建議或諮詢。 |
| 如何取得 [!UICONTROL Adobe Analytics] 資料 [!UICONTROL 客戶歷程分析]? | [!UICONTROL Adobe Analytics] 資料可透過 [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sources/connectors/adobe-applications/analytics.html). 最多 [!UICONTROL Adobe Analytics] 欄位會以XDM格式呈現，但其他欄位尚未提供(例如 [!UICONTROL 行銷渠道] 維度)。 |
| 將資料集元素組合成資料檢視需要多久時間？ | 需要數小時以開始使用，並且需要數天的時間來回填過去 13 個月的資料。 |
| 是否需要帶入 PII 資料來建立資料之間的連結？ | 否，您可以使用任何 ID，包括客戶 ID (非 PII) 的雜湊。 |

## 傳統 [!UICONTROL Adobe Analytics] 元件

| 問題 | 回答 |
| --- | --- |
| 這對我們的傳統 [!UICONTROL Adobe Analytics] 產品？ | [!UICONTROL Customer Journey Analytics 是我們新一代的分析產品。]從我們目前的產品，到 [!UICONTROL 客戶歷程分析] 需要數年的時間和大量的協調。 如需詳細資訊，請參閱 [Customer Journey Analytics 功能支援](/help/getting-started/cja-aa.md)。 |
| 我是否可從 [!UICONTROL 客戶歷程分析] AEP或其他解決方案？ | 還不可以。我們正在尋找新的創新方式來分享來自 [!UICONTROL 客戶歷程分析] 未來不會有這麼長延遲的AEP。 也就是說，您可以將 Query Service 的輸出分享至整合設定檔，作為可能的因應措施。 |
| 我的舊 eVar 設定有什麼改變？ | 傳統Adobe Analytics觀感中的eVar、prop和事件已不再存在於 [!UICONTROL 客戶歷程分析]. 您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | [!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會在「資料檢視」中顯示。]這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]這表示現有的區段或計算量度與 [!UICONTROL 客戶歷程分析]. |
| 如何 [!UICONTROL 客戶歷程分析] 把手 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 沒有唯一值限制，因此無需擔心這些限制！] |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 視情況而定。如果您重度依賴整合客戶流程 (UCP)，建議您等到我們實施拼接之後再改用。如果您已有高客戶驗證率、想將所有資料集中在一處，或是想要移除 eVar，Customer Journey Analytics 可能非常適合您。 |

## 刪除資料元件的含意

在刪除時，我們會考慮6個元件：沙盒、架構、資料集、連線、資料檢視和工作區專案。 以下是有關刪除其中任何元件的一些可能情況：

| 如果我…… | 這可能發生在下列情形... |
| --- | --- |
| 刪除沙盒(位於 [!UICONTROL Adobe Experience Platform]? | 刪除沙盒會中斷任何 [!UICONTROL 客戶歷程分析] 連線到沙盒中的資料集。 不過，CJA中的資料集目前不會刪除。 |
| 刪除中的架構 [!UICONTROL Adobe Experience Platform]，但與此模式關聯的資料集不是嗎？ | [!UICONTROL Adobe Experience Platform] 不允許刪除具有一個或多個與其關聯資料集的方案。 不過，具有適當權限集的管理員可以先刪除資料集，然後刪除架構。 |
| 刪除中的資料集 [!UICONTROL Adobe Experience Platform]? | 在 [!UICONTROL 客戶歷程分析];不過，如果啟用串流資料，刪除資料集後不會再有新資料傳入。<br>換言之，如果 **[!UICONTROL 從此連接中自動導入所有新資料集，從今天開始]** 在連線中，刪除資料集後不會再傳入新資料。 |
| 刪除中的資料集 [!UICONTROL 客戶歷程分析]? | 目前，您無法刪除已儲存連線中的資料集。 您必須刪除整個連接，然後重頭開始。 (不過，您可以刪除 [!UICONTROL Adobe Experience Platform].) |
| 從資料集刪除批次(在 [!UICONTROL Adobe Experience Platform])? | 如果批已被吸收到 [!UICONTROL 客戶歷程分析]的 [!UICONTROL 客戶歷程分析] 目前並不知道批已刪除。 如果批未被攝入，則當批刪除至 [!UICONTROL Adobe Experience Platform]. |
| 刪除批 **在被吸食的同時** into [!UICONTROL 客戶歷程分析]? | 如果資料集中只有一個批次，則該批次的資料或部分資料不會出現在 [!UICONTROL 客戶歷程分析]. 將回退攝取。 例如，如果資料集中有5個批次，且刪除資料集時已收錄其中3個批次，則這3個批次的資料會出現在 [!UICONTROL 客戶歷程分析]. |
| 刪除中的連接 [!UICONTROL 客戶歷程分析]? | 錯誤訊息會指出：<ul><li>為已刪除的連接建立的任何資料視圖將不再工作。</li><li> 同樣地，任何依賴已刪除連線中資料檢視的工作區專案都將停止運作。</li></ul> |
| 刪除 [!UICONTROL 客戶歷程分析]? | 錯誤訊息會指出任何依賴此已刪除資料檢視的工作區專案將停止運作。 |
| 刪除工作區專案於 [!UICONTROL 客戶歷程分析]? | 您可以重新建立項目，也可以使用解決方法恢復項目。 只要前往 [!UICONTROL 管理員>記錄檔>使用與存取記錄檔]，尋找已刪除的專案並複製其ID。 然後開啟任何工作區專案，並使用複製的專案更新URL中的ID。 然後儲存專案。 |
