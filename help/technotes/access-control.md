---
title: Customer Journey Analytics 存取控制
description: 瞭解在Customer Journey Analytics中實作存取控制的方法。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Customer Journey Analytics 存取控制

三種存取層級或三種角色控管Customer Journey Analytics：產品管理員角色、產品設定檔管理員角色和使用者層級存取權。 本主題將更詳細地說明這些角色。

此外，本文將討論限制存取的更細微方式，例如Workspace管理和列層級以及值層級存取控制。

## 產品管理員角色

根據預設，獲指派產品管理員角色的使用者可獲得在Customer Journey Analytics內執行大部分工作的必要許可權。 但是，有些工作需要額外的許可權。

若要將使用者新增為產品管理員：

1. 移至[Admin Console](https://adminconsole.adobe.com/enterprise/)。

1. 選取&#x200B;[!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理員**]&#x200B;標籤> [!UICONTROL **新增管理員**]。

   您新增的使用者獲得[產品管理員預設許可權](#product-admin-default-permissions)。 如有需要，您也可以授與他們其他[許可權](#product-admin-additional-permissions)。

### 產品管理員預設許可權

產品管理員有權完成Customer Journey Analytics中的大部分任務。

產品管理員預設會獲得執行下列工作的必要許可權：

* 建立、更新和刪除資料檢視
* 更新和刪除專案、篩選器、計算量度、對象、註解或其他使用者建立的篩選器
* 與所有使用者共用 Workspace 專案
* 在[報告活動管理員](/help/reporting-activity-manager/reporting-activity-overview.md)中管理報告活動
* 從Analysis Workspace [匯出完整的資料表](/help/analysis-workspace/export/export-cloud.md)

### 產品管理員其他許可權

除了在[Admin Console](https://adminconsole.adobe.com/enterprise/)的&#x200B;**Customer Journey Analytics產品設定檔**&#x200B;中新增為產品管理員外，還需要其他許可權才能在Customer Journey Analytics中完成下列工作：

* 建立、更新及刪除資料[連線](/help/connections/overview.md)

  若要執行此工作，使用者必須屬於提供下列許可權的&#x200B;**Experience Platform產品設定檔**：
   * 資料模型製作：檢視綱要、管理綱要
   * 資料管理：檢視資料集、管理資料集
   * 資料擷取：管理來源
   * 檢視身分命名空間

     如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home)。

* 將資料集匯出至雲端[目的地](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)

  為了執行此任務，使用者需要以下Experience Platform許可權：

   * 管理目的地
   * 啟用目的地

     如需Experience Platform目的地許可權的詳細資訊，請參閱[目的地概觀](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home)。

* 使用[BI副檔名](../data-views/bi-extension.md)

  若要讓使用者使用BI擴充功能，需為產品管理員

   * 必須確定使用者的Experience Platform許可權包含具有查詢服務資源，且具有「管理查詢」和「管理查詢服務整合」選項的角色。 請參閱[管理產品設定檔的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions)。
   * 必須確定使用者具有適當的Customer Journey Analytics許可權：
      * 存取相關資料檢視的許可權。 檢視Admin Console](#customer-journey-analytics-permissions-in-admin-console)中[Customer Journey Analytics許可權的資料檢視。
      * 存取CJA BI擴充功能的許可權。 請參閱Admin Console](#customer-journey-analytics-permissions-in-admin-console)中[Customer Journey Analytics許可權的資料檢視工具。

## 產品設定檔管理員角色

產品設定檔是一組權限。產品設定檔管理員可以

* 建立並管理個別產品設定檔。 例如新增使用者或管理使用者群組及其相關聯的產品設定檔。

* 在Customer Journey Analytics中，編輯作為其管理產品設定檔一部分的資料檢視。 他們無法建立新的資料檢視。

## 使用者層級存取權

下表概述非產品管理員和Customer Journey Analytics產品管理員各種Customer Journey Analytics功能的主要存取許可權。 瞭解這些許可權可協助使用者根據其在組織內的角色和職責，有效導覽和使用Customer Journey Analytics。

| 產品功能 | 非產品管理員（使用者） | 產品管理員 |
| --- | --- | --- |
| **資料檢視** | 無法檢視/更新/建立/刪除 | 可以建立/更新/刪除 |
| **連線** | 無法檢視/更新/建立/刪除 | 可以建立/更新/刪除 |
| **篩選器** | 可以建立 | 可以建立 |
| **專案** | 可以建立 | 可以建立/更新/刪除 |
| **對象** | 可以在Admin Console中使用特殊許可權來建立 | 可以建立 |
| **計算量度** | 可以在Admin Console中使用特殊許可權來建立 | 可以建立 |

{style="table-layout:auto"}

## Workspace 專案管理

另一個層級的存取控制可用於 Workspace 報告層級。您可以限制某些使用者對特定元件的存取權。有關如何在Workspace專案層級限制元件（維度、量度、篩選器、日期範圍）以及管理如何與資料檢視相關聯的更多資訊，請參閱[管理專案](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，因此可能會因Customer Journey Analytics而有所變更。 變更它們也會回溯性地變更報告。

## 使用案例

以下幾個使用案例說明了如何在現實生活場景中使用存取控制。

### 協力廠商存取

與貴公司合作的協力廠商的團隊負責人可以成為產品資料管理員。此管理員可以將公司團隊中的使用者新增到此產品設定檔中。 此管理員可以授予特定資料檢視的存取權，並將其他使用者新增到此產品設定檔中。他們還可以修改他們可以控制的資料檢視以滿足團隊的需求。

### 列層級存取控制

假設您只想讓使用者存取一天內的資料。您可以用以下方法限制這些特定列的存取：

1. 在Customer Journey Analytics中建立一個篩選器，其中&#x200B;**[!UICONTROL 天]**&#x200B;等於您希望他們存取資料的日期。
1. 在 [!UICONTROL 資料檢視] > [!UICONTROL 設定] 中，將該過資料新增到資料檢視。
1. 儲存資料檢視，它會自動將篩選器套用至資料集。現在，任何不符合篩選器定義的列都會自動從編輯的資料檢視中排除。
1. 在 Admin Console 中建立新的產品設定檔，將使用者新增到其中並限制他們對該資料檢視的存取。

### 值層級存取控制

有權存取資料檢視的使用者只能使用管理員已包含在此資料檢視中的量度和維度。管理員可以在資料檢視中使用 [](/help/data-views/component-settings/include-exclude-values.md) 包含/排除功能，以從資料檢視中排除某些維度值。

以下是與醫療保健相關的範例：假設您從包含此資料的資料集在資料檢視中建立了一個名為「高血壓」的量度。此量度可讓您看到該量度的彙總值，但不能看到屬於該量度的個別患者。

## Admin Console中的Customer Journey Analytics許可權

[Admin Console](https://adminconsole.adobe.com/enterprise/) 中每個產品設定檔都有 **[!UICONTROL 權限]** 索引標籤。您可以將使用者新增到特定的產品設定檔。然後，將權限指派給指定的資料檢視，並指定產品設定檔中的使用者擁有哪些權限。以下是Customer Journey Analytics特定的許可權：

![Admin Console 權限](assets/permissions.png)

| 權限 | 定義 |
| --- | --- |
| **[!UICONTROL 資料檢視]** | 如果您將&#x200B;**[!UICONTROL 自動包含]**&#x200B;切換為&#x200B;**[!UICONTROL 開啟]**，則屬於此產品設定檔的使用者可以查看所有現有和新建立的資料檢視。如果此項設定為&#x200B;**[!UICONTROL 關閉]**，您可以選擇使用者有權存取的特定資料檢視。 |
| **[!UICONTROL 報告工具]**： |   |
| **[!UICONTROL 稽核記錄存取權]** | 此權限會強制對 [API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) 及稽核記錄 UI 進行權限檢查。 |
| **[!UICONTROL Analysis Workspace 存取]** | 讓使用者以Customer Journey Analytics存取Analysis Workspace。 |
| [!UICONTROL **引導式分析存取**] | 讓使用者建立[引導式分析專案](/help/guided-analysis/overview.md)。 |
| [!UICONTROL **預測**] | 讓使用者存取Analysis Workspace中的預測功能 |
| **[!UICONTROL 報告使用情況管理員]** | 讓使用者檢視和刪除在其公司中執行的任何報告。 |
| **[!UICONTROL 報告使用情況檢視]** | 讓使用者檢視所有並行報告請求。 |
| [!UICONTROL **完整資料表匯出**] | 讓使用者[將完整的資料表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。 |
| **[!UICONTROL 建立計算量度]** | 讓使用者建立[計算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 建立篩選器]** | 讓使用者建立[篩選器](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL Labs 存取]** | 讓使用者存取Customer Journey Analytics中的[Labs](/help/labs/labs.md)索引標籤。 |
| **[!UICONTROL 建立註解]** | 讓使用者建立[註解](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 建立對象]** | 讓使用者建立[對象](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 對象檢視]** | 讓使用者檢視[對象](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL **與任何人共用專案連結**] | 讓使用者[與任何人共用專案。](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| **[!UICONTROL 資料檢視工具]**： |   |
| [!UICONTROL **完整資料表匯出**] | 讓使用者[將完整的資料表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。 |
| **[!UICONTROL [!UICONTROL CJA BI延伸模組]]** | 讓使用者使用[BI延伸模組](../data-views/bi-extension.md)。 |

{style="table-layout:auto"}
