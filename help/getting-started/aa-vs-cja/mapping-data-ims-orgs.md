---
title: 對應多個IMS組織的Analytics資料
description: 瞭解如何請求將多個來源IMS組織報表套裝中的資料對應至目的地IMS組織。
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
hide: true
hidefromtoc: true
source-git-commit: 3c34bd50c12b370f5e9f95ac5d6357de4f63e5f6
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 1%

---

# 對應多個IMS組織的Analytics資料

Analytics來源聯結器只能從屬於您有權使用Customer Journey Analytics的相同組織的Adobe Analytics報告套裝擷取資料。 對應來自多個IMS組織的Analytics資料的功能為此限制提供了解決方案。 本文會概述啟用此功能的程式。


## 情境

您已布建多個IMS組織，且在這些IMS組織的多個報表套裝中擁有Analytics資料。 此設定可能是下列結果：

* 收購或合併
* 組織結構需求
* 地區部署限制

開箱即用的功能，讓您無法在Customer Journey Analytics中報告跨多個IMS組織的多個報告套裝的資料組合。 此限制的原因是，透過Analytics來源聯結器從Adobe Analytics擷取到Experience Platform的資料擷取僅支援擷取單一IMS組織擁有的資料。 您已布建以及用來登入Adobe Analytics、Experience Platform和Customer Journey Analytics的IMS組織。

透過&#x200B;*對應來自多個IMS組織的Analytics資料*&#x200B;功能，您可以要求Adobe對應資料。 此功能使用Analytics來源聯結器將位於多個&#x200B;*來源* IMS組織的報告套裝中的資料對應到屬於一個&#x200B;*目的地* IMS組織的資料集。 例如：

| 圖例 | 說明 |
|---|---|
| ![跨多個IMS組織對應資料](/help/getting-started/assets/map-data-across-ims-orgs.svg) | 此對應可讓您從IMS組織3內布建的Customer Journey Analytics中的一個連線，報告IMS組織1、IMS組織2和IMS組織3中存在的報表套裝。 |

{style="table-layout:fixed"}

## 使用方式

若要設定並啟用來自多個IMS組織的&#x200B;*對應Analytics資料*&#x200B;功能，您必須透過您的Adobe客戶經理請求對應。 若要進行此步驟：

1. 作為目標IMS組織管理員，請向您想要對應報表套裝的所有來源IMS組織管理員要求核准電子郵件。 您可以使用以下文字作為電子郵件的範本，以請求來源IMS組織管理員的核准。

   | 範例電子郵件範本 |
   | --- |
   | *公司名稱代表*，若要將下列IMS組織（來源IMS組織清單）的存取權授與選取的目的組織，我們需要確保每個IMS組織的管理員都提交其核准，以允許其資料的存取權。 這有助於確保我們已獲得任何受影響的IMS組織的資料存取許可權。 為確保我們獲得適當的核准，請針對每個管理員組織回覆擁有註冊的Adobe管理員，並填入其名稱及其代表的IMS組織，表示「我核准」表示其核准讓此IMS組織的資料出現在目的地組織[列出目的地IMS組織]。 請注意，此管理員必須是在Adobe系統中註冊為該IMS組織管理員的管理員。 |

1. 以目標IMS組織管理員的身分傳送電子郵件給Adobe客戶經理，請求從多個來源IMS組織內的報表套裝對應到目標IMS組織。 附加您從來源IMS組織管理員收到的核准電子郵件。

客戶經理收到電子郵件，要求您對應來自多個組織的Analytics資料後，就會在Adobe中稽核該請求。 客戶經理會與您連絡，以取得任何其他問題、選用的訓練及其他資訊。

核准後，系統就會建立要求的對應，並通知您。 來源IMS組織名稱會附加至Experience Platform中Analytics報表套裝[的](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data)清單中的報表套裝名稱。

## 限制和風險

下列限制適用於來自多個IMS組織的&#x200B;*對應Analytics資料*&#x200B;功能：

* 一個報表套裝只能跨組織連線一次。
* 您必須先刪除在對應中定義為目的地IMS組織的IMS組織的所有連線，才能請求刪除對應。
* ECID在對應的來源IMS組織之間不相容，且與目的地IMS組織不相容。
* 具有足夠許可權可在目標IMS組織中設定Analytics來源聯結器的使用者可以從任何對應的來源IMS組織中擷取Analytics資料。 不會為該使用者檢查任何來源IMS組織的許可權。
