---
title: (B2B) 新增帳戶層級資料當做查詢資料集
description: 了解如何將以帳戶為基礎的資料，以查詢資料集的形式新增至 CJA
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: d2b21d6e4e092c33947220b2d22a8a757407fabb
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 93%

---

# (B2B) 新增帳戶層級資料當做查詢資料集

此 B2B 使用案例顯示如何在帳戶層級、而非個人層級指定資料以進行分析。帳戶層級分析可回答以下類型的問題

* 此帳戶與哪個公司名稱相符？
* 有多少員工與此帳戶/公司相關？
* 此帳戶代表哪些角色？
* 與其他帳戶相比，此帳戶在特定行銷活動的整體成效如何？
* 某帳戶中特定角色 (例如 IT 主管) 的行為是否與其他帳戶中的同一角色有所差異？

您可以將帳戶層級資訊做為一個[查詢](/help/getting-started/cja-glossary.md)資料集，即可做到這一切。

首先，您要在 Adobe Experience Platform 中建立查詢結構，接著內嵌 .csv 格式的帳戶層級資料以建立查詢表格資料集。接下來，您需要繼續建立結合不同資料集的 Customer Journey Analytics (CJA) 連線，包括您剛剛建立的查詢資料集。您之後會建立資料檢視，最後就能夠在 Workspace 中運用上述的所有資料。

>[!NOTE]
>
>查詢表格的大小最多可允許 1 GB。

## 1. 建立查詢結構 (Experience Platform)

為[查詢](/help/getting-started/cja-glossary.md)表格建立專用結構，以確保該資料集可在 CJA 中使用，且設定正確無誤 (記錄類型)。最佳實務是 [建立自定義架構類](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant#create-new-class) 稱為「查詢」（不含任何元素），可重新用於所有查詢表格。

![](../assets/create-new-class.png)

## 2. 建立查詢資料集 (Experience Platform)

建立架構後，就能在 Experience Platform 中使用該架構建立查詢資料集。此查詢資料集包含帳戶層級的行銷資訊，例如：公司名稱、員工總數、網域名稱、產業別、年度營收、是否為 Experience Platform 現有客戶、所處銷售階段、帳戶中正在使用 CJA 的團隊等等。

>[!IMPORTANT]
>
>CJA 不支援查詢資料集中的整數。如果您在 XDM 架構中為查詢資料集新增整數欄位，會無法將這些整數當作量度或計算量度。例如，如果annualRevenue或totalEmployees定義為整數，它們在CJA的報表中會顯示為「0」。 不過，如果您將兩者指派為字串，則可將兩者當作查詢資訊。

例如，annualRevenue或totalEmployees在以下範例中定義為整數 — 這是它在CJA中顯示「0」的原因。

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

此範例是將 3 個資料集合併為一個 CJA 連線：

| 資料集名稱 | 說明 | AEP 架構類別 | 資料集詳細資訊 |
| --- | --- | --- | --- |
| B2B 曝光數 | 包含點按資料流 (帳戶層級的事件層級資料)。舉例來說，其中包含刊登行銷廣告所需的電子郵件 ID、對應的帳戶 ID 及行銷名稱。此外，資料中也包含這些廣告的每位使用者曝光數。 | 以 XDM ExperienceEvent 架構類別為基礎 | `emailID` 設為主要身分識別，並獲指派 `Customer ID` 命名空間。因此，系統會以預設的&#x200B;**[!UICONTROL 人員 ID]** 形式顯示於 Customer Journey Analytics。![曝光數](../assets/impressions-mixins.png) |
| B2B 設定檔 | 此設定檔資料集能協助您深入了解帳戶中使用者的相關資訊，例如其職稱、所屬帳戶、LinkedIn 個人檔案等。 | 以 XDM 個別設定檔架構類別為基礎 | 不需在此架構中選取 `emailID` 作為主要 ID。請務必啟用&#x200B;**[!UICONTROL 設定檔]**；如未啟用，CJA 無法將 B2B 設定檔中的 `emailID` 與 B2B 曝光數資料的 `emailID` 連結![設定檔](../assets/profile-mixins.png) |
| B2B 資訊 | 請參閱上述「建立查詢資料集」。 | B2BAccount (自訂查詢結構類別) | 在 CJA 中連結 B2B 資訊資料集和 B2B 曝光數資料集後，`accountID` 和 B2B 曝光數資料集的關係就能自動建立，如以下步驟所述。![查詢](../assets/lookup-mixins.png) |

合併資料集的方法說明如下：

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 選取您要合併的資料集 (範例為上述的三個資料集)。
1. 針對 B2B 資訊資料集，選取您要在查詢表格中使用的 `accountID` 金鑰。接著，請選取相符金鑰 (對應的維度)，以及事件資料集中的 `accountID`。
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

![](../assets/project-lookup.png)