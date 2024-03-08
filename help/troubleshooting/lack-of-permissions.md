---
title: 缺少許可權
description: 瞭解如何疑難排解缺少許可權所導致的問題
role: Admin
solution: Customer Journey Analytics
feature: Troubleshooting
exl-id: 341123b9-f4d6-4ef7-96f1-789850261b96
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# 缺少許可權

若未設定某些Adobe Experience Platform許可權，Customer Journey Analytics就無法正常運作。

例如，建立 [連線](../connections/overview.md) 和 [資料檢視](../data-views/data-views.md)，您可能會在 [元件](/help/data-views/create-dataview.md#components) 區段：


>[!BEGINSHADEBOX]

*[!UICONTROL 擷取DULE原則時發生錯誤。請驗證帳戶許可權、原則或標籤。 訊息：已禁止。]*

>[!ENDSHADEBOX]


1. 確定您擁有正確的存取控制：

   * 您必須擁有擁有Experience Platform產品的組織的系統或產品管理員許可權。 另請參閱 [存取控制總覽](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#platform-permissions) 以取得詳細資訊。

   * 您必須是AEP-Default-All-Users產品設定檔中的使用者。 如果您沒有將您自己新增至此設定檔的許可權，請詢問您的管理員。 另請參閱 [存取控制階層與工作流程](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html#access-control-hierarchy-and-workflow) 以取得詳細資訊。


1. 導覽至AdobeExperience Platform UI。

1. 選取 **[!UICONTROL 許可權]** 從左側邊欄。

1. 選取 **[!UICONTROL 角色]**.

1. 導覽至相關角色。

1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]** 以編輯角色。

1. 確定 **[!UICONTROL 管理資料使用原則]** 和 **[!UICONTROL 檢視資料使用原則]** 新增至 **[!UICONTROL 資料控管]** 容器。

1. 選取 **[!UICONTROL 儲存]** 以儲存變更。
