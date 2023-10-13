---
title: 取消報告活動管理器中的報告請求
description: 了解如何使用報告活動管理器在尖峰報告期間診斷和修正容量問題。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 23509d26e08b50a6b7a133fdc9a3e2d2d3e8fe43
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 7%

---

# 取消報告活動管理器中的報告請求

{{release-limited-testing}}

此 [!UICONTROL 報告活動管理器] 可讓管理員快速診斷並取消報表請求，以修正尖峰報表時間期間的報表容量問題。

取消報表請求時，請考量下列事項：

* 您可以取消特定請求、取消特定使用者的所有請求，或取消與特定專案相關的所有請求。

* 當您取消請求時，也可以選擇限制指定期間的後續請求。

* 如果符合下列條件，則您無法取消請求： [!UICONTROL **使用者**] 請求的欄顯示為 [!UICONTROL **無法辨識**]. 發生這種情況時，表示使用者是在您沒有管理許可權的登入公司中。

如需報告活動管理員的詳細資訊，包括主要權益和許可權要求，請參閱 [報告活動管理器總覽](/help/reporting-activity-manager/reporting-activity-overview.md).

## 取消特定請求

您可以取消耗用大量報告容量的個別請求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **請求**] 標籤，然後選取一或多個請求。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選用）若要限制指定時段未來的請求，請啟用以下選項： [!UICONTROL **限制後續請求**]，然後從下列選項中選擇：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **使用者與專案**] | 系統會暫時限制與所選請求相關聯的使用者執行關聯專案的報表請求。 |
   | [!UICONTROL **使用者**] | 與所選請求關聯的使用者將暫時被限制提出任何報告請求。 |
   | [!UICONTROL **專案**] | 與所選請求關聯的專案將暫時被限制執行所有報告請求。 |
   | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!-- double-check this --><p>限制設定後，您就無法提前移除限制。</p> |

   {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 依使用者取消請求

您可以取消與一或多個使用者相關聯的所有要求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **使用者**] 標籤，然後選取一或多個使用者。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 來自x位使用者的報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選用）若要限制指定時段未來的請求，請啟用以下選項： [!UICONTROL **限制後續請求**]，然後從下列選項中選擇：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **使用者與專案**] | 選取的使用者暫時無法提出相關專案的任何報告請求。 |
   | [!UICONTROL **使用者**] | 選取的使用者將被暫時限制提出任何報告請求。 |
   | [!UICONTROL **專案**] | 與所選使用者相關聯的專案將受限於任何使用者所提出的任何報告請求。 |
   | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!--double-check this--> <p>限制設定後，您就無法提前移除限制。</p> |

   {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 依專案取消請求

您可以取消與一或多個專案關聯的所有請求。

1. 在Customer Journey Analytics中，前往 **[!UICONTROL 工具]** > **[!UICONTROL 報告活動管理器]**.

1. 選取您要取消報告要求的連線。 <!--double-check this step-->

   如需有關本頁可用資料的詳細資訊，請參閱 [在報告活動管理器中檢視報告活動](/help/reporting-activity-manager/reporting-activity.md).

1. 選取 [!UICONTROL **專案**] 標籤，然後選取一或多個專案。

   <!-- add screenshot -->

1. 選取 [!UICONTROL **取消請求**].

   此 [!UICONTROL **取消 _x_ 來自x個專案的報表請求**] 對話方塊隨即顯示。

1. 取消訊息欄位會顯示取消使用者請求時向使用者顯示的訊息。 已提供預設訊息。 您可以更新預設訊息以提供其他詳細資料。

1. （選用）若要限制指定時段未來的請求，請啟用以下選項： [!UICONTROL **限制後續請求**]，然後從下列選項中選擇：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **使用者與專案**] | 選取的專案將暫時限制在相關使用者提出的任何報告請求中。 |
   | [!UICONTROL **使用者**] | 與所選專案相關聯的使用者將被限制提出任何報告請求。 |
   | [!UICONTROL **專案**] | 選取的專案將暫時禁止任何使用者提出任何報告請求。 |
   | [!UICONTROL **限制**] | 選擇限制要求的時間長度。 您可以選擇1分鐘（預設）、5分鐘、10分鐘、15分鐘或30分鐘。 <!--double-check this--> <p>限制設定後，您就無法提前移除限制。</p> |

   {style="table-layout:auto"}

1. 選取 [!UICONTROL **繼續取消**].

   Analysis Workspace中會顯示通知，通知使用者請求已取消。 如需如何在Analysis Workspace中顯示此內容的詳細資訊，請參閱 [使用者存取已取消報告時的體驗](#experience-when-users-access-a-cancelled-report).

## 使用者存取已取消報告時的體驗

在Analysis Workspace中，使用者嘗試存取管理員已取消的報告時，會看到下列訊息：

![取消使用者通知](assets/cancel-user-facing.png)