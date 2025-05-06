---
title: 建立查詢資料集來將 Customer Journey Analytics 的資料分類
description: 了解如何建立查詢資料集來將 Customer Journey Analytics 的資料分類
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: ht
source-wordcount: '806'
ht-degree: 100%

---

# 建立查詢資料集將 Customer Journey Analytics 的資料分類 {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="針對包含分類資料的每個維度建立查詢資料集"
>abstract="查詢資料集與 Adobe Analytics 中的分類資料類似，是在 Customer Journey Analytics 中進行資料分類的方法。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

查詢資料集與 Adobe Analytics 中的分類資料類似，是在 Customer Journey Analytics 中進行資料分類的方法。

使用 Analytics 來源連接器時，有些標準查詢資料集會在報告時自動套用。若要了解更多資訊，請參閱「[新增標準查詢至資料集](/help/connections/standard-lookups.md)」。

在使用 Experience Platform Web SDK 時，為了對 Customer Journey Analytics 中的資料進行分類，您需要為包含要分類資料的每個維度建立一個自訂結構描述和一個查詢資料集。

## 建立自訂結構描述以便與查詢資料集一起使用

為包含您想要在 Customer Journey Analytics 中分類資料的每個維度建立一個自訂結構描述。當您在後續步驟中建立查詢資料集時，將會引用此結構描述。

對包含要分類資料的每個維度，重複此程序。

若要建立結構描述以便與 Customer Journey Analytics 中的查詢資料集一起使用：

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取「**[!UICONTROL 資料管理]**」中的「**[!UICONTROL 結構描述]**」。

1. 選取「**[!UICONTROL 建立結構描述]**」。

   ![建立結構描述按鈕](assets/schema-create.png)

1. 選取「**[!UICONTROL 手動]**」。這會讓您能以手動方式將欄位和欄位群組加入您的結構描述中。選擇「**[!UICONTROL 選取]**」，進入建立精靈的下個頁面。

1. 在「**[!UICONTROL 結構描述詳細資訊]**」頁面，選取「**[!UICONTROL 其他]**」，然後選取「**[!UICONTROL 自訂]**」。

   ![建立自訂](assets/schema-custom.png)

1. 選取「**[!UICONTROL 建立類別]**」。

   <!-- add screenshot -->

1. 在「**[!UICONTROL 建立類別]**」對話框中，指定結構描述的名稱和說明，選取「**[!UICONTROL 記錄]**」，然後選取「**[!UICONTROL 建立]**」。

1. 繼續[建立查詢資料集](#create-a-lookup-dataset)。

## 建立查詢資料集

在[建立自訂結構描述](#create-a-custom-schema-to-use-with-the-lookup-dataset)以用於查詢資料集後，您需要建立查詢資料集並將其對應到您的結構描述。

對包含要分類資料的每個維度，重複此程序。

若要建立查詢資料集，以便與 Customer Journey Analytics 中的結構描述一起使用：

>[!NOTE]
>
>以下程序是使用 CSV 檔案來建立資料集。您也可用任何其他適用方法將資料匯入 Experience Platform，例如設定資料流。

1. 在 Adobe Experience Platform 中，在左側邊欄中選取「**[!UICONTROL 工作流程]**」。

   ![建立自訂](assets/lookup-dataset-workflows.png)

1. 選取「**[!UICONTROL 將 CSV 對應到 XDM 結構描述]**」，然後選取「**[!UICONTROL 啟動]**」。

1. 在「**[!UICONTROL 資料集詳細資訊]**」部分中，選取「**[!UICONTROL 新資料集]**」。

1. 指定資料集的名稱和說明。

1. 在「**[!UICONTROL 結構描述]**」欄位中，選取您為查詢資料集建立的結構描述，如「[為查詢資料集建立結構描述](#create-a-schema-for-lookup-datasets)」所述。

1. 選取&#x200B;**[!UICONTROL 「下一步」]**。

1. 在&#x200B;**[!UICONTROL 「將 CSV 對應到 XDM 結構描述」頁面]**&#x200B;的「**[!UICONTROL 上傳檔案]**」部分中，選取「**[!UICONTROL 選擇檔案]**」，然後瀏覽檔案系統中包含您要套用分類資料維度的分類資訊的檔案。例如，這可能是列有欄位 ID 和對應欄位名稱的試算表。<!-- correct? How can I better explain what this file is?-->

   ![對應 CSV 檔案](assets/lookup-map-csv.png)

1. 選取「**[!UICONTROL 下一步]**」

1. 檔案上傳後，檢視對應以確保資料準確無誤。CSV 檔案的欄列在&#x200B;**[!UICONTROL 來源資料]**&#x200B;下面，且其對應的 XDM 結構描述欄位列在&#x200B;**[!UICONTROL 目標欄位]**&#x200B;下面。

   Platform 會根據您選取的目標結構描述或資料集，為自動對應欄位自墧提供智慧建議。您可以手動調整對應規則，以配合您的使用案例。

   若要了解更多對應程序，請參閱 Experience Platform 文件中的「[將 CSV 檔案對應到現有 XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)」。

1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 繼續[將查詢資料集新增至 Customer Journey Analytics 中的連線](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics)。

## 將查詢資料集新增至 Customer Journey Analytics 中的連線

在[建立自訂結構描述](#create-a-custom-schema-to-use-with-the-lookup-dataset)且[建立查詢資料集](#create-a-lookup-dataset)後，您需要將查詢資料集新增至 Customer Journey Analytics 中的連線。

對包含要分類資料的每個維度，重複此程序。

要將查詢資料集新增至 Customer Journey Analytics 中的連線：

1. 在 Customer Journey Analytics 的頂部選單中選取「**[!UICONTROL 連線]**」，也可以自「**[!UICONTROL 資料管理]**」選取。

1. 選取「![更多圖示](assets/More.svg)」(在您要新增查詢資料集的連線旁邊)，然後選取「**[!UICONTROL 編輯]**」。

   <!-- add screenshot -->

1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

1. 在「**[!UICONTROL 新增資料集]**」對話框中，選取您已建立的查詢資料集，然後選取「**[!UICONTROL 下一個]**」。

1. 在「**[!UICONTROL 個人 ID]**&#x200B;欄」位中，從您在 Experience Platform 設定的資料集結構描述中所定義的可用身分中選取一個個人 ID。 <!-- fill out other fields? -->

1. 選取「**[!UICONTROL 新增資料集]**」，然後選取「**[!UICONTROL 儲存]**」。

   <!-- is there a step right in between here where you select the dataset -->

1. 使用「**[!UICONTROL 金鑰]**」欄位和「**[!UICONTROL 匹配金鑰]**」欄位，在查詢資料集中的欄位與事件或摘要資料集中的欄位之間建立關聯。

1. 重複此過程，直到所有查詢資料集都新增至 Customer Journey Analytics 的連線中。

{{upgrade-final-step}}

