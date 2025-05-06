---
title: Customer Journey Analytics B2B快速入門手冊
description: Customer Journey Analytics B2B edition快速入門手冊。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: c021dc012f74126c6d0af5cd4ffdf908dd5c696a
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---

# B2B edition快速入門手冊

{{draft-b2b}}

若要實作Customer Journey Analytics B2B edition，請務必先瞭解B2B的特定概念和功能。 此外，您也應熟悉實施Customer Journey Analytics的傳統工作流程。

本檔案著重於實作Customer Journey Analytics的特定工作流程。

## 先決條件

若要實施Customer Journey Analytics B2B edition，須符合下列必要條件：

* 您確實有必要的[存取控制及許可權](/help/technotes/access-control.md)，可在Customer Journey Analytics中提供管理工作。
* 您已購買Customer Journey Analytics B2B edition附加元件套件。


## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟1：將B2B資料匯入Experience Platform** | 這個在Experience Platform中執行的步驟涉及幾個子步驟：<ul><li>**步驟1a：準備您的資料結構描述**：使用[Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-hant)將B2B資料標準化，並為您的B2B資料[定義結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/rtcdp/schemas/b2b)。</li><li>**步驟1b：建立以結構描述為基礎的資料集**： Platform中的資料是由資料集所組成，例如帳戶資料、商機資料、購買群組資料、行銷活動資料、行銷清單資料、電子郵件資料集、CRM資料集、POS資料集等等。 每個資料集都是由結構描述和資料批次組成。您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/tw/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟1c：將資料內嵌至Experience Platform**：您有[多個選項](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)。</li></ul> |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對Experience Platform資料集製作報表，必須先為Experience Platform和Workspace中的資料集建立連線。 當您使用B2B edition設定連線時，會有其他選項。 <br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 3：建立資料檢視** | 資料檢視是&#x200B;*篩選的*&#x200B;資料檢視。 您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等專案使用不同的設定。 您可以為單一資料集建立多個資料檢視。當您使用B2B edition設定資料檢視時，會有其他選項可用。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在工作區中製作跨管道資料報表** | 建立連線和資料檢視後，運用Analysis Workspace的強大功能與彈性，分析您所匯入的B2B資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->