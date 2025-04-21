---
title: 在報告活動管理員取消報告請求
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
solution: Customer Journey Analytics
feature: Basics
exl-id: 87da2447-f114-432a-9f63-e660c2541d0f
role: Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: ht
source-wordcount: '1497'
ht-degree: 100%

---

# 在報告活動管理員取消報告請求

[!UICONTROL 報告活動管理員]可讓管理員能夠快速診斷和取消報告請求，以便在尖峰報告期間修正報告容量問題。

取消報告請求時請考慮以下內容：

* 您可以取消特定的請求、取消來自特定使用者的所有請求或取消與特定專案相關的所有請求。

* 當您取消請求時，您也可以選擇指定時段的限制後續請求。

  當您限制後續請求時，該動作將記錄在[稽核記錄](/help/privacy/audit-log.md)中且行動名稱為 EMBARGO。

* 如果請求的&#x200B;[!UICONTROL **使用者**]&#x200B;欄顯示為「[!UICONTROL **無法識別**]」。當此情況發生時，表示使用者處於您並無管理權限的登入公司。

有關報告活動管理員的更多資訊 (包括關鍵優勢和權限需求)，請參閱[報告活動管理員概觀](/help/reporting-activity-manager/reporting-activity-overview.md)。

## 取消特定請求

您可以取消消耗大量報告容量的個別請求。取消請求時，您可以選擇在特定時間段內進一步限制。

1. 在 Customer Journey Analytics 中，前往「**[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理員]**」。

1. 請選取您想要取消報告請求的連線。<!--double-check this step-->

   有關此頁面上可用資料的更多資訊，請參閱[在報告活動管理員中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md)。

1. 請選取&#x200B;[!UICONTROL **請求**]&#x200B;索引標籤，然後選取一個或多個請求。

   <!-- add screenshot -->

1. 請選取「[!UICONTROL **取消請求**]」。

   將顯示「[!UICONTROL **取消&#x200B;_十_ 報告請求**]」對話框。

1. 取消訊息欄位顯示在取消使用者請求時所顯示的訊息。提供預設訊息。您可以更新預設訊息以提供更多詳細資訊。

1. (可選) 若要限制指定時段的未來請求：

   1. 啟用選項以&#x200B;[!UICONTROL **限制後續請求**]。

      ![取消 1 個請求，顯示己選的限制後續請求和取消訊息。](assets/restrict-subsequent-requests.png)

   1. 從下列選項中選擇：

      | 選項 | 函數 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 與所選請求關聯的使用者將暫時被限制，無法執行關聯專案的報告請求。 |
      | [!UICONTROL **使用者**] | 與所選請求關聯的使用者將暫時被限制提出任何報告請求。 |
      | [!UICONTROL **專案**] | 與所選請求關聯的專案將暫時被限制執行所有報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制請求的時間長度。您可以選擇 1 分鐘 (預設)、5 分鐘、10 分鐘、15 分鐘或 30 分鐘。<!-- double-check this --><p>設定限制後，您無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 請選取「[!UICONTROL **繼續取消**]」。

   Analysis Workspace 中會顯示一則通知，告知使用者請求已刪除。有關此通知如何在 Analysis Workspace 顯示的詳細資訊，請參閱[使用者存取已取消的報告之體驗](#experience-when-users-access-a-cancelled-report)。

## 取消使用者請求

您可以取消與一個或多個使用者相關的所有請求。取消與使用者相關的請求時，您可以選擇在特定時間內進一步限制該使用者的請求。

1. 在 Customer Journey Analytics 中，前往「**[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理員]**」。

1. 請選取您想要取消報告請求的連線。<!--double-check this step-->

   有關此頁面上可用資料的更多資訊，請參閱[在報告活動管理員中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md)。

1. 請選取「[!UICONTROL **使用者**]」索引標籤，然後選取一個或多個使用者。

   <!-- add screenshot -->

1. 請選取「[!UICONTROL **取消請求**]」。

   顯示來自 x 位使用者的「[!UICONTROL **取消 _x_ 個報告請求**]」對話框。

1. 取消訊息欄位顯示在取消使用者請求時所顯示的訊息。提供預設訊息。您可以更新預設訊息以提供更多詳細資訊。

1. (可選) 若要限制指定時段的未來請求：

   1. 啟用選項以&#x200B;[!UICONTROL **限制後續請求**]

      ![取消 1 個請求，顯示已選取的按使用者限制後續請求。](assets/restrict-subsequent-requests-user.png)

   1. 從下列選項中選擇：

      | 選項 | 函數 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 所選的使用者將暫時被限制，無法對關聯專案提出任何報告請求。 <p>此為限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 所選的使用者將暫時被限制，無法提出任何報告請求。 |
      | [!UICONTROL **專案**] | 與所選使用者關聯的專案將被限制，無法由任何使用者提出任何報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制請求的時間長度。您可以選擇 1 分鐘 (預設)、5 分鐘、10 分鐘、15 分鐘或 30 分鐘。<!--double-check this--> <p>設定限制後，您無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 請選取「[!UICONTROL **繼續取消**]」。

   Analysis Workspace 中會顯示一則通知，告知使用者請求已刪除。有關此通知如何在 Analysis Workspace 顯示的詳細資訊，請參閱[使用者存取已取消的報告之體驗](#experience-when-users-access-a-cancelled-report)。

## 根據專案取消請求

您可以取消與一個或多個專案相關的所有請求。取消與專案相關的請求時，您可以選擇在指定時段內進一步限制與該專案相關的請求。

1. 在 Customer Journey Analytics 中，前往「**[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理員]**」。

1. 請選取您想要取消報告請求的連線。<!--double-check this step-->

   有關此頁面上可用資料的更多資訊，請參閱[在報告活動管理員中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md)。

1. 請選取「[!UICONTROL **專案**]」索引標籤，然後選取一個或多個專案。

   <!-- add screenshot -->

1. 請選取「[!UICONTROL **取消請求**]」。

   顯示來自 x 個專案的「[!UICONTROL **取消 _x_ 個報告請求**]」對話框。

1. 取消訊息欄位顯示在取消使用者請求時所顯示的訊息。提供預設訊息。您可以更新預設訊息以提供更多詳細資訊。

1. (可選) 若要限制指定時段的未來請求：

   1. 啟用選項以&#x200B;[!UICONTROL **限制後續請求**]。

      ![取消 1 個請求，顯示按項目限制後續請求](assets/restrict-subsequent-requests-project.png)

   1. 從下列選項中選擇：

      | 選項 | 函數 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 所選的專案將暫時被限制，無法由關聯使用者提出任何報告請求。<p>此為限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 與所選專案關聯的使用者將被限制，無法提出任何報告請求。 |
      | [!UICONTROL **專案**] | 將暫時限制選取的專案，無法由任何使用者提出任何報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制請求的時間長度。您可以選擇 1 分鐘 (預設)、5 分鐘、10 分鐘、15 分鐘或 30 分鐘。<!--double-check this--> <p>設定限制後，您無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 請選取「[!UICONTROL **繼續取消**]」。

   Analysis Workspace 中會顯示一則通知，告知使用者請求已刪除。有關此通知如何在 Analysis Workspace 顯示的詳細資訊，請參閱[使用者存取已取消的報告之體驗](#experience-when-users-access-a-cancelled-report)。

## 根據應用程式取消請求

您可以取消與一個或多個應用程式相關的所有請求。取消與應用程式相關的請求時，您可以選擇在指定時段內進一步限制與該應用程式相關的請求。

包括下列應用程式：

* Analysis Workspace UI
* Workspace 排程專案
* Report Builder
* 產生器 UI：細分群體、計算量度、註解、客群等。
* 來自 2.0 API 的 API 呼叫
* 警報
* 完整表格匯出
* 與任何人共用連結
* 引導式分析
* 查詢 Analytics 報告引擎的任何其他應用程式

如要根據應用程式取消請求：

1. 在 Customer Journey Analytics 中，前往「**[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理員]**」。

1. 請選取您想要取消報告請求的連線。<!--double-check this step-->

   有關此頁面上可用資料的更多資訊，請參閱[在報告活動管理員中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md)。

1. 請選取「[!UICONTROL **應用程式**]」索引標籤，然後選取一個或多個應用程式。

   <!-- add screenshot -->

1. 請選取「[!UICONTROL **取消請求**]」。

   顯示來自 x 個專案的「[!UICONTROL **取消 _x_ 個報告請求**]」對話框。

1. 取消訊息欄位顯示在取消使用者請求時所顯示的訊息。提供預設訊息。您可以更新預設訊息以提供更多詳細資訊。

1. (可選) 若要限制指定時段的未來請求：

   1. 啟用選項以&#x200B;[!UICONTROL **限制後續請求**]

      ![取消 1 個請求，顯示已選取的按應用程式限制後續請求。](assets/restrict-subsequent-requests-application.png)

   1. 從下列選項中選擇：

      | 選項 | 函數 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 將暫時限制選取的應用程式，無法由相關使用者和專案提出任何報告請求。<p>此為限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 將限制與選取應用程式相關的使用者，無法提出任何報告請求。 |
      | [!UICONTROL **專案**] | 將限制與選取應用程式相關的專案，無法由任何使用者提出任何報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制請求的時間長度。您可以選擇 1 分鐘 (預設)、5 分鐘、10 分鐘、15 分鐘或 30 分鐘。<!--double-check this--> <p>設定限制後，您無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 請選取「[!UICONTROL **繼續取消**]」。

   應用程式中 (例如在 Analysis Workspace) 會顯示一則通知，告知使用者已取消此請求。有關此通知如何在 Analysis Workspace 顯示的詳細資訊，請參閱[使用者存取已取消的報告之體驗](#experience-when-users-access-a-cancelled-report)。

## 使用者存取已取消的報告之體驗

在 Analysis Workspace 中，當使用者嘗試存取受取消影響的報告或視覺效果時，會顯示以下訊息：

### 專案訊息

當使用者嘗試存取受取消影響的專案時，他們會看見一則訊息，通知他們該報告暫時受到限制：

![專案取消訊息](assets/workspace-canceled-report.png)

### 視覺效果的訊息

當使用者嘗試存取受取消影響的視覺效果時，他們會看見一則訊息，通知他們該資料處理暫時受到限制：

![視覺效果取消訊息](assets/workspace-cancelled-visualization.png)
