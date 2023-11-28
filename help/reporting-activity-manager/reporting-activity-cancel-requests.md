---
title: 取消報告活動管理器中的報告請求
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
solution: Customer Journey Analytics
feature: Basics
exl-id: 87da2447-f114-432a-9f63-e660c2541d0f
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1473'
ht-degree: 14%

---

# 取消報告活動管理器中的報告請求

此 [!UICONTROL 報告活動管理器] 可讓管理員快速診斷並取消報表請求，以修正尖峰報表時間期間的報表容量問題。

取消報表請求時，請考量下列事項：

* 您可以取消特定請求、取消特定使用者的所有請求，或取消與特定專案相關的所有請求。

* 當您取消請求時，也可以選擇限制指定期間的後續請求。

  當您限制後續請求時，此動作會記錄在 [稽核記錄](/help/privacy/audit-log.md) 以「禁運」為動作名稱。

* 如果符合下列條件，則您無法取消請求： [!UICONTROL **使用者**] 請求的欄顯示為 [!UICONTROL **無法辨識**]. 發生這種情況時，表示使用者是在您沒有管理許可權的登入公司中。

如需報告活動管理員的詳細資訊，包括主要權益和許可權要求，請參閱 [報告活動管理器總覽](/help/reporting-activity-manager/reporting-activity-overview.md).

## 取消特定請求

您可以取消耗用大量報告容量的個別請求。 取消請求時，您可以選擇在指定期間內進一步限制請求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **請求**] 標籤，然後選取一或多個請求。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選擇性）若要限制指定期間的未來請求，請執行下列步驟：

   1. 啟用選項以 [!UICONTROL **限制後續請求**].

      ![取消1個請求，其中顯示「限制選取的後續請求」與「取消」訊息。](assets/restrict-subsequent-requests.png)

   1. 從下列選項中選擇：

      | 選項 | 功能 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 與所選請求關聯的使用者將暫時被限制執行關聯專案的報告請求。 |
      | [!UICONTROL **使用者**] | 與所選請求關聯的使用者將暫時被限制提出任何報告請求。 |
      | [!UICONTROL **專案**] | 與所選請求關聯的專案將暫時被限制執行所有報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!-- double-check this --><p>限制設定後，您就無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 依使用者取消請求

您可以取消與一或多個使用者相關聯的所有要求。 取消與使用者相關的請求時，您可以選擇進一步限制該使用者在指定時段內的請求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **使用者**] 標籤，然後選取一或多個使用者。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 來自x位使用者的報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選擇性）若要限制指定期間的未來請求，請執行下列步驟：

   1. 啟用選項以 [!UICONTROL **限制後續請求**]

      ![取消1個請求，其中顯示「依選取的使用者限制後續請求」。](assets/restrict-subsequent-requests-user.png)

   1. 從下列選項中選擇：

      | 選項 | 功能 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 所選的使用者將暫時被限制提出關聯專案的任何報告請求。 <p>這是限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 所選的使用者將暫時被限制提出任何報告請求。 |
      | [!UICONTROL **專案**] | 與所選使用者關聯的專案將受限於任何使用者提出的任何報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!--double-check this--> <p>限制設定後，您就無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 依專案取消請求

您可以取消與一或多個專案關聯的所有請求。 取消與專案相關的請求時，您可以選擇進一步限制在指定期間內與該專案相關的請求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **專案**] 標籤，然後選取一或多個專案。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 來自x個專案的報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選擇性）若要限制指定期間的未來請求，請執行下列步驟：

   1. 啟用選項以 [!UICONTROL **限制後續請求**].

      ![取消1個顯示「依專案限制後續請求」的請求](assets/restrict-subsequent-requests-project.png)

   1. 從下列選項中選擇：

      | 選項 | 功能 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 所選的專案將暫時受限於關聯使用者提出的任何報告請求。<p>這是限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 與所選專案關聯的使用者將被限制提出任何報告請求。 |
      | [!UICONTROL **專案**] | 選取的專案將暫時禁止任何使用者提出任何報告請求。 |
      | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!--double-check this--> <p>限制設定後，您就無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 依應用程式取消請求

您可以取消與一或多個應用程式關聯的所有要求。 取消與應用程式相關的請求時，您可以選擇進一步限制在指定期間內與該應用程式相關的請求。

應用程式包括：

* Analysis Workspace UI
* Workspace 排程專案
* Report Builder
* 產生器 UI：區段、計算量度、註解、對象等。
* 來自2.0 API的API呼叫
* 智慧型警報
* 完整表格匯出
* 與任何人共用連結
* 引導式分析
* 查詢Analytics報表引擎的任何其他應用程式

若要依應用程式取消請求，請執行下列步驟：

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **應用**] 標籤，然後選取一或多個應用程式。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 來自x個專案的報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選擇性）若要限制指定期間的未來請求，請執行下列步驟：

   1. 啟用選項以 [!UICONTROL **限制後續請求**]

      ![取消1個請求，其中顯示「依選取的應用程式限制後續請求」。](assets/restrict-subsequent-requests-application.png)

   1. 從下列選項中選擇：

      | 選項 | 功能 |
      |---------|----------|
      | [!UICONTROL **使用者與專案**] | 選取的應用程式將暫時限制在相關使用者和專案所提出的任何報告請求中。<p>這是限制最少的選項。</p> |
      | [!UICONTROL **使用者**] | 與所選應用程式相關聯的使用者將被限制提出任何報告請求。 |
      | [!UICONTROL **專案**] | 與所選應用程式關聯的專案將限制在任何使用者提出的任何報告請求中。 |
      | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!--double-check this--> <p>限制設定後，您就無法提前移除限制。</p> |

      {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   應用程式中會顯示通知(例如在Analysis Workspace中)，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 使用者存取已取消報告時的體驗

在Analysis Workspace中，使用者嘗試存取受取消影響的報表或視覺效果時，會看到下列訊息：

### 專案上的訊息

當使用者嘗試存取受取消影響的專案時，他們會看到一則訊息，通知他們報表已暫時受限：

![專案取消訊息](assets/workspace-canceled-report.png)

### 視覺效果上的訊息

當使用者嘗試存取受取消影響的視覺效果時，他們會看到一則訊息，通知他們報表的資料處理暫時受限：

![視覺效果取消訊息](assets/workspace-cancelled-visualization.png)
