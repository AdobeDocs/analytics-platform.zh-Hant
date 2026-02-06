---
title: 設定Content Analytics （獨立）
description: 會引導您完成設定Content Analytics （獨立）所需的步驟
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 35d63b7d-f35a-4a88-ae14-96724d32a931
source-git-commit: 20ead546897ad517840f95a5ec4dcd7f830afe8c
workflow-type: tm+mt
source-wordcount: '2517'
ht-degree: 6%

---

# 獨立設定

>[!IMPORTANT]
>
>本設定指南適用於已授權獨立Adobe Content Analytics套件的客戶。 本指南假設您尚未使用或計畫使用Customer Journey Analytics或Content Analytics功能以外的任何其他Experience Platform應用程式。 如果您想要設定和使用Content Analytics做為現有Customer Journey Analytics實作的一部分，請參閱[設定Content Analytics](configuration.md)。
>

Content Analytics已獲授權為獨立產品，但設定會在Experience Platform和Customer Journey Analytics中進行。 這些平台提供Content Analytics需要並使用的資料收集和分析基礎架構。 本指南提供您需要的所有特定指示，即使您是Experience Platform和Customer Journey Analytics的新手。

開始設定獨立Content Analytics之前，您應該：

* 基本瞭解網站分析概念、熟悉標籤管理系統，並具備JavaScript基本知識。
* 規劃4到6小時的初始設定，以及額外的測試與驗證設定時間。

## 術語

本指南使用Experience Platform和Customer Journey Analytics中的一些技術術語，您可能不熟悉這些術語。 以下是Content Analytics內容中這些詞語（含參考連結）的說明：

| 詞語 | 說明 |
|---|---|
| **結構描述** | [結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)是一組規則，可代表及驗證資料的結構和格式。 在高層面上，結構描述提供了真實世界物件的抽象定義，例如發生在網站上的事件，例如點選。 並概述該物件的每個例項中應該包含哪些資料。 |
| **資料集** | [資料集](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)是資料集合的儲存和管理結構，通常是包含結構描述（欄）和欄位（列）的表格。 資料集就像資料庫表格，其中的每一列都是來自您網站的事件。 |
| **資料流** | [資料流](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)代表將資料從您的網站路由到Adobe Experience Platform中正確資料集的伺服器端組態。 資料串流就像連線網站與儲存空間的資料高速公路。 |
| **標記** | Experience Platform中的[標籤](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home)是新一代Adobe標籤管理功能。 標籤可讓客戶透過簡單的方式部署及管理必要的分析、行銷及廣告標籤功能，以便支援相關客戶體驗。 在Content Analytics中，Adobe的標籤管理系統可讓您在網站上部署追蹤程式碼，而不需以類似方式編輯每個頁面。 標籤功能類似於您可能從Google Tag Manager中瞭解的功能。 |
| **沙箱** | Experience Platform提供[沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)，可將單一Experience Platform執行個體分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。 Content Analytics通常使用&#x200B;*生產*&#x200B;沙箱。 |
| **連線** | [連線](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview)定義要擷取的Experience Platform資料集。 連線會定義資料集(資料儲存在AEP中的位置)與Customer Journey Analytics （資料分析位置）之間的連結。 連線可讓您的收集資料可用於報表。 |
| **資料檢視** | [資料檢視](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/data-views)是一個容器，可讓您決定如何解譯來自連線的資料。 資料檢視會指定所有可用於報表的維度和量度。 資料檢視就像一種設定，可決定可在分析中使用的列和欄。 |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home)是您用來建置Content Analytics報表與分析的拖放式瀏覽器介面。 |
| **體驗** | 在Content Analytics中，[體驗](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)是指網頁上所有可依據頁面URL擷取及分析的文字內容。 |
| **資產** | 在Content Analytics中，[資產](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)是個別且唯一的內容，例如影像。 |


## 設定概述

此設定會引導您設定所有需要具備有效&#x200B;**獨立** Content Analytics實作的應用程式。 您可以將設定劃分為三個階段，每個階段都建立在上一個階段之上：

**階段1** - [準備您的環境](#prepare-your-environment)。 在此階段中，您需要設定使用者許可權並驗證您的資料基礎結構。 沒有這些適當的許可權和資料結構，您就無法完成其餘步驟。 相關步驟包括：

1. **設定存取控制與許可權**&#x200B;以支援Content Analytics組態與實作。
1. **設定結構描述和資料集**&#x200B;以定義您要收集內容分析深入分析的資料模型（結構描述），以及收集該資料（資料集）的位置。

**階段2** - [設定資料集合](#configure-data-collection)。 在此階段中，您將建立從網站擷取內容資料的管道。 因此，Content Analytics知道訪客與您的內容互動的內容。

1. **設定資料串流**&#x200B;以設定如何將您收集的資料路由傳送到資料集。
1. **使用網站標籤**，針對您網站上資料層中的資料設定規則和資料元素，並確保將資料傳送至已設定的資料流。
1. **部署**&#x200B;至測試環境&#x200B;**並驗證**&#x200B;資料集合，然後再發佈至生產環境。

**階段3** - [設定報告](#set-up-reporting)。 在此階段中，讓收集到的資料可在報表中分析。 因此，您實際上可以從Content Analytics中獲得您想要的內容效能深入分析。

1. **設定與資料集的連線**。
1. **設定資料檢視**&#x200B;以定義量度和維度。
1. **設定並實作Content Analytics**。
1. **設定專案**&#x200B;以建置您的Content Analytics報告和視覺效果。


## 準備環境

在此階段中，您需要設定使用者許可權並驗證您的資料基礎結構。

### 設定存取控制與許可權

本節記錄您需要對產品的存取權、產品設定檔，以及設定和設定獨立Content Analytics所需的許可權。 雖然您只對Content Analytics的功能感興趣，但若要讓此功能正常運作，您仍需要其他Experience Platform產品的存取權和許可權。

#### 存取控制

存取控制會決定是否允許您存取Experience Platform產品。

您需要系統管理員或產品管理員，才能將您新增為產品或產品設定檔的管理員。 產品管理員只能將您新增為所管理產品（設定檔）的管理員，系統管理員可以將產品管理員新增到任何產品（設定檔）。

>[!BEGINSHADEBOX]

請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [管理產品設定檔的使用者](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"}以取得示範影片。


>[!ENDSHADEBOX]

您必須是產品管理員，才能使用獨立Content Analytics的下列產品和產品設定檔：

* Adobe Experience Platform
   * AEP-Default-All-Users （存取生產沙箱的預設設定檔）

* Adobe Experience Platform 資料彙集
   * 預設資料收集所有存取權

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics （自訂）
   * Customer Journey Analytics （或任何其他預設布建的產品設定檔）

您可以透過Admin Console定義產品管理員存取權：

1. 存取[Admin Console](https://adminconsole.adobe.com)。
1. 選取&#x200B;**[!UICONTROL 產品]**。
1. 選取特定產品。
1. 選取「**[!UICONTROL 管理員]**」標籤。
1. 選取&#x200B;**[!UICONTROL 新增管理員]**&#x200B;以新增產品管理員。
1. 在&#x200B;**[!UICONTROL 新增產品管理員]**&#x200B;對話方塊中輸入一或多個電子郵件或使用者名稱。 選取「**[!UICONTROL 儲存]**」以便儲存。


您可以透過Admin Console定義產品設定檔管理員存取權：

1. 存取[Admin Console](https://adminconsole.adobe.com)。
1. 選取&#x200B;**[!UICONTROL 產品]**。
1. 選取特定產品。 確定您已擁有產品管理員存取權。
1. 選取&#x200B;**[!UICONTROL 產品設定檔]**。
1. 選取特定的產品設定檔。
1. 選取「**[!UICONTROL 管理員]**」標籤。
1. 選取&#x200B;**[!UICONTROL 新增管理員]**&#x200B;以將管理員新增至產品設定檔。
1. 在&#x200B;**[!UICONTROL 新增產品設定檔管理員]**&#x200B;對話方塊中輸入一或多個電子郵件或使用者名稱。 選取「**[!UICONTROL 儲存]**」以便儲存。


#### 權限

許可權會定義您擁有產品存取權時可在產品內執行的動作。

您在[!UICONTROL 許可權]介面中定義Experience Platform的許可權，並使用以屬性為基礎的存取控制。 對於Customer Journey Analytics，您透過[!UICONTROL Admin Console]定義許可權。

##### Experience Platform

Experience Platform中的[!UICONTROL 許可權]介面是以角色的定義為基礎。 角色是以資源為基礎的許可權的集合。 在新布建的環境中，有兩個預設角色可供使用： **[!UICONTROL 預設的生產所有存取權]**&#x200B;和&#x200B;**[!UICONTROL 沙箱管理員]**。

針對Content Analytics，您需要確認下列資源和相關許可權是否已新增至這些角色：

* 預設的生產所有存取角色

   * 資料收集
      * 檢視資料串流
      * 管理資料串流

   * 資料管理
      * 檢視資料集
      * 管理資料集

   * 資料模型製作
      * 檢視結構描述
      * 管理結構描述
      * 管理身分中繼資料


* 沙箱管理員角色

   * 沙箱
      * Prod
      * (您要用於Content Analytics的任何其他沙箱)

   * 沙箱管理
      * 管理封裝
      * 管理沙箱
      * 重設沙箱
      * 檢視沙箱


在許可權介面中，您可以驗證角色和相關許可權。 以及哪些使用者屬於該角色。

1. 存取您組織的Experience Platform。
1. 在歡迎畫面的&#x200B;**[!UICONTROL 快速存取]**&#x200B;中，選取&#x200B;**[!UICONTROL 全部檢視]**。
1. 啟用![許可權](/help/assets/icons/PinOn.svg)的pin **[!UICONTROL PinOn]**，因此&#x200B;**[!UICONTROL 快速存取]**&#x200B;中的&#x200B;**[!UICONTROL 許可權]**&#x200B;可供日後使用。
1. 選取&#x200B;**[!UICONTROL 許可權]**。
1. 選取![使用者](/help/assets/icons/User.svg) **[!UICONTROL 角色]**。
1. 選取您要驗證的特定角色（例如，**[!UICONTROL 預設的生產所有存取權]**）。 選取&#x200B;**[!UICONTROL 檢視全部]**&#x200B;以檢視所有許可權。
1. 在&#x200B;**[!UICONTROL 詳細資料]**&#x200B;畫面中：
   1. 驗證&#x200B;**[!UICONTROL 許可權]**&#x200B;中列出的&#x200B;**[!UICONTROL 資源]**。
   1. 驗證&#x200B;**[!UICONTROL 沙箱]**&#x200B;中的沙箱名稱。

   若要進行任何更新，請選取![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯]**。
   1. 若要新增缺少的資源，請從&#x200B;**[!UICONTROL 資源]** > ![Adobe Experience Platform](/help/assets/icons/Add.svg)左側邊欄中選取&#x200B;**[!UICONTROL 資源名稱]** **[!UICONTROL 新增]**。
   1. 若要新增缺少的許可權，請在主要面板中缺少許可權的資源中選取![ChevronDown](/help/assets/icons/ChevronDown.svg)，然後選取缺少的許可權。

      ![許可權介面](/help/content-analytics/assets/aep-permissions-ui.png)

   選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存任何更新。

1. 在使用者或使用者群組畫面中：
   1. 確認適當的個別使用者或使用者群組屬於此角色。
      1. 選取「使用者」中的![使用者新增](/help/assets/icons/UserAdd.svg)新增使用者，以新增您在Admin Console中定義的個別使用者。
      1. 選取![新增](/help/assets/icons/Add.svg)在使用者群組中新增群組，以新增您在Admin Console中定義的使用者群組。


##### Customer Journey Analytics

Customer Journey Analytics不支援以屬性為基礎的存取控制。 若要指定許可權，請使用Admin Console。

對於Content Analytics，您需要確認是否包含下列Customer Journey Analytics產品設定檔許可權：

* 資料檢視
   * 所有可用的資料檢視。

* 報告工具
   * 引導式分析存取？
   * 建立計算量度
   * 區段建立
   * Labs存取？
   * 附註建立
   * 建立對象？
   * 對象檢視？
   * 稽核記錄存取權
   * 與任何人分享專案連結
   * 預測
   * AI 助理：產品知識
   * Data Insights 代理
   * 智慧型註解
   * 資料Storytelling？

* 資料檢視工具
   * 完整表格匯出？
   * CJA BI擴充功能？

若要為Customer Journey Analytics驗證並更新這些許可權：

1. 存取[Admin Console](https://adminconsole.adobe.com)。
1. 選取&#x200B;**[!UICONTROL 產品]**。
1. 選取&#x200B;**[!UICONTROL Customer Journey Analytics]**&#x200B;產品。
1. 選取&#x200B;**[!UICONTROL 產品設定檔]**。
1. 選取適用於Customer Journey Analytics的預設已布建產品設定檔。 例如： **[!UICONTROL Customer Journey Analytics]**。
1. 在產品設定檔畫面中，選取&#x200B;**[!UICONTROL 許可權]**。
1. 選取任何![編輯](/help/assets/icons/Edit.svg)按鈕以編輯許可權。 在&#x200B;**[!UICONTROL Customer Journey Analytics的編輯許可權]**&#x200B;對話方塊中：

   ![CJA許可權UI](../assets/cja-permissions-ui.png)

   1. 選取&#x200B;**[!UICONTROL 資料檢視]**&#x200B;並啟用&#x200B;**[!UICONTROL 自動包含： On]**。 此切換可確保所有資料檢視會自動成為&#x200B;**[!UICONTROL 包含的許可權專案]**&#x200B;的一部分。
   1. 選取&#x200B;**[!UICONTROL 報告工具]**，並確保上面列出的所有許可權都是&#x200B;**[!UICONTROL 包含的許可權專案]**&#x200B;的一部分。
   1. 選取「**[!UICONTROL 資料檢視工具]**」，並確定上面列出的所有許可權都是&#x200B;**[!UICONTROL 包含的許可權專案]**&#x200B;的一部分。

   選取&#x200B;**[!UICONTROL 「儲存」]**。


### 設定結構和資料集

若要從您的網站收集資料，您必須受Content Analytics深入分析所限制，先定義您要收集的資料型別。 以及該資料的儲存方式。 透過Adobe Experience Platform Web SDK[快速入門手冊，在](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset)擷取資料的[設定結構描述和資料集](/help/data-ingestion/aepwebsdk.md)中說明了這兩個概念。


## 設定資料彙集

在此階段中，您將建立從網站擷取內容資料的管道。

### 設定資料流

您已定義要收集哪些資料以及如何儲存該資料。 下一個步驟是確保將從網站收集而來的資料路由傳送到資料集。 您需要設定資料串流，如[透過Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)快速入門手冊擷取資料[設定資料串流](/help/data-ingestion/aepwebsdk.md)中所述。


### 使用標籤

您已定義要收集哪些資料（結構描述）、如何儲存該資料（資料集），以及從您的網站收集到的資料如何路由傳送到資料集（資料流）。 下一步，您需要標籤網站，以針對網站上資料層中的資料設定規則和資料元素。 標籤網站可確保將資料傳送至已設定的資料流。 在[透過Adobe Experience Platform Web SDK擷取資料](/help/data-ingestion/aepwebsdk.md#use-tags)快速入門手冊中的[使用標籤](/help/data-ingestion/aepwebsdk.md)中，說明在標籤的協助下標籤您的網站。


### 部署和驗證。

您現在可以將程式碼部署在 `<head>`標籤內的網站開發版本上。部署後，您的網站就會開始將資料收集到Adobe Experience Platform中。 然後，該資料會受Content Analytics限制。

驗證您的實作，必要時進行更正，並在正確後，使用Tags的發佈工作流程功能將其部署到中繼和生產環境


## 設定報告

在此階段中，您可將收集的資料用於報表中的分析。

### 設定與資料集的連線

若要就收集的資料製作報表並為Content Analytics設定該資料，您需要在Customer Journey Analytics中設定連線。 連線會連線至包含所收集資料的資料集。 在[透過Adobe Experience Platform Web SDK擷取資料](../../data-ingestion/aepwebsdk.md#set-up-a-connection)快速入門手冊[設定連線](/help/data-ingestion/aepwebsdk.md)中說明如何設定連線。


### 設定資料檢視

設定Content Analytics之前的最後一步是定義資料檢視。 資料檢視是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。資料檢視可讓您從Customer Journey Analytics連線的一或多個資料集的資料，定義量度和維度。 在[透過Adobe Experience Platform Web SDK擷取資料](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view)快速入門手冊[設定資料檢視](/help/data-ingestion/aepwebsdk.md)中說明如何設定資料檢視。


### 設定 Content Analytics

您現在已具備設定Content Analytics所需的一切。

#### 引導式設定

使用[引導式設定精靈](guided.md)，並選取您在[設定資料檢視](#set-up-a-data-view)步驟中建立的資料檢視。 該選項可確保根據您從網站收集的資料，設定並實作Content Analytics。

請注意，引導式設定精靈會設定下列其他特定Content Analytics物件：

* **資料集**，已針對Content Analytics事件自動設定。 此資料集使用已建立且可用的特定Content Analytics結構描述。
* **資料串流**，此資料串流已自動設定為將Content Analytics事件串流至Content Analytics資料集。
* **Tags屬性**，已自動設定並以Content Analytics擴充功能設定。 此Tags屬性可確保您的網站將Content Analytics資料傳送至Content Analytics資料流和Content Analytics資料集。

  >[!IMPORTANT]
  >
  >請確定您選取建立新標籤屬性的選項，作為精靈中[資料收集](guided.md#new-configuration-1)步驟的一部分。
  >


#### 手動設定

若要為網站實作Content Analytics，您必須手動發佈Content Analytics標籤屬性[&#128279;](manual.md)。


### 設定專案

在Customer Journey Analytics中設定專案，以建置您的[Content Analytics報表和視覺效果](/help/content-analytics/report/report.md)。 或者，您可以使用[Content Analytics範本](/help/content-analytics/report/report.md#template)開始使用。
