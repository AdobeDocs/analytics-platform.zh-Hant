---
title: Customer Journey Analytics B2B快速開始指南
description: 快速開始Customer Journey Analytics B2B版的指南。
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B版"
source-git-commit: 0e4e52cfd42db321c4a7a18a9b1473a67f87e785
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 22%

---

# B2B版快速開始指南

{{draft-b2b}}

要實施Customer Journey Analytics B2B版，請確保您首先瞭解特定概念和功能B2B。 此外，您應該熟悉實施Customer Journey Analytics的傳統工作流程。

本文件側重於特定於Customer Journey Analytics實施的工作流程。

## 先決條件

要實施 Customer Journey Analytics B2B 版，以下先決條件適用：

* 您具有在 Customer Journey Analytics 中提供管理任務所需的 [存取控制和許可權](/help/technotes/access-control.md) 。
* 您已經購買了 Customer Journey Analytics B2B 版附加包。


## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟 1：將數據B2B Experience Platform** | 此步驟按Experience Platform執行，涉及幾個子步驟：<ul><li>**步驟 1a：準備數據 綱要**：使用Adobe Systems體驗數據模型 （XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-hant) 標準化[B2B數據併為[B2B數據定義架構](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b)。</li><li>**步驟 1b：根據綱要**&#x200B;建立資料集：Platform中的數據由數據集組成，例如帳戶數據、商機數據、購買群組數據、行銷活動數據、行銷清單數據、電子郵件數據集、CRM 數據集、POS 數據集等。 每個資料集都是由結構描述和資料批次組成。您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/tw/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 1c：將數據引入Experience Platform**：您有多種 [選擇](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)。</li></ul> |
| **步驟 2：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要報告Experience Platform數據集，首先必須在 Experience Platform 和 工作環境 中的數據集之間建立連接。 配置與B2B版的連接時，您還有其他選項。 <br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 3：建立資料檢視** | 数据視圖是 *数据的篩選* 視圖。 您可以為同一連接創建不同的数据視圖，對造訪超時、歸因等設置不同。 您可以為單一資料集建立多個資料檢視。配置数据時有其他選項視圖擁有B2B版時，您有其他選項。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 4：在工作區中製作跨管道資料報表** | 創建連接和數據檢視后，使用 Analysis Workspace 的強大功能和靈活性分析引入的B2B數據。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 使用案例

[B2B用例](../data-ingestion/data-ingestion.md)檔提供了一個有關如何實施Customer Journey Analytics B2B Edition的示例用例。
