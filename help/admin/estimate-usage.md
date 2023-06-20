---
title: 檢視和管理 Customer Journey Analytics 使用情況
description: 顯示兩種估計使用情況的方法，以及一種管理使用情況的方法。
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 72%

---

# 檢視和管理 Customer Journey Analytics 使用情況

若要檢視您的Customer Journey Analytics使用情況，您可以使用數種方法：

* 為每個連線新增事件資料列。請參閱下方的[估計連線規模] (#估計規模)。透過這個簡單的方式，您就可以依照連線查看特定時間戳記的事件列資料。
* 透過三種方式檢視您的使用情況，其中各項將於下文詳細說明：
   * 使用 Analysis Workspace 報告上個月的事件。
   * 使用 Report Builder 報告上個月的事件。
   * 使用Customer Journey Analytics API建立自動化報表。

若要管理您的Customer Journey Analytics使用量：

* 定義滾動資料時間窗口。

## 估算連線規模 {#estimate-size}

您可能需要知道目前 [!UICONTROL Customer Journey Analytics] 中有多少列事件資料。為了準確說明組織的事件資料記錄 (資料列) 使用情況，請&#x200B;**為您組織所建立的每個連線執行以下操作**。

>[!NOTE]
>
>請在每個月的第一個星期五執行此動作，因為 Adobe 會在當天執行您的最新使用情況報告。

1. 在 [!UICONTROL Customer Journey Analytics] 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

   現在，您可以查看所有目前連線的清單。

1. 按一下每個連線名稱，以取得「連線管理員」。

1. 將適用於針對您組織建立的每個連線的&#x200B;**[!UICONTROL 可用事件資料記錄筆數]**&#x200B;相加。(視連線規模而定，筆數可能需要一段時間才會顯示。)

   ![事件資料](./assets/event-data.png)

   >[!CAUTION]
   >
   >   此計數僅適用於事件資料，不適用於設定檔或查詢資料。如果您有設定檔和查閱資料，則計數會稍高。不過，目前無法報告使用者介面中的設定檔和查閱資料使用情形。這項功能預定於 2023 年推出。

1. 取得所有事件資料列的總和後，請查閱您公司與 Adobe 所簽訂 Customer Journey Analytics 合約中的「資料列」權利。

   這項資料可為您提供「銷售訂單」中授權的最大資料列筆數。如果從步驟 3 所得的資料列筆數大於此筆數，表示您有超額情形。

1. 為了解決這種情況，您有幾個選擇：

   * 變更您的[資料保留設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#set-rolling-window-for-connection-data-retention)。
   * [刪除任何未使用的連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * [刪除Adobe Experience Platform中的資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components).
   * 請聯絡您的Adobe客戶團隊，以授權額外的容量。

## 使用所有事件資料建立工作區專案 {#workspace-event-data}

此方法可讓您對使用資料以及使用的歷史記錄進行更深入的分析。

1. 在工作區中建立專案之前，為您的每個連線[建立資料檢視](/help/data-views/create-dataview.md)，而不套用任何篩選器。

>[!WARNING]
>
>    請勿僅為了測量使用情況而建立包含所有資料的新連線，因為這實際上會使您的使用量增加一倍。

1. 在工作區中，根據每個資料檢視建立新專案，並提取所有事件(從 **[!UICONTROL 量度]** 下拉式清單)，從目前的Customer Journey Analytics合約的第一天開始，進入當月第一個星期五。

   ![事件](./assets/events-usage.png)

   這可讓您清楚了解使用量的每月趨勢。

1. 您可以根據需求，依資料集等深入研究。

## 在 Report Builder 中建立資料區塊 {#arb}

在 Report Builder 中，為每個資料檢視[建立一個資料區塊](/help/report-builder/create-a-data-block.md)，然後加總。

## 在Customer Journey Analytics API中建立自動化報表 {#api-report}

1. 使用 [Customer Journey Analytics報告API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) 若要針對所有事件資料執行報表， **用於每個連線**. 設定此設定，以便執行報告

   * 每個月的第一個星期五。
   * 回到您目前Customer Journey Analytics合約的第一天。

   這可讓您清楚了解使用量的每月趨勢。它會提供您所有Customer Journey Analytics連線上的總列數。

1. 使用 Excel 進一步自訂此報告。

## 定義滾動資料時間窗口以管理您的使用情況 {#rolling}

若要管理您的使用狀況，請 [連線UI](/help/connections/create-connection.md) 可讓您在連線層級將Customer Journey Analytics資料保留定義為單位為月數的滾動時段（1個月、3個月、6個月等）。

主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。

如果您保留預設值 (未勾選)，保留期間將由 Adobe Experience Platform 資料保留設定取代。如果您的Experience Platform中有25個月的資料，則Customer Journey Analytics會透過回填取得25個月的資料。 如果您在Platform中刪除其中10個月，Customer Journey Analytics將保留剩餘15個月。

資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此基本資料或查詢資料集不存在滾動資料時間窗口設定。如果您的連線包含任何設定檔或查詢資料集，由於它們是以事件資料集連結，因此會根據事件資料集時間戳記上的資料保留設定，在Customer Journey Analytics中保留資料。

