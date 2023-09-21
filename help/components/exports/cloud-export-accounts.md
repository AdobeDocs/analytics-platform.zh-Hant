---
description: 設定可傳送Customer Journey Analytics資料的雲端匯出帳戶
keywords: Analysis Workspace
title: 設定雲端匯出帳戶
feature: Components
hide: true
hidefromtoc: true
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '1580'
ht-degree: 6%

---

# 設定雲端匯出帳戶

在您可以將Customer Journey Analytics報表匯出至雲端目的地之前（如所述） [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)，您需要新增並設定要傳送資料的目的地。

此程式包含依照本文所述新增及設定帳戶(例如Amazon S3、Google Cloud Platform等)，然後依照所述新增及設定該帳戶內的位置（例如帳戶內的資料夾） [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

如需有關如何管理現有帳戶（包括檢視、編輯和刪除帳戶）的資訊，請參閱 [管理雲端匯出位置和帳戶](/help/components/exports/manage-export-locations.md).

## 開始建立雲端匯出帳戶

1. 在Customer Journey Analytics中選取 [!UICONTROL **元件**] > [!UICONTROL **匯出**].
1. 在 [!UICONTROL 匯出] 頁面，選取 [!UICONTROL **位置帳戶**] 標籤。
1. 選取 [!UICONTROL **新增帳戶**].

   ![新增帳戶](assets/account-add.png)

   新增帳戶對話方塊隨即顯示。

1. 在 [!UICONTROL **位置帳戶名稱**] 欄位，指定位置帳戶的名稱。 建立位置時會顯示此名稱。

1. 在 [!UICONTROL **位置帳戶說明**] 欄位，提供帳戶的簡短說明，以協助將其與相同帳戶型別的其他帳戶區分開來。

1. 在 [!UICONTROL **帳戶型別**] 欄位中，選取您要匯出的雲端帳戶型別。 可用的帳戶型別為Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和Adobe Experience Platform Data Landing Zone。

1. 繼續下列對應至的區段 [!UICONTROL **帳戶型別**] 您已選取「 」。

   * [Adobe Experience Platform Data Landing Zone](#adobe-experience-platform)

   * [Amazon S3 Role ARN](#amazon-s3-role-arn)

   * [Google Cloud Platform](#google-cloud-platform)

   * [Azure SAS](#azure-sas)

   * [Azure RBAC](#azure-rbac)

   * [Snowflake](#snowflake)

### Adobe Experience Platform Data Landing Zone

>[!IMPORTANT]
>
>將Customer Journey Analytics報表匯出至Adobe Experience Platform資料登陸區域時，請務必在7天內下載資料，然後從AEP資料登陸區域將其刪除。 7天後，資料會自動從AEP資料登陸區域刪除。

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，會顯示下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **IMS 組織 ID**] | IMS組織ID由Adobe提供。 一般不需要此資訊。 如果您遇到帳戶問題並需要聯絡客戶服務，此功能會很有用。 |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 複製 [!UICONTROL **SAS**] 欄位至您的剪貼簿。 使用此SAS權杖來存取從Analysis Workspace從AEP登陸區域匯出的資料。 瞭解如何存取您的資料」 |

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

### Amazon S3 Role ARN

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，指定下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **角色 ARN**] | 您必須提供角色ARN (Amazon資源名稱)，Adobe才能使用該角色來存取Amazon S3帳戶。 若要這麼做，請建立來源帳戶的IAM許可權原則、將原則附加至使用者，然後建立目的地帳戶的角色。 如需特定資訊，請參閱 [此AWS檔案](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 複製 [!UICONTROL **使用者ARN**] 欄位至您的剪貼簿。 使用者ARN (Amazon資源名稱)由Adobe提供。 您必須將此使用者附加至您在Amazon S3角色ARN中建立的原則。

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

### Google Cloud Platform

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，指定下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **專案 ID**] | 您從Google Cloud帳戶複製的Google Cloud專案ID。 請參閱 [有關取得專案ID的Google Cloud檔案](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 複製 [!UICONTROL **主體**] 欄位到您的剪貼簿，然後確定您授予主體許可權，以便在Google Cloud Platform中將檔案上傳到此貯體。 <!-- add link to Google Cloud docs on how to do this -->

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

### Azure SAS

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，指定下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **金鑰保存庫 URI**] | <p>Azure金鑰儲存庫中SAS權杖的路徑。  若要設定Azure SAS，您需要使用Azure金鑰儲存庫將SAS權杖儲存為秘密。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>建立金鑰儲存庫URI後，在金鑰儲存庫上新增存取原則，以授予您建立的Azure應用程式許可權。 如需詳細資訊，請參閱 [有關如何指派金鑰儲存庫存取原則的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **金鑰保存庫祕密名稱**] | 將密碼新增至Azure金鑰儲存庫時建立的密碼名稱。 在Microsoft Azure中，此資訊位於您建立的金鑰儲存庫中，位於 **金鑰儲存庫** 設定頁面。 如需詳細資訊，請參閱 [有關如何從Azure金鑰儲存庫設定和擷取密碼的Microsoft Azure檔案](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **位置帳戶密碼**] <!-- nothing for us to have them do on the second screen. Just need to permission the container if they haven't --> | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 如果您尚未這麼做，請確定您已授與Azure SAS中儲存貯體的許可權。 <!-- add link to Google Cloud docs on how to do this -->

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

### Azure RBAC

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，指定下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **應用程式 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **租用戶 ID**] | 從您建立的Azure應用程式複製此ID。 在Microsoft Azure中，此資訊位於 **概觀** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **位置帳戶密碼**] | 從您建立的Azure應用程式複製密碼。 在Microsoft Azure中，此資訊位於 **憑證和密碼** 標籤中。 如需詳細資訊，請參閱 [Microsoft Azure檔案，說明如何使用Microsoft identity平台註冊應用程式](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 如果您尚未這麼做，請確定您已授與Azure RBAC中儲存貯體的許可權。 <!-- add link to Google Cloud docs on how to do this -->

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

### Snowflake

1. [開始建立雲端匯出帳戶](#begin-creating-a-cloud-export-account)，如上所述。

1. 在 [!UICONTROL **帳戶屬性**] 的區段 [!UICONTROL **新增帳戶**] 對話方塊中，指定下列資訊：

   | 欄位 | 功能 |
   |---------|----------|
   | [!UICONTROL **帳戶識別碼**] | 可唯一識別組織內，以及Snowflake支援的雲端平台和雲端區域的全球網路中的Snowflake帳戶。 <p>您必須從Snowflake帳戶取得帳戶識別碼，然後在此處貼上資訊。</p><p>若要瞭解從何處取得此資訊，請參閱 [Snowflake檔案中的帳戶識別碼頁面](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **使用者**] | 用於連線的使用者登入名稱。 這是將專門用於Adobe的使用者。 在此處指定名稱，然後以Snowflake建立具有相同名稱的使用者。 <p>如需詳細資訊，請參閱 [Snowflake檔案中的「JDBC驅動程式連線引數參考」頁面](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **角色**] | 在驅動程式起始的Snowflake工作階段中使用的預設存取控制角色。 這是將專門用於Adobe的角色。 在此處指定角色，然後以相同名稱在Snowflake中建立角色，並授予其讀取和寫入存取權。<p>如需詳細資訊，請參閱 [Snowflake檔案中的「JDBC驅動程式連線引數參考」頁面](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **「儲存」**]。

   此 [!UICONTROL **已建立匯出帳戶**] 對話方塊隨即顯示。

   <!-- add screen shot -->

1. 複製 [!UICONTROL **公開金鑰**] 欄位至您的剪貼簿。 公開金鑰由Adobe提供。 在Snowflake中使用公開金鑰來連線至您的Snowflake帳戶。 如需詳細資訊，請參閱 [Snowflake檔案中的金鑰組驗證和金鑰組輪換頁面](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

1. 選取&#x200B;[!UICONTROL **「關閉」**]。

1. 繼續使用 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).



