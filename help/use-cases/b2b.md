---
title: (B2B)新增帳戶層級資料做為查閱資料集
description: 瞭解如何將帳戶型資料新增為CJA的查閱資料集
translation-type: tm+mt
source-git-commit: 721915ffdc9f196a13a360fb5ac145f750788bcf
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---


# (B2B)新增帳戶層級資料做為查閱資料集

此B2B使用案例會示範如何指定帳戶層級的資料，而非人員層級的資料以進行分析。 帳戶層級分析可回答問題，例如

* 此帳戶與哪個公司名稱相符？
* 有多少員工與此帳戶／公司相關？
* 此帳戶中代表哪些角色？
* 與其他帳戶相比，此帳戶在特定行銷促銷活動的整體效能如何？
* 某個帳戶的某些角色（如IT經理）的行為是否與另一個帳戶的相同角色不同？

您將帳戶層級資訊帶入 [查閱](/help/getting-started/cja-glossary.md) 資料集（類似於傳統Adobe Analytics中的分類）。

您先在Adobe Experience Platform中建立查閱結構，然後透過擷取。csv帳戶層級資料來建立查閱表格資料集。 然後，您會繼續建立結合不同資料集的連線CJA，包括您建立的查閱資料集。 然後您建立資料檢視，最後就可以在工作區中運用所有資料。

>[!NOTE]
>
>查閱表格的大小可高達1 GB。

## 1.建立查閱結構(Experience Platform)

為 [查閱](/help/getting-started/cja-glossary.md) 表格可確保使用的資料集在CJA中具有正確的設定（記錄類型）。 最佳實務是 [建立自定義架構類](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) 稱為「查閱」（任何元素中皆空白），可重新用於所有查閱表格。

![](assets/create-new-class.png)

## 2.建立查閱資料集(Experience Platform)

架構建立後，您必須在Experience Platform中從該架構建立查閱資料集。 此查閱資料集包含帳戶層級的行銷資訊，例如：公司名稱、員工總數、網域名稱、所屬產業、年收入、他們是否為Experience Platform的目前客戶、他們所在的銷售階段、帳戶內的哪個團隊使用CJA等。

1. 在Adobe Experience Platform中，請至 **[!UICONTROL 資料管理>資料集]**.
1. 按一下 **[!UICONTROL +建立資料集]**.
1. 按一下 **[!UICONTROL 從架構建立資料集]**.
1. 選擇您建立的查找方案類。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 命名資料集（在我們的範例中，B2B資訊）並提供說明。
1. 按一下&#x200B;**[!UICONTROL 「完成」]**。


## 3.將資料集合在連線中（客戶歷程分析）

在此範例中，我們將3個資料集合為一個CJA連線：

| 資料集名稱 | 說明 | AEP結構類 | 資料集詳細資料 |
|---|---|---|---|
| B2B印象 | 包含帳戶層級的點按流、事件層級資料。 例如，它包含執行行銷廣告的電子郵件ID和對應的帳戶ID以及行銷名稱。 此外，也包含每位使用者對這些廣告的印象。 | 基於XDM ExperienceEvent模式類 | The `emailID` 用作主要身分，並指派 `Customer ID` namespace。 因此，它會顯示為預設值 **[!UICONTROL 人員ID]** 在客戶歷程分析中。 ![曝光數](assets/impressions-mixins.png) |
| B2B設定檔 | 此描述檔資料集會告訴您更多有關帳戶中使用者的資訊，例如其職稱、其所屬的帳戶、其LinkedIn描述檔等。 | 基於XDM個人配置檔案模式類 | 無需選擇 `emailID` 作為此架構中的主ID。 請確定啟用 **[!UICONTROL 描述檔]**;如果您不這麼做，CJA將無法連接 `emailID` 在B2B設定檔中， `emailID` 在B2B印象資料中。 （此功能稱為現場拼接。） ![設定檔](assets/profile-mixins.png) |
| B2B資訊 | 請參閱上述「建立查閱資料集」。 | B2BAccount（自訂查閱結構類別） | The relations withe `accountID` 而B2B印象資料集是透過在CJA中連接B2B印象資料集與B2B印象資料集而自動建立的，如下列步驟所述。 ![查找](assets/lookup-mixins.png) |

以下是您結合資料集的方式：

1. 在客戶歷程分析中，選取 **[!UICONTROL 連接]** 頁籤。
1. 選取您要結合的資料集（在我們的範例中，以上三個資料集）。
1. （不確定這是步驟所屬的位置……）對於B2B資訊資料集，請選取 `accountID` 的索引鍵。 然後選取其相符索引鍵（對應的維度）, `accountID` 在事件資料集中。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 命名和描述連接，並根據 [這些說明](/help/connections/create-connection.md).
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

現在資料會被收錄。 上線資料和建立查閱需要大約2到4小時，視查閱表格的大小而定。

## 從此連接建立資料視圖

依照 [建立資料視圖](/help/data-views/create-dataview.md).

* 新增資料集中所需的所有元件（維度和量度）。

## 分析工作區中的資料

您現在可以根據所有3個資料集的資料來建立Workspace專案。

例如，您可以找到介紹中提出的答案：

* 依accountID劃分emailID，以找出電子郵件ID所屬的公司。
* 有多少員工對應至特定帳戶ID?
* 帳戶ID屬於哪個產業？

![](assets/project-lookup.png)
