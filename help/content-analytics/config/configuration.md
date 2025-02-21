---
title: 設定內容分析
description: 如何設定內容分析的概觀
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# 設定內容分析

>[!WARNING]
>
>本文是即將推出之最終版本的初步非官方草稿版本，屬於內容分析檔案的一部分。 所有內容可能會有所變更，而目前的本文版本概不提供任何法律義務。
>

{{release-limited-testing}}


若要為貴組織設定內容分析，請使用內容分析[引導式設定](guided.md)。 設定精靈會引導您完成設定Content Analytics自動設定的必要條件的所有步驟。

成功實作後，您可以使用引導式設定精靈進行一些變更。 不過，除此之外，可能還需要[手動變更](manual.md)。

## 先決條件

設定「內容分析」前，請先確認是否符合下列必要條件：

* 您已將Content Analytics中使用之功能服務的使用者代理和IP位址加入允許清單。 使用者代理字串是`AdobeFeaturization/1.0`。
* 您擁有Customer Journey Analytics產品管理員角色，並具有管理連線和管理資料集合的額外許可權。 所需的Experience Platform許可權為：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 資料彙集] | 檢視資料串流 | 資料串流的唯讀存取權。 |
  | [!UICONTROL 資料彙集] | 管理資料串流 | 存取讀取、建立、編輯和刪除資料串流。 |
  | [!UICONTROL 資料模式] | [!UICONTROL 檢視結構描述] | 對結構描述和相關資源的唯讀存取權。 |
  | [!UICONTROL 資料模式] | [!UICONTROL 管理結構描述] | 讀取、建立、編輯和刪除結構描述和相關資源的存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 檢視資料集] | 資料集和結構描述的唯讀存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 管理資料集] | 存取讀取、建立、編輯和刪除資料集。 結構描述的唯讀存取權。 |
  | [!UICONTROL 資料擷取] | [!UICONTROL 管理來源] | 讀取、建立、編輯和停用來源的存取權。 |
  | [!UICONTROL Identity Management] | [!UICONTROL 檢視身分識別名稱空間] | 身分識別名稱空間的唯讀存取權。 |

* 您已仔細考量下列重要設定選項：

   * 您的網站適合使用體驗報告嗎？ 只有在符合下列條件時，才能正確製作體驗報表：
      * 網站內容僅由URL驅動。
      * 您網站上的頁面可透過頁面URL重現，而且您會瞭解哪些可選URL引數可推動體驗。
   * 您已清楚瞭解您想要擷取哪些頁面的內容參與分析和見解。
   * 您已清楚瞭解要擷取內容參與分析和深入分析的資產（型別）。


>
>[!MORELIKETHIS]
>
>* [引導式設定](guided.md)
>* [手動設定](manual.md)
>* [存取控制](/help/technotes/access-control.md)
>


