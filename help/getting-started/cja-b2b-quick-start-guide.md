---
title: Customer Journey Analytics B2B 快速入門指南
description: Customer Journey Analytics B2B Edition 的快速入門指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
TQID: https://experienceleague.adobe.com/SjixkRCOmeUYuhZCVO7-7tLHalpnXO6QCVE1BiG9h2E
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 499
ht-degree: 77%

---

# B2B Edition 快速入門指南

若要實作 Customer Journey Analytics B2B Edition，請務必先了解 B2B 特定的概念和功能。 您也應該熟悉實作 Customer Journey Analytics 的傳統工作流程。

本文件著重於 Customer Journey Analytics 實作的特定工作流程。

## 先決條件

若要實作 Customer Journey Analytics B2B Edition，以下先決條件適用：

* 您要有在 Customer Journey Analytics 中提供管理工作所需的[存取控制和權限](/help/technotes/access-control.md)。
* 您已經購買 Customer Journey Analytics B2B Edition 附加元件套件。


## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟 1：將 B2B 資料嵌入 Experience Platform** | 這個在 Experience Platform 中執行的步驟包含幾個子步驟：<ul><li>**步驟 1a：準備資料結構描述**：使用 [Adobe 體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 將 B2B 資料標準化，並為您的 B2B 資料[定義結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/schemas/b2b)。<br/>您可以讓結構描述以Real-time CDP B2B edition[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/schemas/b2b)中提供的標準類別為基礎，或使用您自己的自訂類別和結構描述。 [使用案例](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)文章使用Real-time CDP B2B edition類別和結構描述，但是使用Real-time CDP B2B edition類別和結構描述不需要Real-time CDP授權。</li><li>**步驟 1b：根據結構描述建立資料集**：平台中的資料由資料集組成，例如帳戶資料、機會資料、購買群組資料、行銷活動資料、行銷清單資料、電子郵件資料集、CRM 資料集、POS 資料集等。 每個資料集都是由結構描述和資料批次組成。 您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/zh-hant/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 1c：將資料攝取至 Experience Platform**：您在此有[幾個選項](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)。</li></ul> |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。 若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和工作區的資料集建立連線。 在設定與 B2B Edition 的連線時，會有其他的選項。 <br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 3：建立資料檢視** | 資料視圖是資料&#x200B;*經過篩選*&#x200B;的視圖。 您可以為相同的連線建立不同的資料視圖，並針對造訪逾時、歸因等項目使用不同的設定。 您可以為單一資料集建立多個資料檢視。 當您使用B2B edition設定資料檢視時，會有其他選項。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在 Workspace 中報告您的跨管道資料** | 建立連線和資料檢視後，使用Analysis Workspace的強大功能與彈性，分析您所引進的B2B資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->