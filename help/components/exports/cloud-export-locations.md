---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 設定雲端匯出位置
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 6aea4179b368b50641a03a9cb53e4243fa428f4c
workflow-type: tm+mt
source-wordcount: '3136'
ht-degree: 20%

---

# 設定雲端匯出位置 {#configure-cloud-export-locations}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-prefix"
>title="前置詞"
>abstract="您希望放置資料的容器，其內的根資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如， `folder_name/`"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-name"
>title="檔案名稱和路徑"
>abstract="指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。<br/>在檔案名稱和路徑中使用變數，使其成為動態的。 <br/>例如，若您指定`${yyyy}/${MM}/${dd}/my-report-${instance_id}-${idx}`，2026年1月15日自動傳送至此目的地的匯出會有下列檔案路徑和名稱： `[prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv` <br/>按一下下列連結以取得可用變數清單。"

<!-- markdownlint-enable MD034 -->

在您可以將Customer Journey Analytics報表匯出至雲端目的地（從[Analysis Workspace](/help/analysis-workspace/export/export-cloud.md)或從[Report Builder](/help/report-builder/report-builder-export.md)）之前，您需要新增並設定資料所要傳送的位置。 此程式包含：

1. 按[配置雲導出帳戶](/help/components/exports/cloud-export-accounts.md)中所述添加和配置帳戶(如AmazonS3、Google雲平台等)

1. 添加和配置該帳戶中的位置（如帳戶中的資料夾），如本文所述。

有關如何管理現有位置（包括查看、編輯和刪除位置）的資訊，請參閱[管理雲導出位置和帳戶](/help/components/exports/manage-export-locations.md)。

## 開始建立雲導出位置

1. 您必須先新增帳戶，才能新增位置。 如果您尚未新增帳戶，請依照[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)中的說明新增帳戶。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤，然後選取&#x200B;[!UICONTROL **新增位置**]。

   ![已選取[位置]索引標籤的[匯出]視窗，醒目提示[新增位置]按鈕](assets/location-add.png)

   或

   選擇&#x200B;[!UICONTROL **位置帳戶**]&#x200B;頁籤，在要添加位置的現有帳戶上選擇3點表徵圖，然後選擇&#x200B;[!UICONTROL **添加位置**]。

   ![顯示選定添加位置的GCP帳戶和省略號下拉菜單](assets/add-location-existing-account.png)

   將顯示「位置」對話框。

1. 註明下列資訊：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **名稱**] | 位置的名稱。 |
   | [!UICONTROL **說明**] | 提供該位置的簡短說明，以幫助將其與客戶上的其他位置區別開來。 |
   | [!UICONTROL **使您組織中的所有用戶都可以使用位置**] | 啟用此選項可允許組織中的其他用戶使用該位置。 <p>共用位置時請考慮以下事項：</p><ul><li>無法取消共用您共用的位置。</li><li>共用位置只能由該位置的所有者編輯。</li><li>僅當與該位置關聯的帳戶也是共用的時，才可共用該位置。</li></ul> |
   | [!UICONTROL **位置帳戶**] | 選擇要在其中建立位置的帳戶。 有關如何建立帳戶的資訊，請參閱[配置雲導出帳戶](/help/components/exports/cloud-export-accounts.md)。 |

1. 在「[!UICONTROL **位置屬性**]」部分，指明您位置帳戶特定的帳戶類型資訊。

   繼續下面與您在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;欄位中選擇的帳戶類型對應的部分。

   * [AEP 資料登陸區域](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP 資料登陸區域

>[!IMPORTANT]
>
>將Customer Journey Analytics報告導出到Adobe Experience Platform資料登錄區時，請確保在7天內下載資料，然後從AEP資料登錄區中將其刪除。 7天後，資料將自動從AEP資料登錄區中刪除。

1. 通過以下任一方式開始建立雲導出位置：

   * 從上述的「導出」頁面，在[開始建立雲導出位置](#begin-creating-a-cloud-export-location)中

   * [從Analysis Workspace導出完整表時](/help/analysis-workspace/export/export-cloud.md#export-full-tables)

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;對話框的&#x200B;[!UICONTROL **位置屬性**]&#x200B;部分，指定以下資訊以配置Adobe Experience Platform資料登錄區域位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如， `folder_name/` |
   | [!UICONTROL **檔案名稱和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，檔案名稱可以根據傳送日期命名，然後放置在與每月相對應的資料夾中。</p><p>在檔案名稱和路徑中使用下列任何變數，使其成為動態變數：</p><ul><li>**{yyyy}**： 4位數的日曆年度（區分大小寫）</li><li>**{yy}**:2位日曆年（區分大小寫）</li><li>**{MM}**: 2位月（區分大小寫）</li><li>**{dd}**：2位數日（區分大小寫）</li><li>**{HH}**： 2位數小時（區分大小寫）</li><li>**{mm}**： 2位數的分鐘數（區分大小寫）</li><li>**{ss}**： 2位數秒數（區分大小寫）</li><li>**{fff}**： 3位數nanoseconds （區分大小寫）</li><li>**{instance_id}**：請求（實例）UUID</li><li>**{export_id}**：導出（計畫）UUID</li><li>**{idx}**：索引從0開始（每個檔案遞增）</li><li>**{total}**：整個傳輸作業的檔案總號</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，若您指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動傳送至此目的地的匯出檔案路徑和名稱如下： [prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

1. 在AEP Data Landing Zone中存取資料的最簡單方式，就是使用Microsoft Azure Storage Explorer。 儲存資源管理器是配置[AEP資料登錄區域帳戶](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)的說明中使用的相同工具。

   1. 開啟[MicrosoftAzure儲存資源管理器](https://azure.microsoft.com/en-us/products/storage/storage-explorer/)。

   1. 轉到&#x200B;[!UICONTROL **儲存帳戶**] > [!UICONTROL **（附加容器）**] > [!UICONTROL **Blob容器**] > **[!UICONTROL cjaexport-_數字_]**>*** yourcontainername ***。

      >[!NOTE]
      >
      >資料夾名稱&#x200B;**[!UICONTROL cjaexport-_數字_]**是Azure儲存資源管理器提供的預設名稱。 如果您只有一個與SAS URI關聯的連接（正常），則此資料夾的名稱將為&#x200B;**[!UICONTROL cjaexport-1]**。


      ![訪問Azure儲存資源管理器中的檔案](assets/azure-storage-explorer-access.png)

   1. 選擇要下載的導出，然後選擇&#x200B;[!UICONTROL **下載**]&#x200B;以下載。

### Amazon S3 Role ARN

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Amazon S3角色ARN位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **儲存貯體**] | 您想要將Customer Journey Analytics資料傳送至的Amazon S3帳戶中的貯體。 <p>請確定Adobe提供的使用者ARN具有`S3:PutObject`許可權，才能將檔案上傳至此儲存貯體。 </p><p>貯體名稱必須符合特定的命名規則。例如，這些名稱長度必須在 3 至 63 個字元之間，只能由小寫字母、數字、點 (.) 和連字號 (-) 組成，並且必須以字母或數字開頭和結尾。[AWS文檔中提供了完整的命名規則清單](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **前置詞**] | 在貯體內，您希望資料放置的資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如，folder_name/ |
   | [!UICONTROL **檔案名和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，檔案名稱可以根據傳送日期命名，然後放置在與每月相對應的資料夾中。</p><p>在檔案名稱和路徑中使用下列任何變數，使其成為動態變數：</p><ul><li>**{yyyy}**： 4位數的日曆年度（區分大小寫）</li><li>**{yy}**:2位日曆年（區分大小寫）</li><li>**{MM}**: 2位月（區分大小寫）</li><li>**{dd}**: 2位日（區分大小寫）</li><li>**{HH}**: 2位小時（區分大小寫）</li><li>**{mm}**: 2位分鐘（區分大小寫）</li><li>**{ss}**: 2位秒（區分大小寫）</li><li>**{fff}**:3位納米秒（區分大小寫）</li><li>**{instance_id}**：請求（實例）UUID</li><li>**{export_id}**：導出（計畫）UUID</li><li>**{idx}**：索引從0開始（每個檔案遞增）</li><li>**{total}**：整個傳輸作業的檔案總號</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，若您指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動傳送至此目的地的匯出檔案路徑和名稱如下： [prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

### Google Cloud Platform

1. 通過以下任一方式開始建立雲導出位置：

   * 從上述的「導出」頁面，在[開始建立雲導出位置](#begin-creating-a-cloud-export-location)中

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Google Cloud Platform位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **儲存貯體**] | 您想要將Customer Journey Analytics資料傳送至的GCP帳戶中的貯體。 <p>確保已向Adobe提供的承擔者授予`roles/storage.objectCreator`權限。 (當[配置Google雲平台帳戶](/help/components/exports/cloud-export-accounts.md)時提供主體。) <p>有關授予權限的資訊，請參閱 Google Cloud 文件中的「[新增主體至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add)」。</p><p>如果您的組織使用[組織原則限制](https://cloud.google.com/storage/docs/org-policy-constraints)僅允許在允許清單中的 Google Cloud Platform 帳戶，則您需要以下 Adobe 擁有的 Google Cloud Platform 組織 ID： <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **前置詞**] | 在貯體內，您希望資料放置的資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如，folder_name/ |
   | [!UICONTROL **檔案名和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，檔案名稱可以根據傳送日期命名，然後放置在與每月相對應的資料夾中。</p><p>在檔案名稱和路徑中使用下列任何變數，使其成為動態變數：</p><ul><li>**{yyyy}**： 4位數的日曆年度（區分大小寫）</li><li>**{yy}**：2位數的日曆年度（區分大小寫）</li><li>**{MM}**：2位數的月份（區分大小寫）</li><li>**{dd}**：2位數日（區分大小寫）</li><li>**{HH}**： 2位數小時（區分大小寫）</li><li>**{mm}**： 2位數的分鐘數（區分大小寫）</li><li>**{ss}**： 2位數秒數（區分大小寫）</li><li>**{fff}**： 3位數nanoseconds （區分大小寫）</li><li>**{instance_id}**：要求（執行個體） UUID</li><li>**{export_id}**：匯出（排程） UUID</li><li>**{idx}**：索引從0開始（每個檔案都增加）</li><li>**{total}**：整個傳輸工作的檔案總數</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，如果指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動發送到此目標的導出將具有以下檔案路徑和名稱： [prefix_folder_name]/2026/01/15/my-report-[ UUID]-1.csv</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 現在，您可以將資料從Analysis Workspace導出到您配置的帳戶和位置。 有關如何將資料導出到雲的資訊，請參閱[將項目資料導出到雲](/help/analysis-workspace/export/export-cloud.md)。

### Azure SAS

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Azure SAS位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定的帳戶中要發送Customer Journey Analytics資料的容器。 |
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如， `folder_name/`<p>確保設定 Azure SAS 帳戶時，在 Key Vault 密碼名稱欄位中指定的 SAS 權杖儲存體擁有`Write`權限。這樣可讓 SAS 權杖在您的 Azure 容器中建立檔案。 <p>如果您希望 SAS 權杖也覆寫檔案，請確保 SAS 權杖儲存體擁有`Delete`權限。</p><p>如需更多資訊，請參閱 Azure Blob 儲存體文件中的 [Blob 儲存資源](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)。</p> |
   | [!UICONTROL **檔案名和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，檔案名稱可以根據傳送日期命名，然後放置在與每月相對應的資料夾中。</p><p>在檔案名稱和路徑中使用下列任何變數，使其成為動態變數：</p><ul><li>**{yyyy}**： 4位數的日曆年度（區分大小寫）</li><li>**{yy}**:2位日曆年（區分大小寫）</li><li>**{MM}**：2位數的月份（區分大小寫）</li><li>**{dd}**: 2位日（區分大小寫）</li><li>**{HH}**: 2位小時（區分大小寫）</li><li>**{mm}**: 2位分鐘（區分大小寫）</li><li>**{ss}**: 2位秒（區分大小寫）</li><li>**{fff}**:3位納米秒（區分大小寫）</li><li>**{instance_id}**：請求（實例）UUID</li><li>**{export_id}**：導出（計畫）UUID</li><li>**{idx}**：索引從0開始（每個檔案遞增）</li><li>**{total}**：整個傳輸作業的檔案總號</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，若您指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動傳送至此目的地的匯出檔案路徑和名稱如下： [prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 現在，您可以將資料從Analysis Workspace導出到您配置的帳戶和位置。 有關如何將資料導出到雲的資訊，請參閱[將項目資料導出到雲](/help/analysis-workspace/export/export-cloud.md)。

### Azure RBAC

1. 通過以下任一方式開始建立雲導出位置：

   * 從上述的「導出」頁面，在[開始建立雲導出位置](#begin-creating-a-cloud-export-location)中

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Azure RBAC位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定要將Customer Journey Analytics資料傳送至何處的帳戶中的容器。 確保您授予權限可上傳檔案至先前已建立的 Azure 應用程式。 |
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定靜態資料夾名稱，然後在名稱後面加上斜線，建立資料夾。例如， `folder_name/`<p>確保設定 Azure RBAC 帳戶時，您所指定的應用程式 ID 已獲得 `Storage Blob Data Contributor` 角色授權，以便該角色可存取容器 (資料夾)。</p> <p>若要了解更多資訊，請參閱「[Azure 內建角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)」。</p> |
   | [!UICONTROL **檔案名稱和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，可以根據檔案的交付日期來命名檔案名，然後將其放入每月對應的資料夾中。</p> <p>在檔案名和路徑中使用下列變數中的任意變數使其動態：</p><ul><li>**{yyyy}**: 4位日曆年（區分大小寫）</li><li>**{yy}**:2位日曆年（區分大小寫）</li><li>**{MM}**: 2位月（區分大小寫）</li><li>**{dd}**: 2位日（區分大小寫）</li><li>**{HH}**： 2位數小時（區分大小寫）</li><li>**{mm}**： 2位數的分鐘數（區分大小寫）</li><li>**{ss}**： 2位數秒數（區分大小寫）</li><li>**{fff}**： 3位數nanoseconds （區分大小寫）</li><li>**{instance_id}**：要求（執行個體） UUID</li><li>**{export_id}**：導出（計畫）UUID</li><li>**{idx}**：索引從0開始（每個檔案遞增）</li><li>**{total}**：整個傳輸作業的檔案總號</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，如果指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動發送到此目標的導出將具有以下檔案路徑和名稱： [prefix_folder_name]/2026/01/15/my-report-[ UUID]-1.csv</p> |
   | [!UICONTROL **帳戶**] | Azure 儲存體帳戶。 |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 現在，您可以將資料從Analysis Workspace導出到您配置的帳戶和位置。 有關如何將資料導出到雲的資訊，請參閱[將項目資料導出到雲](/help/analysis-workspace/export/export-cloud.md)。

### Snowflake

1. 通過以下任一方式開始建立雲導出位置：

   * 從上述的「導出」頁面，在[開始建立雲導出位置](#begin-creating-a-cloud-export-location)中

   * [從Analysis Workspace導出完整表時](/help/analysis-workspace/export/export-cloud.md#export-full-tables)

1. 在&#x200B;[!UICONTROL **添加位置**]&#x200B;對話框的&#x200B;[!UICONTROL **位置屬性**]&#x200B;部分中，指定以下資訊以配置Snowflake位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **資料庫**] | 指定的資料庫應為現有資料庫。 您建立的角色需要具有訪問此資料庫的權限。<p>這是與階段名關聯的資料庫。</p><p>可以使用以下命令將此角色權限授予Snowflake中的資料庫： `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>有關詳細資訊，請參閱Snowflake文檔[中的](https://docs.snowflake.com/en/sql-reference/commands-database)資料庫、架構和共用命令頁。</p> |
   | [!UICONTROL **結構描述**] | 指定的架構應為現有架構。 您建立的角色需要具有訪問此架構的權限。<p>這是與階段名稱關聯的架構。</p><p>可以使用以下命令將您建立的角色授予Snowflake中的架構權限： `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>有關詳細資訊，請參閱Snowflake文檔[中的](https://docs.snowflake.com/en/sql-reference/commands-database)資料庫、架構和共用命令頁。</p> |
   | [!UICONTROL **階段名稱**] | 資料檔案儲存在Snowflake中的內部階段的名稱。<p>確保您在帳戶上指定的角色對此階段名稱具有「讀」和「寫」權限。 (因為您正在授予讀和寫訪問權限，因此我們建議使用僅由Adobe使用的階段。)</p><p>可以使用以下命令授予對Snowflake中階段名稱的「讀」和「寫」訪問權限： `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>有關授予角色權限的資訊，請參閱Snowflake文檔[中的「授予權限」。](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege)</p> <p>有關階段名稱的詳細資訊，請參閱Snowflake文檔[中的](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)為本地檔案選擇內部階段頁。</p> |
   | [!UICONTROL **階段路徑**] | 資料檔在Snowflake中儲存位置的路徑。 <p>如需詳細資訊，請參閱Snowflake檔案中的[選擇本機檔案的內部階段頁面](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)。</p> |
   | [!UICONTROL **檔案名稱和路徑**] | 指定動態自訂檔案名稱，用於傳送至此位置的自動匯出作業。 您也可以在檔案名稱前面加上動態自訂檔案路徑。 <p>此選項可讓您自動建立檔案名稱及放置資料夾，讓檔案名稱可預測並以邏輯方式組織到資料夾中。 例如，檔案名稱可以根據傳送日期命名，然後放置在與每月相對應的資料夾中。</p><p>在檔案名稱和路徑中使用下列任何變數，使其成為動態變數：</p><ul><li>**{yyyy}**： 4位數的日曆年度（區分大小寫）</li><li>**{yy}**：2位數的日曆年度（區分大小寫）</li><li>**{MM}**：2位數的月份（區分大小寫）</li><li>**{dd}**：2位數日（區分大小寫）</li><li>**{HH}**： 2位數小時（區分大小寫）</li><li>**{mm}**： 2位數的分鐘數（區分大小寫）</li><li>**{ss}**： 2位數秒數（區分大小寫）</li><li>**{fff}**： 3位數nanoseconds （區分大小寫）</li><li>**{instance_id}**：請求（實例）UUID</li><li>**{export_id}**：導出（計畫）UUID</li><li>**{idx}**：索引從0開始（每個檔案遞增）</li><li>**{total}**：整個傳輸作業的檔案總號</li><li>**{completion_millis}**：傳輸時間（毫秒）</li></ul></p><p>例如，若您指定`${yyyy}/${MM}/${dd}/my-report-${instance_id} -${idx}`，則在2026年1月15日自動傳送至此目的地的匯出檔案路徑和名稱如下： [prefix_folder_name]/2026/01/15/my-report-[UUID]-1.csv</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。
