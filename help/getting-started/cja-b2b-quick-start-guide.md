---
title: Customer Journey Analytics B2B 快速入門指南
description: Customer Journey Analytics B2B Edition 的快速入門指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 100%

---


# B2B Edition 快速入門指南

若要實作 Customer Journey Analytics B2B Edition，請務必先了解 B2B 特定的概念和功能。您也應該熟悉實作 Customer Journey Analytics 的傳統工作流程。

本文件著重於 Customer Journey Analytics 實作的特定工作流程。

## 先決條件

若要實作 Customer Journey Analytics B2B Edition，以下先決條件適用：

* 您要有在 Customer Journey Analytics 中提供管理工作所需的[存取控制和權限](/help/technotes/access-control.md)。
* 您已經購買 Customer Journey Analytics B2B Edition 附加元件套件。


## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟 1：將 B2B 資料嵌入 Experience Platform** | 這個在 Experience Platform 中執行的步驟包含幾個子步驟：<ul><li>**步驟 1a：準備資料結構描述**：使用 [Adobe 體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-hant) 將 B2B 資料標準化，並為您的 B2B 資料[定義結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/schemas/b2b)。</li><li>**步驟 1b：根據結構描述建立資料集**：平台中的資料由資料集組成，例如帳戶資料、機會資料、購買群組資料、行銷活動資料、行銷清單資料、電子郵件資料集、CRM 資料集、POS 資料集等。每個資料集都是由結構描述和資料批次組成。您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/tw/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 1c：將資料攝取至 Experience Platform**：您在此有[幾個選項](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)。</li></ul> |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對 Experience Platform 資料集製作報告，必須先在 Experience Platform 和 Workspace 之間的資料集建立連線。在設定與 B2B Edition 的連線時，會有其他的選項。<br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 3：建立資料檢視** | 資料視圖是資料&#x200B;*經過篩選*&#x200B;的視圖。您可以為相同的連線建立不同的資料視圖，並針對造訪逾時、歸因等項目使用不同的設定。您可以為單一資料集建立多個資料檢視。在擁有 B2B Edition 時，設定資料視圖會有其他選項。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在工作區中製作跨管道資料報表** | 建立連線和資料檢視後，使用 Analysis Workspace 的強大功能與彈性來分析您所匯入的 B2B 資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->