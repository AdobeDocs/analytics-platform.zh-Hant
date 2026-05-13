---
title: 缺乏權限
description: 了解如何疑難排解缺乏權限而導致的問題
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
TQID: https://experienceleague.adobe.com/XwJDsOhTuITeyXd9htSUUQb37KnPuxyR9Css0sEikA0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
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
