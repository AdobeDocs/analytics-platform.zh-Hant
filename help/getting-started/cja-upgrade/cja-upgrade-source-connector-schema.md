---
title: 為Analytics來源聯結器建立XDM結構描述
description: 瞭解如何為Analytics來源聯結器建立XDM結構描述
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 8e51e97b0616a5406c5c3a29431fde87a551ab9f
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 2%

---

# 為Analytics來源聯結器建立XDM結構描述

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

您應該已經[為您的Experience Platform Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)建立了新的XDM結構描述，以便與Customer Journey Analytics搭配使用。 此結構描述應包含您計畫收集資料之欄位的任何欄位群組。

除了您已為Web SDK實作建立的XDM結構描述外，您現在需要建立第二個XDM結構描述以與Analytics來源聯結器搭配使用，以將歷史資料帶入Customer Journey Analytics。

此第二個結構描述必須包含：

* 您在為Web SDK實作建立的結構描述中包含的所有欄位群組（包括任何自訂欄位群組）。 （任何不屬於預設欄位群組的自訂欄位，都應作為自訂欄位群組的一部分新增到您的Web SDK結構描述中。）

* Adobe Analytics ExperienceEvent範本欄位群組

若要建立要與Analytics來源聯結器搭配使用的XDM結構描述：

1. 在Adobe Experience Platform中，開始建立新的XDM結構描述，如[建立XDM結構描述以與Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)搭配使用。

1. 新增您在為Web SDK實作建立的結構描述中包含的所有欄位群組（包括任何自訂欄位群組）。

1. 新增完這些欄位群組後，請新增Adobe Analytics ExperienceEvent欄位群組：

   在&#x200B;**[!UICONTROL 欄位群組]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 新增]**&#x200B;以新增其他欄位群組。

   ![新增欄位群組至結構描述](assets/schema-add-field-group.png)

1. 搜尋並選取&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent範本]**&#x200B;欄位群組。

   ![新增Adobe Analytics ExperienceEvent欄位群組](assets/schema-experienceevent.png)

1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

