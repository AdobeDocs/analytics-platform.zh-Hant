---
title: 建立 Analytics 來源連接器的 XDM 結構描述
description: 瞭解如何為Analytics來源聯結器建立XDM結構描述
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 8%

---

# 建立 Analytics 來源連接器的 XDM 結構描述

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

## 瞭解Analytics來源聯結器如何將歷史資料帶入Customer Journey Analytics

您可以使用Analytics來源聯結器將Adobe Analytics報告套裝資料匯入Adobe Experience Platform。 然後，這些資料即可用作Customer Journey Analytics中的歷史資料。

此程式假設您要在升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)時[建立XDM結構描述，因為您想要根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化結構描述。

若要使用Analytics來源聯結器將歷史資料帶入Customer Journey Analytics，您需要：

1. 建立Analytics來源聯結器的XDM結構描述，如下所述。

1. 如果您還沒有Analytics來源聯結器，請[建立Analytics來源聯結器，並將欄位對應到您的XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已有Analytics來源聯結器，請從來源聯結器[將欄位對應到您的XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [將 Analytics 來源連接器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 建立 Analytics 來源連接器的 XDM 結構描述

您應該已經[為您的Experience Platform Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)建立了新的XDM結構描述，以便與Customer Journey Analytics搭配使用。 此結構描述應包含您計畫收集資料之欄位的任何欄位群組。

您現在需要使用您Web SDK結構描述中的相同欄位群組，並將其新增至可與Analytics來源聯結器搭配使用的新結構描述。

Analytics來源聯結器的此結構描述必須包含：

* 您在自訂結構描述中為Web SDK實作建立的所有欄位群組（包括您建立的任何自訂欄位群組）。 （任何不屬於預設欄位群組的自訂欄位，都應作為自訂欄位群組的一部分新增到您的Web SDK結構描述中。）

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
