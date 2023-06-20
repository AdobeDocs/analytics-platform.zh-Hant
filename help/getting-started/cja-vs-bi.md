---
title: 比較 Customer Journey Analytics 和 BI 解決方案
description: 比較 Customer Journey Analytics 和 BI 解決方案
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 66%

---

# 比較 Customer Journey Analytics 和 BI 解決方案

隨著目前對客戶體驗的關注，品牌需要進階的解決方案以便更深入了解整體的客戶歷程。了解這個完整的客戶歷程可讓您分析線上和離線管道如何吸引客戶並提高轉換率、保留率和忠誠度，並獲取有價值的深入分析。在這種情況下，客戶歷程可能是在壽司食品連鎖店直接進行線上餐點訂購。或者購買新車，此時客戶會進行線上研究以及造訪經銷商展示中心，最後再親自購買。

許多組織已將其全通路資料整合到資料湖或 Data Warehouse 中。除了這些資料儲存區之外，再使用 Business intelligence (BI) 工具來提供企業了解客戶歷程所需的報告、視覺效果和深入分析。通常，這種將解決方案和工具結合在一起的方式在本質上和設計上都是通用的，並不明確以客戶為中心。Customer Journey Analytics著重於增強負責客戶體驗的人員，例如行銷人員、資料分析師、資料科學家的能力。 該工具讓他們能夠在跨所有管道的完整背景中即時將客戶歷程視覺化，而沒有許多其他 BI 工具會有的限制。

本檔案的這個章節說明Customer Journey Analytics與常用BI工具之間的根本差異，首先是要瞭解用於達成上述目標的一般工作流程：瞭解客戶歷程。 然後，它會提供在Customer Journey Analytics和BI工具之間如何以不同方式儲存、收集和查詢資料的更多詳細資訊。 最後會說明視覺效果功能中的差異。

## 傳統的 BI 工作流程

分析客戶歷程的傳統方式有一個常見障礙，也就是並非以客戶為中心。每個團隊都獨立收集資料，根據他們有權存取的資料分析體驗並將其最佳化。

![傳統的 BI 工作流程](./assets/biworkflow.png)

如果您想了解特定的數位行銷活動如何影響儲存在不同資料孤島中的離線操作，您可以向 BI 團隊的佇列發出請求。BI 團隊會編寫所需的查詢來獲取和轉換資料。擷取到原始資料後，BI 團隊會建立視覺效果。會和您共享資料，然後您再花時間徹底調查這些深入分析並擷取資料以在其他系統中啟動。

這些步驟中的每一步都可能需要數小時、數天甚至數週的時間。如果查詢的資料有後續問題或其他問題，則可能需要更多時間才能解決這些問題，並且會繼續這樣的循環。若為對客戶歷程的持續分析、探索和理解，此流程效率不彰且無法擴充。此外，BI 團隊通常不僅於解決和客戶歷程相關的問題。

## Customer Journey Analytics：普及線上和離線資料的工作流程

Customer Journey Analytics提供的環境可在總體客戶層級連線線上和離線跨管道資料，其唯一目的是瞭解客戶歷程。 它確實需要初始設定來[連接](/help/connections/overview.md)和[定義](/help/data-views/data-views.md)您認為相關的資料的檢視。但是完成後，這些資料就可以隨時用於正在進行的分析和探索。您可以逐步深入了解客戶歷程。透過將合併的線上和離線資料大眾化，您在幾秒鐘內就能回答和客戶歷程相關的問題。

![Customer Journey Analytics工作流程](./assets/cjaworkflow.png)

您可以使用Customer Journey Analytics透過視覺化Analysis Workspace環境提出問題，並幾乎立即獲得見解。 可立即取得跨管道資料和報表，且無需 SQL 程式碼。只需在 UI 中進行簡單的拖放操作即可完成其他查詢和分析，並提供完全相關的資料。您可以繼續提問，根據需要以漸進的方式探索更多詳細資訊。然後，您可以根據所發現的深入分析立即採取行動，例如與他人共用對象以進行啟動和協調流程。

## Customer Journey Analytics強大的報告引擎

Customer Journey Analytics使用強大的專屬架構，將分析分散至數百甚至數千部伺服器，數秒內即可在Analysis Workspace中顯示資料。 該處理架構的一些值得注意的屬性包括：

* **針對個別客戶相關查詢進行最佳化**：就技術方面而言，Customer Journey Analytics會將資料儲存在大量使用快取的分散式報告引擎中。 該引擎針對個別層級事件資料的回應式查詢進行了微調，因此已對和客戶相關的查詢進行了完美的最佳化。此報表引擎會將資料儲存在欄導向的點陣圖索引中，這些索引允許對彙總量度進行快速即時的計算。它有一個廣泛的篩選引擎，可以進行強大的分段/對象分析。而且它對資料點之間的序列有一個核心的理解，這有助於分析跨這些資料點的行為 (事情發生的順序)，並使用各種複雜的模式來分配歸因。

* **快速套用複雜的路徑分析和篩選器**：此報表引擎適用於部分排序的階層式資料集 (例如，人員 -> 工作階段 -> 事件)。最高層級物件 (個別設定檔) 的所有資料都位在單一處理節點上以獲得準確的結果。這種資料劃分使得複雜的路徑分析和篩選器可快速套用。工作階段化、歸因、資料歸因的狀態持久化和複雜資料操作選項等複雜操作以快速報表時間大規模執行。在 BI 世界中，這些類型的操作通常需要為每個使用案例建立新的 OLAP多維資料集。Customer Journey Analytics報告引擎可讓您不受限制地存取每個查詢的整個資料集，產生完全相關的資料，而不需要事先進行任何刪減。

* **複雜資料串流的高效查詢**：報表引擎和傳統 SQL 以及 NoSQL 資料庫的最大一項差異在於它能夠在基本層級根據序列導向的關係確定述詞。這些基本的查詢操作可以查看由許多交錯 (甚至是巢狀的) 序列組成的記錄資料流。它們會以單一連續序列操作的效率對所有這些交織在一起的資料串流執行查詢。

* **旨在快速回答大型查詢**：報表引擎不像傳統巨量資料系統那樣通用。然而，它專門設計用於回答跨越數百萬甚至數十億條記錄 (事件資料/體驗事件) 的查詢，通常在一秒鐘內完成。不同於其他巨量資料系統，它不會透過對資料進行抽樣或預先運算它認為您可能會問的所有問題的答案來做到這一點。反之，它能夠相當快速地運算答案以支援互動式查詢使用案例。此特定設計的Customer Journey Analytics報告引擎可協助您以高速取得資料，以進行持續分析和探索，進而讓您逐步獲得對客戶歷程的見解和瞭解。

* **充當Headless BI解決方案**：您可以在一個位置定義維度、量度和篩選器，然後任何Customer Journey Analytics使用者端(包括我們的公用Customer Journey AnalyticsAPI)都可以存取這些元件。 這會從一般使用者那裡提取出複雜的查詢，並保證無論您使用哪種報表或視覺效果用戶端，結果都是相同的。

## Customer Journey Analytics獨特的視覺化功能

報表引擎是Customer Journey Analytics的基礎，可讓您逐步與該報表引擎內的所有客戶歷程資料互動並據以行動。 Customer Journey Analytics隨附一套豐富的元件，可讓您透過拖放方式以視覺化方式完成這項工作。 BI 視覺效果工具讓您能夠在 SQL 準備的資料 (由 IT 定義) 的邊界內進行探索。Customer Journey Analytics可讓您視需要劃分和切塊，而不需返回IT建立另一個SQL檢視。

「漸進式」是這裡的關鍵概念：與BI工具中的大部分視覺效果不同，Customer Journey Analytics中的視覺化拖放UI可讓您持續根據特定需求劃分資料：您可以使用相關量度、維度、篩選器（區段）、計算、時間線、註解和其他分析值，以互動方式建立視覺化查詢。

這些視覺效果元件中內建了智慧功能，例如：

* **虛擬分析師功能**&#x200B;例如[異常偵測](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)使用預測演算法和機器學習提供對於驅動資料中異常行為的因素的深入分析。

* **進階分析功能** 專門專注於客戶歷程深入分析的客戶，例如 [流量圖](/help/analysis-workspace/visualizations/c-flow/flow.md)， [歸因面板](/help/analysis-workspace/c-panels/attribution.md)， [流失率圖表](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)、和 [維度劃分](/help/components/dimensions/t-breakdown-fa.md). 開箱即用的視覺效果範例包括：

   * [透過同類群組/延遲表進行客戶保留率分析](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)，您只需在建置器中拖放量度/維度，不到 30 秒即可完成，

   * [流失](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [流程](/help/analysis-workspace/visualizations/c-flow/create-flow.md)視覺效果。不到一分鐘即可完成設定。

* **您漸進式探索的每一步所具有的分段功能**：只要您認為有意義，您隨時都能將您的對象發佈回 Experience Platform，並從那裡發佈到任何受支援的目的地。

* **工作階段化**&#x200B;那是完全[可自訂的](/help/data-views/component-settings/persistence.md)：您可決定工作階段 (作為客戶歷程中管道的一部分) 何時開始和結束。

* **監管與民主化**：在Customer Journey Analytics中建立的儀表板可以是：

   * [精心挑選](/help/analysis-workspace/curate-share/curate.md)給組織中的其他人以進行持續探索，
   * 使用 [Report Builder](/help/report-builder/report-buider-overview.md) (一種專用外掛程式) 匯出至 Excel，
   * 以各種格式[分享](/help/analysis-workspace/curate-share/share-projects.md) (分享格式包括 [PDF](/help/analysis-workspace/curate-share/download-send.md)、[CSV](/help/analysis-workspace/curate-share/download-send.md)，並透過[專用行動應用程式](/help/mobile-app/home.md)) 給那些對最終報表和/或視覺效果感興趣的人。

由於可用的視覺效果不同，很難比較Customer Journey Analytics視覺效果功能與BI工具所提供的功能。 有些BI工具具有更進階的視覺效果，但Customer Journey Analytics著重於互動和可互操作的客戶歷程視覺效果，讓您可在數秒內劃分資料，而不會針對每個額外查詢對您「收費」。


## 摘要

Customer Journey Analytics與BI工具的不同之處在於，前者可緊密整合高度最佳化、以客戶歷程為中心的報告引擎，與方便使用的工具和元件來執行分析、建置報告和進階視覺效果。 這些都來自一個單一 UI，您無需在查詢引擎和視覺效果環境之間來回移動。
