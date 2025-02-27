---
title: 建立查詢資料集來將 Customer Journey Analytics 的資料分類
description: 瞭解如何建立查詢資料集，以便在Customer Journey Analytics中分類資料
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 10%

---

# 建立查詢資料集來將 Customer Journey Analytics 的資料分類 {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="針對包含分類資料的每個維度建立查詢資料集"
>abstract="查詢資料集與 Adobe Analytics 中的分類資料類似，是在 Customer Journey Analytics 中進行資料分類的方法。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

查詢資料集與 Adobe Analytics 中的分類資料類似，是在 Customer Journey Analytics 中進行資料分類的方法。

使用Analytics來源聯結器時，某些標準查詢資料集會在報告時自動套用。 如需詳細資訊，請參閱[將標準查詢新增至資料集](/help/connections/standard-lookups.md)。

若要在使用Customer Journey Analytics Web SDK時分類Experience Platform中的資料，您需要為包含您要分類之資料的每個維度建立自訂結構描述和查詢資料集。

## 建立自訂結構描述以搭配查詢資料集使用

針對包含您要在Customer Journey Analytics中分類之資料的每個維度，建立新的自訂結構描述。 當您在稍後步驟中建立查詢資料集時，它將參考此結構描述。

針對包含您要分類之資料的每個維度，重複此程式。

若要建立結構描述以與Customer Journey Analytics中的查詢資料集搭配使用：

1. 在Adobe Experience Platform中，選取左側邊欄中&#x200B;**[!UICONTROL 資料管理]**&#x200B;區段中的&#x200B;**[!UICONTROL 結構描述]**。

1. 選取&#x200B;**[!UICONTROL 建立結構描述]**。

   ![建立結構描述按鈕](assets/schema-create.png)

1. 選取&#x200B;**[!UICONTROL 手動]**。 這可讓您手動新增欄位和欄位群組到您的結構描述。 選擇&#x200B;**[!UICONTROL 選取]**&#x200B;以繼續建立精靈的下一頁。

1. 在&#x200B;**[!UICONTROL 結構描述詳細資料]**&#x200B;頁面上，選取&#x200B;**[!UICONTROL 其他]**，然後選取&#x200B;**[!UICONTROL 自訂]**。

   ![建立自訂](assets/schema-custom.png)

1. 選取&#x200B;**[!UICONTROL 建立類別]**。

   <!-- add screenshot -->

1. 在&#x200B;**[!UICONTROL 建立類別]**&#x200B;對話方塊中，指定結構描述的名稱和描述，選取&#x200B;**[!UICONTROL 記錄]**，然後選取&#x200B;**[!UICONTROL 建立]**。

1. 繼續進行[建立查詢資料集](#create-a-lookup-dataset)。

## 建立查詢資料集

在您[建立自訂結構描述](#create-a-custom-schema-to-use-with-the-lookup-dataset)以用於查詢資料集之後，您需要建立查詢資料集並將其對應到您的結構描述。

針對包含您要分類之資料的每個維度，重複此程式。

若要建立查詢資料集以與Customer Journey Analytics中的結構描述搭配使用：

>[!NOTE]
>
>以下程式會使用CSV檔案來建立資料集。 您也可以使用任何其他可將資料匯入Experience Platform的方法，例如設定資料串流。

1. 在Adobe Experience Platform中，選取左側邊欄中的&#x200B;**[!UICONTROL 工作流程]**。

   ![建立自訂](assets/lookup-dataset-workflows.png)

1. 選取&#x200B;**[!UICONTROL 將CSV對應至XDM結構描述]**，然後選取&#x200B;**[!UICONTROL 啟動]**。

1. 在&#x200B;**[!UICONTROL 資料集詳細資料]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 新資料集]**。

1. 指定資料集的名稱和說明。

1. 在&#x200B;**[!UICONTROL 結構描述]**&#x200B;欄位中，選取您為查詢資料集建立的結構描述，如[為查詢資料集建立結構描述](#create-a-schema-for-lookup-datasets)中所述。

1. 選取&#x200B;**[!UICONTROL 「下一步」]**。

1. 在&#x200B;**[!UICONTROL 將CSV對應至XDM結構描述頁面]**&#x200B;上，在&#x200B;**[!UICONTROL 上傳檔案]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 選擇檔案]**，然後瀏覽檔案系統，尋找包含您要套用分類資料之維度之分類資訊的檔案。 例如，這可以是列出欄位ID與對應欄位名稱的試算表。<!-- correct? How can I better explain what this file is?-->

   ![對應CSV檔案](assets/lookup-map-csv.png)

1. 選取&#x200B;**[!UICONTROL 下一步]**

1. 檔案上傳後，請檢閱對應以確定其正確性。 CSV檔案的欄列在&#x200B;**[!UICONTROL Source資料]**&#x200B;下，其對應的XDM結構描述欄位列在&#x200B;**[!UICONTROL 目標欄位]**&#x200B;下。

   Platform會根據您選取的目標結構或資料集，自動提供智慧型建議給自動對應的欄位。 您可以手動調整對應規則以符合您的使用案例。

   如需對應程式的詳細資訊，請參閱Experience Platform檔案中的[將CSV檔案對應到現有的XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)。

1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 繼續[在Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics)中將查詢資料集新增到您的連線。

## 將查詢資料集新增至您在Customer Journey Analytics中的連線

在您[建立自訂結構描述](#create-a-custom-schema-to-use-with-the-lookup-dataset)並[建立查詢資料集](#create-a-lookup-dataset)後，您需要在Customer Journey Analytics中將查詢資料集新增到您的連線。

針對包含您要分類之資料的每個維度，重複此程式。

若要將查詢資料集新增至您在Customer Journey Analytics中的連線：

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

1. 選取您要新增查詢資料集的連線旁的![更多圖示](assets/More.svg)，然後選取&#x200B;**[!UICONTROL 編輯]**。

   <!-- add screenshot -->

1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

1. 在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;對話方塊中，選取您建立的查詢資料集，然後選取&#x200B;**[!UICONTROL 下一步]**。

1. 在&#x200B;**[!UICONTROL 人員ID]**&#x200B;欄位中，從您在Experience Platform中設定的資料集結構描述中定義的可用身分中選取人員ID。<!-- fill out other fields? -->

1. 選取&#x200B;**[!UICONTROL 新增資料集]**，然後選取&#x200B;**[!UICONTROL 儲存]**。

   <!-- is there a step right in between here where you select the dataset -->

1. 使用&#x200B;**[!UICONTROL 索引鍵]**&#x200B;欄位和&#x200B;**[!UICONTROL 相符的索引鍵]**&#x200B;欄位，在您的查詢資料集中的欄位與事件或摘要資料集中的欄位之間建立關聯。

1. 在Customer Journey Analytics中將所有查詢資料集新增到您的連線後，請繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

