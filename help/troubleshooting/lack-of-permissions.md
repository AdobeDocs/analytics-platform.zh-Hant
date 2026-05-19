---
title: 缺乏權限
description: 了解如何疑難排解缺乏權限而導致的問題
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
autotag-review: '2026-05-19T09:32:28.410Z'
TQID: 'https://experienceleague.adobe.com/qGrpX20MMcrjeEO75K2Ndoki4eiDmEvmaUCzED8jR1w'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 94%

---

# 缺乏權限

未具備特定 Adobe Experience Platform 權限時，Customer Journey Analytics 就無法正常運作。

例如，建立[連結](../connections/overview.md)和[資料視圖](../data-views/data-views.md)後，您可能會在「[元件](/help/data-views/create-dataview.md#components)」區段看到以下錯誤訊息：


>[!BEGINSHADEBOX]

*[!UICONTROL 擷取DULE原則時發生錯誤。 請驗證帳戶許可權、原則或標籤。 訊息：禁止。]*

>[!ENDSHADEBOX]


1. 確保您擁有正確的存取控制：

   * 您必須擁有具備 Experience Platform 產品之組織的系統或產品管理員權限。 請參閱[存取控制概觀](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions)，了解更多資訊。

   * 您必須是 AEP-Default-All-Users 產品設定檔中的使用者。 如果您沒有權限將自己新增到此設定檔，請詢問您的管理員。 請參閱[存取控制階層與工作流程](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow)，了解更多資訊。


1. 導覽至 Adobe Experience Platform UI。

1. 選取左邊欄的「**[!UICONTROL 權限]**」。

1. 選取「**[!UICONTROL 角色]**」。

1. 導覽至相關角色。

1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)「**[!UICONTROL 編輯]**」以編輯角色。

1. 確保「**[!UICONTROL 管理資料使用政策]**」和「**[!UICONTROL 檢視資料使用政策]**」已新增到「**[!UICONTROL 資料治理]**」容器。

1. 選取「**[!UICONTROL 儲存]**」以儲存變更。
