---
title: 設定 Content Analytics
description: 瞭解如何為網頁和行動裝置頻道設定Content Analytics。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
TQID: https://experienceleague.adobe.com/a-Mu3MKfpRsUqgxx7JWP3NR4vji62VaNFi-hI5teDZI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 776
ht-degree: 76%

---


# 設定 Content Analytics

此文章以概括性方式記載如何設定 Content Analytics。

設定 Content Analytics 前，您必須確認符合[先決條件](#prerequisites)、確實擁有必要的[存取控制](#access-control)，而且了解相關[限制](#limitations)。


概括性步驟

![Content Analytics 設定](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用 Content Analytics [引導式設定](guided.md)精靈引導您完成進行 Content Analytics 設定先決條件所需的所有步驟。 您可以隨時儲存您的設定並於之後返回。
1. 一旦您對設定值感到滿意，就可以實施該設定。 此實施會根據您在精靈中設定的內容建立所有必要的作品。
1. 只有在您[手動發佈](manual.md)時，Tags屬性才會是您的Content Analytics設定已有效部署且資料收集已開始。

1. 您僅能使用[引導式設定精靈](guided.md)對已實施的設定進行一些細微的變更。 例如，變更[資料視圖](/help/data-views/data-views.md)。
1. 您可以使用[Web](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/content-analytics/overview)或[行動裝置](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)之相關Tags屬性中的Adobe Content Analytics擴充功能，對實作組態進行其他變更。
1. 設定修改會有效部署，而且只有在您手動重新發佈Tags屬性時，才會開始資料收集。


## 先決條件

在設定 Content Analytics 之前，請確保滿足以下先決條件：

### Web

* 您已將 Content Analytics 中使用之特徵化服務的使用者代理程式和 IP 地址加入允許名單。 要設定的使用者代理字串是：<code>AdobeFeaturization/1.0</code>。
* 如果您已使用 JavaScript 實施 [Web SDK](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/install/library){target="_blank"} 用於定期行為資料收集，請確保您使用的是預設名稱 <code>alloy</code> ，針對 JavaScript 程式庫。
* 您具有 Customer Journey Analytics 產品管理員角色，並具有管理連線和管理資料視圖的額外權限。
* 如果您決定收集Content Analytics體驗，請確定您根據網頁的變更來設定和更新Content Analytics版本設定。
* 您必須擁有[資料收集權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}許可權。
   * [Experience Platform資料彙集](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}許可權。
* 您已仔細考慮了以下重要的設定選項：

   * 您的網站適合體驗報告。 只有滿足以下條件才可以進行正確的體驗報告：
      * 網站上的頁面必須能夠使用頁面 URL 進行複製。
      * 任何給定使用者看到的文字內容都可以使用頁面 URL 進行複製，並且不需要依賴 cookie 或其他個人化機制。
   * 您已清楚瞭解要擷取哪些頁面以進行內容參與分析和深入分析。
   * 您清楚了解要擷取哪些資產 (類型) 的內容參與度分析和洞察。

### Mobile

* 確保行動應用程式已啟用[Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/)和[Edge Network適用的Experience Platform身分識別](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)擴充功能。
* 您具有 Customer Journey Analytics 產品管理員角色，並具有管理連線和管理資料視圖的額外權限。
* 您必須擁有[資料收集權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}許可權。
   * [Experience Platform資料彙集](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}許可權。



## 存取控制

>[!IMPORTANT]
>
>您無法透過設定 Content Analytics 權限，為單一使用者或使用者群組啟用或停用 Content Analytics 存取權限。
>

若要向使用者或使用者群組授予 Content Analytics 的存取權限，您必須向該使用者或使用者群組授予對一個或多個[為 Content Analytics 設定之資料視圖](guided.md#data-view)的存取權限。

這種存取權表示：

1. 啟用 Content Analytics 的資料視圖包含在特定 Customer Journey Analytics 產品輪廓的資料檢視權限中。
1. 這個特定的 Customer Journey Analytics 產品輪廓是指派給使用者或使用者群組的產品輪廓之一。

## 限制

Content Analytics 事件資料所使用的結構描述為系統所擁有。 無法修改系統擁有的結構描述，意即：

* 您無法透過加入欄位群組來支援例如地理位置、機器人偵測或裝置查詢等功能。
* 您無法透過新增特定識別碼來支援[欄位式拼接](/help/stitching/fbs.md)。

>[!MORELIKETHIS]
>
>* [引導式設定](guided.md)
>* [手動設定](manual.md)
>* [存取控制](/help/technotes/access-control.md)
>
