---
title: Customer Journey Analytics連線總覽
description: 了解 Customer Journey Analytics 中的連線。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 97%

---

# 連線概觀

Customer Journey Analytics 產品管理員可透過連線，定義要攝取的 [!DNL &#x200B; Experience Platform] 資料來源，例如事件、查詢、輪廓和摘要資料集。連線是 Customer Journey Analytics 的基礎，並決定哪些可用的資料 (欄位) 能在[資料視圖](/help/data-views/data-views.md)中被定義為維度或量度。

>[!IMPORTANT]
>
>您可以將多個 [!DNL Experience Platform] 資料集合併到單一連線中。


## 連線工作流程

![連線工作流程](assets/connection-workflow.png)

<!-- Outdated interface 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/v/35111/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

概略上，連線工作流程可讓您：

| 介面 | 說明 |
|:---:|---|
| ➊ | [從連線管理器管理您的 Customer Journey Analytics &#x200B;](manage-connections.md)連線和整體使用情況。 |
| ➋ | [檢查連線的詳細資訊](manage-connections.md#connection-details)，例如攝取、略過或刪除的資料集記錄。 |
| ➌ | [建立或編輯連線的設定](create-connection.md#create-or-edit-a-connection)，例如滾動式資料時間範圍、要使用的沙箱、哪些資料集是連線的一部分等等。 |
| ➍ | [將資料集新增至連線](create-connection.md#add-datasets)。您的連線應該至少有一個事件或摘要資料集，但可包含各種事件、輪廓、查詢和摘要資料集。 |
| ➎ | 對您新增的資料集[配置設定](create-connection.md#dataset-settings)。您可以根據共同的個人識別碼或 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 帳戶識別碼來決定如何連結不同的資料集。 |
| ➏ | [編輯現有資料集的設定](create-connection.md#edit-a-dataset)。您隨時可以在後續階段重新檢視資料集設定。 |



## 存取控制

連線管理的存取權應僅限於核心管理群組。連線設定對於引入 Customer Journey Analytics 的資料量分配具有合約影響。

>[!MORELIKETHIS]
>
>[存取控制](/help/technotes/access-control.md)。

