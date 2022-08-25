---
title: CJA 存取控制
description: 瞭解在CJA中實現訪問控制的方法。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: ccb13b9632433f2fcc9c765e9527f157dad632d4
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 17%

---

# CJA 存取控制

Customer Journey Analytics(CJA)由三個訪問級別或三個角色管理：產品管理員角色、產品配置檔案管理員角色和用戶級訪問。 本主題將更詳細地解釋這些角色。

## 產品管理員角色

產品管理員有權在CJA內完成任何必要的任務。 您必須作為產品管理員添加到 **Customer Journey Analytics產品配置檔案** 的 [Admin Console](https://adminconsole.adobe.com/enterprise/) 在 [!UICONTROL Customer Journey Analytics] > [!UICONTROL 管理員] 頁籤 [!UICONTROL 添加管理員]。 產品管理員可獲得下列權限：

* 建立/更新/刪除連線或資料檢視
* 更新/刪除由其他用戶建立的項目、篩選器、計算度量、受眾、注釋或篩選器
* 與所有使用者共用工作區專案

僅在Customer Journey Analytics中成為產品管理員是不夠的，無法建立、更新或刪除 [連接](/help/connections/overview.md)。 若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：

* 資料模型製作：檢視結構描述、管理結構描述
* 資料管理：檢視資料集、管理資料集
* 資料擷取：管理來源
* 檢視身分命名空間

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 產品配置檔案管理員角色

產品配置檔案是一組權限。 產品配置檔案管理員可以

* 建立和管理單個產品配置檔案，如添加新用戶。

* 在CJA中，編輯資料視圖，這些資料視圖是他們管理的產品配置檔案的一部分。 他們無法建立新資料視圖。

## 用戶級訪問

Customer Journey Analytics中的用戶無法建立、編輯或查看資料視圖或連接。 用戶可以在Admin Console中建立具有特殊權限的篩選器、項目、訪問群體和計算度量。

## 工作區項目建立

可以在工作區報告級別使用另一級訪問控制。 您可以限制某些用戶對特定元件的訪問。 有關如何在Workspace項目級別限制元件（尺寸、度量、段、日期範圍）以及將建立與資料視圖關聯的詳細資訊，請參閱 [建立項目](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。 可以在中修改度量和維 [資料視圖](/help/data-views/data-views.md) 因此在CJA中可能發生變化。 更改它們還追溯更改報告。

## 使用案例

以下幾個使用案例說明了如何在現實環境中使用訪問控制。

### 第三方訪問

您公司與之合作的第三方有一個團隊負責人，該團隊負責人可以成為「產品配置檔案」管理員。 然後，此管理員可以將其團隊中的用戶添加到此產品配置檔案。 此管理員可授予對特定資料視圖的訪問權限，並將其他用戶添加到此產品配置檔案。 他們還可以修改他們有權控制的那些資料視圖以滿足其團隊的需求。

### 行級訪問控制

假設您希望僅讓用戶從一天開始訪問資料。 以下是您如何限制對這些特定行的訪問：

1. 在CJA中建立篩選器，其中 **[!UICONTROL 日]** 等於您希望他們具有資料存取權限的日期。
1. 在 [!UICONTROL 資料視圖] > [!UICONTROL 設定]，將該篩選器添加到資料視圖。
1. 保存資料視圖，並自動將篩選器應用於資料集。 現在，任何不符合篩選器定義的行都會自動從編輯的資料視圖中排除。
1. 在Admin Console中建立新產品配置檔案，向其添加用戶並限制其對此資料視圖的訪問。

### 值級訪問控制

有權訪問資料視圖的用戶只能使用管理員在此資料視圖中包括的度量和維。 管理員可以使用 [包括/排除功能](/help/data-views/component-settings/include-exclude-values.md) 例如，在資料視圖中，從資料視圖中排除某些維值。

下面是一個與醫療保健相關的示例：假設你在一個資料視圖中建立一個稱為&quot;高血壓&quot;的度量，從一個包含這些資料的資料集中。 事實上，這是一個指標可以讓你看到這個指標的總值，但不是那些被它所覆蓋的病人。

## CJA權限

的 **[!UICONTROL 權限]** 頁籤是每個產品配置檔案的一部分 [Admin Console](https://adminconsole.adobe.com/enterprise/)。 您可以將用戶添加到特定的產品配置檔案。 然後，您為特定資料視圖分配權限，並指定產品配置檔案中的用戶具有哪些權限。 下面是特定於CJA的權限：

![管理控制台權限](assets/permissions.png)

| 權限 | 定義 |
| --- | --- |
| **[!UICONTROL 資料檢視]** | 如果切換 **[!UICONTROL 自動包括]** 至 **[!UICONTROL 開]**，屬於此產品配置檔案的用戶可以查看所有現有和新建立的資料視圖。 如果此設定設定為 **[!UICONTROL 關閉]**，您可以選擇用戶有權訪問的特定資料視圖。 |
| **[!UICONTROL 報告工具]**: |  |
| **[!UICONTROL 稽核記錄存取權]** | 目前， [審核日誌](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 僅通過API可用。 此權限用於正在開發的未來UI。 |
| **[!UICONTROL 報告使用情況管理員]** | 允許用戶查看和刪除其公司中運行的任何報表。 （報告使用功能尚未發佈。） |
| **[!UICONTROL 報告使用情況檢視]** | 允許用戶查看所有併發報告請求。 （報告使用功能尚未發佈。） |
| **[!UICONTROL 計算度量建立]** | 允許用戶建立 [計算度量](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 篩選器建立]** | 允許用戶建立 [篩選](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL Labs 存取]** | 允許用戶訪問 [實驗室](/help/labs/labs.md) 的子菜單。 |
| **[!UICONTROL 附註建立]** | 允許用戶建立 [注釋](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 對象建立]** | 允許用戶建立 [觀眾](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 對象檢視]** | 允許用戶查看 [觀眾](/help/components/audiences/audiences-overview.md)。 |