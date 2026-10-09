---
title: 品牌可見度傳入整合設定
description: 瞭解如何設定Brand Visibility與Customer Journey Analytics的整合
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fbbb3ffb1b0d1d5361b594e81c260dab25f44338
workflow-type: tm+mt
source-wordcount: '1783'
ht-degree: 0%
---
# 設定和設定傳入整合

本文詳細說明設定和設定Brand Visibility與Customer Journey Analytics的輸入整合的[先決條件](#prerequisites)、[責任](#responsibilities)、[驗證](#verification)的步驟、[疑難排解步驟](#troubleshoot)以及[完成條件](#completion-criteria)。

## 先決條件

啟用傳入整合前，請先考量下列必要條件。 並使用驗證程式來驗證

### BYOCDN記錄轉送

在品牌可見度來源聯結器可行之前，每個品牌可見度網站的CDN存取記錄檔必須轉送至Adobe Brand Visibility並由其接收。

此要求適用於每個品牌可見度網站。 一個網站、網域或子網域的CDN設定或記錄檔摘要僅涵蓋該網站，除非Adobe確認另一個網站的涵蓋範圍。

透過Adobe驗證移交的兩部分：

1. 您已設定相關的CDN或記錄管道將所需的存取記錄轉送至Adobe提供的Amazon S3目的地。
1. Adobe已確認收到並偵測到相關網站的記錄。

BYOCDN記錄轉送提供用於自動化代理程式流量分析的伺服器端CDN要求資料。 資料並不取決於瀏覽器中執行的JavaScript標籤。 必要的
CDN記錄摘要可確保下游摘要資料集包含預期的品牌可見度代理流量資料。 如需詳細資訊，請參閱[BYOCDN記錄檔轉送參考](https://experienceleague.adobe.com/zh-hant/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)。

### 必要資訊

確保您擁有下表所列每個品牌可見度網站的所有必要詳細資訊的值。

| 必要值 | 驗證或附註 |
|---|---|
| 品牌可見度網站或網域 | 確認CDN記錄轉送涵蓋的網站。 |
| CDN供應商 | 識別提供網站的CDN。 |
| CDN記錄轉送狀態 | 證明網站記錄已轉送並由品牌可見度偵測。 |
| 品牌可見度整備確認 | 啟用及排程聯結器之前，請先向Adobe客戶團隊確認整備程度。 |
| IMS組織 | 使用與Brand Visibility Experience Platform相關的確切IMS組織。 |
| 沙箱 | 使用針對傳入整合指定的確切沙箱名稱。 |
| 連線 | 識別應包含資料集的Customer Journey連線。 |
| 資料視圖 | 識別應包含元件的新資料檢視或現有Customer Journey Analytics資料檢視。 |
| 管理員或擁有者 | 提供組態連絡人的名稱或團隊。 |

在Adobe排程Managed Connector之前，您的Adobe帳戶團隊必須確認網站已準備好進行傳入整合。 傳遞通訊稱為品牌可見度核准或網站整備確認。 排程Managed Connector是Managed Service需求，而非客戶自助服務動作。

### 沙箱

Managed聯結器必須在IMS組織內客戶指定的特定命名AEP沙箱中建立資料集。

確認下列專案：

* IMS 組織
* Target Experience Platform沙箱

目標AEP沙箱與對應的Customer Journey Analytics連線或包含資料集的連線所使用的命名沙箱相同。

只有在Adobe確認受管理的資料集已建立後，客戶才能將資料集新增至適當的CJA連線。

### 摘要資料集

傳入整合提供Experience Platform中的彙總摘要資料集，其中包含與LLM、機器人和自動化代理程式相關聯的伺服器端CDN請求資訊
流量。

Brand Visibility會使用CDN存取記錄檔來識別來自機器人和自動化代理程式的請求。 此流量不會觸發瀏覽器JavaScript標籤，因此不會透過傳統的網頁分析實作來擷取。

如需傳入整合、資料集結構和可用欄位的詳細說明，請參閱[關於資料集](#about-the-dataset)。

Managed Connector會使用以下專案在Experience Platform中建立摘要資料集：

* **[!UICONTROL XDM摘要量度]**&#x200B;類別
* **[!UICONTROL CDN要求摘要]**&#x200B;欄位群組
* 在&#x200B;**[!UICONTROL cdn]**&#x200B;物件下組織的欄位

聯結器會使用下列命名模式，為每個品牌可見度網站建立資料集： <code>Adobe Brand Visibility (ABV)資料集 — _baseUrl （不含Scheme_）</code>. <br/>例如<https://example.com>網站的`Adobe Brand Visibility (ABV) Dataset - example.com`。

在採用此命名慣例之前建立的資料集會顯示舊版模式<code>LLM最佳化(LLMO)資料集 — _baseUrl （不含scheme_）</code>.
在任何情況下，客戶都需要在建立後與其Adobe帳戶團隊確認確切的資料集名稱或資料集ID。

資料集是彙總摘要資料。 在Customer Journey Analytics中分析請求磁碟區時，請使用提供的&#x200B;**[!UICONTROL CDN請求計數]**&#x200B;量度，而不是計算資料集列。

驗證為特定品牌可見度網站建立的資料集結構描述中的可用欄位。 若要規劃資料檢視的設定，請檢閱欄位。

## 責任

Adobe會管理傳入聯結器，且在確認先決條件後：

* 啟用Managed ABV → AEP聯結器。
* 為每個已設定的ABV網站建立摘要資料集。
* 在客戶提供的AEP沙箱中登陸資料集。
* 提供客戶資料集名稱或資料集ID以進行驗證。

您身為客戶的責任如下：

* 確保CDN記錄檔轉送至每個品牌可見度網站，並由其品牌可見度接收。
* 提供正確的IMS組織和已命名的Experience Platform沙箱。
* 若要選取應包含資料集的Customer Journey Analytics連線。
* 將資料集新增至該連線的方式。
* 在相關的Customer Journey Analytics資料檢視中選取要公開為元件的欄位。
* 驗證產生的維度和量度是否支援預期的分析。

>[!IMPORTANT]
>
>建立及填入Experience Platform資料集後，Managed聯結器會刻意停止。 Adobe不會修改您的Customer Journey Analytics連線或資料檢視。

在將資料集新增至連線之前，此資料集無法用於Customer Journey Analytics分析。 資料
無法透過資料檢視供使用者使用，直到已將相關欄位新增到該資料檢視為止。

## 驗證

請使用下列程式來驗證入站整合：

1. 確認ABV網站和CDN記錄檔整備

   針對每個ABV網站：

   * 確認要求所涵蓋的確切網站或網域。
   * 確認CDN提供者。
   * 確認CDN或記錄管道正在轉送所需的存取記錄。
   * 確認品牌可見度正在接收或偵測該網站的記錄。
   * 從Adobe取得網站的品牌可見度整備確認。

   除非確認涵蓋特定ABV網站，否則請勿繼續使用「已啟用CDN記錄」的一般宣告。

1. 驗證Experience Platform中的Managed資料集

   在Adobe確認Managed聯結器已建立資料集後：
   1. 登入&#x200B;**[!UICONTROL Experience Platform]**。
   1. 從沙箱清單中選取擷取期間提供的已命名沙箱。
   1. 在&#x200B;**[!UICONTROL 資料集]**&#x200B;中找到Adobe提供的資料集名稱或資料集ID。
   1. 確認資料集已與預期的品牌可見度網站相關聯。
   1. 記錄&#x200B;**[!UICONTROL 資料集識別碼]**&#x200B;並連結&#x200B;**[!UICONTROL 結構描述]**。
   1. 檢閱資料集記錄計數、最新擷取資訊，以及允許時的可用範例資料。
   1. 開啟連結的結構描述並驗證預期的XDM結構：
      * 類別： **[!UICONTROL XDM摘要量度]**
      * 欄位群組： **[!UICONTROL CDN要求摘要]**
      * 物件： **[!UICONTROL cdn]**
      * 預期的維度和量度，例如&#x200B;**[!UICONTROL botType]**、**[!UICONTROL cdnProvider]**、**[!UICONTROL url]**、**[!UICONTROL 主機]**、**[!UICONTROL 狀態]**、**[!UICONTROL 請求]**&#x200B;和&#x200B;**[!UICONTROL timeToFirstByte]**。

1. 將資料集新增至連線

   您的Customer Journey Analytics管理員必須將受管理的資料集新增到預期的連線：

   1. 登入Customer Journey Analytics。
   1. [建立新連線或編輯預期的現有連線](/help/connections/create-connection.md)。 確認連線使用與建立Managed資料集時相同的Experience Platform沙箱。
   1. 使用Adobe提供的資料集名稱或資料集ID搜尋資料集。
   1. 將資料集新增至連線。
   1. 根據客戶的Customer Journey Analytics設計進行資料集設定。
   1. 儲存連線。
   1. 若要確認資料集已包含在內且擷取作業正在進行，請檢閱連線詳細資料。

1. 設定或更新資料檢視

   在資料整合為連線的一部分之後：
   1. 登入Customer Journey Analytics。
   1. [建立新的資料檢視或編輯與預期報告使用案例關聯的資料檢視](/help/data-views/create-dataview.md)。
   1. 選取包含受管理品牌可見度資料集的連線。
   1. 將必要的結構欄位新增為維度或量度。
   1. 包含計劃分析所需的欄位，例如：
      * **[!UICONTROL 機器人型別]**
      * **[!UICONTROL CDN提供者]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL 主機]**
      * **[!UICONTROL HTTP狀態]**
      * **[!UICONTROL 要求計數]**
      * **[!UICONTROL 到第一個位元組的時間]**
   1. 儲存資料檢視。
   1. 驗證Analysis Workspace或客戶所選報告工作流程中的欄位。

1. 驗證端對端結果

   使用最近的報告期間，並確認：

   * 預期的品牌可見度網站會呈現。
   * 預期的CDN提供者和主機值會出現。
   * 代表機器人或自動代理程式流量。
   * URL和HTTP狀態維度包含預期值。
   * 您可使用CDN請求計數和效能度量。
   * 資料集包含在預期的連線中。
   * 必填欄位會顯示在預期的資料檢視中。

資料變得可用的確切時間，取決於受管理的擷取和Customer Journey Analytics處理工作流程。 您的Adobe客戶團隊應為您的請求提供任何適用的處理期望。

## 疑難排解

請參閱以下發生問題時應該採取的做法：

* 資料集未出現在AEP中。

  確認：

  * IMS組織正確。
  * 選取的Experience Platform沙箱是正確的。
  * Adobe已確認受管理的聯結器已啟用。
  * 已使用Adobe提供的資料集名稱或ID。
  * 資料集是為正確的品牌可見度網站所建立。

* 資料集已存在，但未包含預期的資料。

  確認：
  * 正在轉送CDN記錄檔以取得確切的品牌可見度網站。
  * ABV已確認正在接收或偵測記錄檔。
  * CDN設定中的網站或網域符合品牌可見度網站。
  * 在確認CDN記錄整備後，受管理的聯結器便會啟用。
  * 選取的日期範圍包含記錄擷取開始後的期間。


* 此資料集存在於Experience Platform中，但無法在Customer Journey Analytics中使用。

  確認：
  * Customer Journey Analytics連線使用相同名稱的Experience Platform沙箱。
  * 資料集已明確新增至連線。
  * Customer Journey Analytics管理員具有必要許可權。
  * 新增資料集後，連線已儲存。

* 資料集在連線中，但欄位無法用於報告。

  確認：
  * 資料檢視會選取正確的Customer Journey Analytics連線。
  * 預期的結構欄位已新增為資料檢視元件。
  * 欄位已放置於預期的&#x200B;**[!UICONTROL 維度]**&#x200B;或&#x200B;**[!UICONTROL 量度]**&#x200B;區段中。
  * 資料檢視會在新增元件後儲存。
  * 資料集結構描述符合預期的&#x200B;**[!UICONTROL CDN要求摘要]**&#x200B;欄位群組結構。


## 完成條件


在確認下列所有專案時，傳入整合就可供客戶端Customer Journey Analytics設定了：

* 系統會將CDN記錄檔轉送至每個請求的ABV網站，並由品牌可見度接收。
* Adobe已確認受管理聯結器的網站整備。
* 已提供IMS組織。
* 提供了確切的目標Experience Platform沙箱。
* Adobe已在該沙箱中建立每個網站的摘要資料集。
* 您已驗證資料集及其XDM結構描述。
* 您已將資料集新增至預定的CJA連線。
* 您已設定相關的CJA資料檢視元件。

