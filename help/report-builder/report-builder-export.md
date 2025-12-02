---
title: 從Report Builder匯出報表
description: 說明如何將資料從Report Builder匯出至安全目的地
role: User, Admin
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 1d5d87d8-1920-406b-8cce-41b89b7ae70b
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 38%

---

# 透過匯出至雲端目的地來排程活頁簿

您可以將Customer Journey Analytics活頁簿從Report Builder匯出至Google、Azure和Amazon等雲端提供者。

[將報表從Report Builder匯出至雲端的優點包括](#advantages-of-exporting-to-the-cloud)可在協力廠商工具中使用報表，或將報表與外部資料結合。

在將活頁簿從Report Builder匯出至雲端目的地之前，請確定您的資料區塊、環境和許可權符合[匯出需求](#export-requirements)。

## 瞭解匯出程式

將活頁簿從Report Builder匯出至雲端時，請使用下列程式：

1. [設定雲端帳戶](/help/components/exports/cloud-export-accounts.md)

1. [設定帳戶上的位置](/help/components/exports/cloud-export-locations.md)

1. [從Report Builder匯出報告](#export-a-report-from-report-builder)

1. 存取您雲端帳戶中的資料，並[在Adobe中管理匯出](/help/components/exports/manage-exports.md)

![步驟1到4中所述的匯出程式。](assets/report-builder-export-process.png)

## 從Report Builder匯出報告

>[!NOTE]
>
>在依照本節所述匯出資料之前，請先瞭解上節中有關[匯出程式](#understand-the-export-process)的詳細資訊。

若要從Report Builder匯出報表：

1. 如果您尚未設定，請設定匯出帳戶和位置 (如「[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)」)。

1. 在包含您要匯出之資料的Excel試算表中，開啟&#x200B;**[!UICONTROL Adobe Report Builder]**&#x200B;右側面板。

1. 選取&#x200B;[!UICONTROL **排程**]。

<!-- add screenshot -->

1. 在&#x200B;**[!UICONTROL 活頁簿]**&#x200B;索引標籤上，選取加號圖示以建立新排程

   ![Report Builder排程索引標籤](assets/report-builder-schedule-cloud.png)

   或

   若要以您已建立的排程匯出活頁簿，請從排程清單中選取排程，然後選取&#x200B;**[!UICONTROL 依排程傳送]**。

1. 在&#x200B;[!UICONTROL **Adobe Report Builder**]&#x200B;右側面板中，指定下列資訊以繼續建立新排程：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | **[!UICONTROL 檔案]** | 顯示目前選取要匯出的活頁簿檔案。 選取檔案名稱旁的活頁簿圖示![表格選取](/help/assets/icons/TableSelect.svg)，以選擇目前的活頁簿（如果尚未選取）。 |
   | **[!UICONTROL 檔案名稱]** <!--should be File name --> | 可讓您在匯出活頁簿之前變更檔案名稱。<p>活頁簿檔案名稱預設為活頁簿的名稱</p> |
   | **[!UICONTROL 檔案型別]** | 選擇匯出的檔案型別。 您可以選擇Excel、PDF或CSV。 <p>選取&#x200B;**[!UICONTROL CSV]**&#x200B;時，請注意，排程活頁簿會以ZIP附件傳送。 某些企業電子郵件管理單位可能會封鎖含有ZIP附件的電子郵件。 您會看到相應的警告。</p> |
   | **[!UICONTROL 附加時間戳記至檔案名稱]** | 選取此選項可將時間戳記附加至檔案名稱，以識別活頁簿的更新日期。 時間戳記有助於檢視在特定日期傳送的活頁簿版本。 選取後，您可在以下兩者之間選擇： |
   | **[!UICONTROL 檔案名稱預覽]** <!--should be File name preview --> | 顯示匯出後檔案名稱顯示方式的預覽。 |
   | **[!UICONTROL 以密碼保護活頁簿]** | 指定密碼來保護匯出的檔案，以便只有擁有密碼的人可以存取它。 <p>密碼必須至少為8個字元，且至少包含1個數字和1個特殊字元（例如`!`、`@`、`#`和`$`）。</p> |
   | **[!UICONTROL 電子郵件]** | 選取此選項可將檔案傳送到特定電子郵件地址。 如需詳細資訊，請參閱[透過電子郵件共用排程活頁簿](/help/report-builder/schedule-reportbuilder.md)。 |
   | **[!UICONTROL 其他傳遞]** | 選取此選項以將檔案傳送至雲端帳戶，然後使用如下所述的&#x200B;**[!UICONTROL 帳戶]**&#x200B;和&#x200B;**[!UICONTROL 位置]**&#x200B;下拉式功能表來選取帳戶和位置。 |
   | **[!UICONTROL 帳戶]** | 選取您想要發送資料的雲端匯出帳戶。 <p>或者，如果您尚未設定要使用的雲端帳戶，則您可以設定一個新帳戶：<ol><li>選取「[!UICONTROL **新增帳戶**]」，然後註明下列資訊：<ul><li>[!UICONTROL **位置帳戶名稱**]：指定位置帳戶的名稱。建立位置時會出現該名稱。 </li><li>[!UICONTROL **位置帳戶說明**]：提供帳戶的簡短說明，有助區分該帳戶與相同帳戶類型的其他帳戶。</li><li>**[!UICONTROL 讓您的組織中的所有使用者都可以使用帳戶]**：選取此選項可允許組織中的其他使用者使用該帳戶。 共用帳戶時，請考量下列事項：<ul><li>您無法取消共用您共用的帳戶。</li><li>共用帳戶只能由帳戶擁有者編輯。</li><li>任何人都可以建立共用帳戶的位置。</li></ul></li><li>[!UICONTROL **帳戶型別**]：選取您要匯出的雲端帳戶型別。 可用的帳戶型別為Amazon S3角色ARN、Google Cloud Platform、Azure SAS和Azure RBAC。</li></ul><li>若要完成帳戶設定，請繼續進行下面與您選取的&#x200B;[!UICONTROL **帳戶類型**]&#x200B;相對應的連結：<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li></ul></ol> |
   | **[!UICONTROL 位置]** | 選取您想要發送匯出資料的帳戶位置。<p>或者，如果您尚未設定要在所選帳戶上使用的位置，則您可以設定新位置：<ol><li>選取「[!UICONTROL **新增位置**]」，然後註明下列資訊： <ul><li>[!UICONTROL **名稱**]：位置的名稱。</li><li>[!UICONTROL **說明**]：提供位置的簡短說明，有助區分該位置與帳戶的其他位置。</li><li>**[!UICONTROL 讓位置可供組織中的所有使用者使用]**：選取此選項可允許組織中的其他使用者使用該位置。 共用帳戶時，請考量下列事項：<ul><li>您無法取消共用您共用的位置。</li><li>共用位置只能由帳戶擁有者編輯。</li><li>只有在與位置關聯的帳戶也共用時，才能共用位置。</li></ul></li><li>[!UICONTROL **位置帳戶**]：選取您想要建立位置的帳戶。</li></ul><li>若要完成位置設定，請繼續前往下面與您在「[!UICONTROL **位置帳戶**]」欄位中所選帳戶類型相對應的連結：<ul><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li></ul> |
   | **[!UICONTROL 顯示排程選項]** | 選取此選項可檢視排程匯出的其他選項。 如果您只想傳送一次匯出，請取消選取此選項。 取消選取此選項時，會立即起始匯出。 |
   | **[!UICONTROL 開始於]** | 排定匯出應該開始的日期和時間。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | **[!UICONTROL 結束於]** | 排定匯出到期的日期和時間。在您設定的日期和時間之後，排定匯出不會再進行。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | **[!UICONTROL 頻率]** | 您可以將頻率設定為特定日期的每小時、每日、每週、每月或每年。例如，您可以設定排程，在當月第一個星期日晚上傳送活頁簿，讓收件者能在星期一早上第一時間收到收件匣中的電子郵件。 |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **依排程傳送**]&#x200B;以匯出活頁簿。

   資料將以您指定的頻率發送到您指定的雲端帳戶。

1. (選用) 建立匯出後，無論您選擇立即發送或依明訂的排程發送，您都可以在[匯出頁面](/help/components/exports/manage-exports.md)查看和管理發送情形，也可以在[匯出記錄](/help/components/exports/manage-export-logs.md)中查看。</p>

## 管理匯出

從 Analysis Workspace 匯出資料後，您可以編輯、重新匯出、複製、標記或刪除現有匯出，如[管理匯出](/help/components/exports/manage-exports.md)中所述。

## 匯出至雲端的優點

將 Customer Journey Analytics 資料匯出至雲端可讓您：

* 匯出至共用位置，例如Google Cloud Platform、Microsoft Azure和Amazon S3。

* 儲存大量歷史資料。

  這類資料可用來檢測長期趨勢以取得商業智慧，最後可因此做出更好的商業決策。

* 在匯出的 Customer Journey Analytics 資料中包含計算量度。

* 將結構資料輸出為串連值。

* 匯出單次或依排程。

* 匯出Excel、PDF或CSV格式的檔案。

* 匯出包含多個維度的資料區塊。

## 匯出要求 {#export-requirements}

### 基本需求

請確認您的資料區塊、環境和許可權符合下列要求：

* **資料區塊：**&#x200B;所有資料區塊都必須包含欄、列或值的至少一個元件。

* **環境：** 確保 Customer Journey Analytics 所用的 [IP 位址](/help/technotes/ip-addresses.md)和[網域](/help/technotes/domains.md)都可以通過其組織的防火牆。
