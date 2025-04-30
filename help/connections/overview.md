---
title: Customer Journey Analytics 連線概觀
description: 了解 Customer Journey Analytics 中的連線。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 836c793ae74185728af03636b0ba3e838f46f05d
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---

# 連線概觀

連線可讓Customer Journey Analytics產品管理員建立與不同[!DNL  Experience Platform]資料來源（例如事件、查詢、設定檔及摘要資料集）的連線。 這些連線可整合從連線到衍生資料檢視的資料。 連線是Customer Journey Analytics的基礎，是從[!DNL Experience Platform]來源資料集建立的。

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

在概覽中，「連線」工作流程可讓您：

| 介面 | 說明 |
|:---:|---|
| ➊URL | [從連線管理員管理您的連線和Customer Journey Analytics的整體使用量](manage-connections.md)。 |
| ➋URL | [檢查連線的詳細資料](manage-connections.md#connection-details)，例如擷取、略過或刪除的資料集記錄。 |
| ➌URL | [建立或編輯連線的設定](create-connection.md#create-or-edit-a-connection)，例如滾動資料視窗、要使用的沙箱、連線中的資料集等等。 |
| ➍URL | [新增資料集至連線](create-connection.md#add-datasets)。 您的連線應至少有一個事件或摘要資料集，但可包含各種事件、設定檔、查詢和摘要資料集。 |
| ➎URL | [為您新增的資料集設定設定](create-connection.md#dataset-settings)。 您可以根據常見的以人員為基礎的識別碼或[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}以帳戶為基礎的識別碼，決定如何連結不同的資料集。 |
| ➏URL | [編輯現有資料集的設定](create-connection.md#edit-a-dataset)。 您稍後一律可以重新造訪資料集設定。 |



## 存取控制

連線管理的存取權應限制在核心管理群組。 連線設定對帶入Customer Journey Analytics的資料分配數量有合約影響。

>[!MORELIKETHIS]
>
>[存取控制](/help/technotes/access-control.md)。

