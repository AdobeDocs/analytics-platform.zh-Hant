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
ht-degree: 100%

---

# 設定 Content Analytics

Content Analytics 的設定包括以下步驟：

![Content Analytics 設定](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用 Content Analytics [引導式設定](guided.md)精靈引導您完成進行 Content Analytics 設定先決條件所需的所有步驟。您可以隨時儲存您的設定並於之後返回。
1. 一旦您對設定值感到滿意，就可以實施該設定。此實施會根據您在精靈中設定的內容建立所有必要的作品。
1. 只有當您[手動發佈](manual.md)標記屬性時，您的 Content Analytics 設定才會有效部署並開始資料收集。

1. 您僅能使用[引導式設定精靈](guided.md)對已實施的設定進行一些細微的變更。例如，變更[資料視圖](/help/data-views/data-views.md)。
1. 您可以使用關聯標記屬性中的 [Adobe Content Analytics 擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview)對已實施的設定進行其他變更。
1. 只有當您[手動重新發佈](manual.md)標記屬性時，設定修改才會有效部署，並且會根據您的變更開始資料收集。


## 先決條件

在設定 Content Analytics 之前，請確保滿足以下先決條件：

* 您已將 Content Analytics 中使用之特徵化服務的使用者代理程式和 IP 地址加入允許名單。要設定的使用者代理字串是：<code>AdobeFeaturization/1.0</code>。
* 如果您已使用 JavaScript 實施 [Web SDK](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/install/library){target="_blank"} 用於定期行為資料收集，請確保您使用的是預設名稱 <code>alloy</code> ，針對 JavaScript 程式庫。
* 您具有 Customer Journey Analytics 產品管理員角色，並具有管理連線和管理資料視圖的額外權限。
* 如果您考慮收集 Content Analytics 體驗，請確保根據網頁上的變更設定並更新 [Content Analytics 版本設定](manual.md#versioning) 。
* 您必須擁有[資料收集權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform 權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform Data Collection 權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 您已仔細考慮了以下重要的設定選項：

   * 您的網站適合體驗報告。只有滿足以下條件才可以進行正確的體驗報告：
      * 網站上的頁面必須能夠使用頁面 URL 進行複製。
      * 任何給定使用者看到的文字內容都可以使用頁面 URL 進行複製，並且不需要依賴 cookie 或其他個人化機制。
   * 您清楚了解要擷取哪些頁面的內容參與度分析和見解。
   * 您清楚了解要擷取哪些資產 (類型) 的內容參與度分析和見解。


## 存取控制

>[!IMPORTANT]
>
>您無法透過設定 Content Analytics 權限，為單一使用者或使用者群組啟用或停用 Content Analytics 存取權限。
>

若要向使用者或使用者群組授予 Content Analytics 的存取權限，您必須向該使用者或使用者群組授予對一個或多個[為 Content Analytics 設定之資料視圖](guided.md#data-view)的存取權限。

這種存取權表示：

1. 啟用 Content Analytics 的資料視圖包含在特定 Customer Journey Analytics 產品輪廓的資料檢視權限中。
1. 這個特定的 Customer Journey Analytics 產品輪廓是指派給使用者或使用者群組的產品輪廓之一。

>[!MORELIKETHIS]
>
>* [引導式設定](guided.md)
>* [手動設定](manual.md)
>* [存取控制](/help/technotes/access-control.md)
>
