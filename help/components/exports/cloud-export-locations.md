---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 設定雲端匯出位置
feature: Components
exl-id: 93f1cca0-95da-41a0-a4f9-5ab620a5b9da
role: User, Admin
source-git-commit: dadb22558c93d0f528986dfc033b6668467d1c01
workflow-type: tm+mt
source-wordcount: '1738'
ht-degree: 3%

---

# 設定雲端匯出位置

在您可以將Customer Journey Analytics報表匯出至雲端目的地之前（如所述） [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)，您需要新增並設定傳送資料的位置。

此程式包括新增及設定帳戶(例如Amazon S3、Google Cloud Platform等)，如所述 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)，然後在該帳戶內新增並設定位置（例如帳戶內的資料夾），如本文所述。

如需有關如何管理現有位置（包括檢視、編輯和刪除位置）的資訊，請參閱 [管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md).

## 開始建立雲端匯出位置

1. 您必須先新增帳戶，才能新增位置。 如果您尚未新增帳戶，請依照所述新增帳戶 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md).

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].

1. 選取 [!UICONTROL **位置**] 索引標籤，然後選取 [!UICONTROL **新增位置**].

   ![匯出視窗，其中選取了「位置」標籤，並醒目提示新增位置按鈕](assets/location-add.png)

   或

   選取 [!UICONTROL **位置帳戶**] 索引標籤中，選取現有帳戶上要新增位置的3點圖示，然後選取 [!UICONTROL **新增位置**].

   ![GCP帳戶和省略符號下拉式功能表，其中顯示已選取新增位置](assets/add-location-existing-account.png)

   「位置」對話方塊隨即顯示。

1. 指定下列資訊： |欄位 | 函式 | ---------|----------| | [!UICONTROL **名稱**] | 位置的名稱。  | | [!UICONTROL **說明**] | 提供位置的簡短說明，以協助將其與帳戶上的其他位置區分開來。 | | [!UICONTROL **位置帳戶**] | 選取您要建立位置的帳戶。 如需有關如何建立帳戶的資訊，請參閱 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md). |

1. 在 [!UICONTROL **位置屬性**] 區段，指定您位置帳戶之帳戶型別的專屬資訊。

   繼續以下對應至您在所選帳戶型別的區段 [!UICONTROL **位置帳戶**] 欄位。

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

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Adobe Experience Platform資料登陸區域的位置：

   <!-- still need to update; can't create AEP account -->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/` |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).

1. 在AEP資料登陸區域中存取資料的最簡單方式是使用Microsoft Azure Storage Explorer。 此工具與設定相關資訊的指示相同， [AEP資料登陸區域帳戶](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone).

   1. 開啟 [Microsoft Azure儲存體總管](https://azure.microsoft.com/en-us/products/storage/storage-explorer/).

   1. 前往 [!UICONTROL **儲存體帳戶**] > [!UICONTROL **（附加的容器）**] > [!UICONTROL **Blob容器**] > **[!UICONTROL cjaexport-_數字_]**>*** your_container_name ***.

      >[!NOTE]
      >
      >資料夾名稱 **[!UICONTROL cjaexport-_數字_]**是Azure儲存體總管提供的預設名稱。 如果您只有與SAS URI關聯的單一連線（正常），則此資料夾的名稱將為&#x200B;**[!UICONTROL cjaexport-1]**.


      ![存取Azure儲存體總管中的檔案](assets/azure-storage-explorer-access.png)

   1. 選取您要下載的匯出，然後選取「 」 [!UICONTROL **下載**] 以下載。

### Amazon S3 Role ARN

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Amazon S3角色ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 <p>請確定Adobe提供的使用者ARN具有 `S3:PutObject` 許可權可將檔案上傳至此貯體。 </p> |
   | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).

### Google Cloud Platform

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Google Cloud平台位置：

   <!-- still need to update; can't create GCP account -->

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **貯體**] | 您想要將Adobe Analytics資料傳送至的GCP帳戶中的貯體。 <p>確認您已授予 `roles/storage.objectCreator` 由Adobe提供的主體許可權。 (本金提供於 [設定Google Cloud Platform帳戶](/help/components/exports/cloud-export-accounts.md).) <p>如需授與許可權的詳細資訊，請參閱 [將主體新增至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) (位於Google Cloud檔案中)。</p> |
   | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).

### Azure SAS

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Azure SAS位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定要將Customer Journey Analytics資料傳送到的帳戶中的容器。 |
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/`<p>設定Azure SAS帳戶時，請確定您在「金鑰儲存庫機密名稱」欄位中指定的SAS權杖存放區具有 `Write` 許可權。 這可讓SAS權杖在您的Azure容器中建立檔案。 <p>如果您也希望SAS權杖覆寫檔案，請確定SAS權杖存放區具有 `Delete` 許可權。</p><p>如需詳細資訊，請參閱 [Blob儲存資源](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blobs-introduction#blob-storage-resources) Azure Blob儲存檔案。</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).

### Azure RBAC

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Azure RBAC位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 請確定您授與許可權，可以將檔案上傳至您先前建立的Azure應用程式。 |
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上斜線以建立資料夾。 例如， `folder_name/`<p>請確定您在設定Azure RBAC帳戶時指定的應用程式ID已被授予 `Storage Blob Data Contributor` 角色以存取容器（資料夾）。</p> <p>如需詳細資訊，請參閱 [Azure內建角色](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles).</p> |
   | [!UICONTROL **帳戶**] | Azure儲存體帳戶。 |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).

### Snowflake

1. 透過下列任一種方式開始建立雲端匯出位置：

   * 從「匯出」頁面（如上所述），在 [開始建立雲端匯出位置](#begin-creating-a-cloud-export-location)

   * 時間 [從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)

1. 在 [!UICONTROL **位置屬性**] 的區段 [!UICONTROL **新增位置**] 對話方塊中，指定下列資訊以設定Snowflake位置：

   | 欄位 | 函數 |
   |---------|----------|
   | [!UICONTROL **DB**] | 指定的資料庫應為現有資料庫。 您建立的角色必須具備存取此資料庫的許可權。<p>這是與階段名稱關聯的資料庫。</p><p>您可以使用下列命令，將此角色許可權授與Snowflake中的資料庫： `GRANT USAGE ON DATABASE <your_database> TO ROLE <your_role>;`</p> <p>如需詳細資訊，請參閱 [Snowflake檔案中的「資料庫、綱要，以及共用命令」頁面](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **綱要**] | 指定的結構描述應該是現有的結構描述。 您建立的角色必須具備存取此綱要的許可權。<p>這是與階段名稱關聯的結構描述。<p>您可以使用下列命令，將您建立的許可權授與Snowflake綱要中的角色： `GRANT USAGE ON SCHEMA <your_database>.<your_schema> TO ROLE <your_role>;`</p><p>如需詳細資訊，請參閱 [Snowflake檔案中的「資料庫、綱要，以及共用命令」頁面](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **階段名稱**] | 以Snowflake儲存資料檔案的內部階段名稱。<p>請確定您在帳戶中指定的角色具有此階段名稱的讀取和寫入許可權。 (由於您正在授與讀取和寫入存取權，我們建議您使用僅由Adobe使用的階段。)<p>您可以使用以下命令授予Snowflake中階段名稱的讀取和寫入許可權： `GRANT READ, WRITE ON STAGE <your_database>.<your_schema>.<your_stage_name> TO ROLE <your_role>;`</p> <p>如需授與許可權給角色的相關資訊，請參閱 [在Snowflake檔案中授與許可權](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>如需有關階段名稱的詳細資訊，請參閱 [在Snowflake檔案中選擇「本機檔案的內部階段」頁面](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **階段路徑**] | 資料檔以Snowflake儲存所在位置的路徑。 <p>如需詳細資訊，請參閱 [在Snowflake檔案中選擇「本機檔案的內部階段」頁面](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).
