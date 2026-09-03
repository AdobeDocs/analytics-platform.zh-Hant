---
title: Customer Journey Analytics連線總覽
description: 了解 Customer Journey Analytics 中的連線。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
autotag-review: '2026-05-19T08:50:38.470Z'
TQID: 'https://experienceleague.adobe.com/bD6BGFGwJkHr3w4GYXoOCVH2l49csOvsaYLgqTAL41I'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 294
ht-degree: 88%

---

# 連線概觀

Customer Journey Analytics 產品管理員可透過連線，定義要攝取的 [!DNL &#x200B; Experience Platform] 資料來源，例如事件、查詢、輪廓和摘要資料集。 連線是 Customer Journey Analytics 的基礎，並決定哪些可用的資料 (欄位) 能在[資料視圖](/help/data-views/data-views.md)中被定義為維度或量度。

>[!IMPORTANT]
>
>您可以將多個 [!DNL Experience Platform] 資料集合併到單一連線中。


## 連線工作流程

![連線工作流程](assets/connection-workflow.png)

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [連線至資料來源](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/connections/connecting-customer-journey-analytics-to-data-sources-in-platform){target="_blank"}。

>[!ENDSHADEBOX]

概略上，連線工作流程可讓您：

| 介面 | 說明 |
|:---:|---|
| ➊ | [從連線管理器管理您的 Customer Journey Analytics &#x200B;](manage-connections.md)連線和整體使用情況。 |
| ➋ | [檢查連線的詳細資訊](manage-connections.md#connection-details)，例如攝取、略過或刪除的資料集記錄。 |
| ➌ | [建立或編輯連線的設定](create-connection.md#create-or-edit-a-connection)，例如滾動式資料時間範圍、要使用的沙箱、哪些資料集是連線的一部分等等。 |
| ➍ | [將資料集新增至連線](create-connection.md#add-datasets)。 您的連線應該至少有一個事件或摘要資料集，但可包含各種事件、輪廓、查詢和摘要資料集。 |
| ➎ | 對您新增的資料集[配置設定](create-connection.md#dataset-settings)。 您可以根據共同的個人識別碼或 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 帳戶識別碼來決定如何連結不同的資料集。 |
| ➏ | [編輯現有資料集的設定](create-connection.md#edit-a-dataset)。 您隨時可以在後續階段重新檢視資料集設定。 |



## 存取控制

連線管理的存取權應僅限於核心管理群組。 連線設定對於引入 Customer Journey Analytics 的資料量分配具有合約影響。

>[!MORELIKETHIS]
>
>[存取控制](/help/technotes/access-control.md)。

