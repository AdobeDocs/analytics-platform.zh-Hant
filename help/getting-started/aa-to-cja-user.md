---
title: CJAAdobe Analytics使用手冊
description: 當您的公司將資料從Adobe Analytics移動到Customer Journey Analytics時，從用戶的角度考慮什麼
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 21%

---

# CJAAdobe Analytics使用手冊

你的公司開始雇傭Customer Journey Analytics。 作為熟悉Adobe Analytics的用戶，你已經擁有了一個不錯的先機。 在與Customer Journey Analytics合作時，你會注意到一些相似之處和一些重大差異。 本頁旨在解釋那些沒有改變的事以及一些主要差異。 我們還將告訴您，您如何獲得有關新概念的更多資訊，以及進一步的步驟，使您的客戶之旅更輕鬆、更成功。

與傳統的Adobe Analytics相比，CJA中的幾項功能已經更名並重新設計，以符合行業標準。 某些更新的術語包括段、虛擬報表套件、分類、客戶屬性和容器名稱。 耳熟能詳的概念，如電子貨幣和道具，以及它們施加的限制，已不復存在。

## 未更改的內容

在報告方面，您熟悉的許多內容沒有改變。

* 你仍然可以利用 [Analysis Workspace](/help/analysis-workspace/home.md) 分析資料。 工作區與傳統Adobe Analytics的工作區一樣。
* 您還有相同版本的 [Adobe Analytics儀表板](/help/mobile-app/home.md) 隨你。 儀表板(即Mobile應用)與傳統Adobe Analytics一樣。
* [Report Builder](/help/report-builder/report-buider-overview.md) 它有一個新的介面，現在可以在PC、Mac和Excel的Web版本上運行。

在報導方面， **什麼不同** 即您可以訪問更多的跨通道資料進行分析。 下面是一些包含跨通道資料源的可視化示例：

![多通道可視化](assets/cross-channel.png)

## 新架構 {#architecture}

Customer Journey Analytics從Adobe Experience Platform獲取資料。 Experience Platform使您能夠集中並標準化來自任何系統或渠道的客戶資料和內容，並應用資料科學和機器學習來改進個性化體驗的設計和交付。

Platform 中的客戶資料以資料集形式儲存，而資料集是由結構和資料批次組成。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理員已建立 [連接](/help/connections/create-connection.md) 到平台中的資料集。 然後他們建了 [資料視圖](/help/data-views/data-views.md) 在那些聯繫里。 將資料視圖視為類似於虛擬報告套件。 資料視圖是Customer Journey Analytics報告的基礎。 報告套件的概念已不復存在。

## 連線

通過連接，Analytics Admin可以整合來自 [!DNL Adobe Experience Platform] 入 [!UICONTROL 工作區]。 若要針對 [!DNL Experience Platform] 資料集製作報表，必須先為 [!DNL Experience Platform] 和 [!UICONTROL Analysis Workspace] 的資料集建立連線。

以下是影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 報表套裝 {#report-suites}

如果您的組織仍在Adobe Analytics平台上並添加CJA/AEP，則可以通過Adobe Analytics源連接器或Web SDK將您的報告套件資料引入Experience Platform。 通常，您會使用分析架構來源特定於報告套件的資料集。

但是，報告套件不再是在CJA中報告的基礎。 [資料視圖](/help/data-views/data-views.md) 。 有關資料視圖的詳細資訊，請參閱下面的部分。

來自多個資料集的現有實現可以組合為Experience Platform。 基於這些資料集的連接和資料視圖可以合併先前存在於單獨報告套件中的資料。

## （虛擬）報告套件現在是「資料視圖」 {#data-views}

[!UICONTROL 資料視圖] 將虛擬報表套件的概念應用到 [啟用對資料的其他控制項](/help/data-views/create-dataview.md) 連接可用。 這使時區和會話超時間隔可以配置。 您還可以動態應用各個維的屬性和到期屬性。 請注意，這些應用於所有資料。

**您需要做的**:

* 請注意，在Workspace中，您現在使用的報告套件選擇器允許您從管理員已與您共用的資料視圖中進行選擇：

   ![資料視圖選擇器](assets/data-views.png)

* 熟悉許多 [使用資料視圖中的事例](/help/data-views/data-views-usecases.md)。

## Vars和道具

[!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 [!UICONTROL eVar]、[!UICONTROL prop] 和 [!UICONTROL event]。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。

**您需要做的**:

* 熟悉這些架構元素可用於深入查看資料的多種方法。

## 段現在是「篩選器」

[!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]這意味著現有的資料段都與 [!UICONTROL Customer Journey Analytics]。 此外，已將&quot;段&quot;更名為&quot;filters&quot;。

目前，您無法共用/發佈 [!UICONTROL 篩選] ([!UICONTROL 段]從 [!DNL Customer Journey Analytics] Experience Platform統一配置檔案或其他Experience Cloud應用程式。 此功能當前正在開發中。

**您需要做的**:

* 如果要將現有Adobe Analytics段移至Customer Journey Analytics，請查看 [這個視頻](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=zh-Hant)。
* 否則，在Customer Journey Analytics中重新建立篩選器。

## 計算量度

[!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]這意味著現有計算的度量都與 [!UICONTROL Customer Journey Analytics]。

**您需要做的**:

* 如果要將Adobe Analytics計算的度量移到Customer Journey Analytics，請查看 [這個視頻](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=zh-Hant)。
* 否則，在Customer Journey Analytics中重新建立計算的度量。

## 會話和變數持久性設定

[!UICONTROL Customer Journey Analytics] 在報告時應用所有這些設定，這些設定現在處於 [資料視圖](/help/data-views/component-settings/persistence.md)。 對這些設定的更改現在具有追溯性，您可以使用多個資料視圖擁有多個版本！

## 分類現在是「查找資料集」

查找資料集用於查找在事件或配置檔案資料中找到的值或鍵。 例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。如需範例，請參閱這個[使用案例](/help/use-cases/b2b.md)。

## 客戶屬性現在是「配置式資料集」

配置檔案資料集包含應用於訪問者、用戶或客戶的資料 [!UICONTROL 事件] 資料。 例如，它允許您上傳有關客戶的CRM資料。 您可以挑選要包含的人員 ID。在 [!DNL Experience Platform] 中定義的每個資料集，都有各自專屬的一組一或多個已定義的人員 ID，例如 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。

## 身分

CJA將標識的概念擴展到ECID之外，以包括要使用的任何ID，包括客戶ID、Cookie ID、縫合ID、用戶ID、跟蹤代碼等。 跨資料集使用公用命名空間ID，或使用 [跨渠道分析](/help/connections/cca/overview.md) 幫助將不同資料集的人聯繫在一起。 任何在CJA中設定Workspace項目的用戶都需要瞭解跨資料集使用的ID。

下面是一段視頻，重點介紹了身份在Customer Journey Analytics中的使用：

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## 容器已更名

指定容器 [建立的每個資料視圖](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers)。

* **命中容器現在是「事件」容器**。 「[!UICONTROL 人員]」容器包含指定時間段內訪客的每個工作階段和事件。
* **訪問容器現在是「會話」容器**。 「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。
* **訪問者集裝箱現已 [!UICONTROL 人員] 容器**。 「[!UICONTROL 人員]」容器包含指定時間段內訪客的每個工作階段和事件。

**您需要做的**:

您可以選擇更名任何容器以滿足組織的需要。

## `Uniques Exceeded` 限制

[!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！]
