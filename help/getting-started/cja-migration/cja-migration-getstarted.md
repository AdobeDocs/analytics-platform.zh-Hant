---
title: 開始移轉至Customer Journey Analytics
description: 規劃從Adobe Analytics移轉至Customer Journey Analytics的程式
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a23322ab189e6469783a179e2de7aa0195eda737
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 8%

---

# 步驟1：開始移轉至Customer Journey Analytics

Customer Journey Analytics是新一代的分析產品。 它允許多管道資料收集（線上和離線資料），結合強大的報表時間處理功能（透過資料檢視中元件和衍生欄位的定義）。

開始從Adobe Analytics移轉至Customer Journey Analytics的流程之前，您應該瞭解Customer Journey Analytics的好處，以及成功移轉所需的步驟。

## 瞭解Customer Journey Analytics的好處

以下是一些主要優點：(如需完整清單，以及這些主要功能各自的相關詳細資訊，請參閱 [僅適用於Customer Journey Analytics的功能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

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

  值可以是數值、文字、物件、清單或所有專案的混合。 Dimension可以是巢狀或階層式。

## 瞭解移轉程式

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
此頁面代表移轉的步驟1，如下表所示。 完成此表格中的所有步驟，從Adobe Analytics移轉至Customer Journey Analytics。

| 任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [規劃資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

## 首先，選擇移轉方法

有多種方法可用來移轉至Customer Journey Analytics。 [選擇最適合您組織的方法](/help/getting-started/cja-migration/cja-migration-method.md).

您選擇的移轉方法取決於貴組織目前的Adobe Analytics環境和長期目標。