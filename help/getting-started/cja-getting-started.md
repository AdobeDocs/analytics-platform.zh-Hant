---
title: Customer Journey Analytics 快速入門
description: 了解實作 Customer Journey Analytics 所需的必要條件和工作流程。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 51%

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
| **步驟1：如果您要從Adobe Analytics移轉至Customer Journey Analytics：選擇移轉路徑，並將資料傳送至Adobe Experience Platform** | 從Adobe Analytics移轉至Customer Journey Analytics時，有多種路徑可供使用。 每個可能的移轉路徑都有其各自的優缺點，而最適合一個組織的路徑可能不適合另一個組織。 <p>若要開始從Adobe Analytics移轉至Customer Journey Analytics，請參閱 [開始移轉至Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **步驟 2：將其他資料匯入 Adobe Experience Platform** | 這個在 Adobe Experience Platform 中執行的步驟包含幾個子步驟：<ul><li>**步驟 2a：準備資料綱要**：使用[Adobe 體驗資料模型 (Experience Data Model，XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 將客戶體驗資料標準化，並為客戶體驗管理[定義綱要](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)。</li><li>**步驟 2b：建立以綱要為基礎的資料集**：Platform 中的資料是由資料集所構成，例如電子郵件資料集、CRM 資料集、POS 資料集、Adobe Analytics 資料集等等。每個資料集都是由綱要和資料批次組成。您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 2C：擷取資料至 Experience Platform**：在這裡，您有幾個選擇。</li></ul> |
| **步驟 3：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和工作區的資料集建立連線。<br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 4：建立資料檢視** | 資料檢視是「經過篩選」的資料查看畫面。您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟5：連線報表API使用情形**</br>&#x200B;僅適用於從Adobe Analytics移轉時 | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟6：說明資料摘要和Data Warehouse使用案例**</br>&#x200B;僅適用於從Adobe Analytics移轉時 | 決定如何使用Customer Journey Analytics中可用的匯出選項，以最好的方式復寫您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 <!-- link to docs Rob is creating --> |
| **步驟7：移轉專案和元件**</br>&#x200B;僅適用於從Adobe Analytics移轉時 | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。<p>如需有關在Customer Journey Analytics中複製Adobe Analytics專案，以及從Adobe Analytics報表套裝對應專案元件到Customer Journey Analytics資料檢視的資訊，請參閱 [將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html).</p> |
| **步驟8：規劃使用者上線** | 就像在Adobe Analytics中一樣，Analysis Workspace是Customer Journey Analytics中主要面向使用者的工具。 不過，在Customer Journey Analytics中使用Analysis Workspace時有一些使用者需注意的主要差異。<p>您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。</p><p>如需Adobe Analytics和Customer Journey Analytics之間部分主要差異的詳細資訊，請參閱 [Adobe Analytics使用者使用指南](/help/getting-started/aa-to-cja-user.md).</p> |
| **步驟 9：在工作區中製作跨管道資料報表** | 建立連線和資料檢視後，運用 Analysis Workspace 的強大功能與彈性，分析您所匯入的資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 快速入門指南

[資料擷取](../data-ingestion/data-ingestion.md)章節提供上述工作流程的快速入門指南。這些快速入門指南說明如何在 Adobe Experience Platform 從各種來源 (包括 Adobe Analytics) 擷取資料，然後在 Customer Journey Analytics 中使用該資料。
