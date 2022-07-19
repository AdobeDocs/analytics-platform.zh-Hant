---
title: CJA訪問控制
description: 瞭解建立連接、添加資料集、建立資料視圖等的訪問控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---


# CJA訪問控制

若要建立連線和資料集等，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中設定以下權限：

* 若要存取 Customer Journey Analytics 或建立連線，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中將自己新增為 **Customer Journey Analytics 產品**&#x200B;的管理員。 產品管理員可獲得下列權限：
   * 建立/更新/刪除連線或資料檢視
   * 更新/刪除其他使用者建立的專案、篩選器、計算量度或篩選
   * 與所有使用者共用「工作區」專案
* 光有 Customer Journey Analytics 的產品管理員權限，仍無法建立、更新或刪除連線。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：
   * 檢視結構描述
   * 管理結構描述
   * 檢視身分識別命名空間
   * 檢視資料集

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

>[!NOTE]
>
>當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。 量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動，這樣也會回溯性地變更報告。

## 使用者存取權

Customer Journey Analytics 中，產品管理員以外的使用者無法查看資料檢視或連線，但可以建立篩選器、專案和計算量度。