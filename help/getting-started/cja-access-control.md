---
title: CJA訪問控制
description: 瞭解建立連接、添加資料集、建立資料視圖等的訪問控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 53%

---

# CJA訪問控制

要在Customer Journey Analytics中訪問和執行任務，必須將您作為管理員添加到 **Customer Journey Analytics產品配置檔案** 的 [Admin Console](https://adminconsole.adobe.com/enterprise/)。 產品管理員可獲得下列權限：

* 建立/更新/刪除連接或資料視圖
* 更新/刪除其他使用者建立的專案、篩選器、計算量度或篩選
* 將Workspace項目共用給所有用戶

## 需要的Adobe Experience Platform權限

僅僅在Customer Journey Analytics中成為產品管理員是不夠的，無法建立、更新或刪除連接。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：

* 檢視結構描述
* 管理結構描述
* 檢視身分識別命名空間
* 檢視資料集

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 授予對單個度量或維的訪問權限

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。 量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動，這樣也會回溯性地變更報告。

## 使用者存取權

Customer Journey Analytics中的非產品管理員（用戶）無法查看資料視圖或連接，但可以建立篩選器、項目和計算的度量。

