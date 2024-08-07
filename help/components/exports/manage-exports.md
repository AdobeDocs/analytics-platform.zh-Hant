---
description: 管理現有的匯出
keywords: Analysis Workspace
title: 管理匯出
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 6f8a43acfba23d6faeff078873742315f1506699
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---

# 管理匯出

匯出完整資料表(如[匯出Customer Journey Analytics報告至雲端](/help/analysis-workspace/export/export-cloud.md)中所述)之後，可在[!UICONTROL 匯出]頁面的[!UICONTROL 匯出]索引標籤上取得匯出。

您只能看到您建立的匯出。

## 篩選和搜尋匯出

若要尋找所需的資訊，您可以篩選匯出清單或搜尋匯出。

### 篩選匯出清單

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **匯出**]&#x200B;標籤。

1. 選取&#x200B;**篩選器**&#x200B;圖示。

   <!--add screenshot -->

   您可以依下列條件篩選：

   | 篩選器 | 說明 |
   |---------|----------|
   | [!UICONTROL **帳戶類型**] | 與匯出相關聯的帳戶型別。 可用的帳戶型別如下： <ul><li>[!UICONTROL **AEP資料登陸區域**]</li><li>[!UICONTROL **Amazon S3角色ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google雲端平台**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **狀態**] | 匯出的狀態。 可使用下列狀態： <ul><li>[!UICONTROL **作用中**]：指出排定的匯出尚未過期，或一次性匯出尚未完成。 </li><li>[!UICONTROL **已完成**]：表示匯出已成功匯出。 對於排程的匯出，這表示排程已過期。</li><li>[!UICONTROL **已失敗**]<p>下列情況可能會導致匯出失敗。 將游標暫留在&#x200B;[!UICONTROL **失敗**]&#x200B;狀態上可檢視有關失敗的詳細資料。 <ul><li>排程的匯出到期日</li><li>已達排程匯出的列數限制 </li></ul> </p></li></ul> |
   | [!UICONTROL **頻率**] | 匯出的頻率。 可使用下列頻率： <ul><li>[!UICONTROL **一次**]</li><li>[!UICONTROL **每日**]</li><li>[!UICONTROL **每週**]</li><li>[!UICONTROL **每月**]</li><li>[!UICONTROL **每年**]</li></ul> |

   {style="table-layout:auto"}

### 搜尋匯出

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 選取&#x200B;[!UICONTROL **匯出**]&#x200B;標籤。

1. 在搜尋欄位中，開始輸入與您搜尋之匯出相關的任何資訊。 您可以從表格中任何可用的欄搜尋資料。

## 編輯匯出

您可以編輯匯出的屬性、格式、排程和位置資訊。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取您要編輯之匯出旁的核取方塊。

   選取多個匯出專案時，此選項無法使用。

1. 選取&#x200B;[!UICONTROL **編輯**]。

   顯示&#x200B;[!UICONTROL **匯出完整資料表**]&#x200B;對話方塊。

1. 更新任何可用選項。 如需各個選項的相關資訊，請參閱[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)中的[從Analysis Workspace匯出完整表格](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace)。

## 複製匯出

您可以複製現有的匯出。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取您要複製的匯出旁的核取方塊。

   選取多個匯出專案時，此選項無法使用。

1. 選取&#x200B;[!UICONTROL **複製**]。

   會建立匯出的重複專案。 新匯出的名稱與原始匯出的名稱相符，檔案名稱后面附有&#x200B;_[!UICONTROL — 副本]_。

1. （選擇性） [編輯新的匯出](#edit-an-export)，包括檔案名稱以及您要變更的任何其他屬性。

## 手動啟動匯出

您可以手動啟動匯出，針對排定的匯出或先前完成的一次性匯出。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取您要執行之匯出旁的核取方塊。

   選取多個匯出專案時，此選項無法使用。

1. 選取&#x200B;[!UICONTROL **立即匯出**]。

## 標籤匯出

將標籤套用至匯出時，您可以在[!UICONTROL 匯出]頁面上的[!UICONTROL 標籤]欄中檢視這些標籤。 如需詳細資訊，請參閱[設定資料行](#configure-columns)。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取一或多個要標籤的匯出專案旁的核取方塊。

1. 選取&#x200B;[!UICONTROL **編輯標籤**]。

1. 在&#x200B;[!UICONTROL **標籤匯出**]&#x200B;對話方塊中，輸入標籤名稱以建立新標籤，或從下拉式選單中選擇現有標籤。

   所選匯出專案之間的任何共同標籤都會顯示在標籤對話方塊中。<!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. 選取&#x200B;[!UICONTROL **套用標籤**]。

## 刪除匯出

您可以從「匯出」頁面刪除匯出。 已刪除的排程匯出將不再傳送。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取一或多個要刪除的匯出專案旁的核取方塊。

1. 選取&#x200B;[!UICONTROL **刪除**]，然後在您看到確認訊息時選取&#x200B;[!UICONTROL **刪除**]。

## 在[!UICONTROL 匯出]頁面上設定欄

您可以在[!UICONTROL 匯出]索引標籤上新增或移除欄，以設定要顯示的資訊。

選取欄標題，依該欄排序匯出。 依預設，匯出會依上次修改匯出的日期和時間排序。

1. 在Customer Journey Analytics中，選取&#x200B;[!UICONTROL **元件**] > [!UICONTROL **匯出**]。

1. 在&#x200B;[!UICONTROL **匯出**]&#x200B;索引標籤上，選取[!UICONTROL 匯出]頁面右上角的&#x200B;**自訂表格**&#x200B;圖示![自訂表格](assets/customize-table-icon.png)。

   可使用下列欄:

   | 可用欄 | 說明 |
   |---------|----------|
   | 名稱 | 匯出的名稱。 使用者在建立匯出時為其命名，如[匯出至雲端的Customer Journey Analytics報告](/help/analysis-workspace/export/export-cloud.md)中所述。 |
   | ID | 建立匯出時自動指派的ID。<!-- True? --> |
   | 資料檢視名稱 | 與匯出相關聯的資料檢視名稱。 使用者可以在建立匯出時選取資料檢視，如[將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md)中所述。 |
   | 狀態 | 匯出的狀態。 可用的狀態為[!UICONTROL 作用中]、[!UICONTROL 已完成]及[!UICONTROL 失敗]。<p> **注意：**&#x200B;如需疑難排解匯出失敗的資訊，請參閱[疑難排解匯出失敗](/help/components/exports/troubleshoot-exports.md)。</p> |
   | 標記 | 顯示套用至匯出的任何標籤。 如需如何將標籤套用至匯出的詳細資訊，請參閱[標籤匯出](#tag-an-export)。 |
   | 表格大小 (上次傳送) | 上次傳送匯出的大小。 |
   | 建立者 | 建立匯出的使用者。 |
   | 已建立 | 建立匯出的日期和時間。<!-- true? --> |
   | 位置 | 匯出資料的帳戶位置。 |
   | 帳戶 | 匯出資料所在的帳戶。 |
   | 頻率 | 傳送匯出的頻率。 可用的選項包括[!UICONTROL 一次]、[!UICONTROL 每日]、[!UICONTROL 每週]、[!UICONTROL 按一週的日期]、[!UICONTROL 按月份的日期]、[!UICONTROL 按月份的日期]每年，以及[!UICONTROL 按特定日期每年]。 |
   | 傳送時間 | 傳送匯出的時間。 |
   | 最後傳送 | 上次傳送匯出的時間。 |
   | 修改時間 | 上次修改匯出的時間。 依預設，「匯出」頁面上的專案會依此欄排序。 |
   | 帳戶類型 | 匯出資料所在的雲端帳戶型別。 可用的帳戶型別為[!UICONTROL Amazon S3SnowflakeARN]、[!UICONTROL Google雲端平台]、[!UICONTROL Azure SAS]、[!UICONTROL Azure RBAC]、[!UICONTROL 角色]和[!UICONTROL Adobe Experience Platform]。 |

   {style="table-layout:auto"}

1. 確定已選取您要顯示的任何欄。 選取的欄會出現在匯出頁面上，並顯示相關資訊。
