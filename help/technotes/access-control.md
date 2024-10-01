---
title: Customer Journey Analytics 存取控制
description: 瞭解在Customer Journey Analytics中實作存取控制的方法。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '1461'
ht-degree: 14%

---

# 存取控制

三種存取層級或三種角色控制Customer Journey Analytics：產品管理員角色、產品設定檔管理員角色和使用者層級存取權。 本主題將更詳細地說明這些角色。

此外，本文將討論限制存取的更細微方式，例如Workspace管理和列層級以及值層級存取控制。

## 角色型存取控制

可使用下列角色型存取控制層級。

### 產品管理員角色

根據預設，被指派為產品管理員角色的使用者將獲得在Customer Journey Analytics內執行大部分任務的必要許可權。 但是，有些工作需要額外的許可權。

若要將使用者新增為產品管理員：

1. 移至[Admin Console](https://adminconsole.adobe.com/enterprise/)。

1. 選取&#x200B;[!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理員**]&#x200B;標籤> [!UICONTROL **新增管理員**]。

   您新增的使用者獲得[產品管理員預設許可權](#product-admin-default-permissions)。 如有需要，您也可以授與他們其他[許可權](#product-admin-additional-permissions)。

#### 產品管理員預設許可權

產品管理員有權完成Customer Journey Analytics中的大部分任務。

產品管理員預設會獲得執行下列工作的必要許可權：

* 建立、更新和刪除資料檢視
* 更新和刪除專案、篩選器、計算量度、對象、註解或其他使用者建立的篩選器
* 與所有使用者共用 Workspace 專案
* 在[報告活動管理員](/help/reporting-activity-manager/reporting-activity-overview.md)中管理報告活動
* 從Analysis Workspace [匯出完整的資料表](/help/analysis-workspace/export/export-cloud.md)

#### 產品管理員其他許可權

除了在[Admin Console](https://adminconsole.adobe.com/enterprise/)的&#x200B;**Customer Journey Analytics產品設定檔**&#x200B;中被新增為產品管理員之外，還需要額外的許可權才能在Customer Journey Analytics中完成下列工作：

* 建立、更新及刪除資料[連線](/help/connections/overview.md)

  若要執行此工作，使用者必須屬於提供下列許可權的&#x200B;**Experience Platform產品設定檔**：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 資料模式] | [!UICONTROL 檢視結構描述] | 對結構描述和相關資源的唯讀存取權。 |
  | [!UICONTROL 資料模式] | [!UICONTROL 管理結構描述] | 讀取、建立、編輯和刪除結構描述和相關資源的存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 檢視資料集] | 資料集和結構描述的唯讀存取權。 |
  | [!UICONTROL 資料管理] | [!UICONTROL 管理資料集] | 存取讀取、建立、編輯和刪除資料集。 結構描述的唯讀存取權。 |
  | [!UICONTROL 資料擷取] | [!UICONTROL 管理來源] | 讀取、建立、編輯和停用來源的存取權。 |
  | [!UICONTROL Identity Management] | [!UICONTROL 檢視身分識別名稱空間] | 身分識別名稱空間的唯讀存取權。 |

  如需Experience Platform許可權的詳細資訊，請參閱[管理產品設定檔的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions)。

* 將資料集匯出至[目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)

  若要執行此工作，使用者必須屬於提供下列許可權的&#x200B;**Experience Platform產品設定檔**：

  | 類別 | 權限 | 說明 |
  |---|---|---|
  | [!UICONTROL 目的地] | [!UICONTROL 管理目的地] | 讀取、建立和刪除目的地連線和目的地帳戶的存取權。 |
  | [!UICONTROL 目的地] | [!UICONTROL 啟用目的地] | 允許使用者啟用現有目的地的區段。 在啟動工作流程中啟用對應步驟。 此許可權也會要求將「檢視目的地」許可權授與想要對目的地啟用資料的使用者。 |

  如需Experience Platform許可權的詳細資訊，請參閱[管理產品設定檔的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions)。

* 使用[BI副檔名](../data-views/bi-extension.md)

  若要讓使用者使用BI擴充功能，需為產品管理員

   * 必須確定使用者的Experience Platform許可權包含具有查詢服務資源，且具有「管理查詢」和「管理查詢服務整合」選項的角色。 如需Experience Platform許可權的詳細資訊，請參閱[管理產品設定檔的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions)。

     | 類別 | 權限 | 說明 |
     |---|---|---| 
     | [!UICONTROL 查詢服務] | [!UICONTROL 管理查詢] | 存取Platform資料的讀取、建立、編輯和刪除結構化SQL查詢。 |
     | [!UICONTROL 查詢服務] | [!UICONTROL 管理查詢服務整合] | 存取以建立、更新和刪除不會到期的認證以進行查詢服務存取。 |

   * 必須確定使用者具有適當的Customer Journey Analytics許可權：
      * 存取相關資料檢視的許可權。 在[使用者層級存取](#user-level-access)中檢視[!UICONTROL 資料檢視]。
      * 存取Customer Journey AnalyticsBI擴充功能的許可權。 在[使用者層級存取](#user-level-access)中檢視[!UICONTROL 資料檢視工具]。

### 產品設定檔管理員角色

產品設定檔是一組權限。產品管理員可建立產品設定檔，並可指派產品設定檔管理員來管理一或多個產品設定檔。 然後，產品設定檔管理員可以：

* 管理指派的產品設定檔。 例如新增或移除使用者或使用者群組，以及修改產品設定檔的許可權。

* 在Customer Journey Analytics中，編輯屬於已指派產品設定檔一部分的資料檢視。 產品設定檔管理員無法建立新的資料檢視。

### 使用者層級存取權

下表概述您可以為相關使用者設定的不同Customer Journey Analytics功能的主要存取許可權。 您可以透過產品設定檔管理不同的使用者存取層級。 產品設定檔結合了大量許可權，您可以將其指派給個別使用者或使用者群組。

**[!UICONTROL 許可權]**&#x200B;索引標籤是[Admin Console](https://adminconsole.adobe.com/enterprise/)中每個產品設定檔的一部分。

![Admin Console 權限](assets/permissions.png)

| 類別 | 權限 | 說明 |
| --- | --- | ---|
| [!UICONTROL 資料檢視] | *資料檢視名稱* | 如果您將&#x200B;**[!UICONTROL 自動包含]**&#x200B;切換為&#x200B;**[!UICONTROL 開啟]**，則屬於此產品設定檔的使用者可以查看所有現有和新建立的資料檢視。如果此項設定為&#x200B;**[!UICONTROL 關閉]**，您可以選擇使用者有權存取的特定資料檢視。 |
| [!UICONTROL 報告工具] | [!UICONTROL Analysis Workspace 存取] | 允許使用者存取[Analysis Workspace](/help/analysis-workspace/home.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 引導式分析存取] | 讓使用者存取[引導式分析](/help/guided-analysis/overview.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立計算量度] | 讓使用者建立[計算量度](/help/components/calc-metrics/calc-metr-overview.md)。 使用者只能標籤、共用、刪除、重新命名、核准、取消核准其建立的計算量度或與其共用的計算量度。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立篩選器] | 讓使用者建立[篩選器](/help/components/filters/filters-overview.md)。 使用者只能標籤、共用、刪除、重新命名、核准、取消核准他們建立的篩選器或與他們共用的篩選器。 |
| [!UICONTROL 報告工具] | [!UICONTROL Labs 存取] | 讓使用者存取Customer Journey Analytics中的[Labs](/help/labs/labs.md)索引標籤。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立註解] | 讓使用者建立[註解](/help/components/annotations/overview.md)。 使用者只能標籤、共用、刪除和重新命名他們建立的註解或與他們共用的註解。 |
| [!UICONTROL 報告工具] | [!UICONTROL 建立客群] | 讓使用者建立[對象](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL 報告工具] | [!UICONTROL 稽核記錄存取權] | 強制對[API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/)和稽核記錄UI進行許可權檢查。 |
| [!UICONTROL 報告工具] | [!UICONTROL 與任何人共用專案連結] | 讓使用者[與任何人共用專案。](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL 報告工具] | [!UICONTROL 預測] | 讓使用者存取Analysis Workspace中的[Forecasting](../analysis-workspace/c-forecast/forecasting.md)功能 |
| [!UICONTROL 報告工具] | [!UICONTROL AI助理：產品知識] | 讓使用者存取[AI小幫手](../ai-assistant.md)以取得產品知識。 |
| [!UICONTROL 報告工具] | [!UICONTROL 智慧型註解] | 讓使用者存取[智慧型字幕](/help/analysis-workspace/visualizations/intelligent-captions.md)。 |
| [!UICONTROL 資料檢視工具] | [!UICONTROL 完整資料表匯出] | 讓使用者[將完整的資料表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。 |
| [!UICONTROL 資料檢視工具] | [!UICONTROL CJA BI延伸模組] | 讓使用者使用[BI延伸模組](../data-views/bi-extension.md)。 |

{style="table-layout:auto"}

## Workspace 專案管理

另一個層級的存取控制可用於 Workspace 報告層級。您可以限制某些使用者對特定元件的存取權。有關如何在Workspace專案層級限制元件（維度、量度、篩選器、日期範圍）以及管理如何與資料檢視相關聯的更多資訊，請參閱[管理專案](/help/analysis-workspace/curate-share/curate.md)。

## 授與個別量度或維度的存取權

當您使用 Customer Journey Analytics 時，無法像在傳統 Adobe Analytics 中一樣為個別量度或維度授予或拒絕權限。量度和維度可以在[資料檢視](/help/data-views/data-views.md)中修改，因此可能會因Customer Journey Analytics而有所變更。 變更它們也會回溯性地變更報告。

## 使用案例

以下幾個使用案例說明了如何在現實生活場景中使用存取控制。

### 協力廠商存取

您可以提供產品設定檔管理存取權給貴公司合作的協力廠商的團隊負責人。 此管理員可以將公司團隊中的使用者新增到此產品設定檔中。 此產品設定檔管理員可以授予特定資料檢視的存取權，並將協力廠商內的其他使用者新增到此產品設定檔中。 產品設定檔管理員可以修改資料檢視，以符合第三方團隊的需求。

### 列層級存取控制

您只想讓使用者存取一天內的資料。 您可以用以下方法限制這些特定列的存取：

1. 在特定資料檢視的[!UICONTROL 設定]中建立篩選器，其中[!UICONTROL 天]等於您希望他們存取資料的日期。 如需詳細資訊，請參閱[建立資料檢視](/help/data-views/create-dataview.md#settings-filters)。
1. 儲存資料檢視，這會將篩選器套用至基礎連線中資料集的資料部分。 任何不符合篩選器定義的列都會自動從資料檢視中排除，且無法在此資料檢視用於Analysis Workspace。
1. 在Admin Console中建立新的[產品設定檔](#product-profile-admin-role)，將使用者新增至產品設定檔，並僅將此特定資料檢視加入產品設定檔。

### 值層級存取控制

有權存取資料檢視的使用者只能使用管理員已包含在此資料檢視中的量度和維度。 管理員可以在資料檢視中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)或[值分組](../data-views/component-settings/value-bucketing.md)元件設定，以從資料檢視中排除或彙總某些維度值。

例如：您在資料檢視中，從包含資料集中個別患者資料的元件建立名為&#x200B;*高血壓*&#x200B;的量度。 您使用值分組來僅提供對分組值的存取權，因此資料的使用者看不到個別患者的資料。


