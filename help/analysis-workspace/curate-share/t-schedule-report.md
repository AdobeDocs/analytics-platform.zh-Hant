---
description: 瞭解如何直接或依排程傳送Analysis Workspace專案，以傳送電子郵件。
keywords: Analysis Workspace
title: 傳送及排程專案
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 50%

---

# 傳送和排程

您可以透過電子郵件將Customer Journey Analytics專案以檔案形式傳送給所選使用者。 您可以即席傳送檔案，也可以設定專案依排程傳送。 專案可以用CSV或PDF格式傳送。

任何套用於專案的索引標籤都會自動套用於匯出檔案。

還有匯出 Customer Journey Analytics 資料的其他方法，如[匯出概觀](/help/analysis-workspace/export/export-project-overview.md)所述。

![傳送檔案](assets/send-file.png)

## 傳送檔案

若要透過電子郵件傳送檔案給收件者：

1. 選取&#x200B;**[!UICONTROL 共用] > [!UICONTROL 傳送檔案]**。
1. 指定檔案類型：
   * [!UICONTROL **CSV**]：如果您需要純文字資料，請選擇此選項。
   * [!UICONTROL **PDF**]：如果您希望下載的檔案包含專案中所有顯示 (可見) 的表格和視覺效果，請選擇此選項。
1. （選用）使用&#x200B;**[!UICONTROL 說明]**&#x200B;新增要包含在電子郵件中的說明。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. （僅適用於Healthcare Shield客戶）提供[密碼保護排程報告](#password-protect-a-new-scheduled-project)的密碼。
1. （選擇性）選取&#x200B;**[!UICONTROL 顯示排程選項]**&#x200B;至[排程檔案匯出](#schedule-file-export)。
1. 按一下&#x200B;**[!UICONTROL 立即傳送]**。 選取「**[!UICONTROL 取消]**」即可取消。


## 排程檔案匯出 {#schedule}

若要透過電子郵件依排程傳送檔案給收件者

1. 選取&#x200B;**[!UICONTROL 共用] > [!UICONTROL 排程檔案匯出]**。
1. 指定檔案類型：
   * [!UICONTROL **CSV**]：如果您需要純文字資料，請選擇此選項。
   * [!UICONTROL **PDF**]：如果您希望下載的檔案包含專案中所有顯示 (可見) 的表格和視覺效果，請選擇此選項。
1. （選用）使用&#x200B;**[!UICONTROL 說明]**&#x200B;新增要包含在電子郵件中的說明。
1. 新增收件者或群組。您也可以輸入電子郵件地址。
1. （僅適用於Healthcare Shield客戶）提供[密碼保護排程報告](#password-protect-a-new-scheduled-project)的密碼。
1. 請確定已選取&#x200B;**[!UICONTROL 顯示排程選項]**。
1. 選取&#x200B;**[!UICONTROL 頻率]**。 您可以選取：

   | 頻率 | 選項 |
   |---|---|
   | **[!UICONTROL 每小時傳送]** | 輸入&#x200B;**[!UICONTROL 每小時傳送一次的值]**。 |
   | **[!UICONTROL 每日傳送]** | 選取&#x200B;**[!UICONTROL 每日頻率]**： **[!UICONTROL 每天傳送]**、**[!UICONTROL 每個工作日傳送]**&#x200B;或&#x200B;**[!UICONTROL 自訂頻率]**。<br/>如果您選取&#x200B;**[!UICONTROL 自訂頻率]**，請輸入&#x200B;**[!UICONTROL 每隔]**&#x200B;天傳送的值。 |
   | **[!UICONTROL 每週傳送]** | 輸入&#x200B;**[!UICONTROL 每週]**&#x200B;傳送的值。 並選取一週的&#x200B;**[!UICONTROL 天]**。 |
   | **[!UICONTROL 按一週的某天每月傳送]** | 選取&#x200B;**[!UICONTROL 星期]**&#x200B;和&#x200B;**[!UICONTROL 星期]**。 |
   | **[!UICONTROL 每月依月份日期傳送]** | 從&#x200B;**[!UICONTROL 於本月]**&#x200B;的當天傳送中選取一個值。 |
   | **[!UICONTROL 每年依月份日期]**&#x200B;傳送 | 選取&#x200B;**[!UICONTROL 一週中的某天]**，選取一個月中的&#x200B;**[!UICONTROL 周]**，然後選取一年中的&#x200B;**[!UICONTROL 每月]**。 |
   | **[!UICONTROL 依特定日期每年傳送]** | 選取&#x200B;**[!UICONTROL 月份]**，並從&#x200B;**[!UICONTROL 於當月的這個日期傳送]**&#x200B;中選取值。 |

1. 輸入從&#x200B;**開始的**&#x200B;開始日期。 或者，選取![行事曆](/help/assets/icons/Calendar.svg)以從行事曆中挑選開始日期。

1. 在&#x200B;**[!UICONTROL 結束日期]**&#x200B;中輸入結束日期。 或者，選取![行事曆](/help/assets/icons/Calendar.svg)以從行事曆中挑選結束日期。
1. 選取&#x200B;**[!UICONTROL 依排程傳送]**。 選取「**[!UICONTROL 取消]**」即可取消。


## 密碼保護排程專案 {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="密碼加密"
>abstract="提供的密碼將用於加密已排程專案的檔案。您組織的安全要求要求使用密碼加密。"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>密碼保護排程專案的選項僅會對已購買 [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html) 附加產品的 Customer Journey Analytics 客戶顯示。

Adobe 使用密碼來加密排程專案，無論它們是以 .pdf 或是 .csv 格式傳送。

貴公司購買 Healthcare Shield SKU 並啟用後，會在下列情況下顯示為排程專案建立密碼：

* 有人建立一個新排程專案時。

* 即將傳送現有排程專案時。目前排程專案會停用，直到密碼保護設定完成。排程專案的所有者會收到一封電子郵件，告知他們這項要求。

### 密碼需求

密碼需求符合 Adobe 標準，要求至少 8 個字元，其中至少一個數字和一個特殊字元。

### 密碼保護新排程專案

1. 儲存專案後，前往「**[!UICONTROL 共用]** > **[!UICONTROL 立即發送檔案]**」，或「**[!UICONTROL 共用]** > **[!UICONTROL 依排程發送檔案]**」。
1. 按照上面的指示，在[立即傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#now)或[依排程傳送檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=zh-Hant#schedule)下面。

### 密碼保護現有排程專案

當您以密碼保護現有的排程專案時，專案所有者會收到類似以下內容的電子郵件：

![Customer Journey Analytics 電子郵件通知會顯示您的組織需要密碼加密。](assets/email-password.png)

1. 登入 Customer Journey Analytics。
1. 選取「**[!UICONTROL 檢視排程專案]**」。
1. 在 **[!UICONTROL 編輯排程專案]** 對話框中，輸入再重新輸入密碼。
1. 讓排程專案的收件者知道此密碼。請勿將密碼發給非排程專案的收件者。



## 已排程的專案管理員 {#manager}

已排程的Analysis Workspace專案可從主介面使用&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 已排程的專案]**&#x200B;來管理。 如需更多資訊，請參閱「[已排程專案](/help/components/scheduled-projects-manager.md)」。
