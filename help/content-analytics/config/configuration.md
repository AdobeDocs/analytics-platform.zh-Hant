---
title: 設定內容分析
description: 如何設定內容分析的概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 596e54a559bac69214e1de3ea37da6177f110b7a
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---

# 設定內容分析

>[!WARNING]
>
>本文是即將推出之最終版本的初步非官方草稿版本，屬於內容分析檔案的一部分。 所有內容可能會有所變更，而目前的本文版本概不提供任何法律義務。
>

{{release-limited-testing}}

Content Analytics的設定包含下列步驟：

![內容分析的設定](../assets/aca-configuration.svg)

1. 使用內容分析[引導式設定](guided.md)精靈，引導您完成設定內容分析必要條件的所有必要步驟。 您可以儲存設定，稍後再返回。
1. 在您熟悉設定值後，即可實作設定。 此實作會根據您在精靈中設定的專案，建立所有必要的成品。 會建立、更新或選取下列人工因素：
   * 自訂歷程分析
      * 已選取[資料檢視](/help/data-views/data-views.md)。
      * 已選取[連線](/help/connections/overview.md)，自動衍生自選取的資料檢視。
   * Experience Platform
      * 沙箱已選取，並自動衍生自連線。 沙箱中已啟用必要的工作流程和服務。
      * 在沙箱中選取內容分析結構描述。 如果無法取得，則會建立必要的結構描述。
      * 在沙箱上選取的內容分析資料集。 如果無法取得，則會建立必要的資料集。
   * 資料收集
      * 在資料串流中建立資料串流並設定Experience Platform服務，以將資料串流至Content Analytics體驗事件資料集。
      * Tag屬性是以Adobe Content Analytics擴充功能建立，並設定為設定精靈中的正確沙箱、資料流和其他設定選項。
1. 唯有當您手動發佈Tag屬性時，Content Analytics才能有效部署和啟動。
1. 您只能使用[引導式組態](guided.md)精靈對實作組態進行某些有限的變更。 例如，變更[資料檢視](/help/data-views/data-views.md)。
1. 您可以透過關聯標籤屬性中的[Adobe Content Analytics擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)，對已實作的設定進行其他變更。
1. 只有在您手動重新發佈Tag屬性時，才會有效部署和啟用步驟4和5中的設定修改。


設定「內容分析」前，請先確認是否符合下列必要條件：


>[!PREREQUISITES]
>
>* 您已將Content Analytics中使用之功能服務的使用者代理和IP位址加入允許清單。 使用者代理字串是`AdobeFeaturization/1.0`。
>* 您擁有Customer Journey Analytics產品管理員角色，並具有管理連線和管理資料集合的額外許可權。 所需的Experience Platform許可權為：
>  
>   | 類別 | 權限 | 說明 |
>   |---|---|---|
>   | [!UICONTROL 資料彙集] | 檢視資料串流 | 資料串流的唯讀存取權。 |
>   | [!UICONTROL 資料彙集] | 管理資料串流 | 存取讀取、建立、編輯和刪除資料串流。 |
>   | [!UICONTROL 資料模式] | [!UICONTROL 檢視結構描述] | 對結構描述和相關資源的唯讀存取權。 |
>   | [!UICONTROL 資料模式] | [!UICONTROL 管理結構描述] | 讀取、建立、編輯和刪除結構描述和相關資源的存取權。 |
>   | [!UICONTROL 資料管理] | [!UICONTROL 檢視資料集] | 資料集和結構描述的唯讀存取權。 |
>   | [!UICONTROL 資料管理] | [!UICONTROL 管理資料集] | 存取讀取、建立、編輯和刪除資料集。 結構描述的唯讀存取權。 |
>   | [!UICONTROL 資料擷取] | [!UICONTROL 管理來源] | 讀取、建立、編輯和停用來源的存取權。 |
>   | [!UICONTROL Identity Management] | [!UICONTROL 檢視身分識別名稱空間] | 身分識別名稱空間的唯讀存取權。 |
>
>* 您已仔細考量下列重要設定選項：
>
>   * 您的網站適合使用體驗報告嗎？ 只有在符合下列條件時，才能正確製作體驗報表：
>   * 網站內容僅由URL驅動。
>   * 您網站上的頁面可透過頁面URL重現，而且您會瞭解哪些可選URL引數可推動體驗。
>* 您已清楚瞭解您想要擷取哪些頁面的內容參與分析和見解。
>* 您已清楚瞭解要擷取內容參與分析和深入分析的資產（型別）。
>


>[!MORELIKETHIS]
>
>* [引導式設定](guided.md)
>* [手動設定](manual.md)
>* [存取控制](/help/technotes/access-control.md)
>


