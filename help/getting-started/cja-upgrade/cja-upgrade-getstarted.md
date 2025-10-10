---
title: 開始升級到 Customer Journey Analytics
description: 規劃從 Adobe Analytics 升級至 Customer Journey Analytics。
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 100%

---

# 步驟 1：開始升級到 Customer Journey Analytics

>[!AVAILABILITY]
>
>此頁面上的資訊將被以下更全面的升級資訊取代： <ul><li>**建議的升級步驟**<p>如需詳細資訊，請參閱[從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升級指南**<p>新的升級指南現已推出，可動態產生適合您組織和獨特情況的升級步驟。</p><p>若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。</p></li></ul>

Customer Journey Analytics 是下一代的分析產品。此功能允多管道資料彙集 (線上和離線資料)，結合強大的報表時間處理功能 (透過在資料檢視中定義元件和衍生欄位)。

在開始從 Adob&#x200B;&#x200B;e Analytics 升級至 Customer Journey Analytics 之前，您應該了解 Customer Journey Analytics 的優點以及成功升級的必要步驟。

## 了解 Customer Journey Analytics 的好處

以下列有部分主要優點：(有關完整清單以及每個主要功能的更多資訊，請參閱「[只有在 Customer Journey Analytics 提供的功能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics))。

* [多管道報告](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics 可結合 Experience Platform 的功能，儲存各種資料結構描述和類型。收集和報告來自多種管道的資料，例如數位 (網頁)、銷售點系統、行動裝置、CRM 系統等。

* [資料檢視中的報告時間轉換](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics 中的資料檢視可讓您進一步詮釋來自連線的資料。您可以變更或移除資料而無需變更實施、使用子字串操作維度、從任何值建立量度、區段子事件，或使用衍生欄位。以上所有轉換都是非破壞性。

* [轉換適用於歷史資料和新資料](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  資料檢視操控能以非破壞性方式同時套用至歷史資料和新資料。

* [衍生欄位](/help/data-views/derived-fields/derived-fields.md)

  衍生欄位允許對您的資料進行報告時間轉換。資料可以動態組合、更正或建立，並追溯套用於所有的報告。

* [資料檢視是取代虛擬報告套件](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  資料檢視運用現有的虛擬報告套裝概念，並將其擴展以啟用透過連接使資料成為可用的其他控制項。這些變動使一般設定 (如時區和工作階段超時間隔) 成為可設定且具有追溯性。

* [無限制的客戶維度和量度](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  值可以是數字、文字、物件、清單，或所有這些的混合。維度可能是嵌套式或階層式。

## 了解升級程序

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
本頁資訊涵蓋升級程序的步驟 1，重點如下表所示。完成此表所有步驟，即可從 Adob&#x200B;&#x200B;e Analytics 升級至 Customer Journey Analytics。

| 升級工作 | 詳細資料 |
|---------|----------|
| <span class="preview">**步驟 1：開始升級**</span> | <span class="preview">了解升級到 Customer Journey Analytics 的好處和基本升級流程。</span> |
| **步驟 2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 有多種方法可以升級到 Customer Journey Analytics。根據您組織目前的 Adob&#x200B;&#x200B;e Analytics 環境和長期目標，選擇最適合您組織的方法。 |
| **步驟 3： [將資料發送至 Adob&#x200B;&#x200B;e Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 將資料發送送至 Adob&#x200B;&#x200B;e Experience Platform 的流程會因您在步驟 2 選擇的升級路徑而不同。 |
| **步驟 4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多數組織需要保留其歷史 Adob&#x200B;&#x200B;e Analytics 資料達一段時間。有多種選項可以達到此目的。 |
| **步驟 5： [執行額外的實施工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段中，您需要執行各類工作後，您的 Customer Journey Analytics 環境才可供使用。<p>這些額外工作適用於 Adob&#x200B;&#x200B;e Analytics 的升級以及新的 Customer Journey Analytics 實施。</p><p>這些工作包括：</p><ul><li>將其他資料引入 Experience Platform</li><li>建立 Platform 資料集和 Customer Journey Analytics 之間的連線</li><li>建立資料檢視</li><li>轉移報告 API 用法</li><li>考量資料摘要和 Data Warehouse</li><li>移轉專案和元件</li><li>規劃使用者上線</li></ul> <p>如需更多資訊，請參閱「[Customer Journey Analytics 快速入門手冊](/help/getting-started/cja-getting-started.md)」。 |

{style="table-layout:auto"}

## 首先，選擇升級路徑

有多種方法可以升級到 Customer Journey Analytics。[選擇最適合您組織的方法](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

您選擇的升級路徑取決於您組織目前的 Adob&#x200B;&#x200B;e Analytics 環境和長期目標。
