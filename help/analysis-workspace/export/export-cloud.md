---
description: 瞭解如何將完整的表格匯出至雲端位置。
keywords: Analysis Workspace
title: 將完整的表格匯出至雲端
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c4a7884ae05d9290b2974483474ba8326492d014
workflow-type: tm+mt
source-wordcount: '3234'
ht-degree: 56%

---

# 將完整表格匯出至雲端 {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="建立類似 Data Warehouse 的完整表格匯出"
>abstract="您在 Analysis Workspace 中看到資料時，便可以馬上進行完整表格匯出。您可以視需要建立或排程完整表格匯出。<br><br>如果您已經知道匯出中要包含哪些資料，您只需幾分鐘即可建立完整的表格匯出。"

<!-- markdownlint-enable MD034 -->

在Customer Journey Analytics中，您可以將完整的表格從Analysis Workspace匯出至指定的雲端目的地。

還有匯出 Customer Journey Analytics 報告的其他方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)所述。

## 了解完整表格匯出

您可以將完整表格從 Analysis Workspace 匯出至雲端服務提供者，例如 Google、Azure、Amazon 和 Adob&#x200B;&#x200B;e。

[完整資料表匯出的優點](#advantages-of-full-table-export)包括能夠匯出數百萬列、包含計算量度、串連值中的結構資料輸出等等。

匯出完整表格時，請考慮以下事項：

* 匯出至雲端之前，請確認您的表格、環境及許可權符合[最低匯出需求](#minimum-requirements)。

* 匯出完整表格至雲端時，有些[功能](#unsupported-features)和[元件](#unsupported-components)不受支援。

將完整表格匯出至雲端時，請使用以下流程：

1. [設定雲端帳戶](/help/components/exports/cloud-export-accounts.md)

1. [設定帳戶上的位置](/help/components/exports/cloud-export-locations.md)

1. [從 Workspace 匯出完整表格](#export-full-tables)

1. 存取雲端帳戶中的資料，以及[在Adobe中管理匯出](/help/components/exports/manage-exports.md)

![如步驟 1 至 4 所述的完整表格匯出。](assets/export-full-table-process.png)

## 匯出完整表格  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-details"
>title="詳細資料"
>abstract="指定匯出的名稱。您也可以新增說明和任何標記。此資訊有助於在匯出表格和電子郵件通知中識別匯出內容。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-data-structure"
>title="資料結構"
>abstract="此為您正在匯出的自由格式表格。您可以將元件從左側面板拖曳到表格中，以此修改資料結構。您可以將元件拖曳至篩選器區域中，以此套用篩選器。當您新增元件至畫布時，表格會動態更新。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="包括資訊清單檔案"
>abstract="選取後，任何成功的匯出傳遞都會包含一份資訊清單檔案。 您可以利用資訊清單檔案來確認所有文件均已成功傳遞。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-schedule"
>title="排程"
>abstract="選取匯出頻率。選擇「立即傳送」(一次性)，立即啟動匯出。 排程匯出會在您指定的日期和時間啟動。"

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-destination"
>title="目標"
>abstract="選取資料傳送目的地的雲端帳戶和位置。您可以選擇現有的帳戶和位置，或選取「新增」建立內容。指定使用者和群組接收匯出失敗或即將到期的資訊。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-file-format"
>title="檔案格式"
>abstract="選擇 Parquet 檔案格式時，元件名稱中包含的一些特殊字元會以底線 (_) 取代。如需所取代字元的完整清單，請參閱下列連結。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-export-notifications"
>title="通知"
>abstract="新增您想要在此匯出失敗或即將到期時收到通知的使用者和群組。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>在按照這部分所述匯出資料之前，請了解更多關於上面「[了解完整表格匯出](#understand-full-table-export)」部分的完整表格匯出資訊。

若要從 Analysis Workspace 匯出完整表格：

1. 如果您尚未設定匯出帳戶和位置，請參閱[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)和[設定匯出位置](/help/components/exports/cloud-export-locations.md)中的說明。

1. 在Analysis Workspace中，以滑鼠右鍵按一下自由表格標題以顯示內容功能表，然後選取「[!UICONTROL **匯出完整表格**]」。

   ![反白顯示「匯出完整表格」的自由表格內容功能表。](assets/export-full-table.png)

1. 在「[!UICONTROL **新增完整表格匯出**]」對話框中，指定以下資訊：

   | 欄位名稱 | 函數 |
   |---------|----------|
   | 名稱 | 指定匯出的名稱。此名稱顯示在匯出清單中。 |
   | 標記 | 您可以將現有標記套用至匯出，也可以建立新標記並且套用。 <p>若要套用現有標記至匯出，請從下拉式選單中選取任何標記。您公司中的任何標籤皆可套用。</p> <p>若要建立新標記，請輸入新標記的名稱，然後按 Enter。</p><p>將標記套用至匯出時，請考慮以下事項： <ul><li>您套用的標記可以在匯出表格中篩選或搜尋。</li> <li>匯出完整表格時，不會自動套用已套用至專案的標記，如在「[管理匯出](/help/components/exports/manage-exports.md)」中的「在匯出頁面上設定欄」所述)。（或者，當[排程匯出完整專案](/help/analysis-workspace/export/t-schedule-report.md)時，套用至專案的任何標籤都會自動套用至匯出。） </li></ul> |
   | 說明 | 新增說明至匯出。檢視匯出時，您可以選擇以[匯出頁面](/help/components/exports/manage-exports.md)中的資料欄來檢視說明。 |
   | 資料視圖 | 選取資料檢視，其中包含您想要包含在匯出的元件。![資料](/help/assets/icons/Data.svg)資料檢視下拉式功能表位於對話方塊的左上角。  <p>**注意：**&#x200B;如果您選取的資料檢視遺漏了資料表格中已包含的元件，系統會提示您清除並使用所選資料檢視中所包含的元件重新建立面板。 </p> |
   | 資料結構 | 顯示您正在匯出的自由格式表格。您可以將元件從左側面板拖曳到表格中，以此修改資料結構。您可以將元件拖曳至篩選器區域中，以此套用篩選器。表格會在您新增元件至畫布時動態更新。 您最多可以包含10欄。<p>套用至專案中完整表格的任何區段都會顯示在表格上方。 您可以將區段或區段群組套用至匯出。</p> |
   | 報告時段 | 選取要包含在每個匯出檔案中的報告時間範圍。選項包含&#x200B;[!UICONTROL **今天**], **[!UICONTROL 昨天]**, **[!UICONTROL 過去 7 天]**, **[!UICONTROL 過去 30 天]**, **[!UICONTROL 本週]**&#x200B;和&#x200B;**[!UICONTROL 本月]**。 <p>當&#x200B;**[!UICONTROL 匯出頻率]**&#x200B;設為「**[!UICONTROL 立即傳送 (一次性)]**&#x200B;時，不會顯示此選項。</p> |
   | 全部清除 | 清除資料表格的內容。這會讓您直接在全新完整表格匯出對話框中開始建立新表格。 |
   | 檔案格式 | 選擇匯出的資料應該是.csv、.json或.parquet格式。 <p>選擇Parquet檔案格式時，元件名稱中包含的下列任何字元都會取代為底線(_)： <ul><li>&#39; &#39; - ASCII空間</li><li>&#39;，&#39; - ASCII逗號</li><li>&#39;；&#39; - ASCII冒號</li><li>&#39;{&#39;或&#39;}&#39; - ASCII開啟/關閉大括弧</li><li>&#39;（&#39;或&#39;）&#39; - ASCII左括弧/右括弧</li><li>&#39;\n&#39; - ASCII新行</li><li>&#39;\t&#39; - ASCII索引標籤</li><li>&#39;=&#39; - ASCII等於</li></ul></p> |
   | 包括資訊清單檔案 | 啟用時，任何成功的匯出傳遞都會包含資訊清單檔案。 <p>清單文件可讓您確認所有文件均已成功傳遞，其中包含以下資訊：</p> <ul><li>已傳遞的所有檔案清單</li><li>每個檔案的 MD5 總和檢查碼</li></ul><p>匯出的資料會以壓縮檔案形式儲存在您設定的雲端目標中，如「[設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)」和「[設定 Google 匯出位置](/help/components/exports/cloud-export-locations.md)」中所述。</p><p>壓縮檔案的檔案名稱如下，視您選擇&#x200B;**[!UICONTROL csv]**、**[!UICONTROL json]**&#x200B;或&#x200B;**[!UICONTROL parquet]**&#x200B;做為檔案格式而定：</p><ul> <li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li><li>`cja-export-<instanceId>-<idx>.snappy.parquet`<p>Parquet檔案中的每一欄都經過壓縮。</p></li></ul><p>在上述&#x200B;**[!UICONTROL 檔案格式]**&#x200B;欄位中選擇檔案格式。</p> |
   | 頻率 | 設定匯出應發生頻率的時間表。 <p>您可以選擇「[!UICONTROL **立即發送 (一次性)**]」，可僅發送一次匯出。選擇此選項時，將立即啟動匯出。</p><p>或者，您可以選擇按照明訂的排程發送匯出。按照排程發送時，選項包括&#x200B;**[!UICONTROL 每日]**、**[!UICONTROL 每星期]**、**[!UICONTROL 每個月按星期的日子]**、**[!UICONTROL 每個月按月的日期]**、**[!UICONTROL 每一年按月的日期]**&#x200B;和&#x200B;**[!UICONTROL 每年特定日期]** </p> <p>選取匯出頻率時，請考慮以下因素：</p><ul><li>**[!UICONTROL 回顧視窗]**&#x200B;欄位中的選項會隨著您在此選取的專案而變更。</li><li>根據您選擇的選項，會顯示其他設定欄位。</li></ul> |
   | 開始日期 | 排定匯出應該開始的日期和時間。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | 結束日期 | 排定匯出到期的日期和時間。在您設定的日期和時間之後，排定匯出不會再進行。 <p>此選項只有在選擇排定匯出頻率時才會出現。</p> |
   | 檢視所有使用者的目的地 | 系統管理員可以選取此選項來檢視所有帳戶和位置，無論其建立者為何。 |
   | 帳戶 | 選取您想要發送資料的雲端匯出帳戶。 <p>或者，如果您尚未設定要使用的雲端帳戶，則您可以設定一個新帳戶：<ol><li>在&#x200B;**[!UICONTROL 帳戶]**&#x200B;下拉式功能表中，選取&#x200B;**[!UICONTROL 新增帳戶]**，然後指定下列資訊：<ul><li>**[!UICONTROL 位置帳戶名稱]**：指定位置帳戶的名稱。建立位置時會出現此名稱 </li><li>**[!UICONTROL 位置帳戶說明]**：提供帳戶的簡短說明，有助區分該帳戶與相同帳戶類型的其他帳戶。</li><li>**讓您的組織中的所有使用者都可以使用帳戶**：如果您要允許組織中的其他使用者使用該帳戶，請選取此選項。</li><li>**[!UICONTROL 帳戶類型]**：選取您要匯出的目的雲端帳戶類型。可用的帳戶類型包括 Amazon S3 Role ARN、Google Cloud Platform、Azure SAS、Azure RBAC、Snowflake 和 AEP Data Landing Zone。</li></ul><li>若要完成帳戶設定，請繼續進行下面與您選取的&#x200B;**[!UICONTROL 帳戶類型]**&#x200B;相對應的連結：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | 位置 | 選取您想要發送匯出資料的帳戶位置。<p>或者，如果您尚未設定要使用的雲端帳戶，則您可以設定一個新帳戶：<ol><li>在&#x200B;**[!UICONTROL 位置]**&#x200B;下拉式功能表中，選取&#x200B;**[!UICONTROL 新增位置]**，然後指定下列資訊：<ul><li>**[!UICONTROL 名稱]**：位置的名稱。</li><li>**[!UICONTROL 說明]**：提供位置的簡短說明，有助區分該位置與帳戶的其他位置。</li><li>**讓位置可供您組織中的所有使用者使用**：如果您要允許組織中的其他使用者使用該位置，請選取此選項。</li><li>**[!UICONTROL 位置帳戶]**：選取您想要建立位置的帳戶。</li></ul><li>若要完成位置設定，請繼續前往下面與您在「**[!UICONTROL 位置帳戶]**」欄位中所選帳戶類型相對應的連結：<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone)。</li><li>[Amazon S3 Role ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud Platform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |
   | 通知 | 新增您想要在此匯出失敗或即將到期時收到通知的使用者和群組。 開始輸入使用者的名稱或電子郵件地址，或開始輸入群組的名稱，然後在其出現在下拉式清單中時選取它。 |

   {style="table-layout:auto"}

1. 選取「[!UICONTROL **儲存**]」以儲存匯出。

   資料將以您指定的頻率發送到您指定的雲端帳戶。

1. (選用) 建立匯出後，無論您選擇立即發送或依明訂的排程發送，您都可以在[匯出頁面](/help/components/exports/manage-exports.md)查看和管理發送情形，也可以在[匯出記錄](/help/components/exports/manage-export-logs.md)中查看。

## 管理匯出

從 Analysis Workspace 匯出資料後，您可以編輯、重新匯出、複製、標記或刪除現有匯出，如[管理匯出](/help/components/exports/manage-exports.md)中所述。

## 完整表格匯出的優點 {#advantages}

將 Customer Journey Analytics 資料匯出至雲端可讓您：

* 匯出到共用位置，例如 Adob&#x200B;&#x200B;e Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3 或 Snowflake。

* 儲存大量歷史資料。

  這類資料可用來偵測長期趨勢，以獲得商業情報，最終做出更好的商業決策。

* 匯出包含數千或數百萬行 (300 萬、3000 萬、1.5 億或 3 億行，實際取決於授權類型) 的完整表格。其他匯出方法最多允許 50,000 筆資料列。

* 在匯出的 Customer Journey Analytics 資料中包含計算量度。

* 將結構資料輸出為串連值。

* 一次性或按排程匯出。(也提供[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)。

* 匯出檔案為CSV、JSON或Parquet格式。 (也提供[其他匯出選項](/help/analysis-workspace/export/export-project-overview.md)。

* 匯出包含多個維度的表格。

## 基本需求

確保您的表格、環境和權限符合以下要求：

* **資料表：**&#x200B;所有資料表都必須至少包含資料列中的一個維度，以及完整資料表匯出支援的每個資料行中的一個量度。

* **環境：** 確保 Customer Journey Analytics 所用的 [IP 位址](/help/technotes/ip-addresses.md)和[網域](/help/technotes/domains.md)都可以通過其組織的防火牆。

* **許可權：**&#x200B;在Adobe Admin Console中，必須為使用者指派產品設定檔，該產品設定檔必須具有&#x200B;**[!UICONTROL 完整資料表匯出]**&#x200B;許可權，才能匯出完整資料表。 有關在 Admin Console 中為產品設定檔指派權限的資訊，請參閱「[Admin Console 中的 Customer Journey Analytics 權限](/help/technotes/access-control.md)。

  >[!NOTE]
  >
  >  被指派[產品管理員角色](/help/technotes/access-control.md#product-admin-role)的使用者一定有匯出完整表格的存取權；這些使用者不需要被指派&#x200B;**[!UICONTROL 完整表格匯出]**&#x200B;權限。


## 不支援的功能

以下功能不受支援且會自動從完整表格匯出中刪除：

* 百分比
* 總計
* 搜尋篩選
* 靜態列
* 日期對齊
* 來自摘要資料集的量度
* 動態維度項目

  動態維度專案建立時，是將維度拖曳至自由表格中的欄標題上，導致欄遭到前5個維度專案的動態篩選。 在Analysis Workspace中，每當您載入專案時，排名前5的維度專案都會更新。 在完整表格匯出作業中，這些維度專案會變成靜態。 有關詳細資訊，請參閱「[自由格式表格中的動態與靜態維度項目](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。
* 第一個劃分中的維度會進行轉換，並在匯出表格的列中新增為次要維度。 表格中不包含任何其他劃分。
* 大部分的資料集不支援排序；可能會為小型資料集排序資料。

## 不支援的元件

以下元件不受支援，且在執行完整表格匯出時， Analysis Workspace 會提示您從表格中刪除這些元件：

* 計算量度定義中使用不支援的函式（如需詳細資訊，請參閱[不支援的計算量度函式](#unsupported-calculated-metric-functions)）
* 管理員已限制匯出的元件（如需詳細資訊，請參閱&#x200B;*標籤和原則*&#x200B;中資料檢視表[中資料治理原則的](/help/data-views/data-governance.md)區段）
* 符合以下所有條件的任何維度：
   * 從屬於[物件陣列](/help/use-cases/object-arrays.md)一部分的欄位建立(類似Adobe Analytics中的多值變數)。
   * 已啟用[持續性](/help/data-views/component-settings/persistence.md)。
   * 未使用[繫結維度](/help/use-cases/data-views/binding-dimensions-metrics.md)。
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

## 計算量度函式支援

下列基本和進階區段列出匯出完整表格時支援的計算量度函式：

### 基本函式支援


| 基本函式 | 支援狀態 |
|---------|----------|
| 絕對值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 欄最大值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 欄最小值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 欄總和 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 計數 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 指數 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 平均值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 中位數 | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 模數 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 百分位數 | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 乘冪運算子 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 四分位數 | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 列計數 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 列最大值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 列最小值 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 列總和 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 四捨五入 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 平方根 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 標準差 | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 變異數 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |

### 進階功能支援

#### 代數函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 以10為底的對數（指數代數） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 立方根（指數代數） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 自然對數（指數代數） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Floor （數值調整代數） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### 邏輯函式

| 進階函式 | 支援狀態 |
|---------|----------|
| If （邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### 布林函式

| 進階函式 | 支援狀態 |
|---------|----------|
| Not （布林運運算元邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| Or （布林運運算元邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| And （布林運運算元邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### 比較函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 小於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 小於或等於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 等於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 大於或等於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 大於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 不等於（比較邏輯） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |


#### 三角函式

| 進階函式 | 支援狀態 |
|---------|----------|
| Pi | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 正弦（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 餘弦（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 正切（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 反正弦（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 反餘弦（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 反正切（標準） | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### 雙曲函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 雙曲餘弦 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 雙曲正弦 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |
| 雙曲正切 | 支援![StatusGreen](/help/assets/icons/StatusGreen.svg) |

#### WASKR函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 信賴度(WASKR) | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 信賴度（下限） (WASKR) | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 信賴度（上限） (WASKR) | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |

#### 分佈函式

| 進階函式 | 支援狀態 |
|---------|----------|
| T分數（學生T分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| T檢定（學生T分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| CDF-T （學生T分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| Z分數（常態分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| Z檢定（常態分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| CDF-Z （常態分佈） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |

#### 回歸函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 相關係數（指數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（指數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （指數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（指數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 相關係數（線性回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（線性回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （線性回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（線性回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 相關係數（對數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（對數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （對數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（對數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 相關係數（乘冪回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（乘冪回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （乘冪回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（乘冪回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 相關係數（二次回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（二次回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （二次回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（二次回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 相關係數（倒數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 截距（倒數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 預計Y （倒數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |
| 斜率（倒數回歸） | 不支援![StatusRed](/help/assets/icons/StatusRed.svg) |

#### 其他進階函式

| 進階函式 | 支援狀態 |
|---------|----------|
| 近似計數相異 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |
| 累積 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |
| 累積平均值 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |
| 提升度 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |
| 樣本變數 | ![藍色](/help/assets/icons/StatusBlue.svg)狀態已計畫 |

## 歸因行為

完整表格匯出支援使用非預設歸因模型的計算量度 (如「[欄設定](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)」中的「*使用非預設歸因模型*」部分)。

如果報表中使用非預設歸因模型，則會根據報表是單一維度還是多個維度，忽略或保留報表中使用的配置模型：

* **在單一維度中包含量度歸因的報告：** [量度歸因](/help/data-views/component-settings/attribution.md)覆蓋[配置模式](/help/data-views/component-settings/persistence.md)，就像平常使用量度歸因會進行的一樣。

  例如，「首次接觸」指標歸因會覆蓋「最近」的維度配置。

* **同時在多個維度中包含量度歸因的報告：除了應用於[維度配置模式](/help/data-views/component-settings/persistence.md)外，還會應用於** [量度歸因](/help/data-views/component-settings/attribution.md)。

  例如，除了「最近」維度配置之外，還會應用「首次接觸」量度歸因。此外，量度歸因會套用至後續配置的維度專案配對（就像它們是單一維度專案一樣），而非如一般在自由表格中獨立套用至每個維度專案。

  >[!NOTE]
  >
  >僅有將資料匯出至雲端時才會支援多維報告，如本文所述。

## 與Data Warehouse比較

如果您先前使用 Data Warehouse 來匯出 Adob&#x200B;&#x200B;e Analytics 資料，下表可以幫助您了解在 Customer Journey Analytics 中匯出完整表格與在 Adob&#x200B;&#x200B;e Analytics 中使用 Data Warehouse 匯出資料之間的差異。

| 功能 | Customer Journey Analytics 中的完整表格匯出 | Adobe Analytics 中的 Data Warehouse |
|---------|----------|---------|
| 建立自訂報告 | 是 | 是 |
| 計算量度 | 是 | 無 |
| 區段 | 是 | 有限 |
| 維度 | 限制 10 個 | 無限制 |
| 量度 | 限制 10 個 | 無限制 |
| 報告列 | 限制為 300 萬列、3,000 萬列、1.5 億列或 3 億列，視等級而定 | 無限制 |
| 報告數量 | 無限制 | 無限制 |
| 臨時 (一次性) 傳遞 | 是 | 是 |
| 安排定期傳遞 | 是 | 是 |
| 電子郵件傳遞 | 無 | 是 |
| FTP / SFTP | 否 | 舊版支援 |
| Azure | 是 | 是 |
| Amazon S3 | 是 | 是 |
| Google Cloud Platform | 是 | 是 |
| Snowflake | 是 | 無 |
| 傳遞頻率 | 每日 | 每小時 |
