---
title: 設定內容分析
description: 如何設定內容分析的概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 2%

---

# 設定內容分析

{{draft-aca}}

{{release-limited-testing}}

Content Analytics的設定包含下列步驟：

![內容分析的設定](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用Content Analytics [引導式組態](guided.md)精靈，引導您完成設定Content Analytics組態必要條件的所有必要步驟。 您可以隨時儲存設定，並稍後返回。
1. 在您熟悉設定值後，即可實作設定。 此實作會根據您在精靈中設定的專案，建立所有必要的成品。
1. 只有當您[手動發佈](manual.md) Tags屬性時，您的Content Analytics設定才會有效部署並啟動。

1. 您只能使用[引導式組態](guided.md)精靈對已實作的組態進行一些微幅變更。 例如，變更[資料檢視](/help/data-views/data-views.md)。
1. 您可以使用關聯Tags屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，對實作組態進行其他變更。
1. 只有在您[手動重新發佈](manual.md) Tags屬性時，組態修改才會有效部署並啟動。


## 先決條件

設定Content Analytics之前，請確定符合下列必要條件：

* 您已將Content Analytics中使用之功能服務的使用者代理和IP位址加入允許清單。 要設定的使用者代理字串是： <code>AdobeFeaturization/1.0</code>。
* 您擁有Customer Journey Analytics產品管理員角色，並具有管理連線和管理資料檢視的其他許可權。
* 您具備必要的Experience Platform許可權：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 資料彙集] | 檢視資料串流 | 資料串流的唯讀存取權。 |
  | [!UICONTROL 資料彙集] | 管理資料串流 | 讀取、建立、編輯和刪除資料串流的存取權。 |
  | [!UICONTROL 資料模式] | [!UICONTROL 檢視結構描述] | 對結構描述和相關資源的唯讀存取權。 |
  | [!UICONTROL 資料模式] | [!UICONTROL 管理結構描述] | 讀取、建立、編輯和刪除結構描述和相關資源的存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 檢視資料集] | 資料集和結構描述的唯讀存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 管理資料集] | 存取讀取、建立、編輯和刪除資料集。 結構描述的唯讀存取權。 |
  | [!UICONTROL 資料擷取] | [!UICONTROL 管理來源] | 讀取、建立、編輯和停用來源的存取權。 |
  | [!UICONTROL Identity Management] | [!UICONTROL 檢視身分識別名稱空間] | 身分識別名稱空間的唯讀存取權。 |

* 您已仔細考量下列重要設定選項：

   * 您的網站適合體驗報告。 只有在符合下列條件時，才可能提供適當的體驗報表：
      * 您只能透過公開的URL存取網站內容。 存取網站不需要個人化的Token、Cookie或無法透過URL取得的其他機制。
      * 您網站上的頁面可透過頁面URL重現，而且您會瞭解哪些可選URL引數可推動體驗。
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
