---
title: 新增帳戶層級資料當作查詢資料集
description: 瞭解如何將以帳戶為基礎的資料，以查詢資料集的形式新增至Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: b4c77c3ef4d57aac6e914a2373b6a9169f4872df
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 73%

---

# 新增帳戶層級資料當作查詢資料集

此 B2B 使用案例顯示如何在帳戶層級、而非個人層級指定資料以進行分析。帳戶層級分析可回答以下類型的問題

* 此帳戶與哪個公司名稱相符？
* 有多少員工與此帳戶/公司相關？
* 此帳戶代表哪些角色？
* 與其他帳戶相比，此帳戶在特定行銷活動的整體成效如何？
* 某帳戶中特定角色 (例如 IT 主管) 的行為是否與其他帳戶中的同一角色有所差異？

您可以將帳戶層級資訊做為一個[查詢](/help/technotes/glossary.md)資料集，即可做到這一切。

首先，您要在Adobe Experience Platform中建立查詢結構，接著內嵌.csv格式的帳戶層級資料以建立查詢表格資料集。 接下來，您需要繼續建立結合不同資料集的Customer Journey Analytics(Customer Journey Analytics)連線，包括您建立的查詢資料集。 您之後會建立資料檢視，最後就能夠在 Workspace 中運用上述的所有資料。

>[!NOTE]
>
>查詢表格的大小最多可允許 1 GB。

## 1. 建立查詢結構 (Experience Platform)

為[lookup](/help/technotes/glossary.md)資料表建立您自己的結構描述，以確保使用的資料集能夠以正確設定（記錄型別）的Customer Journey Analytics提供。 最佳作法是以「Lookup」為名稱[建立自訂架構類別](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant#create-new-class) (不含任何元素)，供所有查詢表格重複使用。

![建立新類別對話方塊。](../assets/create-new-class.png)

## 2.建立查詢資料集(Experience Platform)

建立架構後，就能在 Experience Platform 中使用該架構建立查詢資料集。此查詢資料集包含帳戶層級的行銷資訊，例如：公司名稱、員工總數、網域名稱、產業別、年度營收、是否為Experience Platform的現有客戶、所處銷售階段、帳戶中正在使用Customer Journey Analytics的團隊等等。

1. 開啟 Adobe Experience Platform 後，前往&#x200B;**[!UICONTROL 「資料管理 > 資料集」]**。
1. 按一下&#x200B;**[!UICONTROL 「+ 建立資料集」]**。
1. 按一下&#x200B;**[!UICONTROL 「從架構建立資料集」]**。
1. 選取您建立的查詢架構類別。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 為資料集命名 (例如範例中的「B2B Info」)，並輸入相關說明。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。

## 3. 將資料內嵌至 Experience Platform

如果您是使用 CSV 檔案，這份[將 CSV 檔案對應至 XDM 架構](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html?lang=zh-Hant)的相關說明應該會有所幫助。

您也可以參閱[其他方法](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hant)。

視查詢表格的大小而定，將資料上線及建立查詢作業約需 2 至 4 小時。

## 4. 將資料集合併成連線 (Customer Journey Analytics)

在此範例中，我們將3個資料集合併為一個Customer Journey Analytics連線：

| 資料集名稱 | 說明 | Adobe Experience Platform結構描述類別 | 資料集詳細資訊 |
| --- | --- | --- | --- |
| B2B 曝光數 | 包含點按資料流 (帳戶層級的事件層級資料)。舉例來說，其中包含刊登行銷廣告所需的電子郵件 ID、對應的帳戶 ID 及行銷名稱。此外，資料中也包含這些廣告的每位使用者曝光數。 | 以 XDM ExperienceEvent 架構類別為基礎 | `emailID`設為主要身分識別，並獲指派 `Customer ID` 命名空間。因此，系統會以預設的&#x200B;**[!UICONTROL 人員 ID]** 形式顯示於 Customer Journey Analytics。![曝光數](../assets/impressions-mixins.png) |
| B2B 設定檔 | 此設定檔資料集能協助您深入了解帳戶中使用者的相關資訊，例如其職稱、所屬帳戶、LinkedIn 個人檔案等。 | 以 XDM 個別設定檔架構類別為基礎 | 選取`emailID`作為此結構描述中的主要ID。 |
| B2B 資訊 | 請參閱上述「建立查詢資料集」。 | B2BAccount (自訂查詢結構類別) | 將B2B資訊資料集與Customer Journey Analytics中的B2B曝光數資料集連結，已自動建立`accountID`和B2B曝光數資料集之間的關係，如以下步驟所述。 ![查詢](../assets/lookup-mixins.png) |

合併資料集的方法說明如下：

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 選取您要合併的資料集 (範例為上述的三個資料集)。
1. 針對 B2B 資訊資料集，選取您要在查詢表格中使用的 `accountID`金鑰。接著，請選取相符金鑰 (對應的維度)，以及事件資料集中的 `accountID`。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 為連線命名並輸入說明，並根據此處[說明](/help/connections/create-connection.md)完成設定。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 5. 從此連線建立資料檢視

按照[建立資料檢視](/help/data-views/create-dataview.md)的說明操作。

* 從資料集中新增需要的所有元件 (維度和量度)。

## 6. 分析工作區的資料

現在您可以根據全部 3 個資料集的資料，建立工作區專案。

例如，您可以針對簡介中提出的問題尋找答案：

* 依 accountID 劃分 emailID，以釐清電子郵件 ID 所屬的公司。
* 有多少員工對應至特定帳戶 ID？
* 某帳戶 ID 屬於哪個產業？

![project-lookup2](assets/analyze.png)
