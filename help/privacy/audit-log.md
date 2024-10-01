---
title: 稽核記錄
description: 瞭解如何檢視和管理Customer Journey Analytics稽核記錄。
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 31381cd397a821cc3ff1b3c15ae968a7260a6e9e
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 66%

---

# 稽核記錄 {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_userid"
>title="使用者 ID"
>abstract="在包含所要使用者的記錄項目上點擊「資訊」按鈕，即可找到使用者 ID。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_tools_auditlog_componentid"
>title="元件 ID"
>abstract="在包含所要元件的記錄項目上點擊「資訊」按鈕，即可找到元件 ID。"

<!-- markdownlint-enable MD034 -->


為了提高系統中所執行活動的透明度和可見度，Adobe Customer Journey Analytics可讓您以「稽核記錄」的形式，稽核各種服務和功能的使用者活動。 這些記錄形成了稽核軌跡，可以幫助解決問題，並幫助您的企業有效地遵守公司資料管理原則和監管要求，例如健康保險便利和責任法案 (HIPAA)。

就基本概念而言，稽核記錄說明了&#x200B;**誰**&#x200B;執行了&#x200B;**什麼**&#x200B;動作，以及&#x200B;**何時**&#x200B;執行。稽核記錄中所記錄的每個動作都包含中繼資料，其指出動作類型、日期和時間、執行動作之使用者的電子郵件 ID，以及與動作類型相關的其他屬性。

本主題涵蓋Customer Journey Analytics中的稽核記錄，包括如何在UI中檢視和管理它們。

## 存取稽核記錄

為您的組織啟用此功能後，活動發生時系統自動收集稽核記錄。您無需手動啟用記錄收集。

若要檢視和匯出稽核記錄，您必須已被授予 Adobe Console 中的&#x200B;**[!UICONTROL 稽核記錄存取權]**&#x200B;存取控制權限。若要瞭解如何管理Customer Journey Analytics功能的個別許可權，請參閱[存取控制檔案](../technotes/access-control.md)。

## 在 UI 中檢視稽核記錄

在Customer Journey Analytics中，導覽至&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL 稽核記錄]**。

系統依預設會顯示今天和昨天的稽核記錄。

![今天和昨天的稽核記錄醒目提示。](assets/audit_ui.png)

您可以使用右上方的欄選擇器來選擇要顯示哪些欄。

## 檢視個別記錄項目的資訊

按兩下說明旁邊的資訊 (i) 按鈕。

![反白顯示資訊按鈕的稽核記錄。](assets/info-button-audit.png)

系統會顯示以下項目：

* **[!UICONTROL 動作名稱]**：採取的動作。 可能的值包括：
   * API要求
   * 核准
   * 建立
   * DELETE
   * 編輯
   * 禁運
   * 匯出
   * 組織變更
   * 重新整理
   * 共用
   * 轉移
   * 取消核准
   * 取消共用
* **[!UICONTROL 建立日期]**：執行動作的日期和時間。
* **[!UICONTROL 描述]**：動作摘要。
* **[!UICONTROL 使用者名稱]**：執行此動作的使用者。
* **[!UICONTROL 電子郵件]**：執行動作之使用者的電子郵件地址。
* **[!UICONTROL 元件名稱]**：使用者對其執行動作的元件。
* **[!UICONTROL 元件型別]**：元件的型別。 可能的值包括：
   * 註解
   * 對象
   * CALCULATED_METRIC
   * CONNECTION
   * 資料群組
   * 資料檢視
   * DATASET_STITCHING
   * DATE_RANGE
   * 功能存取
   * 篩選
   * IMS組織
   * 行動
   * 專案
   * 報告
   * 排程專案
   * 使用者
   * 使用者群組
* **[!UICONTROL 元件ID]**：使用者對其執行動作的元件識別碼。
* **[!UICONTROL IMS組織ID]**：組織的IMS ID，格式為`ABC123@AdobeOrg`。
* **[!UICONTROL 記錄識別碼]**：識別此記錄專案的唯一識別碼。
* **[!UICONTROL 使用者ID]**：識別執行動作之使用者的唯一識別碼。
* **[!UICONTROL 使用者型別]**：使用的驗證型別。 有效值包括：
   * IMS
   * OKTA

### 篩選稽核記錄

選擇漏斗圖示 (![篩選](assets/filter-icon.png)) 以顯示篩選控制項以幫助縮小結果範圍。僅顯示最後 1,000 條記錄，無論選擇的各種篩選器為何。

![稽核記錄檔顯示資料範圍所顯示的篩選器。](assets/filters.png)

以下篩選器可用於 UI 中的稽核事件：

| 篩選器 | 說明 |
| --- | --- |
| [!UICONTROL 日期範圍] | 選取不同日期，或拖曳游標橫跨多個日期來選取日期範圍，藉此篩選不同日期範圍。系統依預設會選擇今天和昨天的日期。 |
| [!UICONTROL 動作] | 篩選上面列出的任何動作名稱。 |
| [!UICONTROL 使用者 ID] | 依照使用者 ID 篩選特定使用者。選擇使用者名稱旁邊的資訊 (i) 按鈕可以找到使用者 ID。 |
| [!UICONTROL 電子郵件] | 篩選特定使用者的電子郵件地址。選擇使用者名稱旁邊的資訊 (i) 按鈕可以找到電子郵件。 |
| [!UICONTROL 元件 ID] | 篩選特定元件 ID。選擇所要元件的資訊 (i) 按鈕可以找到使用者 ID。 |
| [!UICONTROL 元件類型] | 篩選上面列出的任何元件型別。 |

{style="table-layout:auto"}

## 由稽核記錄擷取的事件類型

下表概述了稽核記錄中對元件類型執行的動作：

| 元件類型 | 動作 |
| --- | --- |
| [!UICONTROL 註解] | <ul><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 客群] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li><li>匯出</li><li>重新整理</li></ul> |
| [!UICONTROL 計算量度] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 連線] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 資料檢視] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 日期範圍] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 篩選器] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL IMS 組織] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 專案] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 報表] | <ul><li>API 要求</li></ul> |
| [!UICONTROL 排定的專案] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 使用者] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 使用者群組] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |

{style="table-layout:auto"}

## 下載稽核記錄

您可以下載 CSV 或 JSON 格式的稽核記錄。套用的任何篩選器或選擇的欄都會反映在下載的檔案中。

1. 按一下畫面右上方的「**[!UICONTROL 下載]**」。
1. 指定格式。
1. 再按一下 **[!UICONTROL 下載]**。

## 管理 API 中的稽核記錄

所有可以在 UI 中執行的動作，也可以使用 API 呼叫來完成。如需詳細資訊，請參閱[Customer Journey Analytics API參考檔案](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)。
