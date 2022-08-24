---
title: CJA 存取控制
description: 瞭解CJA中三級訪問的訪問控制要求。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# CJA 存取控制

Customer Journey Analytics(CJA)由三個訪問級別或三個角色管理：產品管理員角色、產品配置檔案管理員角色和用戶級訪問。 本主題將更詳細地解釋這些角色。

## 產品管理員角色

產品管理員有權在CJA內完成任何必要的任務。 您必須作為產品管理員添加到 **Customer Journey Analytics產品配置檔案** 的 [Admin Console](https://adminconsole.adobe.com/enterprise/) 在「Customer Journey Analytics」>「管理員」頁籤>「添加管理員」下。 產品管理員可獲得下列權限：

* 建立/更新/刪除連線或資料檢視
* 更新/刪除專案、篩選條件、計算量度或其他使用者建立的篩選條件
* 與所有使用者共用工作區專案

光是成為 Customer Journey Analytics 中的產品管理員仍無法建立、更新或刪除連線。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：

* 資料模型製作：檢視結構描述、管理結構描述
* 資料管理：檢視資料集、管理資料集
* 資料擷取：管理來源
* 檢視身分命名空間

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 產品配置檔案管理員角色

此角色與「產品管理員」類似，但範圍更有限。 產品配置檔案是一組權限。 例如，產品配置檔案管理員可以授予產品配置檔案成員對所有或特定資料視圖的訪問權限。 對於報告工具，這些管理員可以添加以下權限：

![管理控制台權限](assets/permissions.png)

## 用戶級訪問

Customer Journey Analytics中的非產品管理員（用戶）無法建立、編輯或查看資料視圖或連接。 用戶可以在Admin Console中建立具有特殊權限的篩選器、項目、訪問群體和計算度量。

## 工作區項目建立

有關如何在Workspace項目級別限制元件（尺寸、度量、段、日期範圍）以及將建立與資料視圖關聯的詳細資訊，請參閱 [建立項目](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。 量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動，這樣也會回溯性地變更報告。

