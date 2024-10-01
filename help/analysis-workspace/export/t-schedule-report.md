---
description: 透過電子郵件傳送Analysis Workspace專案，或排程進行傳送。
keywords: Analysis Workspace
title: 透過電子郵件傳送報告給其他人
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 388e008f4ee092dd8224bfacd020cdf762d4fb82
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 60%

---

# 傳送檔案給其他人

您可以透過電子郵件將Customer Journey Analytics報表以檔案形式傳送給所選使用者。 您可以隨選傳送檔案，也可以設定要依排程傳送的檔案。 能以 CSV 或 PDF 格式傳送檔案。

套用至專案的任何標籤都會自動套用至匯出。

也可以使用其他匯出Customer Journey Analytics資料的方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)中所述。

## 立即傳送檔案 {#now}

若要透過電子郵件立即傳送檔案給收件者：

1. 按一下「**[!UICONTROL 共用] > [!UICONTROL 匯出檔案]**」。
1. 指定檔案類型：
   * [!UICONTROL **CSV**]：如果您需要純文字資料，請選擇此選項。
   * [!UICONTROL **PDF**]：如果您希望下載的檔案包含專案中所有顯示 (可見) 的表格和視覺效果，請選擇此選項。
1. (選用) 新增要包含在電子郵件中的說明，以說明傳送的檔案。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. (僅適用於 Healthcare Shield 客戶) 提供密碼。請參閱「密碼保護排程報告」章節。
1. (選用) 按一下&#x200B;**[!UICONTROL 「顯示排程選項」]**，以指定傳送排程。
1. 按一下&#x200B;**[!UICONTROL 「立即傳送」]**。

![傳送檔案視窗及立即傳送按鈕。](assets/send-file-no-scheduling-options.JPG)

## 依排程傳送檔案 {#schedule}

若要透過電子郵件定期傳送檔案給收件者：

1. 按一下「**[!UICONTROL 共用] > [!UICONTROL 排程檔案匯出]**」。
1. 指定檔案類型 (CSV 或 PDF)。
1. (選用) 新增要加入電子郵件中的說明，以說明傳送的檔案。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. (僅適用於 Healthcare Shield 客戶) 提供密碼。請參閱「密碼保護排程報告」章節。
1. 修改「開始時間」和「結束時間」輸入內容，指定應傳送排程的時間範圍。結束日期必須在建立或修改排程當日起一年內。
1. 指定傳送頻率。每個頻率都允許不同的自訂內容。
1. 按一下&#x200B;**[!UICONTROL 「依排程傳送」]**。

![顯示[傳送檔案]視窗和排程選項，以顯示[開始日期]、[結束日期]及每日頻率設定。](assets/send-file.JPG)

## 排程專案管理員 {#manager}

可在「**[!UICONTROL Analytics] > [!UICONTROL 元件] > [!UICONTROL 排程專案]**」中管理已排程 Analysis Workspace 專案。

在「排程專案管理員」中，您可以編輯和刪除周期性專案排程。在搜尋列中或使用左側面板中的篩選選項來搜尋排程。 您可以依標籤、核准的排程、擁有者等篩選。

| 欄位 | 說明 |
| --- | --- |
| [!UICONTROL 我的最愛] | 選取星號圖示可將此排程加入我的最愛。 |
| [!UICONTROL 排程 ID] | 此 ID 主要是用於偵錯。 |
| [!UICONTROL 標題和說明] | 此專案的標題和說明。 |
| [!UICONTROL 所有者] | 建立及擁有專案的人。 |
| [!UICONTROL 標記] | (選擇性) 標記是組織專案的好方法。 所有使用者都可建立標記，並將一個或多個標記套用到專案。 不過，您只能看見自己所擁有或他人與您共用的那些專案的標記。 |
| [!UICONTROL 已傳遞到] | 此排程專案的收件者。 |
| [!UICONTROL 到期日] | 您可以將到期日設定為一年，無論排程頻率為何。 |
| [!UICONTROL 頻率] | 您想要將此排程專案傳送給收件者的頻率。 |
| [!UICONTROL 執行時間] | 在一天中的什麼時間傳送此排程專案。 |
| [!UICONTROL 查詢數] | 針對此專案執行的查詢數。 |

下列是「已排程的專案管理員」中的常見動作：

| 動作 | 說明 |
|---|---|
| **[!UICONTROL 編輯排程]** | 按一下排程的標題以更新傳送設定。 |
| **[!UICONTROL 刪除排程]** | 選取清單中的排程專案，然後在功能表按一下「刪除」。這會刪除專案選取的排程，不會刪除專案本身。 |
| **[!UICONTROL 新增標籤]** | 選取清單中的排程專案，然後選擇「標籤」或「核准」來組織排程，更能輕鬆搜尋。 |
| **[!UICONTROL 檢視失敗的排程]** | 導覽至左側面板>「其他篩選器>失敗」，檢視失敗的排程。 |
| **[!UICONTROL 檢視過期的排程]** | 導覽至左側面板>「其他篩選器>過期」，檢視過期的排程。 按一下排程標題，以設定新的傳送排程。 |
| **[!UICONTROL 檢視排程 ID]** | 導覽至右上角的欄選項，然後將「排程 ID」欄新增至表格。排程的 ID 對除錯而言通常很實用。 |

「排程專案管理員」會顯示特定使用者建立的項目。若應用程式內的使用者帳戶已停用，所有已排程的傳送將停止。
如需詳細資訊，請參閱[排程專案](/help/components/scheduled-projects-manager.md)。

## 密碼保護排程專案 {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_sendfile_password"
>title="密碼加密"
>abstract="提供的密碼將用於加密已排程專案的檔案。貴組織的安全要求已要求進行密碼加密。"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>密碼保護排程專案的選項僅會對已購買[Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html)附加產品的Customer Journey Analytics客戶顯示。

Adobe 使用密碼來加密排程專案，無論它們是以 .pdf 或是 .csv 格式傳送。

貴公司購買Healthcare Shield SKU並啟用後，會在下列情況下顯示提示，要求為排程專案建立密碼：

* 有人建立一個新排程專案時。

* 即將傳送現有排程專案時。目前排程的專案在密碼保護到位前會停用。 排程專案的擁有者會收到通知此需求的電子郵件。

![編輯排程專案視窗和密碼加密通知，指示您的組織需要密碼加密。](assets/password.png)

### 密碼需求

密碼要求符合Adobe標準，要求至少8個字元，其中至少一個數字和一個特殊字元。

### 密碼保護新排程專案

1. 儲存專案後，請移至&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 立即傳送檔案]**，或&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 依排程傳送檔案]**。
1. 按照上面的指示，在[立即傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#now)或[依排程傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#schedule)下面。

### 密碼保護現有排程專案

在排程專案之前，專案所有者會收到類似以下內容的電子郵件：

![貴組織需要指示密碼加密的Customer Journey Analytics電子郵件通知。](assets/email-password.png)

1. 登入Customer Journey Analytics。
1. 選取&#x200B;**[!UICONTROL 檢視排程專案]**。
1. 在 **[!UICONTROL 編輯排程專案]** 對話框中，輸入再重新輸入密碼。
1. 讓排程專案的收件者知道此密碼。 請勿將密碼散發給不是排程專案收件者的使用者。
