---
title: 預估及管理CJA使用量
description: 顯示兩種估計使用的方法和一種管理使用的方法。
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 42%

---


# 預估及管理CJA使用量

若要了解您的CJA使用方式，您可以使用2種方法：

* 為每個連線新增事件資料列。 (請參閱 **估計連接大小** 以下)
* 使用Analysis Workspace來報告上個月的事件。 (請參閱 **使用所有事件資料建立工作區專案** 在下面。)

若要管理CJA使用情形：

* 使用CJA API。 (請參閱 **在CJA API中建立報表** 在下面。)

## 估算連線規模 {#estimate-size}

您可能需要知道目前有多少列事件資料 [!UICONTROL Customer Journey Analytics]. 為了準確說明組織的事件資料記錄 (資料列) 使用情況，請&#x200B;**為您組織所建立的每個連線執行以下操作**。

>[!NOTE]
>
>請在每個月的第一個星期五執行此動作，因為Adobe會在當天執行您的最新使用情況報表。

1. 在 [!UICONTROL Customer Journey Analytics] 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

   現在，您可以查看所有目前連線的清單。

1. 按一下每個連線名稱，以取得「連線管理員」。

1. 將 **[!UICONTROL 可用事件資料的記錄]** 針對您的組織建立的每個連線。 (視連線規模而定，筆數可能需要一段時間才會顯示。)

   ![事件資料](assets/event-data.png)

   >[!CAUTION]
   >
   >   此計數僅適用於事件資料，不適用於設定檔或查詢資料。 如果您有設定檔和查閱資料，則計數會稍高。 不過，目前無法報告使用者介面中的設定檔和查閱資料使用情形。 這項功能預定於2023年推出。

1. 取得所有事件資料列的總和後，請查閱您公司與 Adobe 所簽訂 Customer Journey Analytics 合約中的「資料列」權利。

   這項資料可為您提供「銷售訂單」中授權的最大資料列筆數。 如果從步驟 3 所得的資料列筆數大於此筆數，表示您有超額情形。

1. 為了解決這種情況，您有幾個選擇：

   * 變更您的[資料保留設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#set-rolling-window-for-connection-data-retention)。
   * [刪除任何未使用的連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * [刪除 AEP 中的資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * 聯絡您的 Adobe 客戶經理，請他們授權額外的容量。

## 使用所有事件資料建立工作區專案 {#workspace-event-data}

1. 在工作區中建立專案之前， [建立資料檢視](/help/data-views/create-dataview.md) 會從「所有」連線提取資料，且未套用篩選器。 換句話說，它會包含您的所有資料。

1. 在工作區中，建立新專案並拉入所有事件(從 **[!UICONTROL 量度]** 下拉式清單)。

   ![事件](assets/events-usage.png)

1. 做這個

## 在CJA API中建立報表 {#api-report}

使用 [CJA報表API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 執行所有事件資料的報表。