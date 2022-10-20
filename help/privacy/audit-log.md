---
title: 稽核記錄
description: 了解如何檢視和管理CJA稽核記錄。
source-git-commit: a866dec61df93bf730529a2d7513b4d76bab6694
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---


# 稽核記錄

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

為了提高系統中執行活動的透明度和可見性，Customer Journey Analytics(CJA)可讓您以「稽核記錄」的形式，稽核各種服務和功能的使用者活動。 這些日誌形成了一個審核跟蹤，可以幫助排除問題，並幫助您的企業有效遵守公司資料管理政策和法規要求，如健康保險可移植性和責任法案(HIPAA)。

從基本意義上講，審核日誌會告訴 **誰** 執行 **what** 動作，和 **when**. 記錄在記錄檔中的每個動作都包含中繼資料，指出動作類型、日期和時間、執行動作之使用者的電子郵件ID，以及與動作類型相關的其他屬性。

本主題涵蓋CJA中的稽核記錄，包括如何在UI中檢視和管理這些記錄。

## 對審核日誌的訪問

為您的組織啟用功能時，稽核記錄會隨著活動發生而自動收集。 您不需要手動啟用記錄檔收集。

若要檢視及匯出稽核記錄，您必須已獲授權 **[!UICONTROL 稽核記錄存取]** 存取Adobe控制台中的控制權限。 若要了解如何管理CJA功能的個別權限，請參閱 [存取控制檔案](/help/getting-started/cja-access-control.md).

## 在UI中檢視稽核記錄

在CJA中，導覽至 **[!UICONTROL 工具]** > **[!UICONTROL 稽核記錄]**.

預設會顯示今天和昨天的稽核記錄。

![稽核記錄](assets/audit_ui.png)

前往右上角的欄選取器，即可選取可見的欄。

## 查看有關單個日誌條目的資訊

按兩下說明旁的資訊(i)按鈕。

![稽核記錄](assets/info-button-audit.png)

顯示下列項目：

| 項目 | 說明 |
| --- | --- |
| 動作名稱 | 以下是可能動作的清單： <ul><li>API_Request</li><li>核准</li><li>建立</li><li>編輯</li><li>轉存</li><li>登錄失敗</li><li>登錄成功</li><li>登出</li><li>Org_change</li><li>重新整理</li><li>共用</li><li>轉移</li><li>取消核准</li><li>取消共用</li></ul> |
| 說明 | 動作、元件類型（含ID）和其他值的摘要。 |
| 使用者名稱 | 執行動作的使用者。 |
| 元件類型 | 可能的元件類型包括： <ul><li>註解</li><li>對象</li><li>計算度量</li><li>連線</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>篩選器</li><li>IMS_Org</li><li>行動</li><li>專案</li><li>報表</li><li>Scheduled_Project</li><li>使用者</li><li>User_Group</li></ul> |
| IMS 組織 ID | 首次登入Adobe Experience Cloud時，為您的例項指定的唯一ID。 其格式應為：xxx@AdobeOrg。 |
| 使用者 ID | 識別執行此動作之使用者的唯一ID。 |
| 建立日期 | 執行此動作時。 |
| 電子郵件 | 執行動作之使用者的電子郵件。 |
| 元件 ID | 唯一ID，用於識別要執行的元件。 |
| 記錄 ID | 標識此日誌條目的唯一ID。 |
| 使用者類型 | 可能的類型包括：IMS、OKTA |

### 篩選稽核記錄

選取漏斗圖示(![篩選](assets/filter-icon.png))以顯示篩選控制項清單，以縮小結果範圍。 系統只會顯示最近1,000筆記錄，而不考慮選取的各種篩選器。

![篩選器](assets/filters.png)

下列篩選器適用於UI中的稽核事件：

| 篩選 | 說明 |
| --- | --- |
| [!UICONTROL 日期範圍] | 選取不同日期或拖曳游標至多個日期以選取日期範圍，以篩選不同日期範圍。 預設會選取今天和昨天的日期。 |
| [!UICONTROL 動作] | 篩選下列一或多個動作： <ul><li>API_Request</li><li>核准</li><li>建立</li><li>編輯</li><li>轉存</li><li>登錄失敗</li><li>登錄成功</li><li>登出</li><li>Org_change</li><li>重新整理</li><li>共用</li><li>轉移</li><li>取消核准</li><li>取消共用</li></ul> |
| [!UICONTROL 使用者 ID] | 依使用者ID篩選特定使用者。 選取使用者名稱旁的資訊(i)按鈕，即可找到使用者ID。 |
| [!UICONTROL 電子郵件] | 篩選特定使用者的電子郵件地址。 選取使用者名稱旁的資訊(i)按鈕，即可找到電子郵件。 |
| [!UICONTROL 元件 ID] | 篩選特定元件ID。 選取所需元件的資訊(i)按鈕，即可找到使用者ID。 |
| [!UICONTROL 元件類型] | 依一或多個元件類型篩選： <ul><li>註解</li><li>對象</li><li>計算度量</li><li>連線</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>篩選器</li><li>IMS_Org</li><li>行動</li><li>專案</li><li>報表</li><li>Scheduled_Project</li><li>使用者</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 由稽核記錄擷取的事件類型

下表概述稽核記錄檔要記錄哪些元件類型的動作：

| 元件類型 | 動作 |
| --- | --- |
| [!UICONTROL 註解] | <ul><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 對象] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li><li>轉存</li><li>重新整理</li></ul> |
| [!UICONTROL 計算度量] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 連線] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 資料檢視] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 日期範圍] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 篩選器] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL IMS組織] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 專案] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 報表] | <ul><li>API_Request</li></ul> |
| [!UICONTROL 排程專案] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 使用者] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |
| [!UICONTROL 使用者群組] | <ul><li>API_Request</li><li>建立</li><li>刪除</li><li>編輯</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 下載稽核記錄

您可以下載CSV或JSON格式的稽核記錄檔。 所套用的任何篩選器或選取的欄都會反映在下載的檔案中。

1. 按一下 **[!UICONTROL 下載]** 在畫面右上角。
1. 指定格式。
1. 按一下 **[!UICONTROL 下載]** 。

## 在API中管理稽核記錄

您在UI中可執行的所有動作也可以透過API呼叫完成。 請參閱 [CJA API參考檔案](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) 以取得更多資訊。