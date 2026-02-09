---
title: 跨IMS資料對映
description: 瞭解如何請求將多個來源IMS組織報表套裝中的資料對應至目的地IMS組織。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
source-git-commit: 16486ded009a9dbd9170240c0941853a4deec0af
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# 跨ims資料對應

Analytics來源聯結器只能從屬於您有權使用Customer Journey Analytics的相同組織的Adobe Analytics報告套裝擷取資料。 *跨IMS資料對應*&#x200B;功能是對應來自多個IMS組織的Analytics資料，並提供此限制的解決方案。 本文會概述啟用此功能的程式。


## 情境

您已布建多個IMS組織，且在這些IMS組織的多個報表套裝中擁有Analytics資料。 此設定可能是下列結果：

* 收購或合併
* 組織結構需求
* 地區部署限制

開箱即用的功能，讓您無法在Customer Journey Analytics中報告跨多個IMS組織的多個報告套裝的資料組合。 此限制的原因是，透過Analytics來源聯結器從Adobe Analytics擷取到Experience Platform的資料擷取僅支援擷取單一IMS組織擁有的資料。 您已布建以及用來登入Adobe Analytics、Experience Platform和Customer Journey Analytics的IMS組織。

透過&#x200B;*跨IMS資料對應*&#x200B;功能，您可以要求Adobe對應資料。 此功能使用Analytics來源聯結器將位於多個&#x200B;*來源* IMS組織的報告套裝中的資料對應到屬於一個&#x200B;*目的地* IMS組織的報告套裝（和最終資料集）。 例如：

| 圖例 | 說明 |
|---|---|
| ![跨多個IMS組織對應資料](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 此對應可讓您從IMS組織3內布建的Customer Journey Analytics中的一個連線，報告IMS組織1、IMS組織2和IMS組織3中存在的報表套裝。 |

{style="table-layout:fixed"}

## 使用方式

若要設定和啟用&#x200B;*跨IMS資料對應*&#x200B;功能，您必須透過Adobe客戶經理要求對應。 若要這麼做：

1. 作為目標IMS組織管理員，請向您想要對應報表套裝的所有來源IMS組織管理員要求核准電子郵件。 您可以使用以下文字作為電子郵件的範本，以請求來源IMS組織管理員的核准。

   | 範例電子郵件範本 |
   | --- |
   | *公司名稱代表*，若要將下列IMS組織（來源IMS組織清單）的存取權授與選取的目的組織，我們需要確保每個IMS組織的管理員都提交其核准，以允許其資料的存取權。 這有助於確保我們已獲得任何受影響的IMS組織的資料存取許可權。 為確保我們獲得適當的核准，請針對每個管理員組織回覆擁有註冊的Adobe管理員，並填入其名稱及其代表的IMS組織，表示「我核准」表示其核准讓此IMS組織的資料出現在目的地組織[列出目的地IMS組織]。 請注意，此管理員必須是在Adobe系統中註冊為該IMS組織管理員的管理員。 |

1. 代表目標IMS組織管理員傳送電子郵件給Adobe客戶經理，請求從多個來源IMS組織內的報表套裝對應到目標IMS組織。 附加您從來源IMS組織管理員收到的核准電子郵件。

一旦Adobe客戶經理收到電子郵件，其中包含來自多個組織的Analytics資料對應請求，即會在Adobe中稽核該請求。 Adobe客戶經理若需任何其他問題、選用的培訓及其他資訊，請聯絡您。

核准後，系統就會建立要求的對應，並通知您。 來源IMS組織名稱會附加至Experience Platform中Analytics報表套裝[的](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)清單中的報表套裝名稱。


## 限制

下列限制適用於&#x200B;*跨IMS資料對應*&#x200B;功能：

* 一個報表套裝只能跨組織連線一次。
* 您必須先刪除在對應中定義為目的地IMS組織的IMS組織的所有連線，才能請求刪除對應。
* ECID在對應的來源IMS組織之間不相容，且與目的地IMS組織不相容。


## 考量事項

請求&#x200B;*跨IMS資料對應*&#x200B;功能之前，您可能會想要考慮下列主題：

### 設定檔

在核准&#x200B;*跨IMS資料對應*&#x200B;功能後，您就可以將資料新增到目標IMS組織中一個或多個報表套裝的Experience Platform。 您透過[Analytics來源聯結器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)的設定來執行此動作。 然後會在Experience Platform中建立Target資料集。 在此設定和流程中，您可以選擇從一個或多個報表套裝將設定檔資料傳送至設定檔服務。

如上所述，預估由設定和程式所產生的設定檔總數。 確保總數不超過您依照合約有權為目的地組織使用的設定檔數量。 套用[篩選規則和條件](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"}以選擇性地包含或排除擷取至設定檔服務的資料。 或停用將設定檔資料傳送至相關報表套裝的設定檔服務的選項。


### 拼接

在核准&#x200B;*跨IMS資料對應*&#x200B;功能後，您就可以將資料新增到目標IMS組織中一個或多個報表套裝的Experience Platform。 您透過[Analytics來源聯結器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics)的設定來執行此動作。 接著會在Experience Platform中建立您在Analytics來源聯結器中所設定報表套裝的Target資料集。 在此設定和流程中，您可以選擇從一個或多個報表套裝將設定檔資料傳送至設定檔服務。

您可以在目標資料集上同時使用[欄位式](/help/stitching/fbs.md)和[圖表式](/help/stitching/gbs.md)拼接。 當您針對這些目標資料集中的一或多個使用圖表式拚接時，請確定您符合設定檔數目的合約權利，如[設定檔](#profiles)區段所述。

如果您未獲得即時客戶個人檔案的授權，但仍想要在一或多個目標資料集上使用圖表式拼接，請確定您僅為這些目標資料集啟用[身分識別服務](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)。


### 權限

具有足夠許可權可在目標IMS組織中設定Analytics來源聯結器的使用者可以從任何對應的來源IMS組織中擷取Analytics資料。 不會為該使用者檢查任何來源IMS組織的許可權。

### 資料報表

*跨IMS資料對應*&#x200B;功能只是確保您可以使用資料做為Customer Journey Analytics [連線](/help/connections/overview.md)、一或多個[資料檢視](/help/data-views/data-views.md)和[工作區專案](/help/analysis-workspace/home.md)的一部分的第一步。 您需要仔細檢查您現在在一個IMS組織中可用的資料。 在您能夠正確報告此資料之前，請考慮資料準備、衍生欄位、其他查詢表格等功能。
