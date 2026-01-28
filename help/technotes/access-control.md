---
title: Customer Journey Analytics 存取控制
description: 了解如何在 Customer Journey Analytics 中實施存取控制。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 99%

---

# 存取控制

Customer Journey Analytics 由三個存取層級或三個角色管理：產品管理員角色、產品輪廓管理員角色和使用者層級存取權。本主題將更詳細地說明這些角色。

此外，本文還將討論使用更細微的方法來限制存取，例如 Workspace 精選設定以及列層級和值層級的存取控制。

## 角色型存取控制

可使用下列角色型存取控制層級。

### 產品管理員角色

根據預設，獲指派產品管理員角色的使用者可獲得在 Customer Journey Analytics 中執行大部分工作的必要權限。但是，有些工作需要額外的權限。

若要將使用者新增為產品管理員：

1. 前往 [Admin Console](https://adminconsole.adobe.com/enterprise/)。

1. 選取「[!UICONTROL **Customer Journey Analytics**]」>「[!UICONTROL **管理員**]」索引標籤 >「[!UICONTROL **新增管理員**]」。

   您新增的使用者會獲得[產品管理員預設權限](#product-admin-default-permissions)。如有需要，您也可以授予他們[其他權限](#product-admin-additional-permissions)。

#### 產品管理員預設權限

產品管理員具備完成 Customer Journey Analytics 中大部分任務的權限。

產品管理員預設會獲得執行下列工作的必要權限：

* 更新和刪除專案、區段、計算量度、客群、附註或其他使用者建立的區段
* 與所有使用者共用 Workspace 專案
* 在[報告活動管理員](/help/reporting-activity-manager/reporting-activity-overview.md)中管理報告活動
* 從 Analysis Workspace [匯出完整表格](/help/analysis-workspace/export/export-cloud.md)

#### 產品管理員其他權限

除了在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 的 **Customer Journey Analytics 產品輪廓**&#x200B;中新增為產品管理員外，還需要其他權限才能在 Customer Journey Analytics 中完成下列工作：

* 建立、更新及刪除[資料視圖](/help/data-views/data-views.md)。
* 建立、更新及刪除[連線](/help/connections/overview.md)

  若要執行此工作，使用者必須屬於提供下列權限的 **Experience Platform 產品輪廓**：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 沙箱] | [!UICONTROL 至少一個] | 存取連線的相關沙箱。 |
  | [!UICONTROL 資料建模] | [!UICONTROL 檢視結構描述] | 對結構描述和相關資源的唯讀存取權。 |
  | [!UICONTROL 資料建模] | [!UICONTROL 管理結構描述] | 讀取、建立、編輯和刪除結構描述與相關資源的存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 檢視資料集] | 資料集和結構描述的唯讀存取權。 |
  | [!UICONTROL 身分管理] | [!UICONTROL 檢視身分識別命名空間] | 身分識別命名空間的唯讀存取權。 |

  如需關於 Experience Platform 權限的更多資訊，請參閱[管理產品輪廓的權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/ui/permissions)。


* 如果 Journey Optimizer 與存在 Journey Optimizer 連線的 Customer Journey Analytics 整合，則也必須新增歷程權限方可存取連線：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 歷程] | [!UICONTROL 檢視歷程事件、資料來源及動作] | 歷程事件、歷程自訂動作和歷程資料來源的唯讀存取權。 |
  | [!UICONTROL 歷程] | [!UICONTROL 管理歷程事件、資料來源及動作] | 讀取、建立、編輯和刪除事件、來源或動作。 |
  | [!UICONTROL 歷程] | [!UICONTROL 檢視歷程] | 歷程的唯讀存取權。 |
  | [!UICONTROL 歷程] | [!UICONTROL 管理歷程] | 讀取、建立、編輯和刪除歷程。 |

* 將資料集匯出至[目標](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/ui/activate/export-datasets)

  若要執行此工作，使用者必須屬於提供下列權限的 **Experience Platform 產品輪廓**：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 目標] | [!UICONTROL 管理目標] | 讀取、建立和刪除目標連線和目標帳戶的存取權。 |
  | [!UICONTROL 目標] | [!UICONTROL 啟用目標] | 允許使用者啟用現有目標的區段。在啟動工作流程中啟用對應步驟。此權限也會要求針對想要對目標啟用資料的使用者授予「檢視目標」權限。 |

  如需關於 Experience Platform 權限的更多資訊，請參閱[管理產品輪廓的權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/ui/permissions)。

* 使用 [BI 擴充功能](../data-views/bi-extension.md)

  若要讓使用者能夠使用 BI 擴充功能，產品管理員

   * 必須確保使用者的 Experience Platform 權限中包含的角色，具有查詢服務資源以及「管理查詢」和「管理查詢服務整合」選項。如需關於 Experience Platform 權限的更多資訊，請參閱[管理產品輪廓的權限](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/ui/permissions)。

     | 類別 | 權限 | 說明 |
     |---|---|---|
     | [!UICONTROL 查詢服務] | [!UICONTROL 管理查詢] | 讀取、建立、編輯和刪除 Platform 資料的結構化 SQL 查詢的存取權。 |
     | [!UICONTROL 查詢服務] | [!UICONTROL 管理查詢服務整合] | 建立、更新和刪除適用於存取查詢服務的永不過期的認證。 |

   * 必須確保使用者具有適當的 Customer Journey Analytics 權限：
      * 存取相關資料視圖的權限。請參閱[使用者層級存取權](#user-level-access)中的[!UICONTROL 資料視圖]。
      * 存取 Customer Journey Analytics BI 擴充功能的權限。請參閱[使用者層級存取權](#user-level-access)中的[!UICONTROL 資料視圖工具]。

### 產品輪廓管理員角色

產品輪廓是一組權限。產品管理員可以建立產品輪廓，並可指派產品輪廓管理員來管理一個或多個產品輪廓。然後，產品輪廓管理員可以：

* 管理獲指派的產品輪廓。例如新增或移除使用者或使用者群組，以及修改產品輪廓的權限。

* 在 Customer Journey Analytics 中，編輯屬於獲指派的產品輪廓一部分的資料視圖。產品輪廓管理員無法建立新的資料視圖。

### 使用者層級存取權

下表概述不同的 Customer Journey Analytics 功能有哪些主要存取權限，而您可以針對相關使用者設定這些權限。您可以透過產品輪廓管理不同層級的使用者存取權。產品輪廓結合大量權限，而您可以將這些權限指派給單一使用者或使用者群組。

[Admin Console](https://adminconsole.adobe.com/enterprise/) 中每個產品輪廓都有「**[!UICONTROL 權限]**」索引標籤。

![Admin Console 權限](assets/permissions.png)

| 類別 | 權限 | 說明 |
| --- | --- | ---|
| [!UICONTROL 資料視圖] | *資料視圖名稱* | 如果您將&#x200B;**[!UICONTROL 自動包含]**&#x200B;切換為&#x200B;**[!UICONTROL 開啟]**，則屬於此產品輪廓的使用者可以查看所有現有和新建立的資料檢視。如果此項設定為&#x200B;**[!UICONTROL 關閉]**，您可以選擇使用者有權存取的特定資料檢視。 |
| [!UICONTROL 報告工具] | [!UICONTROL Analysis Workspace 存取權] | 允許使用者存取 [Analysis Workspace](/help/analysis-workspace/home.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 引導式分析存取權] | 讓使用者存取[引導式分析](/help/guided-analysis/overview.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立計算量度] | 讓使用者可以建立[計算量度](/help/components/calc-metrics/calc-metr-overview.md)。使用者只能標記、共用、刪除、重新命名、核准、取消核准自己建立的或是與其共用的計算量度。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立區段] | 讓使用者可以建立[區段](/help/components/segments/seg-overview.md)。使用者只能標記、共用、刪除、重新命名、核准、取消核准自己建立的或是與其共用的區段。 |
| [!UICONTROL 報告工具] | [!UICONTROL Labs 存取權] | 讓使用者可以存取 Customer Journey Analytics 中的「[Labs](/help/labs/labs.md)」索引標籤。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立附註] | 讓使用者可以建立[註解](/help/components/annotations/overview.md)。使用者只能標記、共用、刪除和重新命名自己建立的或是與其共用的註解。 |
| [!UICONTROL 報告工具] | [!UICONTROL 客群視圖] | 讓使用者可以檢視[客群](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立客群] | 讓使用者建立[對象](/help/components/audiences/audiences-overview.md)。 需要[在Adobe Experience Platform中管理區段](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/access-control/home)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 資料敘事] | 讓使用者可以[根據 Workspace 專案產生投影片簡報。](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL 報告工具] | [!UICONTROL 稽核記錄存取權] | 強制對 [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) 及稽核記錄使用者介面進行權限檢查。 |
| [!UICONTROL 報告工具] | [!UICONTROL 與任何人共用專案連結] | 讓使用者可以[與任何人共用專案。](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL 報告工具] | [!UICONTROL 預測] | 讓使用者可以存取 Analysis Workspace 中的[預測](../analysis-workspace/c-forecast/forecasting.md)功能 |
| [!UICONTROL 報告工具] | [!UICONTROL AI 助理：產品知識] | 讓使用者可以存取 [AI 助理](../ai-assistant.md)以獲取產品知識。 |
| [!UICONTROL 報告工具] | [!UICONTROL 智慧型註解] | 讓使用者可以存取[智慧型註解](/help/analysis-workspace/visualizations/intelligent-captions.md)。 |
| [!UICONTROL 資料檢視工具] | [!UICONTROL 完整表格匯出] | 讓使用者可以[將完整表格匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。 |
| [!UICONTROL 資料檢視工具] | [!UICONTROL CJA BI 擴充功能] | 讓使用者可以使用 [BI 擴充功能](../data-views/bi-extension.md)。 |

{style="table-layout:auto"}

## Workspace 專案管理

另一個層級的存取控制可用於 Workspace 報告層級。您可以限制某些使用者對特定元件的存取權。有關如何在 Workspace 專案層級限制元件 (維度、量度、客戶細分、日期範圍) 以及管理如何與資料檢視相關聯的更多資訊，請參閱[管理專案](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。量度和維度可以在[資料視圖](/help/data-views/data-views.md)中進行修改，所以在 Customer Journey Analytics 中隨時可能有所變更。變更它們也會回溯性地變更報告。

## 使用案例

以下幾個使用案例說明了如何在現實生活場景中使用存取控制。

### 第三方存取

您可以將產品輪廓管理存取權提供給與貴公司合作的第三方的團隊負責人。此管理員可以將其公司團隊中的使用者新增到此產品輪廓中。此產品輪廓管理員可以授予對特定資料視圖的存取權，並將第三方中的其他使用者新增至此產品輪廓。產品輪廓管理員可以根據第三方團隊的要求來修改資料視圖。

### 列層級存取控制

若您只想讓使用者存取一天內的資料。您可以用以下方法限制只能存取這些特定的列：

1. 在特定資料視圖的「[!UICONTROL 設定]」中建立區段，其中「[!UICONTROL 天]」等於您允他們存取資料的日期。請參閱[建立資料視圖](/help/data-views/create-dataview.md#settings-filters)了解更多資訊。
1. 儲存資料視圖，這會將區段套用至底層連線中資料集的資料部分。任何不符合區段定義的列都會自動從資料視圖中排除，且使用此資料視圖時，Analysis Workspace 無法使用這些列。
1. 在 Admin Console 中建立新的[產品輪廓](#product-profile-admin-role)，將使用者新增至產品輪廓，並僅將此特定資料視圖加入產品輪廓。

### 值層級存取控制

擁有資料視圖存取權的使用者，只能使用管理員已包含在此資料視圖中的量度和維度。管理員可以在資料視圖中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)或[值分組](../data-views/component-settings/value-bucketing.md)元件設定，從資料視圖中排除或彙總某些維度值。

例如：您在資料視圖中，使用包含資料集中個別患者資料的元件，建立名為&#x200B;*高血壓*&#x200B;的量度。您使用值分組，僅提供對分組值的存取權，因此資料的使用者看不到個別患者的資料。
