---
title: 新增帳戶資料作為查詢資料集
description: 瞭解如何將帳戶資料當做查詢資料集新增到Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 36%

---

# 新增帳戶資料作為查詢資料集

此B2B使用案例會示範如何將帳戶資料新增至人員層級和事件層級的分析。 新增帳戶資料時，您可以回答下列問題：

* 此帳戶與哪個公司名稱相符？
* 此帳戶代表哪些角色？
* 某帳戶中特定角色 (例如 IT 主管) 的行為是否與其他帳戶中的同一角色有所差異？

若要新增帳戶資料資訊，請新增並使用包含此資訊的[查詢](/help/technotes/glossary.md)資料集。

相關步驟包括：

1. [以Experience Platform建立查詢結構描述](#create-lookup-schema)。
1. [以Experience Platform建立查詢資料集](#create-lookup-dataset)，讓您擷取CSV型帳戶資料。
1. [在Customer Journey Analytics中將資料集合併到連線](#combine-datasets-in-a-connection)中，包括您建立的查詢資料集。
1. [以Customer Journey Analytics建立資料檢視](#create-a-data-view-from-this-connection)。
1. [在Workspace中以Customer Journey Analytics分析此資料](#analyze-the-data-in-workspace)。

>[!NOTE]
>
>查詢表格的大小最多可允許 1 GB。
>

## 建立查詢結構描述

當您為[lookup](/help/technotes/glossary.md)資料表建立自己的結構描述時，該結構描述可確保使用的資料集能夠以正確設定（記錄型別）的Customer Journey Analytics使用。 最佳實務是[建立可重複用於所有查詢表格的自訂結構描述類別](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)。

![建立新類別對話方塊。](../assets/create-new-class.png)

## 建立查詢資料集

建立結構描述後，您需要根據該結構描述在Experience Platform中建立查詢資料集。 此查詢資料集包含帳戶資訊。 例如：公司名稱、員工總數、網域名稱、公司所屬的產業、年收入等。 確保資料中包含的人員識別碼可與事件資料中使用的人員識別碼相符。

1. 在Experience Platform中，移至&#x200B;**[!UICONTROL 資料管理>資料集]**。
1. 按一下&#x200B;**[!UICONTROL 「+ 建立資料集」]**。
1. 按一下&#x200B;**[!UICONTROL 「從架構建立資料集」]**。
1. 選取您建立的「查詢結構描述」類別。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 為資料集命名（例如，`B2B Info`），並提供說明。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 擷取資料

如果您是使用 CSV 檔案，這份[將 CSV 檔案對應至 XDM 架構](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema)的相關說明應該會有所幫助。

您也可以參閱[其他方法](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)。

視查詢表格的大小而定，將資料上線及建立查詢作業約需 2 至 4 小時。

## 在連線中合併資料集

在此範例中，您將3個資料集合併為一個Customer Journey Analytics連線：

| 資料集名稱 | 說明 | Adobe Experience Platform結構描述類別 | 資料集詳細資訊 |
| --- | --- | --- | --- |
| B2B 曝光數 | 包含點按資料流 (帳戶層級的事件層級資料)。舉例來說，其中包含刊登行銷廣告所需的電子郵件 ID、對應的帳戶 ID 及行銷名稱。此外，資料中也包含這些廣告的每位使用者曝光數。 | 以XDM ExperienceEvent結構描述類別為基礎 | `emailID`設為主要身分識別，並獲指派 `Customer ID` 命名空間。因此，在Customer Journey Analytics中會顯示為預設&#x200B;**[!UICONTROL 人員ID]**。 ![曝光數](../assets/impressions-mixins.png) |
| B2B 設定檔 | 此設定檔資料集能協助您深入了解帳戶中使用者的相關資訊，例如其職稱、所屬帳戶、LinkedIn 個人檔案等。 | 以 XDM 個別設定檔架構類別為基礎 | 選取`emailID`作為此結構描述中的主要ID。 |
| B2B 資訊 | 請參閱上述「建立查詢資料集」。 | B2B帳戶（自訂查詢結構類別） | 當您將B2B資訊資料集與Customer Journey Analytics中的B2B曝光數資料集連線時，`accountID`和B2B曝光數資料集之間的關係會自動建立，如以下步驟所述。 ![查詢](../assets/lookup-mixins.png) |

合併資料集的方法說明如下：

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 選取您要合併的資料集。
1. 針對B2B資訊資料集，選取查詢表格中使用的金鑰（例如`personKey.sourceKey`）。 接著，請選取相符的索引鍵（對應的維度），以及事件資料集中的索引鍵（例如p`ersonKey.sourceKey`）。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 為連線命名並輸入說明，並根據此處[說明](/help/connections/create-connection.md)完成設定。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 從此連線建立資料檢視

依照[建立資料檢視](/help/data-views/create-dataview.md)上的指示操作。

* 從資料集中新增您需要的所有元件（維度和量度）。 請確定對於需要重複資料刪除以重複計數的量度，您相應地設定這些量度（請參閱[量度重複資料刪除元件設定](/help/data-views/component-settings/metric-deduplication.md)）。 此類量度的範例為員工人數或收入。

## 在Workspace中分析資料

現在您可以根據全部 3 個資料集的資料，建立工作區專案。

例如，您可以針對簡介中提出的問題尋找答案：

* 依 accountID 劃分 emailID，以釐清電子郵件 ID 所屬的公司。
* 有多少員工對應至特定帳戶 ID？
* 某帳戶 ID 屬於哪個產業？

>[!MORELIKETHIS]
>
>如需詳細資訊，請參閱[範例B2B專案](example.md)。

