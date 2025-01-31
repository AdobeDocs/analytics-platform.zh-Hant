---
title: Adobe Analytics 使用者的使用手冊
description: 當您的公司將 Adobe Analytics 資料轉移到 Customer Journey Analytics 時，以使用者角度需要考慮什麼
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '1454'
ht-degree: 92%

---

# Adobe Analytics 使用者的使用手冊

如果您的組織開始使用 Adobe Customer Journey Analytics，您可能會注意到 Adobe Analytics 和 Customer Journey Analytics 之間的一些相似點和差異。本頁面旨在說明這些差異，以幫助您的組織適應新的實施和報告工作流程。本頁面還提供了有關新概念的更多資源，以及進一步的步驟，讓您作為分析師的旅途更輕鬆、更成功。

Customer Journey Analytics 中的幾項功能都經過重新命名和重新設計，以符合行業標準。部分更新用語包括區段、虛擬報告套裝、分類、客戶屬性和容器名稱。eVars 和 props 的局限性已不復存在，而是支援靈活的自訂維度和量度。

## 沒有變動的內容

在報告方面，您熟悉的許多內容都沒有改變。

* 您仍然可以利用 [Analysis Workspace](/help/analysis-workspace/home.md) 的強大功能來分析資料。工作區與傳統 Adobe Analytics 的工作區一樣。
* 可以使用相同版本的 [Adobe Analytics 儀表板](/help/mobile-app/home.md)，且 Customer Journey Analytics 和 Adobe Analytics 之間運作方式類似。
* [Report Builder](/help/report-builder/report-buider-overview.md) 具有新介面，並在 MS Windows、MacOS 和 Excel 的 Web版本上執行。(在此版本的Report Builder之前，除非在VMware上執行，否則無法在Mac上使用。) 此版本尚未支援傳統AA資料請求。

## 報告的變動

您可以存取更多要分析的跨通道資料。例如，您可以建立一個工作區項目來分析多個通道的效能，前提是這些資料集由您的組織攝取，並包含在 Customer Journey Analytics 使用的資料檢視中 (請參閱下面的「資料體系結構的變動」)。

![顯示 multi-channel-visualizations 的資料來源檢視](assets/cross-channel.png)

## 資料架構的變動 {#architecture}

Customer Journey Analytics 從 Adobe Experience Platform 取得資料。Experience Platform 可讓您集中並標準化來自任何系統或通道的客戶資料和內容，並應用資料科學和機器學習來改進個性化體驗的設計和交付。

Experience Platform 中的客戶資料以資料集形式儲存，資料集含有[結構描述](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant)和資料批次。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=zh-Hant)。

您的 Customer Journey Analytics 管理員會建立與 Experience Platform 中資料集的[連線](/help/connections/create-connection.md)。然後他們會使用這些連線來建置[資料檢視](/help/data-views/data-views.md)。資料檢視在概念上與虛擬報告套裝相似，是 Customer Journey Analytics 報告的基礎。由於 Experience Platform 會從是所有報告資料取得來源，因此報告套裝不再以資料容器存在。

透過連線，Analytics管理員可以將來自Adobe Experience Platform的資料集整合到Customer Journey Analytics中。


<!-- Outdated UI

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configuring connections](https://video.tv.adobe.com/){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->


Adobe 提供了多種將資料導入 Adobe Experience Platform 的方法，包括透過 Adobe Analytics 來源連接器或 Web SDK 的報告套裝資料。可在 Experience Platform 中結合來自多個報告套裝的現有實作。基於這些資料集的連線和資料檢視可以合併先前存在於單獨報告套裝中的資料。

## 虛擬報告套裝概念的變動 {#data-views}

[!UICONTROL 資料檢視]運用現有的虛擬報告套裝概念，並將其擴展以[啟用透過連接使資料成為可用的其他控制項](/help/data-views/create-dataview.md)。這些變動使一般設定 (如時區和工作階段超時間隔) 成為可設定且具有追溯性。也可以在報告或資料檢視級別上自定義個別變數設定，如屬性和期限。這些設定為不具損害性且可追溯。

請注意，右上方的報告套裝選擇器現在允許您從可用資料檢視中進行選擇：

![data-view-selector](assets/data-views.png)

參閱[資料檢視的使用案例](/help/use-cases/data-views/data-views-usecases.md)，了解這個概念的更多資訊。

## eVars 和 props概念的變動

[!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 [!UICONTROL eVar]、[!UICONTROL prop] 和[!UICONTROL 事件]概念。在 Adobe Analytics 中，eVars 和 props 會儲存內容、客戶、活動等的描述。而事件會計數營收、訂閱或產生的潛在客戶等。Customer Journey Analytics 保留了這兩種類型的資料，並且您能以相同的方式存取這些資料 — 分別從 Analysis Workspace 的左滑軌、在維度或量度下存取。

在 Customer Journey Analytics 中，提供無限制的結構描述元素，包括維度、量度和清單欄位。這些元素對應到無限結構描述元素，包括 Experience Platform 中的維度、量度和清單欄位。在 Adobe Analytics 處理規則後套用的所有瀏覽和屬性設定，現在都會在 Customer Journey Analytics 中在查詢時套用。

使用這項靈活性，您可能會遇到這樣的情況：單一結構描述欄位既可用作維度又可用作量度，以支援不同的追蹤需求。

## 區段概念的變動

嚴格來說，區段並未從 Adobe Analytics 移轉到 Customer Journey Analytics，但您可以使用元件移轉工具在 Customer Journey Analytics 中重新建立 Adobe Analytics 區段。根據對應的維度和計量在 Customer Journey Analytics 中重新建立區段。如需更多資訊，請參閱[準備將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)。

雖然您尚不能從 [!DNL Customer Journey Analytics]共用或發佈[!UICONTROL 篩選] ([!UICONTROL 區段]) 至 Experience Platform 統一輪廓，但此功能正在開發中。

除了區段概念有變動，區段容器也已更新。

* **「點擊」容器現在是「[!UICONTROL 事件]」容器**。「[!UICONTROL 事件]」容器可讓您根據單獨事件來劃分人員的資料。
* **「瀏覽」容器現在是「[!UICONTROL 工作階段]」容器**。「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。
* **「訪客」容器現在是「[!UICONTROL 人員]」容器**。「[!UICONTROL 人員]」容器包含指定時間段內人員的每個工作階段和事件。

## 計算量度概念的變動

Adobe Analytics 和 Customer Journey Analytics 之間的計算量度名稱類似。但是，[!UICONTROL Customer Journey Analytics] 不再使用 eVars、props 或事件，而是使用任何 Experience Platform 結構描述元素。此根本變更表示現有計算量度完全與[!UICONTROL Customer Journey Analytics]不相容。


>[!BEGINSHADEBOX]

如需有關如何移動計算量度的示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [將計算量度從Adobe Analytics移動至Customer Journey Analytics](https://video.tv.adobe.com/v/31788?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

## 變數屬性和過期設定的變動

[!UICONTROL Customer Journey Analytics] 在報告時會套用所有變數設定，包括屬性和過期。這些設定現在位於[資料檢視](/help/data-views/component-settings/persistence.md)中，並且某些變數設定 (如屬性) 可以在工作區專案中變動。

在相同資料檢視中，相同變數可以有多個版本。例如，您可以有一個追蹤程式碼維度，該維度會在 30 天後過期，另一個維度會在工作階段結束時過期。這兩個追蹤程式碼都使用相同的來源資料，但使用不同的屬性設定。

您也可根據相同連接有多個資料檢視。例如，您可以有一個工作階段超時 30 分鐘的資料檢視，另一個工作時段超時 15 分鐘的資料檢視。兩個資料檢視都顯示在右上部選擇器中，因此您可以在兩個之間無縫轉換。

## 分類概念的變動

「分類」現在稱為&#x200B;*查找資料集*。查詢資料集是用來查詢在事件或輪廓資料中找到的數值或索引鍵。例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查找資料。

## 客戶屬性概念的變動

「客戶屬性」現在稱為「輪廓資料集」。輪廓資料集包含套用於[!UICONTROL 事件]資料中的人員、使用者或客戶的資料。例如，這可讓您上傳有關客戶的 CRM 資料。您可以挑選要包含的人員 ID。[!DNL Experience Platform]中定義的每個資料集有其自己一組已定義的一或多名人員 ID。

## Adobe 如何識別訪客的變動

Customer Journey Analytics 將身分識別的概念擴展到 ECID 之外，以包括要使用的任何 ID，包括客戶 ID、Cookie ID、拼接 ID、使用者 ID、追蹤程式碼等。跨資料集使用通用命名空間 ID，或使用[拼接](../stitching/overview.md)可協助將不同資料集的人們連結在一起。任何在 Customer Journey Analytics 中設定工作區專案的使用者都必須了解跨資料集使用的 ID。請觀看以下影片，重點說明Customer Journey Analytics中身分識別的使用情況


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在Customer Journey Analytics中使用身分](https://video.tv.adobe.com/v/30750/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

## 低流量維度項目概念的變動

在傳統 Adobe Analytics 中，接收太多唯一值的變數會開始將維度項目貯在[!UICONTROL 低流量]下。Customer Journey Analytics 對高基數欄位的限制較少。對報告體系結構的變動，可讓 Analysis Workspace 能夠報告許多更獨特的維度項目。請參閱「[高基數維度](../components/dimensions/high-cardinality.md)」，深入了解 Customer Journey Analytics 如何為具有許多唯一值的維度最佳化報告。
