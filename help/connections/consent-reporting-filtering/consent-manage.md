---
title: 管理同意報告和篩選設定
description: 瞭解如何檢視、編輯和刪除同意報告和篩選設定，以及同意原則查詢資料集如何在Customer Journey Analytics中保持同步。
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# 管理同意報告和篩選設定

在您[建立同意報告和篩選設定](/help/connections/consent-reporting-filtering/consent-configure.md)之後，您可以檢視、編輯或刪除它。

只有系統管理員可以管理同意報告和篩選設定。

如需概述資訊，請參閱[同意報告和篩選概述](/help/connections/consent-reporting-filtering/consent-overview.md)。

## 檢視現有設定

若要檢視現有的組態：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 同意報告和篩選]**。

   以下各欄提供各個設定的相關資訊：

   * **[!UICONTROL 建立者]**：建立組態的使用者。

   * **[!UICONTROL 沙箱]**：包含設定檔資料集的Experience Platform沙箱。

   * **[!UICONTROL Connection]**：套用組態的連線。

   * **[!UICONTROL 篩選]**：已啟用的篩選行銷動作（如果有的話）。

   * **[!UICONTROL 建立日期]**：組態建立的日期。

   * **[!UICONTROL 上次修改日期]**：上次修改組態的日期。

   * **[!UICONTROL 狀態]**：組態的狀態。

   您可以選取欄圖示![欄圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)，取消選取您要隱藏的任何欄，然後選取&#x200B;**[!UICONTROL 套用]**，以隱藏任何欄。

1. （選擇性）若要篩選設定清單，請選取&#x200B;**篩選** ![篩選圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然後依下列任一條件篩選：

   * **[!UICONTROL 連線]**

   * **[!UICONTROL 建立者]**

   * **[!UICONTROL 沙箱]**

   * **[!UICONTROL 狀態]**

## 編輯設定

>[!IMPORTANT]
>
>對篩選的變更只會影響在您儲存對設定的變更後擷取的資料。 啟用篩選功能不會移除變更前擷取的非同意訪客資料，而且停用篩選功能不會復原啟用篩選功能時所排除的資料。

編輯現有設定：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 同意報告和篩選]**。

1. 選取您要編輯的組態名稱。

   或

   選取您要編輯的組態旁邊的核取方塊，然後選取&#x200B;**[!UICONTROL 編輯]**。

1. 進行變更，然後選取&#x200B;**[!UICONTROL 儲存]**。

## 刪除設定

若要刪除現有組態，請執行下列動作：

1. 在Customer Journey Analytics中，選取&#x200B;**[!UICONTROL 資料管理]** > **[!UICONTROL 同意報告和篩選]**。

1. 選取您要刪除之組態旁的核取方塊，然後選取&#x200B;**[!UICONTROL 刪除]**。

## 同意原則查詢資料集如何保持同步

Customer Journey Analytics會自動使同意原則查詢資料集與Experience Platform保持同步。 在Experience Platform中建立、更新、重新命名或刪除同意原則時，查詢資料集中對應的原則名稱和說明就會更新。

請記住下列事項：

* 每個沙箱最多存在一個同意原則查詢資料集。 相同沙箱中的多個設定共用該查詢資料集。
* 由於原則名稱和說明來自Experience Platform，請更新Experience Platform中的原則中繼資料，而不是直接編輯查詢資料集。
