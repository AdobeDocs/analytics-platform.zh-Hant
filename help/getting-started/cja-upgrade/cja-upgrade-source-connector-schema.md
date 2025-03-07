---
title: 建立 Analytics 來源連接器的自訂結構描述
description: 瞭解如何建立Analytics來源聯結器的自訂結構描述
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fad62c04-b435-466a-ab3c-cf2d174ddbfb
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 23%

---

# 建立 Analytics 來源連接器的自訂結構描述 {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create-schema"
>title="建立 Analytics 來源連接器的結構描述"
>abstract="此結構描述是 Adobe Analytics ExperienceEvent 欄位群組，與構成您組織的自訂結構描述的所有欄位群組之組合。您可以將 Analytics 來源連接器使用的欄位對應至您組織的結構描述，並且僅用於歷史資料。<br><br>雖然本質上具有技術成分，但建立此結構描述可以在數小時內完成，如果您確切知道哪些欄位群組構成組織的自訂結構描述，則速度可能會更快。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 瞭解Analytics來源聯結器如何將歷史資料帶入Customer Journey Analytics

您可以使用Analytics來源聯結器將Adobe Analytics報告套裝資料匯入Adobe Experience Platform。 然後，這些資料即可用作Customer Journey Analytics中的歷史資料。

此程式假設您要[建立自訂結構描述，以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)使用，因為您想要根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化結構描述。

若要使用Analytics來源聯結器將歷史資料帶入Customer Journey Analytics，您需要：

1. 建立Analytics來源聯結器的自訂結構描述，如下所述。

1. 如果您還沒有Analytics來源聯結器，請[建立Analytics來源聯結器，並將欄位對應到您的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已有Analytics來源聯結器，請從來源聯結器[將欄位對應到您的XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [將 Analytics 來源連接器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 建立 Analytics 來源連接器的自訂結構描述

您應該已經[建立新的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，以便用於Experience Platform Web SDK實作，並與Customer Journey Analytics搭配使用。 此結構描述應包含您計畫收集資料之欄位的任何欄位群組。

您現在需要使用您網站SDK結構描述中的相同欄位群組，並將其新增至可與Analytics來源聯結器搭配使用的新結構描述。

Analytics來源聯結器的此結構描述必須包含：

* 在您為網頁SDK實作建立的自訂結構描述中包含的所有欄位群組（包括您建立的任何自訂欄位群組）。 (任何不屬於預設欄位群組的自訂欄位，都應作為自訂欄位群組的一部分新增到您的Web SDK結構描述中。)

* Adobe Analytics ExperienceEvent範本欄位群組

若要建立要與Analytics來源聯結器搭配使用的自訂結構描述：

1. 在Adobe Experience Platform中，開始建立新的自訂結構描述，如[建立自訂結構描述以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)中所述。

1. 新增您為網站SDK實作建立的結構描述中包含的所有欄位群組（包括任何自訂欄位群組）。

1. 新增完這些欄位群組後，請新增Adobe Analytics ExperienceEvent欄位群組：

   在&#x200B;**[!UICONTROL 欄位群組]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 新增]**&#x200B;以新增其他欄位群組。

   ![新增欄位群組至結構描述](assets/schema-add-field-group.png)

1. 搜尋並選取&#x200B;**[!UICONTROL Adobe Analytics ExperienceEvent範本]**&#x200B;欄位群組。

   ![新增Adobe Analytics ExperienceEvent欄位群組](assets/schema-experienceevent.png)

1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

{{upgrade-final-step}}
