---
title: 稽核記錄
description: 了解如何檢視和管理 CJA 稽核記錄。
source-git-commit: 37a23a4669c08c8f7d9c6595286998ebd7e60ac4
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# 稽核記錄

為了提高系統中所執行活動的透明度和可見度，Customer Journey Analytics (CJA) 可讓您以「稽核記錄」的形式，稽核各種服務和功能的使用者活動。這些記錄形成了稽核軌跡，可以幫助解決問題，並幫助您的企業有效地遵守公司資料管理原則和監管要求，例如健康保險便利和責任法案 (HIPAA)。

就基本概念而言，稽核記錄說明了&#x200B;**誰**&#x200B;執行了&#x200B;**什麼**&#x200B;動作，以及&#x200B;**何時**&#x200B;執行。稽核記錄中所記錄的每個動作都包含中繼資料，其指出動作類型、日期和時間、執行動作之使用者的電子郵件 ID，以及與動作類型相關的其他屬性。

本主題涵蓋 CJA 中的稽核記錄，包括如何在 UI 中檢視和管理它們。

## 存取稽核記錄

為您的組織啟用此功能後，活動發生時系統自動收集稽核記錄。您無需手動啟用記錄收集。

若要檢視和匯出稽核記錄，您必須已被授予 Adobe Console 中的&#x200B;**[!UICONTROL 稽核記錄存取權]**&#x200B;存取控制權限。若要了解如何管理 CJA 功能的個人權限，請參閱[存取控制文件](/help/getting-started/cja-access-control.md)。

## 在 UI 中檢視稽核記錄

在 CJA 中，瀏覽到 **[!UICONTROL 工具]** > **[!UICONTROL 稽核記錄]**。

系統依預設會顯示今天和昨天的稽核記錄。

![稽核記錄](assets/audit_ui.png)

您可以使用右上方的欄選擇器來選擇要顯示哪些欄。

## 檢視個別記錄項目的資訊

按兩下說明旁邊的資訊 (i) 按鈕。

![稽核記錄](assets/info-button-audit.png)

系統會顯示以下項目：

| 項目 | 說明 |
| --- | --- |
| 動作名稱 | 以下是可能的動作清單： <ul><li>API 要求</li><li>核准</li><li>建立</li><li>編輯</li><li>匯出</li><li>登入失敗</li><li>登入成功</li><li>登出</li><li>組織變更</li><li>重新整理</li><li>共用</li><li>轉移</li><li>取消核准</li><li>取消共用</li></ul> |
| 說明 | 動作、元件類型 (含 ID) 和其他值的摘要。 |
| 使用者名稱 | 執行動作的使用者。 |
| 元件類型 | 可能的元件類型包括： <ul><li>註解</li><li>對象</li><li>計算量度</li><li>連線</li><li>資料群組</li><li>資料檢視</li><li>功能存取</li><li>篩選器</li><li>IMS 組織</li><li>行動</li><li>專案</li><li>報表</li><li>排程專案</li><li>使用者</li><li>使用者群組</li></ul> |
| IMS 組織 ID | 首次登入 Adobe Experience Cloud 時為您的執行個體提供的唯一 ID。格式應為：xxx@AdobeOrg。 |
| 使用者 ID | 識別執行此動作之使用者的唯一 ID。 |
| 建立日期 | 執行此動作時的時間。 |
| 電子郵件 | 執行此動作之使用者的電子郵件。 |
| 元件 ID | 識別動作執行目標元件的唯一 ID。 |
| 記錄 ID | 識別此記錄項目的唯一 ID。 |
| 使用者類型 | 可能的類型包括：IMS、OKTA |

### 篩選稽核記錄

選擇漏斗圖示 (![篩選](assets/filter-icon.png)) 以顯示篩選控制項以幫助縮小結果範圍。僅顯示最後 1,000 條記錄，無論選擇的各種篩選器為何。

![篩選器](assets/filters.png)

以下篩選器可用於 UI 中的稽核事件：

| 篩選器 | 說明 |
| --- | --- |
| [!UICONTROL 日期範圍] | 選取不同日期，或拖曳游標橫跨多個日期來選取日期範圍，藉此篩選不同日期範圍。系統依預設會選擇今天和昨天的日期。 |
| [!UICONTROL 動作] | 篩選下列其中一個或多個動作： <ul><li>API 要求</li><li>核准</li><li>建立</li><li>編輯</li><li>匯出</li><li>登入失敗</li><li>登入成功</li><li>登出</li><li>組織變更</li><li>重新整理</li><li>共用</li><li>轉移</li><li>取消核准</li><li>取消共用</li></ul> |
| [!UICONTROL 使用者 ID] | 依照使用者 ID 篩選特定使用者。選擇使用者名稱旁邊的資訊 (i) 按鈕可以找到使用者 ID。 |
| [!UICONTROL 電子郵件] | 篩選特定使用者的電子郵件地址。選擇使用者名稱旁邊的資訊 (i) 按鈕可以找到電子郵件。 |
| [!UICONTROL 元件 ID] | 篩選特定元件 ID。選擇所要元件的資訊 (i) 按鈕可以找到使用者 ID。 |
| [!UICONTROL 元件類型] | 篩選一個或多個元件類型： <ul><li>註解</li><li>對象</li><li>計算量度</li><li>連線</li><li>資料群組</li><li>資料檢視</li><li>功能存取</li><li>篩選器</li><li>IMS 組織</li><li>行動</li><li>專案</li><li>報表</li><li>排程專案</li><li>使用者</li><li>使用者群組</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 由稽核記錄擷取的事件類型

下表概述了稽核記錄中對元件類型執行的動作：

| 元件類型 | 動作 |
| --- | --- |
| [!UICONTROL 註解] | <ul><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 對象] | <ul><li>API 要求</li><li>建立</li><li>刪除</li><li>編輯</li><li>匯出</li><li>重新整理</li></ul> |
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

{style=&quot;table-layout:auto&quot;}

## 下載稽核記錄

您可以下載 CSV 或 JSON 格式的稽核記錄。套用的任何篩選器或選擇的欄都會反映在下載的檔案中。

1. 按一下畫面右上方的「**[!UICONTROL 下載]**」。
1. 指定格式。
1. 再按一下 **[!UICONTROL 下載]**。

## 管理 API 中的稽核記錄

所有可以在 UI 中執行的動作，也可以使用 API 呼叫來完成。如需詳細資訊，請參閱 [CJA API 參考文件](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs)。