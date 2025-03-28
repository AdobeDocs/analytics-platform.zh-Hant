---
title: 建立 Analytics 來源連接器和對應欄位
description: 瞭解如何建立Analytics來源聯結器和對應欄位
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f96565a2-f556-4b45-b88e-984613614d2e
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 24%

---

# 建立 Analytics 來源連接器和對應欄位 {#create-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-create"
>title="建立 Analytics 來源連接器"
>abstract="使用 Analytics 來源連接器攝取報告套裝資料，以便在 Customer Journey Analytics 中使用。<br><br>使用預設設定建立 Analytics 來源連接器只需幾分鐘。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-map-fields"
>title="建立 Analytics 來源連接器和對應結構描述欄位"
>abstract="來源連接器需要知道如何將 Adobe Analytics 欄位對應至您組織的結構描述。使用此介面為來源連接器提供該對應。此步驟是新增歷史資料至 Customer Journey Analytics 的環節之一。<br><br>此步驟所需時間在很大程度上取決於您必須對應的維度和量度的數量。此步驟並不困難，但是它十分繁瑣且重複性高。預計資料流對應大約需要一週的時間才能完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 瞭解Analytics來源聯結器如何將歷史資料帶入Customer Journey Analytics

您可以使用Analytics來源聯結器將Adobe Analytics報告套裝資料匯入Adobe Experience Platform。 然後，這些資料即可用作Customer Journey Analytics中的歷史資料。

此程式假設您要[建立自訂結構描述，以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)使用，因為您想要根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化結構描述。

若要使用Analytics來源聯結器將歷史資料帶入Customer Journey Analytics，您需要：

1. [建立 Analytics 來源連接器的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 如果您還沒有Analytics來源聯結器，請建立Analytics來源聯結器，並將欄位對應至您的自訂Web SDK結構描述，如下所述。

   或

   如果您已有Analytics來源聯結器，請從來源聯結器[將欄位對應到您的自訂Web SDK結構描述](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. [將 Analytics 來源連接器資料集新增至連線](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)

## 建立 Analytics 來源連接器和對應欄位

在建立自訂結構描述後，您需要建立Adobe Analytics來源聯結器以用於歷史資料。 (如需建立來源聯結器的更完整的一般准則，請參閱[在UI中建立Adobe Analytics來源連線](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hant)。)

若要建立用於歷史資料的Adobe Analytics來源聯結器：

1. 在Platform UI的左側邊欄中，選取&#x200B;**[!UICONTROL 連線]**&#x200B;區段中的&#x200B;**[!UICONTROL 來源]**。

1. 從 [!UICONTROL 「類別」]清單中選取 **[!UICONTROL Adobe 應用程式]**。

1. 在Adobe Analytics動態磚中選取&#x200B;**[!UICONTROL 新增資料]**。

   ![已選取來源的Adobe Experience Platform視窗，同時反白顯示Adobe應用程式和新增資料。](./assets/sources-overview.png)

1. 選取&#x200B;**[!UICONTROL 報表套裝]**，然後從報表套裝清單中，選取包含您要在Customer Journey Analytics中使用的歷史資料的報表套裝。

   顯示報告套裝清單的![Adobe Experience Platform視窗](./assets/report-suites.png)

1. 選取畫面右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 選取&#x200B;**[!UICONTROL 自訂結構描述]**，然後選取您在[中建立的結構描述。建立包含Adobe Analytics欄位群組的自訂結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)。<!-- Deleted this, because I changed this from choosing the default schemawe're pointing them now at the schema they just created: "Adobe Experience Platform  automatically creates the schema and the corresponding dataset to map all standard fields from the selected Adobe Analytics report suite." -->

   <!-- add screenshot -->

1. 將每個Adobe Analytics維度對應至自訂結構描述維度。

   1. 在&#x200B;**[!UICONTROL 對應標準欄位]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 自訂]**&#x200B;索引標籤。

   1. 選取&#x200B;**[!UICONTROL 新增對應]**。

   ![對應結構描述欄位](assets/schema-mapping.png)

   1. 在&#x200B;**[!UICONTROL Source欄位]**&#x200B;中，從Adobe Analytics ExperienceEvent範本欄位群組中選取Adobe Analytics欄位。 然後，在&#x200B;**[!UICONTROL 目標欄位]**&#x200B;中，在XDM結構描述中選取您要將它對應到的自訂欄位。

      由於Adobe Analytics和XDM之間的固有架構差異，並非所有AppMeasurement欄位在XDM中都擁有對應的欄位。

   1. 為您在Adobe Analytics中用來收集資料的Adobe Analytics ExperienceEvent範本欄位群組中的每個欄位重複此程式。

1. 選取畫面右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 為資料流命名，並 (可選) 提供說明。

   ![Adobe Experience Platform視窗醒目提示資料流詳細資料區段](./assets/dataflow-detail.png)

1. 選取畫面右上角的&#x200B;**[!UICONTROL 下一步]**。

1. 檢閱連線，然後選取&#x200B;**[!UICONTROL 完成]**。

   ![Adobe Experience Platform視窗醒目提示要檢閱的連線和資料型別區段](./assets/review.png)

   建立連線後，系統會自動建立資料流，以使用報表套裝中的Adobe Analytics資料填入資料集。 此資料流會擷取最多13個月的生產沙箱歷史資料。 非生產沙箱中的回填限製為三個月。

   如果您使用Analytics來源聯結器將歷史資料帶入Customer Journey Analytics Web SDK實作，則需要將此自動建立的資料集新增至您為Web SDK實作建立的連線。

{{upgrade-final-step}}
