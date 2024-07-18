---
title: 缺乏權限
description: 了解如何疑難排解缺乏權限而導致的問題
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# 缺乏權限

未具備特定 Adobe Experience Platform 權限時，Customer Journey Analytics 就無法正常運作。

例如，建立[連結](../connections/overview.md)和[資料視圖](../data-views/data-views.md)後，您可能會在「[元件](/help/data-views/create-dataview.md#components)」區段看到以下錯誤訊息：


>[!BEGINSHADEBOX]

*[!UICONTROL 擷取 DULE 原則時發生錯誤。請驗證帳戶權限、原則或標籤。訊息：禁止。]*

>[!ENDSHADEBOX]


1. 確保您擁有正確的存取控制：

   * 您必須擁有具備 Experience Platform 產品之組織的系統或產品管理員權限。請參閱[存取控制概觀](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions)，了解更多資訊。

   * 您必須是 AEP-Default-All-Users 產品設定檔中的使用者。如果您沒有權限將自己新增到此設定檔，請詢問您的管理員。請參閱[存取控制階層與工作流程](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow)，了解更多資訊。


1. 導覽至 Adobe Experience Platform UI。

1. 選取左邊欄的「**[!UICONTROL 權限]**」。

1. 選取「**[!UICONTROL 角色]**」。

1. 導覽至相關角色。

1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)「**[!UICONTROL 編輯]**」以編輯角色。

1. 確保「**[!UICONTROL 管理資料使用政策]**」和「**[!UICONTROL 檢視資料使用政策]**」已新增到「**[!UICONTROL 資料治理]**」容器。

1. 選取「**[!UICONTROL 儲存]**」以儲存變更。
