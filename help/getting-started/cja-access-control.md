---
title: CJA 存取控制
description: 了解建立連線、新增資料集、建立資料檢視等作業的存取控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: ht
source-wordcount: '241'
ht-degree: 100%

---

# CJA 存取控制

若要在 Customer Journey Analytics 中存取及執行任務，您必須在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中將自己新增為 **Customer Journey Analytics 產品描述檔**&#x200B;的管理員。 產品管理員可獲得下列權限：

* 建立/更新/刪除連線或資料檢視
* 更新/刪除專案、篩選條件、計算量度或其他使用者建立的篩選條件
* 與所有使用者共用工作區專案

## 必要的 Adobe Experience Platform 權限

光是成為 Customer Journey Analytics 中的產品管理員仍無法建立、更新或刪除連線。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：

* 檢視結構描述
* 管理結構描述
* 檢視身分識別命名空間
* 檢視資料集

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。 量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動，這樣也會回溯性地變更報告。

## 使用者存取權

Customer Journey Analytics 中的非產品管理員 (使用者) 無法查看資料檢視或連線，但可以建立篩選條件、專案和計算量度。

