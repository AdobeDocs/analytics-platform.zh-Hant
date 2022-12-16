---
title: 預估及管理CJA使用量
description: 顯示兩種估計使用的方法和一種管理使用的方法。
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 68%

---


# 預估及管理CJA使用量

若要了解您的CJA使用方式，您可以使用2種方法：

* 為每個連線新增事件資料(請參閱 **估計連接大小** 以下)
* 使用Analysis Workspace...

若要管理CJA使用情形：

* 使用CJA API

## 估算連線規模 {#estimate-size}

您可能需要知道目前有多少列事件資料 [!UICONTROL Customer Journey Analytics]. 為了準確說明組織的事件資料記錄 (資料列) 使用情況，請&#x200B;**為您組織所建立的每個連線執行以下操作**。

>[!NOTE]
>
>請在每個月的第一個星期五執行此動作，因為Adobe會在當天執行您的最新使用情況報表。

1. 在 [!UICONTROL Customer Journey Analytics] 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

   現在，您可以查看所有目前連線的清單。

1. 按一下每個連線名稱，以取得「連線管理員」。

1. 將適用於所有已建立連線的&#x200B;**[!UICONTROL 可用事件資料記錄筆數]**&#x200B;相加。 (視連線規模而定，筆數可能需要一段時間才會顯示。)

   ![事件資料](assets/event-data.png)

1. 取得所有事件資料列的總和後，請查閱您公司與 Adobe 所簽訂 Customer Journey Analytics 合約中的「資料列」權利。

   這項資料可為您提供「銷售訂單」中授權的最大資料列筆數。 如果從步驟 3 所得的資料列筆數大於此筆數，表示您有超額情形。

1. 為了解決這種情況，您有幾個選擇：

   * 變更您的[資料保留設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#set-rolling-window-for-connection-data-retention)。
   * [刪除任何未使用的連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * [刪除 AEP 中的資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * 聯絡您的 Adobe 客戶經理，請他們授權額外的容量。
