---
description: 管理現有匯出的記錄
keywords: Analysis Workspace
title: 管理匯出記錄
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 8%

---

# 管理匯出記錄

匯出記錄檔會提供每次匯出的詳細資訊，並在每次Analysis Workspace資料匯出至雲端時產生。 (如需如何將資料匯出至雲端的相關資訊，請參閱[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。)

對於已排程的匯出，記錄會反映匯出設定，與傳送記錄時的設定相同。 無法刪除記錄檔。

## 檢視匯出記錄

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **記錄檔**]&#x200B;索引標籤。

   顯示[記錄檔]索引標籤的![匯出視窗](assets/export-logs-tab.png)

   每個記錄的詳細資訊都會顯示在可用的欄中。

1. 執行以下任一操作：

   * [自訂顯示的資料行](#configure-columns)。

   * 選取記錄檔名稱旁的&#x200B;**資訊圖示** ![資訊圖示](assets/information-icon.png)，以檢視與記錄檔相關聯的匯出。

   * 選取記錄檔名稱旁的&#x200B;**編輯匯出圖示** ![資訊圖示](assets/edit-export-icon.png)，以編輯與記錄檔關聯的匯出。

     如需編輯匯出的詳細資訊，請參閱[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)。

## 篩選和搜尋記錄

若要尋找您需要的資訊，您可以篩選記錄清單或搜尋記錄。

### 篩選記錄清單

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **記錄檔**]&#x200B;索引標籤。

1. 選取&#x200B;**篩選器**&#x200B;圖示。

   ![匯出視窗，顯示依帳戶型別區分的篩選器清單](assets/export-log-filters.png)

   您可以依下列條件篩選：

   | 篩選器 | 說明 |
   |---------|----------|
   | [!UICONTROL **匯出識別碼**] | 指定您要檢視之匯出日誌的匯出ID。 |
   | [!UICONTROL **帳戶類型**] | 與記錄關聯的帳戶型別。 可用的帳戶型別如下： <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **狀態**] | 匯出的狀態。 可使用下列狀態： <ul><li>[!UICONTROL **擱置中**]：匯出的特定執行個體已啟動，但尚未完成。<p>重新執行狀態為「擱置中」的匯出作業將會延遲匯出程式。</p></li><li>[!UICONTROL **已完成**]：匯出的特定執行個體已完成處理，並可在匯出帳戶中使用。</li><li>[!UICONTROL **已失敗**]<p>各種情況都可能導致匯出失敗。 將滑鼠懸停在失敗狀態上可檢視有關失敗的詳細資訊。<p>如需失敗可能原因的詳細資訊，請參閱[疑難排解失敗的匯出](/help/components/exports/troubleshoot-exports.md)。</p> |

   {style="table-layout:auto"}

### 搜尋記錄

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **記錄檔**]&#x200B;索引標籤。

1. 在搜尋欄位中，開始輸入與您搜尋的記錄檔相關聯的任何資訊。 您可以從表格中任何可用的欄搜尋資料。

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## 編輯匯出

您可以編輯與特定記錄檔相關聯的匯出。

選取多個記錄檔時，此選項無法使用。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **記錄檔**]&#x200B;索引標籤。

1. 找到與您要編輯之匯出關聯的記錄。

1. 選取記錄名稱旁的&#x200B;**編輯匯出**&#x200B;圖示![匯出記錄圖示](assets/export-icon.png)。

   或

   選取記錄檔旁的核取方塊，然後選取&#x200B;[!UICONTROL **編輯匯出**]。

## 設定資料欄

您可以在[!UICONTROL 記錄檔]索引標籤上新增或移除資料行，以設定要顯示的資訊。

選取欄標題，依該欄排序記錄。 依預設，記錄檔會依開始匯出的日期和時間排序。

若要在[!UICONTROL 記錄檔]索引標籤上設定資料行：

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **記錄檔**]&#x200B;索引標籤。

1. 選取&#x200B;**記錄檔**&#x200B;頁面右上角的![自訂表格](assets/customize-table-icon.png)圖示[!UICONTROL 自訂表格]。

   可使用下列欄：

   | 可用欄 | 說明 |
   |---------|----------|
   | 匯出名稱 | 匯出的名稱。 使用者在建立匯出時為其命名，如[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)中所述。 |
   | 匯出 ID | 建立匯出時自動指派的ID。<!-- True? --> |
   | 實例 ID | Customer Journey Analytics例項的ID。<!-- True? --> |
   | 資料檢視名稱 | 與匯出相關聯的資料檢視名稱。 使用者建立匯出時可選取資料檢視，如[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)中所述。 |
   | 檔案的數量 | 匯出中包含的檔案數。 |
   | 大小 | 匯出的大小。<p>檔案大小的計算基準為1024，有時表示為KIB和MIB。 如果您的雲端提供者以1000為基數計算大小，這可能會導致您的雲端提供者中顯示的大小與此處顯示的大小稍微不同。</p> |
   | 位置 | 匯出資料的帳戶位置。 |
   | 帳戶 | 匯出資料所在的帳戶。 |
   | 狀態 | 匯出的狀態。 可用的狀態為[!UICONTROL 擱置中]、[!UICONTROL 已傳遞]及[!UICONTROL 失敗]。 |
   | 傳遞日期 | 匯出發生的日期。 |
   | 帳戶類型 | 匯出資料所在的雲端帳戶型別。 可用的帳戶型別為[!UICONTROL Amazon S3角色ARN]、[!UICONTROL Google Cloud Platform]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL Snowflake]和[!UICONTROL Adobe Experience Platform]。 |
   | 列數 | 匯出表格中包含的列數。 |

   {style="table-layout:auto"}

1. 確定已選取您要顯示的任何欄。 選取的資料行會顯示在[!UICONTROL 記錄檔]頁面上，並顯示相關資訊。

## 檢視稽核記錄

完整資料表匯出也會在[Customer Journey Analytics稽核記錄](/help/privacy/audit-log.md)中進行追蹤。<!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
