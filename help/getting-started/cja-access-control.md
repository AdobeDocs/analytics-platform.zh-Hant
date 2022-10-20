---
title: CJA 存取控制
description: 了解在 CJA 中實施存取控制的方法。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 8262d7f0ec56a792bfcd8fe94b7f7685ee5b5438
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 98%

---

# CJA 存取控制

Customer Journey Analytics (CJA) 由三個存取層級或三個角色管理：產品管理員角色、產品設定檔管理員角色和使用者層級存取權。本主題將更詳細地說明這些角色。

此外，我們還將討論使用更細微的方法來限制存取，例如 Workspace 管理和列層級以及值層級存取控制。

## 產品管理員角色

產品管理員有權在 CJA 中完成任何必要的任務。您必須在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 的 [!UICONTROL Customer Journey Analytics] > [!UICONTROL 管理員]索引標籤 > [!UICONTROL 新增管理員]底下，將自己新增為 **Customer Journey Analytics 產品設定檔**&#x200B;的產品管理員。產品管理員可獲得下列權限：

* 建立/更新/刪除連線或資料檢視
* 更新/刪除專案、篩選器、計算量度、對象、註解或其他使用者建立的篩選器
* 與所有使用者共用 Workspace 專案

光是成為 Customer Journey Analytics 中的產品管理員仍無法建立、更新或刪除 [連線](/help/connections/overview.md)。若要建立與 Experience Platform 資料集的連線，您還需要 Experience Platform 權限。具體來說，您必須成為 **Experience Platform 產品設定檔**&#x200B;的管理員，進而取得下列權限：

* 資料模型製作：檢視結構描述、管理結構描述
* 資料管理：檢視資料集、管理資料集
* 資料擷取：管理來源
* 檢視身分命名空間

如需 Experience Platform 權限的詳細資訊，請參閱[存取 Adobe Experience Platform 控制項](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 產品設定檔管理員角色

產品設定檔是一組權限。產品設定檔管理員可以

* 建立和管理單一產品設定檔，例如新增使用者或管理使用者群組及其關聯的產品設定檔。

* 在 CJA 中，編輯作為其管理產品設定檔一部分的資料檢視。他們無法建立新的資料檢視。

## 使用者層級存取權

Customer Journey Analytics 中的使用者無法建立、編輯、查看資料檢視或連線。使用者可以在 Admin Console 中建立具有特殊權限的篩選器、專案、對象和計算量度。

## Workspace 專案管理

另一個層級的存取控制可用於 Workspace 報告層級。您可以限制某些使用者對特定元件的存取權。有關如何在 Workspace 專案層級限制元件 (維度、量度、客戶細分、日期範圍) 以及管理如何與資料檢視相關聯的更多資訊，請參閱[管理專案](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，所以可能會在 CJA 中有所變動。變更它們也會回溯性地變更報告。

## 使用案例

以下幾個使用案例說明了如何在現實生活場景中使用存取控制。

### 協力廠商存取

與貴公司合作的協力廠商的團隊負責人可以成為產品資料管理員。然後，此管理員可以將其團隊中的使用者新增到此產品設定檔中。此管理員可以授予特定資料檢視的存取權，並將其他使用者新增到此產品設定檔中。他們還可以修改他們可以控制的資料檢視以滿足團隊的需求。

### 列層級存取控制

假設您只想讓使用者存取一天內的資料。您可以用以下方法限制這些特定列的存取：

1. 在 CJA 中建立一個篩選器，其中&#x200B;**[!UICONTROL 日期]**&#x200B;為您希望他們存取資料的日期。
1. 在[!UICONTROL 資料檢視] > [!UICONTROL 設定] 中，將該過資料新增到資料檢視。
1. 儲存資料檢視，它會自動將篩選器套用至資料集。現在，任何不符合篩選器定義的列都會自動從編輯的資料檢視中排除。
1. 在 Admin Console 中建立新的產品設定檔，將使用者新增到其中並限制他們對該資料檢視的存取。

### 值層級存取控制

有權存取資料檢視的使用者只能使用管理員已包含在此資料檢視中的量度和維度。管理員可以在資料檢視中使用 [](/help/data-views/component-settings/include-exclude-values.md) 包含/排除功能，以從資料檢視中排除某些維度值。

以下是與醫療保健相關的範例：假設您從包含此資料的資料集在資料檢視中建立了一個名為「高血壓」的量度。此量度可讓您看到該量度的彙總值，但不能看到屬於該量度的個別患者。

## Admin Console 中的 CJA 權限

[Admin Console](https://adminconsole.adobe.com/enterprise/) 中每個產品設定檔都有&#x200B;**[!UICONTROL 權限]**&#x200B;索引標籤。您可以將使用者新增到特定的產品設定檔。然後，將權限指派給指定的資料檢視，並指定產品設定檔中的使用者擁有哪些權限。以下是 CJA 特定的權限：

![Admin Console 權限](assets/permissions.png)

| 權限 | 定義 |
| --- | --- |
| **[!UICONTROL 資料檢視]** | 如果您將&#x200B;**[!UICONTROL 自動包含]**&#x200B;切換為&#x200B;**[!UICONTROL 開啟]**，則屬於此產品設定檔的使用者可以查看所有現有和新建立的資料檢視。如果此項設定為&#x200B;**[!UICONTROL 關閉]**，您可以選擇使用者有權存取的特定資料檢視。 |
| **[!UICONTROL 報告工具]**： |  |
| **[!UICONTROL 稽核記錄存取權]** | 此權限會在 [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 和 [稽核記錄UI](/help/privacy/audit-log.md). |
| **[!UICONTROL 報告使用情況管理員]** | 可讓使用者查看和刪除在其公司中執行的任何報告。(報告使用情況功能尚未發佈。) |
| **[!UICONTROL 報告使用情況檢視]** | 可讓使用者查看所有並行報告要求。(報告使用情況功能尚未發佈。) |
| **[!UICONTROL 建立計算量度]** | 可讓使用者建立[計算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 建立篩選器]** | 可讓使用者建立[篩選器](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL Labs 存取]** | 可讓使用者存取 CJA 中的 [Labs](/help/labs/labs.md) 索引標籤。 |
| **[!UICONTROL 建立註解]** | 可讓使用者建立[註解](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 建立對象]** | 可讓使用者建立[對象](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 對象檢視]** | 可讓使用者查看[對象](/help/components/audiences/audiences-overview.md)。 |

{style=&quot;table-layout:auto&quot;}
