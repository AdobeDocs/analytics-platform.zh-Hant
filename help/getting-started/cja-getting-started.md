---
title: Customer Journey Analytics 快速入門
description: 了解實作 Customer Journey Analytics 所需的必要條件和工作流程。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: ab4b65a8948d650615cdf9b99718cbc50499e9f5
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 85%

---

# Customer Journey Analytics 快速入門

若要實施 Customer Journey Analytics，您必須依照此工作流程操作。某些初始工作需在 Adobe Experience Platform 中執行，有些則需在 Customer Journey Analytics 中執行。

## 必要條件

Customer Journey Analytics 適用於以下客戶

* 已針對 [Adobe Experience Platform](https://www.adobe.com/tw/experience-platform.html) 佈建的客戶，以及
* 已購買 Customer Journey Analytics SKU 的客戶

## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟 1：如果您要從 Adobe Analytics 移轉至 CJA，請了解該做什麼。** | 請參閱 [將Adobe Analytics報表套裝資料用於Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) 和 [從傳統Adobe Analytics擷取和使用資料](../data-ingestion/analytics.md). |
| **步驟 2：將其他資料匯入 Adobe Experience Platform** | 這個在 Adobe Experience Platform 中執行的步驟包含幾個子步驟：<ul><li>**步驟 2a：準備資料結構描述**：使用[Adobe 體驗資料模型 (Experience Data Model，XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 將客戶體驗資料標準化，並為客戶體驗管理[定義結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)。</li><li>**步驟 2b：建立以結構描述為基礎的資料集**：Platform 中的資料是由資料集所構成，例如電子郵件資料集、CRM 資料集、POS 資料集、Adobe Analytics 資料集等等。每個資料集都是由結構描述和資料批次組成。您可以[在 Experience Platform 中建立一個資料集](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 2C：擷取資料至 Experience Platform**：在這裡，您有幾個選擇。 </li></ul> |
| **步驟 3：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和工作區的資料集建立連線。<br>請參閱[建立連線](/help/connections/create-connection.md)。 |
| **步驟 4：建立資料檢視** | 資料檢視是「經過篩選」的資料查看畫面。您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 5：在工作區中製作跨管道資料報表** | 建立連線和資料檢視後，運用 Analysis Workspace 的強大功能與彈性，分析您所匯入的資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 快速入門手冊

此 [資料擷取](../data-ingestion/data-ingestion.md) 一節提供上述工作流程的快速入門手冊。 這些快速入門手冊說明如何在Adobe Experience Platform中內嵌來自各種來源(包括Adobe Analytics)的資料，然後在Customer Journey Analytics中使用這些資料。
