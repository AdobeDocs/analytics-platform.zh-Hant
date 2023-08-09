---
title: 缺少許可權
description: 瞭解如何疑難排解缺少許可權所導致的問題
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 84a1cd485110be23b1977d916fc39e058b370066
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# 缺少許可權

若未設定某些Adobe Experience Platform許可權，Customer Journey Analytics就無法正常運作。

例如，建立 [連線](../connections/overview.md) 和 [資料檢視](../data-views/data-views.md)，您可能會在 [元件](/help/data-views/create-dataview.md#components) 區段：


>[!BEGINSHADEBOX]

*[!UICONTROL 發生錯誤，我們無法載入結構描述欄位。請重試。]*

>[!ENDSHADEBOX]


若要更正此錯誤，您必須擁有擁有Experience Platform產品的組織的系統或產品管理員許可權。 另請參閱 [存取控制總覽](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) 以取得詳細資訊。

1. 導覽至Adobe Experience Platform UI。

1. 選取 **[!UICONTROL 許可權]** 從左側邊欄。

1. 選取 **[!UICONTROL 角色]**.

1. 導覽至相關角色。

1. 選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 編輯]** 以編輯角色。

1. 確定 **[!UICONTROL 管理資料使用原則]** 和 **[!UICONTROL 檢視資料使用原則]** 新增至 **[!UICONTROL 資料控管]** 容器。

1. 選取 **[!UICONTROL 儲存]** 以儲存變更。


