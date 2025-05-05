---
title: 設定 Content Analytics
description: 如何設定 Content Analytics 的概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 3%

---

# 設定 Content Analytics

Content Analytics的設定包含下列步驟：

![內容分析的設定](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用Content Analytics [引導式組態](guided.md)精靈，引導您完成設定Content Analytics組態必要條件的所有必要步驟。 您可以隨時儲存設定，並稍後返回。
1. 在您熟悉設定值後，即可實作設定。 此實作會根據您在精靈中設定的專案，建立所有必要的成品。
1. 只有在您[手動發佈](manual.md) Tags屬性時，才會有效部署您的Content Analytics設定，並啟動資料收集。

1. 您只能使用[引導式組態](guided.md)精靈對已實作的組態進行一些微幅變更。 例如，變更[資料檢視](/help/data-views/data-views.md)。
1. 您可以使用關聯Tags屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，對實作組態進行其他變更。
1. 只有在您[手動重新發佈](manual.md) Tags屬性時，組態修改才會有效部署，而且會根據您的變更開始資料收集。


## 先決條件

設定Content Analytics之前，請確定符合下列必要條件：

* 您已將Content Analytics中使用之功能服務的使用者代理和IP位址加入允許清單。 要設定的使用者代理字串是： <code>AdobeFeaturization/1.0</code>。
* 如果您已使用JavaScript[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/library){target="_blank"}實作網路SDK以進行一般行為資料收集，請確定您使用的是預設名稱<code>alloy</code> 用於JavaScript資料庫。
* 您擁有Customer Journey Analytics產品管理員角色，並具有管理連線和管理資料檢視的其他許可權。
* 如果您考慮收集Content Analytics體驗，請確定您根據網頁上的變更來設定和更新[Content Analytics版本設定](manual.md#versioning)。
* 您必須擁有資料彙集[&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}的許可權：
   * [Experience Platform許可權](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform資料彙集許可權](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 您已仔細考量下列重要設定選項：

   * 您的網站適合體驗報告。 只有在符合下列條件時，才可能提供適當的體驗報表：
      * 網站上的頁面必須使用頁面URL可複製。
      * 任何指定使用者看到的文字內容都可以使用頁面URL重現，而不取決於Cookie或其他個人化機制。
   * 您已清楚瞭解您想要擷取哪些頁面的內容參與分析和見解。
   * 您已清楚瞭解要擷取內容參與分析和深入分析的資產（型別）。


## 存取控制

>[!IMPORTANT]
>
>您沒有可以設定的Content Analytics許可權，無法啟用或停用個別使用者或使用者群組的Content Analytics存取權。
>

若要提供使用者或使用者群組存取Content Analytics的許可權，您必須提供使用者或使用者群組存取一或多個[資料檢視(針對Content Analytics](guided.md#data-view)所設定)。

此存取權表示：

1. 已啟用Content Analytics的資料檢視包含在特定Customer Journey Analytics產品設定檔的資料檢視許可權中。
1. 該特定Customer Journey Analytics產品設定檔是指派給使用者或使用者群組的產品設定檔之一。

>[!MORELIKETHIS]
>
>* [引導式設定](guided.md)
>* [手動設定](manual.md)
>* [存取控制](/help/technotes/access-control.md)
>
