---
description: 透過電子郵件傳送 Analysis Workspace 專案，或排程進行傳送。
keywords: Analysis Workspace
title: 為專案排程
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 84%

---

# 排程專案

您可以從工作區的&#x200B;**[!UICONTROL 「共用」]**&#x200B;功能表，透過電子郵件將 Analysis Workspace 專案傳送給選取的收件者。能以 CSV 或 PDF 格式傳送檔案。

## 立即傳送檔案 {#now}

若要透過電子郵件立即傳送檔案給收件者：

1. 按一下 **[!UICONTROL 共用] > [!UICONTROL 匯出檔案]**.
1. 指定檔案型別：
   * [!UICONTROL **CSV**]：如果您想要純文字資料，請選擇此選項。
   * [!UICONTROL **PDF**]：如果您希望下載的檔案包含專案中所有顯示的（可見）表格和視覺效果，請選擇此選項。
1. （選用）新增要納入電子郵件中的說明，以說明正在接收的檔案。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. (僅適用於 Healthcare Shield 客戶) 提供密碼。請參閱「密碼保護排程報告」章節。
1. 按一下「**[!UICONTROL 立即傳送]**」。
1. (選用) 按一下&#x200B;**[!UICONTROL 「顯示排程選項」]**，以指定傳送排程。

![立即傳送檔案](assets/send-file-no-scheduling-options.JPG)

## 依排程傳送檔案 {#schedule}

若要透過電子郵件定期傳送檔案給收件者：

1. 按一下 **[!UICONTROL 共用] > [!UICONTROL 排程檔案匯出]**.
1. 指定檔案類型 (CSV 或 PDF)。
1. (選用) 新增要加入電子郵件中的說明，以說明傳送的檔案。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. (僅適用於 Healthcare Shield 客戶) 提供密碼。請參閱「密碼保護排程報告」章節。
1. 修改「開始時間」和「結束時間」輸入內容，指定應傳送排程的時間範圍。結束日期必須在建立或修改排程當日起一年內。
1. 指定傳送頻率。每個頻率都允許不同的自訂內容。
1. 按一下&#x200B;**[!UICONTROL 「依排程傳送」]**。

![](assets/send-file.JPG)

## 排程專案管理員 {#manager}

可在「**[!UICONTROL Analytics] > [!UICONTROL 元件] > [!UICONTROL 排程專案]**」中管理已排程 Analysis Workspace 專案。

如需詳細資訊，請參閱 [排程專案](/help/components/scheduled-projects-manager.md)

## 密碼保護排程專案 {#password}

>[!NOTE]
>
>密碼保護排程專案的選項僅會對已購買的Customer Journey Analytics客戶顯示 [Health Shield](https://business.adobe.com/solutions/experience-cloud-for-healthcare.html) 附加產品。

Adobe 使用密碼來加密排程專案，無論它們是以 .pdf 或是 .csv 格式傳送。

貴公司購買 Healthcare Shield SKU 並啟用後，會在兩種情況下彈出提示，要求為排程專案建立密碼：

* 有人建立一個新排程專案時。

* 即將傳送現有排程專案時。目前排程專案將停用，直到密碼保護設定完成。排程專案的所有者將就此收到一封電子郵件。

![密碼保護](assets/password.png)

### 密碼需求

密碼需求符合 Adobe 標準，要求至少 8 個字元，其中至少一個數字和一個特殊字元。

### 密碼保護新排程專案

1. 儲存專案後，前往 **[!UICONTROL 共用]** > **[!UICONTROL 立即傳送檔案]**，或 [!UICONTROL 共用] > **[!UICONTROL 依排程傳送檔案]**。
1. 按照上面的指示，在[立即傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#now)或[依排程傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#schedule)下面。

### 密碼保護現有排程專案

在專案排定的時間之前，專案所有者將收到類似以下內容的電子郵件：

![電子郵件](assets/email-password.png)

1. 再次登入 Customer Journey Analytics。
1. 按一下 **[!UICONTROL 檢視排程專案]**。
1. 在 **[!UICONTROL 編輯排程專案]** 對話框中，輸入再重新輸入密碼。
1. (僅) 讓排程專案的收件者知道此密碼。


