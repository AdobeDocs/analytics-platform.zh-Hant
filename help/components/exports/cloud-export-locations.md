---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 設定雲端匯出位置
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: 1bf36f60b0b3aec04bb1452e5f63f97051d9bb50
workflow-type: tm+mt
source-wordcount: '1932'
ht-degree: 21%

---

# 設定雲端匯出位置

在您可以依照[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)中的說明將Customer Journey Analytics報表匯出至雲端目的地之前，您需要新增並設定資料所要傳送的位置。

此程式包括新增及設定帳戶(例如Amazon S3、Google Cloud Platform等)，如[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)中所述，然後新增及設定該帳戶內的位置（例如帳戶內的資料夾），如本文所述。

如需有關如何管理現有位置（包括檢視、編輯和刪除位置）的資訊，請參閱[管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md)。

## 開始建立雲端匯出位置

1. 您必須先新增帳戶，才能新增位置。 如果您尚未新增帳戶，請依照[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)中的說明新增帳戶。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **位置**]&#x200B;索引標籤，然後選取&#x200B;[!UICONTROL **新增位置**]。

   ![已選取[位置]索引標籤的[匯出]視窗，醒目提示[新增位置]按鈕](assets/location-add.png)

   或

   選取&#x200B;[!UICONTROL **位置帳戶**]&#x200B;索引標籤，在您要新增位置的現有帳戶上選取3點圖示，然後選取&#x200B;[!UICONTROL **新增位置**]。

   ![GCP帳戶與省略符號下拉式功能表，顯示選取的新增位置](assets/add-location-existing-account.png)

   「位置」對話方塊隨即顯示。

1. 指定下列資訊：
|欄位 | 函式 |
---------|----------|
| [!UICONTROL **名稱**] | 位置的名稱。  |
| [!UICONTROL **描述**] | 提供位置的簡短說明，以協助將其與帳戶上的其他位置區分開來。 |
| [!UICONTROL **讓位置可供您組織中的所有使用者使用**] | **注意：**&#x200B;此功能處於發行的有限測試階段，可能尚未在您的環境中提供。 當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。 <p>啟用此選項可允許組織中的其他使用者使用該位置。</p> <p>共用位置時，請考量下列事項：</p><ul><li>您無法取消共用您共用的位置。</li><li>共用位置只能由位置擁有者編輯。</li><li>只有在與位置關聯的帳戶也共用時，才能共用位置。</li></ul> |
| [!UICONTROL **位置帳戶**] | 選取您要建立位置的帳戶。 如需有關如何建立帳戶的資訊，請參閱[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)。 |

1. 在「[!UICONTROL **位置屬性**]」部分，指明您位置帳戶特定的帳戶類型資訊。

   繼續下列對應您在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;欄位中選取的帳戶型別的區段。

   * [AEP 資料登陸區域](#aep-data-landing-zone)
   * [Amazon S3 Role ARN](#amazon-s3-role-arn)
   * [Google Cloud Platform](#google-cloud-platform)
   * [Azure SAS](#azure-sas)
   * [Azure RBAC](#azure-rbac)
   * [Snowflake](#snowflake)

### AEP 資料登陸區域

>[!IMPORTANT]
>
>將Customer Journey Analytics報表匯出至Adobe Experience Platform資料登陸區域時，請務必在7天內下載資料，然後從AEP資料登陸區域將其刪除。 7天後，資料會自動從AEP資料登陸區域刪除。

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Adobe Experience Platform資料登陸區域位置：

   <!-- still need to update; can't create AEP account -->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/` |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

1. 在AEP資料登陸區域中存取資料的最簡單方式是使用Microsoft Azure Storage Explorer。 此工具與設定[AEP資料登陸區域帳戶](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)的指示中所使用的工具相同。

   1. 開啟[Microsoft Azure儲存體總管](https://azure.microsoft.com/en-us/products/storage/storage-explorer/)。

   1. 移至&#x200B;[!UICONTROL **儲存體帳戶**] > [!UICONTROL **（附加的容器）**] > [!UICONTROL **Blob容器**] > **[!UICONTROL cjaexport-_number_]**>*** your_container_name ***。

      >[!NOTE]
      >
      >資料夾名稱&#x200B;**[!UICONTROL cjaexport-_number_]**是Azure儲存體總管提供的預設名稱。 如果您只有與SAS URI關聯的單一連線（一般），則此資料夾的名稱將是&#x200B;**[!UICONTROL cjaexport-1]**。


      ![存取Azure儲存體總管中的檔案](assets/azure-storage-explorer-access.png)

   1. 選取您要下載的匯出，然後選取&#x200B;[!UICONTROL **下載**]&#x200B;進行下載。

### Amazon S3 Role ARN

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Amazon S3角色ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體**] | 您想要將Customer Journey Analytics資料傳送至的Amazon S3帳戶中的貯體。 <p>請確定Adobe提供的使用者ARN具有`S3:PutObject`許可權，以便上傳檔案至此儲存貯體。 </p><p>貯體名稱必須符合特定的命名規則。例如，這些名稱長度必須在 3 至 63 個字元之間，只能由小寫字母、數字、點 (.) 和連字號 (-) 組成，並且必須以字母或數字開頭和結尾。[AWS 文件中有命名規則的完整清單](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucketnamingrules.html)。 </p> |
   | [!UICONTROL **前置詞**] | 在貯體內，您希望資料放置的資料夾。指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如，folder_name/ |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

### Google Cloud Platform

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Google Cloud Platform位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體**] | 您想要傳送Customer Journey Analytics資料的GCP帳戶中的貯體。 <p>確定您已授予`roles/storage.objectCreator`許可權給Adobe提供的主體。 ([設定Google Cloud Platform帳戶](/help/components/exports/cloud-export-accounts.md)時提供主體。) <p>有關授予權限的資訊，請參閱 Google Cloud 文件中的「[新增主體至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add)」。</p><p>如果您的組織使用[組織原則限制](https://cloud.google.com/storage/docs/org-policy-constraints)僅允許在允許清單中的 Google Cloud Platform 帳戶，則您需要以下 Adobe 擁有的 Google Cloud Platform 組織 ID： <ul><li>`DISPLAY_NAME`：`adobe.com`</li><li>`ID`：`178012854243`</li><li>`DIRECTORY_CUSTOMER_ID`：`C02jo8puj`</li></ul> </p> |
   | [!UICONTROL **前置詞**] | 在貯體內，您希望資料放置的資料夾。指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如，folder_name/ |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

### Azure SAS

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Azure SAS位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定要將Customer Journey Analytics資料傳送到的帳戶中的容器。 |
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/`<p>確保設定 Azure SAS 帳戶時，在 Key Vault 密碼名稱欄位中指定的 SAS 權杖儲存體擁有`Write`權限。這樣可讓 SAS 權杖在您的 Azure 容器中建立檔案。 <p>如果您希望 SAS 權杖也覆寫檔案，請確保 SAS 權杖儲存體擁有`Delete`權限。</p><p>有關詳細資訊，請參閱 Azure Blob 儲存文件中的「[Blob 儲存資源](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources)」 。</p> |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

### Azure RBAC

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Azure RBAC位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定要將Customer Journey Analytics資料傳送到的帳戶中的容器。 確保您授予權限可上傳檔案至先前已建立的 Azure 應用程式。 |
   | [!UICONTROL **前置詞**] | 在容器內，您希望資料放置的資料夾。指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/`<p>確保設定 Azure RBAC 帳戶時，您所指定的應用程式 ID 已獲得 `Storage Blob Data Contributor` 角色授權，以便該角色可存取容器 (資料夾)。</p> <p>若要了解更多資訊，請參閱「[Azure 內建角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)」。</p> |
   | [!UICONTROL **帳戶**] | Azure儲存體帳戶。 |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

### Snowflake

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從如上所述的[匯出]頁面，在[開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * [從Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)匯出完整資料表時

1. 在&#x200B;[!UICONTROL **新增位置**]&#x200B;對話方塊的&#x200B;[!UICONTROL **位置屬性**]&#x200B;區段中，指定下列資訊以設定Snowflake位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **資料庫**] | 指定的資料庫應為現有資料庫。 您建立的角色必須具備存取此資料庫的許可權。<p>這是與階段名稱關聯的資料庫。</p><p>您可以使用下列命令將此角色許可權授與Snowflake中的資料庫： `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>如需詳細資訊，請參閱Snowflake檔案](https://docs.snowflake.com/en/sql-reference/commands-database)中的[資料庫、結構描述和共用命令頁面。</p> |
   | [!UICONTROL **綱要**] | 指定的結構描述應該是現有的結構描述。 您建立的角色必須具備存取此綱要的許可權。<p>這是與階段名稱關聯的結構描述。<p>您可以使用下列命令，將您建立的許可權授與Snowflake中的結構描述： `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>如需詳細資訊，請參閱Snowflake檔案](https://docs.snowflake.com/en/sql-reference/commands-database)中的[資料庫、結構描述和共用命令頁面。</p> |
   | [!UICONTROL **階段名稱**] | 以Snowflake儲存資料檔案的內部階段名稱。<p>請確定您在帳戶中指定的角色具有此階段名稱的讀取和寫入許可權。 (由於您正在授與讀取和寫入存取權，我們建議您使用僅由Adobe使用的階段。)<p>您可以使用以下命令授予Snowflake中階段名稱的讀取和寫入許可權： `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>如需授與許可權給角色的相關資訊，請參閱Snowflake檔案](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege)中的[授與許可權。 <p>如需階段名稱的詳細資訊，請參閱Snowflake檔案](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)中的[選擇本機檔案的內部階段頁面。</p> |
   | [!UICONTROL **階段路徑**] | 資料檔以Snowflake儲存所在位置的路徑。 <p>如需詳細資訊，請參閱Snowflake檔案](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage)中的[選擇本機檔案的內部階段頁面。</p> |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱[將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。
