---
title: 開始升級至Customer Journey Analytics
description: 規劃從Adobe Analytics升級至Customer Journey Analytics的程式
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 11%

---

# 步驟1：開始升級至Customer Journey Analytics

Customer Journey Analytics是新一代的分析產品。 它允許多管道資料收集（線上和離線資料），結合強大的報表時間處理功能（透過資料檢視中元件和衍生欄位的定義）。

在開始從Adobe Analytics升級至Customer Journey Analytics的流程之前，您應該瞭解Customer Journey Analytics的好處，以及成功升級所需的步驟。

## 瞭解Customer Journey Analytics的好處

以下是一些主要優點： (如需完整清單，以及這些主要功能的詳細資訊，請參閱[僅適用於Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)的功能。)

* [多頻道報告](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics 可結合 Experience Platform 的功能，儲存各種資料綱要和類型。從多個管道收集和報告資料，例如數位(Web)、銷售點系統、行動裝置、CRM系統等。

* [資料檢視中的報表時間轉換](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics 中的資料檢視可讓您進一步詮釋來自連線的資料。您可以在不變更實作的情況下變更或移除資料、使用子字串來控制維度、從任何值建立量度、篩選子事件或使用衍生欄位。 所有這些轉換都是非破壞性的。

* [轉換適用於歷史資料和新資料](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  資料檢視操作可以非破壞性方式套用至歷史資料和新資料。

* [衍生欄位](/help/data-views/derived-fields/derived-fields.md)

  衍生的欄位允許對您的資料進行報告時間轉換。資料可以動態組合、更正或建立，並追溯套用於所有的報告。

* [資料檢視取代虛擬報表套裝](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  資料檢視運用現有的虛擬報表套裝概念，並將其擴展以啟用透過連線使資料成為可用的其他控制項。 這些變更可讓一般設定（例如時區和工作階段超時間隔）可供設定且具有追溯性。

* [無限制的客戶維度和量度](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  值可以是數值、文字、物件、清單或所有專案的混合。 維度可能是嵌套式或階層式。

## 瞭解升級程式

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
本頁資訊涵蓋升級程式的步驟1，如下表標示之處。 完成此表格中的所有步驟，從Adobe Analytics升級至Customer Journey Analytics。

| 升級任務 | 詳細資料 |
|---------|----------|
| <span class="preview">**步驟1：開始升級**</span> | <span class="preview">瞭解升級至Customer Journey Analytics的好處及基本的升級程式。</span> |
| **步驟2：[選擇升級路徑](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | 升級至Customer Journey Analytics有多種方法。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3：[傳送資料至Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的升級路徑而有所不同。 |
| **步驟4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟5：[執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外工作適用於從Adobe Analytics升級以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的帳戶處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱[Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

## 首先，選擇升級路徑

升級至Customer Journey Analytics有多種方法。 [選擇最適合您組織的方法](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

您選擇的升級路徑取決於貴組織目前的Adobe Analytics環境和長期目標。
