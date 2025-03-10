---
description: 瞭解如何將Analysis Workspace專案匯出至雲端位置。
keywords: Analysis Workspace
title: 將 Customer Journey Analytics 報告匯出至雲端
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: 668f17531b4b8a01acffdbb0edef07092859d100
workflow-type: tm+mt
source-wordcount: '2281'
ht-degree: 6%

---

# 將 Customer Journey Analytics 報告匯出至雲端 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="建立類似 Data Warehouse 的完整表格匯出"
>abstract="您在 Analysis Workspace 中看到資料時，便可以馬上進行完整表格匯出。您可以根據需求建立或安排完整表格匯出。<br><br>如果您已經知道在此次匯出中要包含哪些資料，則建立完整表格匯出僅需幾分鐘即可完成。"

<!-- markdownlint-enable MD034 -->

您可以從Customer Journey Analytics匯出Workspace的完整表格，並將匯出內容傳送至指定的雲端目的地。

也可使用其他匯出Customer Journey Analytics報表的方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)中所述。

## 瞭解完整的表格匯出

您可以將完整表格從Analysis Workspace匯出至Google、Azure、Amazon和Adobe等雲端提供者。

[將完整資料表匯出至雲端的優勢](#advantages-of-exporting-to-the-cloud)包括能夠匯出數百萬列、包含計算量度、串連值中的結構資料輸出等等。

匯出完整表格時，請考量下列事項：

* 匯出至雲端之前，請確認您的表格、環境及許可權符合[匯出需求](#export-requirements)。

* 將完整資料表匯出至雲端時，有些[功能](#unsupported-features)和[元件](#unsupported-components)不受支援。

將完整的表格匯出至雲端時，請使用下列程式：

1. [設定雲端帳戶](/help/components/exports/cloud-export-accounts.md)

1. [在帳戶上設定位置](/help/components/exports/cloud-export-locations.md)

1. [從Workspace匯出完整表格](#export-full-tables-from-analysis-workspace)

1. [存取雲端中的資料](#view-exported-data-and-manifest-file)和[在Adobe中管理匯出](/help/components/exports/manage-exports.md)

![步驟1到4中說明的完整資料表匯出程式。](assets/export-full-table-process.png)

## 從Analysis Workspace匯出完整表格

>[!NOTE]
>
>在依照本節所述匯出資料之前，請先在上述[瞭解完整資料表匯出](#understand-full-table-export)一節中進一步瞭解完整資料表匯出。

若要從Analysis Workspace匯出完整表格：

1. 如果您尚未設定匯出帳戶和位置，請參閱[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)中的說明。

1. 在Analysis Workspace中，以滑鼠右鍵按一下包含您要匯出之資料的自由格式表格。

1. 選取&#x200B;[!UICONTROL **匯出完整資料表**]。

   ![反白顯示「匯出完整表格」的「自由表格」下拉式功能表。](assets/export-full-table.png)

1. 在&#x200B;[!UICONTROL **新的完整資料表匯出**]&#x200B;對話方塊中，指定下列資訊：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | 名稱 | 指定匯出的名稱。 此名稱會顯示在匯出清單中。 |
   | 標記 | 您可以將現有標籤套用至匯出，也可以建立新標籤並套用它。 <p>若要將現有標籤套用至匯出，請從下拉式選單中選取任何標籤。 您公司中的任何標籤都可以套用<!-- double-check this -->。</p> <p>若要建立新標籤，請輸入新標籤的名稱，然後按Enter鍵。</p><p>將標籤套用至匯出時，請考量下列事項： <ul><li>您套用的標籤可在匯出表格中篩選或搜尋。</li> <li>匯出完整表格時，套用至專案的標籤不會自動套用，如[管理匯出](/help/components/exports/manage-exports.md)中的「在匯出頁面上設定欄」中所述。 （或者，當[排程完整專案進行匯出](/help/analysis-workspace/export/t-schedule-report.md)時，套用至專案的任何標籤都會自動套用至匯出。） <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | 說明 | 新增說明至匯出。 檢視匯出時，您可以選擇在[匯出頁面](/help/components/exports/manage-exports.md)中以欄的形式檢視說明。 |
   | 資料視圖 | 選取包含要納入匯出之元件的資料檢視。 資料檢視下拉式功能表位於對話方塊的左上角，可由資料檢檢視示![資料檢檢視示](assets/data-view-icon.png)識別。  <p>**注意：**&#x200B;如果您選擇的資料檢視遺漏已包含在資料表格中的元件，系統會提示您清除資料表格，並使用所選資料檢視中所包含的元件重新建立資料表格。 </p> |
   | 回顧視窗 | 選取要包含在每個匯出檔案中的報表時間範圍。 選項包括&#x200B;[!UICONTROL **今天**]、[!UICONTROL **昨天**]、[!UICONTROL **最近7天**]、[!UICONTROL **最近30天**]、[!UICONTROL **本週**]&#x200B;和&#x200B;[!UICONTROL **本月**]。 <p>當&#x200B;[!UICONTROL **匯出頻率**]&#x200B;設定為&#x200B;[!UICONTROL **立即傳送（一次性）**]&#x200B;時，不會顯示此選項。 |
   | 資料表 | 顯示您正在匯出的自由表格。 您可以將元件從左側面板拖曳到表格中，藉此修改資料表格。 表格會在您新增元件至畫布時動態更新。  <p>套用至專案中完整表格的任何區段都會顯示在表格中每個個別欄的頂端。</p> |
   | 清除 | 清除資料表的內容。 這可讓您直接在「新增完整表格」匯出對話方塊中開始建立新表格。 |
   | 匯出頻率 | 設定匯出發生的頻率排程。 <p>您可以選擇&#x200B;[!UICONTROL **立即傳送（一次性）**]，只傳送一次匯出。 選取此選項時，會立即起始匯出。<p>或者，您可以選擇按照定義的排程傳送匯出。 依排程傳送時，選項包括&#x200B;[!UICONTROL **每日**]、[!UICONTROL **每週**]、[!UICONTROL **按一週的日期**]&#x200B;每月、[!UICONTROL **按月份的日期**]、[!UICONTROL **按月份的日期**]&#x200B;每年，以及&#x200B;[!UICONTROL **按特定日期每年**]。 </p><p>選取匯出頻率時，請考量下列事項：</p><ul><li>[!UICONTROL **回顧視窗**]&#x200B;欄位中的選項會依據您在此選取的專案而變更。<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>系統會根據您選擇的選項，顯示其他設定欄位。</li></ul> |
   | 開始日期 | 排程匯出應該開始的日期和時間。 <p>只有在選擇排定的匯出頻率時，才能使用此選項。</p> |
   | 結束日期 | 排定的匯出到期的日期和時間。 排定的匯出在您設定的日期和時間後不再執行。 <p>只有在選擇排定的匯出頻率時，才能使用此選項。</p> |
   | 檔案格式 | 選擇匯出的資料應該是.csv還是.json格式。 |
   | 帳戶 | 選取您要傳送資料的雲端匯出帳戶。 <p>或者，如果您尚未設定要使用的雲端帳戶，您可以設定新帳戶：<ol><li>選取「[!UICONTROL **新增帳戶**]」，然後註明下列資訊：<ul><li>[!UICONTROL **位置帳戶名稱**]：指定位置帳戶的名稱。 建立位置時會顯示此名稱 </li><li>[!UICONTROL **位置帳戶描述**]：提供帳戶的簡短描述，以協助將其與相同帳戶型別的其他帳戶區分開來。</li><li>[!UICONTROL **帳戶型別**]：選取您要匯出的雲端帳戶型別。 可用的帳戶型別為Amazon S3角色ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake和AEP資料登陸區域。</li></ul><li>若要完成設定帳戶，請繼續下列對應至您選取之&#x200B;[!UICONTROL **帳戶型別**]&#x200B;的連結：<ul><li>[AEP資料登陸區域](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3角色ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google雲端平台](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 位置名稱 | 選取您要將匯出資料傳送到的帳戶位置。<p>或者，如果您尚未在選取的帳戶上設定您要使用的位置，您可以設定新的位置：<ol><li>選取&#x200B;[!UICONTROL **新增位置**]，然後指定下列資訊： <ul><li>[!UICONTROL **名稱**]：位置的名稱。</li><li>[!UICONTROL **描述**]：提供位置的簡短描述，以協助將其與帳戶上的其他位置區分開來。</li><li>[!UICONTROL **位置帳戶**]：選取您要建立位置的帳戶。</li></ul><li>若要完成位置設定，請繼續下列對應您在&#x200B;[!UICONTROL **位置帳戶**]&#x200B;欄位中所選帳戶型別的連結：<ul><li>[AEP資料登陸區域](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3角色ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google雲端平台](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. 選取&#x200B;[!UICONTROL **儲存**]&#x200B;以儲存匯出。

   資料會以您指定的頻率傳送至您指定的雲端帳戶。

1. （選擇性）建立匯出後，無論您選擇現在傳送或依定義的排程傳送，都可以在[匯出頁面](/help/components/exports/manage-exports.md)檢視及管理匯出，並在[匯出記錄檔](/help/components/exports/manage-export-logs.md)中檢視。</p>

## 管理匯出

從Analysis Workspace匯出資料後，您可以編輯、重新匯出、複製、標籤或刪除現有的匯出，如[管理匯出](/help/components/exports/manage-exports.md)中所述。

## 檢視匯出的資料和資訊清單檔案

### 匯出的資料

匯出的資料可在您設定的雲端目的地以壓縮檔案形式使用，如[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)和[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)中所述。

視您選擇CSV或JSON作為檔案格式而定，壓縮檔案的檔案名稱如下：

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>匯出資料表時，您可在&#x200B;[!UICONTROL **檔案格式**]&#x200B;欄位中選擇檔案格式，如[從Analysis Workspace匯出完整資料表](#export-full-tables-from-analysis-workspace)中所述。

### 資訊清單檔案

檔案名稱為`cja-export-{reportInstanceId}-{idx}.json.gz`的資訊清單檔案包含在任何至少包含一個檔案的成功匯出傳遞中。 資訊清單檔案可讓您確認所有檔案已成功傳遞。 其包含下列資訊：

* 所有已傳送檔案的清單

* 每個檔案的MD5檢查值

<!-- add in  what the file name, structure, and file format will be -->

## 匯出至雲端的優勢

將Customer Journey Analytics資料匯出至雲端可讓您：

* 匯出至共用位置，例如Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3或Snowflake。

* 儲存大量歷史資料。

  這類資料可用於偵測長期趨勢，以獲得商業智慧，最終做出更好的商業決策。

* 匯出包含數千或數百萬列的完整表格（3百萬、3千萬、1.5億或3億列，視授權型別而定）。 其他匯出方法最多允許50,000列。

* 在匯出的Customer Journey Analytics資料中包含計算量度。

* 將資料輸出結構為串連值。

* 匯出單次或依排程。 （也可搭配[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)使用。）

* 匯出CSV或JSON格式的檔案。 （也可搭配[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)使用。）

* 匯出包含多個維度的表格。

## 匯出需求 {#export-requirements}

### 最低需求

確定您的表格、環境和許可權符合以下要求：

* **資料表：**&#x200B;所有資料表都必須至少包含資料列中的一個維度，以及每個資料欄中的一個量度，才能支援完整的資料表匯出。

* **環境：**&#x200B;請確定Customer Journey Analytics使用的[IP位址](/help/technotes/ip-addresses.md)和[網域](/help/technotes/domains.md)允許通過其組織的防火牆。

* **許可權：**&#x200B;在Adobe Admin Console中，必須為使用者指派具有&#x200B;[!UICONTROL **完整資料表匯出**]&#x200B;許可權的產品設定檔，才能匯出完整的資料表。 如需在Admin Console中指派許可權給產品設定檔的相關資訊，請參閱Admin Console中的[Customer Journey Analytics許可權](/help/technotes/access-control.md)。

  >[!NOTE]
  >
  >  獲指派[產品管理員角色](/help/technotes/access-control.md#product-admin-role)的使用者一律擁有匯出完整表格的存取權；這些使用者不需要獲指派&#x200B;[!UICONTROL **完整表格匯出**]&#x200B;許可權。


### 不支援的功能

下列功能不受支援，並且會自動從完整表格匯出中移除：

* 百分比
* 總計
* 搜尋篩選
* 靜態列
* 日期調整
* 動態維度

  如需詳細資訊，請參閱自由表格中的[動態與靜態維度專案](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。
* 第一個劃分中的維度會進行轉換，並在匯出的表格列中將新增為次要維度；表格中不會包含任何其他劃分
* 大部分的資料集不支援排序；可能會為小型資料集排序資料

### 不支援的元件

下列元件不受支援，Analysis Workspace在執行完整表格匯出時會提示您從表格中將其移除：

* 在量度定義中使用基本或進階函式的計算量度（如需詳細資訊，請參閱[基本函式](/help/components/calc-metrics/cm-functions.md)和[進階函式](/help/components/calc-metrics/cm-adv-functions.md)）
* 管理員已限制匯出的元件（如需詳細資訊，請參閱[標籤和原則](/help/data-views/data-governance.md)中資料檢視表&#x200B;*中資料治理原則的*&#x200B;篩選區段）
* 符合下列所有條件的任何維度：
   * 是從屬於[物件陣列](/help/use-cases/object-arrays.md)一部分的欄位建立的(類似於Adobe Analytics中的多值變數)
   * 已啟用[持續性](/help/data-views/component-settings/persistence.md)
   * 未使用[繫結維度](/help/use-cases/data-views/binding-dimensions-metrics.md)
* 來自參考不同[物件陣列](/help/use-cases/object-arrays.md)之欄位的多個維度。 （允許參考相同物件陣列的多個維度。）
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

完整表格匯出支援使用非預設歸因模型的計算量度（如[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)中的&#x200B;*使用非預設歸因模型*&#x200B;區段所述）。

如果報表中使用非預設歸因模型，則會根據報表是單一維度還是多個維度，忽略或保留報表中使用的配置模型：

* **對於在單一維度中包含量度歸因的報表：** [量度歸因](/help/data-views/component-settings/attribution.md)會覆寫[配置模型](/help/data-views/component-settings/persistence.md)，如同使用量度歸因時通常所做的一樣。

  例如，「首次接觸」量度歸因會覆寫「最近」維度配置。

* **對於同時包含多個維度的量度歸因的報表：** [除了維度[配置模型](/help/data-views/component-settings/persistence.md)之外，還套用了量度歸因](/help/data-views/component-settings/attribution.md)。

  例如，除了「最近」維度配置外，也會套用「首次接觸」量度歸因。 此外，量度歸因將套用至後續配置的維度專案配對，就好像它們是單一維度專案一樣，而不是如通常在自由表格中一樣單獨套用至每個維度專案。

  >[!NOTE]
  >
  >只有在將資料匯出至雲端時，才支援多維度報表，如本文所述。

## 完整表格匯出(在Customer Journey Analytics中)與Data Warehouse(在Adobe Analytics中)的比較

如果您先前使用Data Warehouse匯出Adobe Analytics資料，下表可協助您瞭解在Customer Journey Analytics中匯出完整表格與在Adobe Analytics中使用Data Warehouse匯出資料之間的差異。


| 功能 | Customer Journey Analytics中的完整表格匯出 | Adobe Analytics中的Data Warehouse |
|---------|----------|---------|
| 建立自訂報表 | 有 | 有 |
| 計算量度 | 有 | 無 |
| 客戶細分 | 是 | 有限 |
| 維度 | 限製為5 | 無限制 |
| 量度 | 限製為5 | 無限制 |
| 報告列 | 根據層級，限製為300萬、3000萬、1.5億或3億 | 無限制 |
| 報告數量 | 無限制 | 無限制 |
| 臨機（一次性）傳遞 | 有 | 有 |
| 排程循環傳遞 | 有 | 有 |
| 電子郵件傳遞 | 無 | 是 |
| FTP / SFTP | 否 | 舊版支援 |
| Azure | 有 | 有 |
| Amazon S3 | 有 | 有 |
| Google Cloud Platform | 有 | 有 |
| Snowflake | 有 | 無 |
| 傳遞頻率 | 每日 | 每小時 |
