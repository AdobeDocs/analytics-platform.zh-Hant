---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出帳戶
keywords: Analysis Workspace
title: 設定雲端匯出帳戶
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# 設定雲端匯出帳戶

{{select-package}}

在您可以將Customer Journey Analytics資料匯出至雲端目的地之前（如所述） [將Customer Journey Analytics資料匯出至雲端](/help/analysis-workspace/export/export-cloud.md)，您需要新增並設定傳送資料的位置。

此程式包含依照本文所述新增及設定帳戶(例如Amazon S3、Google Cloud Platform等)，然後依照所述新增及設定該帳戶內的位置（例如帳戶內的資料夾） [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

如需有關如何管理現有帳戶（包括檢視、編輯和刪除帳戶）的資訊，請參閱 [管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md).

您需要為Customer Journey Analytics設定存取雲端目的地帳戶所需的資訊。

若要設定雲端匯出帳戶：

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].
1. 在 [!UICONTROL 匯出] 頁面，選取 [!UICONTROL **位置帳戶**] 標籤。
1. 選取 [!UICONTROL **新增帳戶**].

   ![新增帳戶](assets/account-add.png)

   新增帳戶對話方塊隨即顯示。
1. 指定下列資訊： |欄位 |函式 | ---------|----------| | [!UICONTROL **位置帳戶名稱**] |位置帳戶的名稱。 建立位置時會顯示此名稱 | | [!UICONTROL **位置帳戶說明**] |提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。 | | [!UICONTROL **帳戶型別**] |選取您要匯出的雲端帳戶型別。 可用的帳戶型別為Amazon S3角色ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和Adobe Experience Platform。 |
1. 在 [!UICONTROL **帳戶屬性**] 區段，指定您所選取之帳戶型別的特定資訊。

   如需設定指示，請展開以下對應至 [!UICONTROL **帳戶型別**] 您已選取的專案。

   +++Amazon S3 Role ARN

   指定下列資訊以設定Amazon S3角色ARN帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必須提供角色ARN (Amazon資源名稱)，Adobe才能使用該角色來存取Amazon S3帳戶。 若要這麼做，請建立來源帳戶的IAM許可權原則、將原則附加至使用者，然後建立目的地帳戶的角色。 如需特定資訊，請參閱 [此AWS檔案](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **使用者 ARN**] | 使用者ARN (Amazon資源名稱)由Adobe提供。 您必須將此使用者附加至您建立的原則。 |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   指定下列資訊以設定Google Cloud Platform帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **專案 ID**] | 您從Google Cloud帳戶複製的Google Cloud專案ID。 請參閱 [有關取得專案ID的Google Cloud檔案](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **主體**] | 主體由Adobe提供。 按一下 [!UICONTROL **複製**] 圖示加以存取 [!UICONTROL **主體**] 欄位以複製欄位內容，然後確定您授予主體許可權，以便在Google Cloud Platform中將檔案上傳至此貯體。 <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   指定下列資訊以設定Azure SAS帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **金鑰保存庫 URI**] | <p>Azure金鑰儲存庫中SAS權杖的路徑。  若要設定Azure SAS，您需要使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。 如需詳細資訊，請參閱 [有關如何指派金鑰儲存庫存取原則的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **金鑰保存庫祕密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **位置帳戶密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   指定下列資訊以設定Azure RBAC帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帳戶密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   指定下列資訊以設定Snowflake帳戶：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **帳戶識別碼**] | 可唯一識別組織內，以及Snowflake支援的雲端平台和雲端區域的全球網路中的Snowflake帳戶。 <p>如需詳細資訊，請參閱 [Snowflake檔案中的帳戶識別碼頁面](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **使用者**] | 指定連線的使用者登入名稱。 這是將專門用於Adobe的使用者。 在這裡指定使用者名稱后，您可以在Snowflake中建立使用者。 <p>如需詳細資訊，請參閱 [Snowflake檔案中的「JDBC驅動程式連線引數參考」頁面](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **角色**] | 在驅動程式起始的Snowflake工作階段中使用的預設存取控制角色。 您應該為具有讀取和寫入存取權的Adobe建立特定的角色。<p>如需詳細資訊，請參閱 [Snowflake檔案中的「JDBC驅動程式連線引數參考」頁面](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **公開金鑰**] | 公開金鑰由Adobe提供。 選取旁邊的「複製」圖示 [!UICONTROL **公開金鑰**] 欄位以複製欄位的內容，然後在您的Snowflake帳戶中使用公開金鑰。 如需詳細資訊，請參閱 [Snowflake檔案中的金鑰組驗證和金鑰組輪換頁面](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   所有Adobe Experience Platform客戶都能將資料匯出至AEP Landing Zone。

   指定下列資訊以設定Adobe Experience Platform帳戶。

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS組織ID由Adobe提供。 按一下旁邊的「複製」圖示 [!UICONTROL **IMS組織ID**] 欄位以複製欄位內容，然後在您的Adobe Experience Platform帳戶中使用ID。 |

+++

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

