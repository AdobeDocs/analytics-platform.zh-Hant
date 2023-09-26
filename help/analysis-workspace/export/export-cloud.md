---
description: 將Analysis Workspace專案匯出至雲端位置。
keywords: Analysis Workspace
title: 將Customer Journey Analytics報表匯出至雲端
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: ba59267dc39f1e564e555e0d5183613f9171403f
workflow-type: tm+mt
source-wordcount: '1716'
ht-degree: 4%

---

# 將Customer Journey Analytics報表匯出至雲端

您可以從Customer Journey Analytics匯出工作區完整的表格，並將匯出內容傳送到指定的雲端目的地。

您也可以使用其他匯出Customer Journey Analytics報表的方法，如中所述 [匯出概觀](/help/analysis-workspace/export/export-project-overview.md).

## 從Analysis Workspace匯出完整表格

>[!NOTE]
>
>在依本節所述匯出資料之前，請確定 [匯出需求](#export-requirements) 符合。

若要從Analysis Workspace匯出完整表格：

1. 如果您尚未設定匯出帳戶和位置，如所述 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md).

1. 在Analysis Workspace中，以滑鼠右鍵按一下包含您要匯出之資料的自由格式表格。

1. 選取 [!UICONTROL **匯出完整表格**].

   ![匯出完整表格](assets/export-full-table.png)

1. 在 [!UICONTROL **新的完整表格匯出**] 對話方塊中，指定下列資訊：

   | 欄位名稱 | 功能 |
   |---------|----------|
   | 名稱 | 指定匯出的名稱。 此名稱會顯示在匯出清單中。 |
   | 標記 | 您可以將現有標籤套用至匯出，也可以建立新標籤並套用它。 <p>若要將現有標籤套用至匯出，請從下拉式選單中選取任何標籤。 您公司中的任何標籤皆可套用<!-- double-check this -->.</p> <p>若要建立新標籤，請輸入新標籤的名稱，然後按Enter鍵。</p><p>將標籤套用至匯出時，請考量下列事項： <ul><li>您套用的標籤可在匯出表格中篩選或搜尋。</li> <li>匯出完整表格時，套用至專案的標籤不會自動套用，如以下的「在匯出頁面上設定欄」中所述： [管理匯出](/help/components/exports/manage-exports.md). (或者，當 [排程完整專案以供匯出](/help/analysis-workspace/export/t-schedule-report.md)，套用至專案的任何標籤都會自動套用至匯出。)  <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 說明 | 新增說明至匯出。 您可以選擇將說明檢視為 [匯出頁面](/help/components/exports/manage-exports.md) 檢視匯出時。 |
   | 資料檢視 | 選取包含要納入匯出之元件的資料檢視。 資料檢視下拉式功能表位於對話方塊的左上角，可由資料檢檢視示識別![資料檢檢視示](assets/data-view-icon.png).  <p>**注意：** 如果您選擇的資料檢視缺少已包含在資料表格中的元件，則會提示您清除資料表格並使用包含在所選資料檢視中的元件重新建立資料表格。 </p> |
   | 回顧視窗 | 選取要包含在每個匯出檔案中的報表時間範圍。 選項包括 [!UICONTROL **今天**]， [!UICONTROL **昨天**]， [!UICONTROL **過去7天**]， [!UICONTROL **過去30天**]， [!UICONTROL **本週**]、和 [!UICONTROL **本月**]. |
   | 清除 | 清除資料表的內容。 這可讓您直接在「新增完整表格」匯出對話方塊中開始建立新表格。 |
   | 匯出頻率 | 設定匯出發生的頻率排程。 <p>您可以選擇 [!UICONTROL **立即傳送（一次）**] 僅傳送一次匯出。 選取此選項時，會立即起始匯出。<p>或者，您可以選擇按照定義的排程傳送匯出。 依排程傳送時，選項包括 [!UICONTROL **每日**]， [!UICONTROL **每週**]， [!UICONTROL **按一週的第幾天，每月一次**]， [!UICONTROL **每月按日期**]， [!UICONTROL **每年按日期**]、和 [!UICONTROL **每年依特定日期**]. </p><p>選取匯出頻率時，請考量下列事項：</p><ul><li>中的選項 [!UICONTROL **回顧期間**] 欄位會依您在此選取的專案而變更。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>系統會根據您選擇的選項，顯示其他設定欄位。</li></ul> |
   | 開始於 | 排程匯出應該開始的日期和時間。 <p>只有在選擇排定的匯出頻率時，才能使用此選項。</p> |
   | 結束日期 | 排定的匯出到期的日期和時間。 排定的匯出在您設定的日期和時間後不再執行。 <p>只有在選擇排定的匯出頻率時，才能使用此選項。</p> |
   | 檔案格式 | 選擇匯出的資料應該是.csv還是.json格式。 |
   | 帳戶 | 選取您要傳送資料的雲端匯出帳戶。 <p>如需詳細資訊，請參閱 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md).</p> |
   | 位置名稱 | 選取您要將匯出資料傳送到的帳戶位置。 <p>如需詳細資訊，請參閱 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).</p><p>您可以選取 [!UICONTROL **新增位置**] 按鈕來建立現有匯出帳戶的新位置。 |

   {style="table-layout:auto"}

1. 選取 [!UICONTROL **儲存**] 以儲存匯出。

   資料會以您指定的頻率傳送至您指定的雲端帳戶。

1. （選擇性）建立匯出後，無論您選擇現在傳送或依定義的排程傳送，都可以在以下位置檢視及管理匯出： [匯出頁面](/help/components/exports/manage-exports.md) 並在以下位置檢視： [匯出記錄檔](/help/components/exports/manage-export-logs.md).</p>

## 匯出至雲端的優勢

將Customer Journey Analytics資料匯出至雲端可讓您：

* 匯出至共用位置，例如Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3或Snowflake。

* 儲存大量歷史資料。

  這類資料可用於偵測長期趨勢，以獲得商業智慧，最終做出更好的商業決策。

* 匯出包含數千或數百萬列的完整表格（3百萬、3千萬或1.5億列，視授權型別而定）。 其他匯出方法最多允許50,000列。

* 在匯出的Customer Journey Analytics資料中包含計算量度。

* 將資料輸出結構為串連值。

* 匯出臨時或依排程。 (也可搭配 [其他匯出選項](/help/analysis-workspace/export/export-project-overview.md).)

* 匯出CSV或JSON格式的檔案。 (也可搭配 [其他匯出選項](/help/analysis-workspace/export/export-project-overview.md).)

* 匯出包含多個維度的表格。

## 匯出需求 {#export-requirements}

### 最低需求

確定您的表格、環境和許可權符合以下要求：

* **表格：** 所有表格在列中必須至少包含一個維度，在每一欄中至少包含一個量度，才能支援完整的表格匯出。

* **環境：** 管理員應確保IP位址列在 [Customer Journey Analytics使用的IP位址](/help/admin/ip-addresses.md) 包含在防火牆允許清單中。

* **許可權：** 在Adobe Admin Console中，必須為使用者指派產品設定檔，該設定檔必須 [!UICONTROL **完整表格匯出**] 為其指派許可權以匯出完整的表格。 如需在Admin Console中指派許可權給產品設定檔的相關資訊，請參閱 [Admin Console中的Customer Journey Analytics許可權](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=en#customer-journey-analytics-permissions-in-admin-console) 在 [Customer Journey Analytics存取控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html).

### 不支援的功能

下列功能不受支援，並且會自動從完整表格匯出中移除：

* 百分比
* 總計
* 搜尋篩選
* 靜態列
* 日期調整
* 動態維度

  如需詳細資訊，請參閱 [自由表格中的動態與靜態維度專案](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* 第一個劃分中的Dimension會轉換，並新增為匯出表格列中的次要維度；表格中不包含任何其他劃分
* 大部分的資料集不支援排序；可能會為小型資料集排序資料

### 不支援的元件

下列元件不受支援，Analysis Workspace在執行完整表格匯出時會提示您從表格中將其移除：

* 在量度定義中使用基本或進階函式的計算量度(請參閱 [基本函式](/help/components/calc-metrics/cm-functions.md) 和 [進階函式](/help/components/calc-metrics/cm-adv-functions.md) 以取得詳細資訊)
* 管理員限制無法匯出的元件(請參閱 *篩選資料檢視中的資料控管原則* 中的區段 [標籤和原則](/help/data-views/data-governance.md) 以取得詳細資訊)
* 每個報表超過5個維度和5個量度（最多支援5個維度和5個量度）
* 在表格欄中：
   * 日期範圍
   * 維度
* 在表格列中：
   * 計算量度
   * 量度
   * 日期範圍
   * 篩選器

### 歸因行為

完整表格匯出支援使用非預設歸因模型的計算量度(如 *使用非預設歸因模型* 中的區段 [欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md))。

如果報表中使用非預設歸因模型，則會根據報表是單一維度還是多個維度，忽略或保留報表中使用的配置模型：

* **對於在單一維度中包含量度歸因的報表：** [量度歸因](/help/data-views/component-settings/attribution.md) 覆寫 [配置模式](/help/data-views/component-settings/persistence.md) 使用量度歸因時，通常就會這麼做。

  例如，「首次接觸」量度歸因會覆寫「最近」維度配置。

* **對於同時包含多個維度的量度歸因的報表：** [量度歸因](/help/data-views/component-settings/attribution.md) 除了維度外也會套用 [配置模式](/help/data-views/component-settings/persistence.md).

  例如，除了「最近」維度配置外，也會套用「首次接觸」量度歸因。 此外，量度歸因將套用至後續配置的維度專案配對，就好像它們是單一維度專案一樣，而不是如通常在自由表格中一樣單獨套用至每個維度專案。

  >[!NOTE]
  >
  >只有在將資料匯出至雲端時，才支援多維度報表，如本文所述。

## 管理匯出

從Analysis Workspace匯出資料後，您可以編輯、重新匯出、複製、標籤或刪除現有的匯出專案，如所述 [管理匯出](/help/components/exports/manage-exports.md).

## 檢視匯出的資料和資訊清單檔案

### 匯出的資料

匯出的資料可在您設定的雲端目的地以壓縮檔案形式使用，如所述 [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md) 和 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md).

視您選擇CSV或JSON作為檔案格式而定，壓縮檔案的檔案名稱如下：

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>您可在以下位置選擇檔案格式： [!UICONTROL **檔案格式**] 欄位匯出表格時，如中所述 [從Analysis Workspace匯出完整表格](#export-full-tables-from-analysis-workspace).

### 資訊清單檔案

檔案名稱為的資訊清單檔案 `cja-export-{reportInstanceId}-{idx}.json.gz` 任何至少包含一個檔案的成功匯出傳遞都會包含。 資訊清單檔案可讓您確認所有檔案已成功傳遞。 其包含下列資訊：

* 所有已傳送檔案的清單

* 每個檔案的大小

* 每個檔案的時間戳記

<!-- add in  what the file name, structure, and file format will be -->

## 完整表格匯出(在Customer Journey Analytics中)與Data Warehouse(在Adobe Analytics中)的比較

如果您先前使用Data Warehouse匯出Adobe Analytics資料，下表可協助您瞭解在Customer Journey Analytics中匯出完整表格與在Adobe Analytics中使用Data Warehouse匯出資料之間的差異。


| 功能 | 以Customer Journey Analytics匯出完整表格 | Adobe Analytics中的Data Warehouse |
|---------|----------|---------|
| 建立自訂報表 | 有 | 有 |
| 計算量度 | 有 | 無 |
| 區段 | 是 | 有限 |
| 維度 | 限製為5 | 無限制 |
| 量度 | 限製為5 | 無限制 |
| 報告列 | 根據層級，限製為300萬、3000萬、1.5億或3億 | 無限制 |
| 報告數量 | 無限制 | 無限制 |
| 隨機傳遞 | 有 | 有 |
| 排程循環傳遞 | 有 | 有 |
| 電子郵件傳遞 | 無 | 是 |
| FTP / SFTP | 否 | 舊版支援 |
| Azure | 有 | 有 |
| Amazon S3 | 有 | 有 |
| Google Cloud Platform | 有 | 有 |
| Snowflake | 有 | 否 |
| 傳遞頻率 | 每日 | 每小時 |
