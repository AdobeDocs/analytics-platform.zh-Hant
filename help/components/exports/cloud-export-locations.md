---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出位置
keywords: Analysis Workspace
title: 設定雲端匯出位置
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 92b59f0e1f2668e5c2b2d1a73aee5ef6fbc7c420
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 5%

---

# 設定雲端匯出位置

在您可以將Customer Journey Analytics報表匯出至雲端目的地之前（如所述） [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)，您需要新增並設定傳送資料的位置。

此程式包括新增及設定帳戶(例如Amazon S3、Google Cloud Platform等)，如所述 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)，然後在該帳戶內新增並設定位置（例如帳戶內的資料夾），如本文所述。

如需有關如何管理現有位置（包括檢視、編輯和刪除位置）的資訊，請參閱 [管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md).

若要設定雲端匯出位置：

1. 您必須先新增帳戶，才能新增位置。 如果您尚未新增帳戶，請依照所述新增帳戶 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md).
1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].
1. 選取 [!UICONTROL **位置**] 索引標籤，然後選取 [!UICONTROL **新增位置**].

   ![新增位置按鈕](assets/location-add.png)

   或

   選取 [!UICONTROL **位置帳戶**] 索引標籤中，選取現有帳戶上要新增位置的3點圖示，然後選取 [!UICONTROL **新增位置**].

   ![將位置新增至現有帳戶](assets/add-location-existing-account.png)

   「位置」對話方塊隨即顯示。

1. 指定下列資訊： |欄位 |函式 | ---------|----------| | [!UICONTROL **名稱**] |位置名稱。  | | [!UICONTROL **說明**] |提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **位置帳戶**] |選取您要建立位置的帳戶。 如需有關如何建立帳戶的資訊，請參閱 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md). |

1. 在 [!UICONTROL **位置屬性**] 區段，指定您位置帳戶之帳戶型別的專屬資訊。

   如需設定指示，請展開以下與您在所選帳戶型別對應的區段 [!UICONTROL **位置帳戶**] 欄位。

   +++Adobe Experience Platform資料登陸區域

   指定下列資訊以設定Adobe Experience Platform資料登陸區域位置：

   <!-- still need to update; can't create AEP account -->

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS組織ID由Adobe提供。 按一下旁邊的「複製」圖示 [!UICONTROL **IMS組織ID**] 欄位以複製欄位內容，然後在您的Adobe Experience Platform帳戶中使用ID。 |
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |

+++

   +++Amazon S3 Role ARN

   指定下列資訊以設定Amazon S3角色ARN位置：

   <!-- still need to update; can't create S3 role ARN account -->

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **分段**] | 您想要將Adobe Analytics資料傳送至的Amazon S3帳戶中的貯體。 確保Adobe提供的使用者ARN有權將檔案上傳到此貯體。 |
   | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定下列資訊來設定Google Cloud平台位置：

   <!-- still need to update; can't create GCP account -->

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **分段**] | 您想要傳送Customer Journey Analytics資料的GCP帳戶中的貯體。 確保您已授予Adobe所提供之主體的許可權，可將檔案上傳至此儲存貯體。 (本金提供於 [設定Google Cloud Platform帳戶](/help/components/exports/cloud-export-accounts.md).) 如需授與許可權的詳細資訊，請參閱 [將主體新增至貯體層級原則](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) (位於Google Cloud檔案中)。 |
   | [!UICONTROL **前置詞**] | 要放置資料之儲存貯體中的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定下列資訊以設定Azure SAS位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器名稱**] | 您指定要將Customer Journey Analytics資料傳送到的帳戶中的容器。 |
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定下列資訊以設定Azure RBAC位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **容器**] | 您指定要將Adobe Analytics資料傳送至何處的帳戶中的容器。 請確定您授與許可權，可以將檔案上傳至您先前建立的Azure應用程式。 |
   | [!UICONTROL **前置詞**] | 容器內您要放置資料的資料夾。 指定資料夾名稱，然後在名稱后面加上反斜線以建立資料夾。 例如， `folder_name/` |
   | [!UICONTROL **帳戶**] | Azure儲存體帳戶。 |

   {style="table-layout:auto"}

+++

   +++Snowflake

   指定下列資訊以設定Snowflake位置：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **資料庫**] | 指定的資料庫應該是指定的預設角色具有許可權的現有資料庫。<p>這是與階段名稱關聯的資料庫。</p> <p>如需詳細資訊，請參閱 [Snowflake檔案中的「資料庫、綱要，以及共用命令」頁面](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **綱要**] | 指定的結構描述應該是指定的預設角色具有許可權的現有結構描述。<p>這是與階段名稱關聯的結構描述。</p><p>如需詳細資訊，請參閱 [Snowflake檔案中的「資料庫、綱要，以及共用命令」頁面](https://docs.snowflake.com/en/sql-reference/commands-database).</p> |
   | [!UICONTROL **階段名稱**] | 以Snowflake儲存資料檔案的階段名稱。 <p>請確定您在帳戶中指定的角色具有此階段名稱的讀取和寫入許可權。 (由於您正在授與讀取和寫入存取權，我們建議您使用僅由Adobe使用的階段。) <p>如需授與許可權給角色的相關資訊，請參閱 [在Snowflake檔案中授與許可權](https://docs.snowflake.com/en/sql-reference/sql/grant-privilege). <p>如需有關階段名稱的詳細資訊，請參閱 [在Snowflake檔案中選擇「本機檔案的內部階段」頁面](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **階段路徑**] | 資料檔以Snowflake儲存所在位置的路徑。 <p>如需詳細資訊，請參閱 [在Snowflake檔案中選擇「本機檔案的內部階段」頁面](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 您現在可以將資料從Analysis Workspace匯出至您設定的帳戶和位置。 如需如何將資料匯出至雲端的詳細資訊，請參閱 [將專案資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md).
