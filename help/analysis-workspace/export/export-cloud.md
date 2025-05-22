---
description: 了解如何將 Analysis Workspace 專案匯出至雲端位置。
keywords: Analysis Workspace
title: 將 Customer Journey Analytics 報告匯出至雲端
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c503b5bc65565b342e5e6bea8c019d8e1ee1e429
workflow-type: tm+mt
source-wordcount: '2284'
ht-degree: 98%

---

# 將 Customer Journey Analytics 報告匯出至雲端 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="建立類似 Data Warehouse 的完整表格匯出"
>abstract="您在 Analysis Workspace 中看到資料時，便可以馬上進行完整表格匯出。您可以根據需求建立或安排完整表格匯出。<br><br>如果您已經知道在此次匯出中要包含哪些資料，則建立完整表格匯出僅需幾分鐘即可完成。"

<!-- markdownlint-enable MD034 -->

您可以從 Customer Journey Analytics 匯出 Workspace 完整表格，並將匯出資料傳送至指定的雲端目的地。

還有匯出 Customer Journey Analytics 報告的其他方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)所述。

## 了解完整表格匯出

您可以將完整表格從 Analysis Workspace 匯出至雲端服務提供者，例如 Google、Azure、Amazon 和 Adob&#x200B;&#x200B;e。

[將完整表格匯出至雲端的優勢](#advantages-of-exporting-to-the-cloud)包含匯出數百萬行資料的能力、包含串連值中的計算量度、結構資料輸出等等。

匯出完整表格時，請考慮以下事項：

* 在匯出至雲端之前，請確保您的表格、環境和權限符合[匯出要求](#export-requirements)。

* 匯出完整表格至雲端時，有些[功能](#unsupported-features)和[元件](#unsupported-components)不受支援。

將完整表格匯出至雲端時，請使用以下流程：

1. [設定雲端帳戶](/help/components/exports/cloud-export-accounts.md)

1. [設定帳戶上的位置](/help/components/exports/cloud-export-locations.md)

1. [從 Workspace 匯出完整表格](#export-full-tables-from-analysis-workspace)

1. [存取雲端中的資料](#view-exported-data-and-manifest-file)和[管理 Adob&#x200B;&#x200B;e 中的匯出資料](/help/components/exports/manage-exports.md)

![如步驟 1 至 4 所述的完整表格匯出。](assets/export-full-table-process.png)

## 從 Analysis Workspace 匯出完整表格 {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="資訊清單檔案"
>abstract="啟用後，任何成功的匯出傳遞都會包含一份資訊清單檔案。您可以利用資訊清單檔案來確認所有文件均已成功傳遞。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>在按照這部分所述匯出資料之前，請了解更多關於上面「[了解完整表格匯出](#understand-full-table-export)」部分的完整表格匯出資訊。

若要從 Analysis Workspace 匯出完整表格：

1. 如果您尚未設定，請設定匯出帳戶和位置 (如「[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)」)。

1. 在 Analysis Workspace 中，以滑鼠右鍵按一下包含要匯出資料的自由格式表格。

1. 選取「[!UICONTROL **匯出完整表格**]」。

   ![自由格式表下拉選單及醒目顯示的匯出完整表格」。](assets/export-full-table.png)

1. 在「[!UICONTROL **新增完整表格匯出**]」對話框中，指定以下資訊：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | 名稱 | 指定匯出的名稱。此名稱顯示在匯出清單中。 |
   | 標記 | 您可以將現有標記套用至匯出，也可以建立新標記並且套用。 <p>若要套用現有標記至匯出，請從下拉式選單中選取任何標記。您公司的任何標記均可套用<!-- double-check this -->。</p> <p>若要建立新標記，請輸入新標記的名稱，然後按 Enter。</p><p>將標記套用至匯出時，請考慮以下事項： <ul><li>您套用的標記可以在匯出表格中篩選或搜尋。</li> <li>匯出完整表格時，不會自動套用已套用至專案的標記，如在「[管理匯出](/help/components/exports/manage-exports.md)」中的「在匯出頁面上設定欄」所述)。(或者，當[安排整個專案供匯出](/help/analysis-workspace/export/t-schedule-report.md)時，任何套用於專案的標記都會自動套用於匯出)。  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 說明 | 新增說明至匯出。檢視匯出時，您可以選擇以[匯出頁面](/help/components/exports/manage-exports.md)中的資料欄來檢視說明。 |
   | 資料檢視 | 選取資料檢視，其中包含您想要包含在匯出的元件。資料檢視下拉選單位於對話框的左上角，且可以透過資料檢視圖示![資料檢視圖示](assets/data-view-icon.png)來識別。  <p>**注意：** 如果您選擇資料檢視但其中缺少資料表格中已包含的元件，則系統會提示您清除資料表格並使用已選取資料檢視中所含元件來重新建立。 </p> |
   | 回顧視窗 | 選取要包含在每個匯出檔案中的報告時間範圍。選項包含&#x200B;[!UICONTROL **今天**], [!UICONTROL **昨天**], [!UICONTROL **過去 7 天**], [!UICONTROL **過去 30 天**], [!UICONTROL **本週**]&#x200B;和&#x200B;[!UICONTROL **本月**]。 <p>當&#x200B;[!UICONTROL **匯出頻率**]&#x200B;設為「[!UICONTROL **立即傳送 (一次性)**]&#x200B;時，不會顯示此選項。 |
   | 資料表 | 顯示您正在匯出的自由格式表格。您可以將元件從左側面板拖曳到表格中來修改資料表格。當您新增元件至畫布時，表格會動態更新。  <p>任何套用至專案中完整表格的區段，都會出現在表格中每個單獨欄的最上方。</p> |
   | 清除 | 清除資料表格的內容。這會讓您直接在全新完整表格匯出對話框中開始建立新表格。 |
   | 匯出頻率 | 設定匯出應發生頻率的時間表。 <p>您可以選擇「[!UICONTROL **立即發送 (一次性)**]」，可僅發送一次匯出。選擇此選項時，將立即啟動匯出。<p>或者，您可以選擇按照明訂的排程發送匯出。按照排程發送時，選項包括&#x200B;[!UICONTROL **每日**]、[!UICONTROL **每星期**]、[!UICONTROL **每個月按星期的日子**]、[!UICONTROL **每個月按月的日期**]、[!UICONTROL **每一年按月的日期**]&#x200B;和&#x200B;[!UICONTROL **每年特定日期**] </p><p>選取匯出頻率時，請考慮以下因素：</p><ul><li>[!UICONTROL **回顧視窗**]&#x200B;欄位中的選項取決於您在此選取的內容。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>其他設定欄位會根據您選擇的選項來顯示。</li></ul> |
   | 開始日期 | 排定匯出應該開始的日期和時間。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | 結束日期 | 排定匯出到期的日期和時間。在您設定的日期和時間之後，排定匯出不會再進行。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | 檔案格式 | 選擇匯出的資料是否應該是 .csv 或 .json 格式。 |
   | 包括資訊清單檔案 | 啟用後，任何成功的匯出傳遞都會包含一份資訊清單檔案。清單文件可讓您確認所有文件均已成功傳遞，其中包含以下資訊：<ul><li>已傳遞的所有檔案清單</li><li>每個檔案的 MD5 總和檢查碼</li></ul><p>匯出的資料會以壓縮檔案形式儲存在您設定的雲端目標中，如「[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)」和「[設定 Google 匯出位置](/help/components/exports/cloud-export-locations.md)」中所述。</p><p>壓縮檔案的檔案名稱如下，實際名稱取決於您是選擇 CSV 或 JSON 作為檔案格式：</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>您在上述&#x200B;[!UICONTROL **檔案格式**]&#x200B;欄位中選擇檔案格式。</p> |
   | 帳戶 | 選取您想要發送資料的雲端匯出帳戶。 <p>或者，如果您尚未設定要使用的雲端帳戶，則您可以設定一個新帳戶：<ol><li>選取「[!UICONTROL **新增帳戶**]」，然後註明下列資訊：<ul><li>[!UICONTROL **位置帳戶名稱**]：指定位置帳戶的名稱。建立位置時會出現該名稱。 </li><li>[!UICONTROL **位置帳戶說明**]：提供帳戶的簡短說明，有助區分該帳戶與相同帳戶類型的其他帳戶。</li><li>[!UICONTROL **帳戶類型**]：選取您要匯出的目的雲端帳戶類型。可用的帳戶類型包括 Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake 和 AEP Data Landing Zone。</li></ul><li>若要完成帳戶設定，請繼續進行下面與您選取的&#x200B;[!UICONTROL **帳戶類型**]&#x200B;相對應的連結：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 位置 | 選取您想要發送匯出資料的帳戶位置。<p>或者，如果您尚未設定要在所選帳戶上使用的位置，則您可以設定新位置：<ol><li>選取「[!UICONTROL **新增位置**]」，然後註明下列資訊： <ul><li>[!UICONTROL **名稱**]：位置的名稱。</li><li>[!UICONTROL **說明**]：提供位置的簡短說明，有助區分該位置與帳戶的其他位置。</li><li>[!UICONTROL **位置帳戶**]：選取您想要建立位置的帳戶。</li></ul><li>若要完成位置設定，請繼續前往下面與您在「[!UICONTROL **位置帳戶**]」欄位中所選帳戶類型相對應的連結：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」以儲存匯出。

   資料將以您指定的頻率發送到您指定的雲端帳戶。

1. (選用) 建立匯出後，無論您選擇立即發送或依明訂的排程發送，您都可以在[匯出頁面](/help/components/exports/manage-exports.md)查看和管理發送情形，也可以在[匯出記錄](/help/components/exports/manage-export-logs.md)中查看。</p>

## 管理匯出

從 Analysis Workspace 匯出資料後，您可以編輯、重新匯出、複製、標記或刪除現有匯出，如[管理匯出](/help/components/exports/manage-exports.md)中所述。

## 匯出至雲端的優點 {#advantages}

將 Customer Journey Analytics 資料匯出至雲端可讓您：

* 匯出到共用位置，例如 Adob&#x200B;&#x200B;e Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3 或 Snowflake。

* 儲存大量歷史資料。

  這類資料可用來檢測長期趨勢以取得商業智慧，最後可因此做出更好的商業決策。

* 匯出包含數千或數百萬行 (300 萬、3000 萬、1.5 億或 3 億行，實際取決於授權類型) 的完整表格。其他匯出方法最多允許 50,000 筆資料列。

* 在匯出的 Customer Journey Analytics 資料中包含計算量度。

* 將結構資料輸出為串連值。

* 一次性或按排程匯出。(也提供[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)。

* 以 CSV 或 JSON 格式匯出檔案。(也提供[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)。

* 匯出包含多個維度的表格。

## 匯出要求 {#export-requirements}

### 基本需求

確保您的表格、環境和權限符合以下要求：

* **表格：** 為了得到完整表格匯出的支援，所有表格的資料列中都必須至少包含一個維度，每一欄都必須包含一個量度。

* **環境：** 確保 Customer Journey Analytics 所用的 [IP 位址](/help/technotes/ip-addresses.md)和[網域](/help/technotes/domains.md)都可以通過其組織的防火牆。

* **權限：** 在 Adob&#x200B;&#x200B;e Admin Console 中，必須為使用者指派一個具備被指派 [!UICONTROL **完整表格匯出**]&#x200B;權限的設定檔，以便使用者可以匯出完整表格。有關在 Admin Console 中為產品設定檔指派權限的資訊，請參閱「[Admin Console 中的 Customer Journey Analytics 權限](/help/technotes/access-control.md)。

  >[!NOTE]
  >
  >  被指派[產品管理員角色](/help/technotes/access-control.md#product-admin-role)的使用者一定有匯出完整表格的存取權；這些使用者不需要被指派&#x200B;[!UICONTROL **完整表格匯出**]&#x200B;權限。


### 不支援的功能

以下功能不受支援且會自動從完整表格匯出中刪除：

* 百分比
* 總計
* 搜尋篩選
* 靜態列
* 日期對齊
* 來自摘要資料集的量度
* 動態維度

  有關詳細資訊，請參閱「[自由格式表中的動態與靜態維度項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。
* 第一個劃分中的維度會被轉換並新增為次要維度至匯出表格的資料列中；表格中未包括任何其他劃分
* 大多數資料集不支援排序；若是小型資料集，資料可能可進行排序

### 不支援的元件

以下元件不受支援，且在執行完整表格匯出時， Analysis Workspace 會提示您從表格中刪除這些元件：

* 使用量度定義中的基本或進階函數的計算量度 (請參閱「[基本函數](/help/components/calc-metrics/cm-functions.md)」和「[進階函數](/help/components/calc-metrics/cm-adv-functions.md)」，了解更多資訊)
* 管理員已限制匯出的元件（如需詳細資訊，請參閱[標籤和原則](/help/data-views/data-governance.md)中資料檢視表&#x200B;*中資料治理原則的*&#x200B;區段）
* 符合以下所有條件的任何維度：
   * 是從屬於[物件列陣](/help/use-cases/object-arrays.md) (類似於 Adob&#x200B;&#x200B;e Analytics 中的多值變數) 建立
   * [已啟用持續性](/help/data-views/component-settings/persistence.md)
   * 不使用[繫結維度](/help/use-cases/data-views/binding-dimensions-metrics.md)
* 來自引用不同[物件陣列](/help/use-cases/object-arrays.md)欄位的多個維度 。(允許引用相同物件陣列的多個維度)。
* 每個報告包含超過 10 個維度和 10 個量度 (最多支援 10 個維度和 10 個量度)
* 在表格欄位中：
   * 日期範圍
   * 維度
* 在表格資料列中：
   * 計算量度
   * 量度
   * 日期範圍
   * 區段

### 歸因行為

完整表格匯出支援使用非預設歸因模型的計算量度 (如「[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)」中的「*使用非預設歸因模型*」部分)。

如果報告中使用非預設歸因模型，則報告中使用的配置模型會被忽略或保留，具體取決於報告是具有單一維度還是多個維度：

* **在單一維度中包含量度歸因的報告：** [量度歸因](/help/data-views/component-settings/attribution.md)覆蓋[配置模式](/help/data-views/component-settings/persistence.md)，就像平常使用量度歸因會進行的一樣。

  例如，「首次接觸」指標歸因會覆蓋「最近」的維度配置。

* **同時在多個維度中包含量度歸因的報告：除了應用於[維度配置模式](/help/data-views/component-settings/persistence.md)外，還會應用於** [量度歸因](/help/data-views/component-settings/attribution.md)。

  例如，除了「最近」維度配置之外，還會應用「首次接觸」量度歸因。此外，量度歸因將應用於後配置的維度項對，就好像這些是單一維度項目一樣，而不是像通常在自由格式表中那樣個別應用於每個維度項目。

  >[!NOTE]
  >
  >僅有將資料匯出至雲端時才會支援多維報告，如本文所述。

## 完整表格匯出 (在 Customer Journey Analytics 中) 與 Data Warehouse (在 Adob&#x200B;&#x200B;e Analytics 中) 的比較 {#comparison}

如果您先前使用 Data Warehouse 來匯出 Adob&#x200B;&#x200B;e Analytics 資料，下表可以幫助您了解在 Customer Journey Analytics 中匯出完整表格與在 Adob&#x200B;&#x200B;e Analytics 中使用 Data Warehouse 匯出資料之間的差異。


| 功能 | Customer Journey Analytics 中的完整表格匯出 | Adobe Analytics 中的 Data Warehouse |
|---------|----------|---------|
| 建立自訂報告 | 有 | 有 |
| 計算量度 | 有 | 無 |
| 區段 | 是 | 有限 |
| 維度 | 限制 10 個 | 無限制 |
| 量度 | 限制 10 個 | 無限制 |
| 報告列 | 限制為 300 萬列、3,000 萬列、1.5 億列或 3 億列，視等級而定 | 無限制 |
| 報告數量 | 無限制 | 無限制 |
| 臨時 (一次性) 傳遞 | 有 | 有 |
| 安排定期傳遞 | 有 | 有 |
| 電子郵件傳遞 | 無 | 是 |
| FTP / SFTP | 否 | 舊版支援 |
| Azure | 有 | 有 |
| Amazon S3 | 有 | 有 |
| Google Cloud Platform | 有 | 有 |
| Snowflake | 有 | 無 |
| 傳遞頻率 | 每日 | 每小時 |
