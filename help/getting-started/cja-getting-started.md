---
title: Customer Journey Analytics 快速入門指南
description: 了解實施 Customer Journey Analytics 所需的必要條件和工作流程。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 7b824c914187854e9779ebdc51c5f5d6e77f6b16
workflow-type: ht
source-wordcount: '786'
ht-degree: 100%

---

# 快速入門指南

若要實施 Customer Journey Analytics，您必須依照此工作流程操作。某些初始工作需在 Adobe Experience Platform 中執行，有些則需在 Customer Journey Analytics 中執行。

## 必要條件

Customer Journey Analytics 適用於以下客戶

* 已針對 [Adobe Experience Platform](https://www.adobe.com/tw/experience-platform.html) 佈建的客戶，以及
* 已購買 Customer Journey Analytics SKU 的客戶

## 工作流程

| 任務 | 詳細資料 |
| --- | --- |
| **步驟 1：如果您要從 Adobe Analytics 升級至 Customer Journey Analytics：選擇升級路徑，並將資料傳送至 Adobe Experience Platform** | 從 Adobe Analytics 升級至 Customer Journey Analytics 時，有許多不同的可用路徑。每種可能的升級路徑都有其自身的優點和缺點，適合一個組織的路徑可能不是另一個組織的合理選擇。 <p>若要開始從 Adobe Analytics 升級至 Customer Journey Analytics，請執行下列任一動作：</p><ul><li>遵循 Adobe 建議的升級路徑。如需更多資訊，請參閱[從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</li><li>了解所有可用的升級路徑，並選擇最適合您組織的路徑。如需更多資訊，請參閱[開始升級到 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)。</li></ul> |
| **步驟 2：將其他資料匯入 Adobe Experience Platform** | 這個在 Adobe Experience Platform 中執行的步驟包含幾個子步驟：<ul><li>**步驟 2a：準備資料結構描述**：使用[Adobe 體驗資料模型 (Experience Data Model，XDM)](https://experienceleague.adobe.com/tw/docs/experience-platform/xdm/home.html?lang=zh-Hant) 將客戶體驗資料標準化，並為客戶體驗管理[定義結構描述](https://experienceleague.adobe.com/tw/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)。</li><li>**步驟 2b：建立以結構描述為基礎的資料集**：Platform 中的資料是由資料集所構成，例如電子郵件資料集、CRM 資料集、POS 資料集、Adobe Analytics 資料集等等。每個資料集都是由結構描述和資料批次組成。您可以[在 Experience Platform 中建立資料集](https://experienceleague.adobe.com/tw/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=zh-Hant)。</li><li>**步驟 2C：擷取資料至 Experience Platform**：在這裡，您有幾個選擇。</li></ul> |
| **步驟 3：建立 Platform 資料集和 Customer Journey Analytics 之間的連線** | 連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對 Experience Platform 資料集製作報表，必須先為 Experience Platform 和工作區的資料集建立連線。<br>請參閱「[建立或編輯連線](/help/connections/create-connection.md)」。 |
| **步驟 4：建立資料檢視** | 資料檢視是「經過篩選」的資料查看畫面。您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。<br>請參閱[建立資料檢視](/help/data-views/create-dataview.md)。 |
| **步驟 5：移植報告 API 使用情況**</br>&#x200B;僅在從 Adobe Analytics 遷移時適用 | Customer Journey Analytics 報告 API 採用相同的格式，但使用不同的端點。將報告 API 使用情況從 Adobe Analytics 報告 API 移植到 Customer Journey Analytics 報告 API。 |
| **步驟 6：考慮資料摘要和 Data Warehouse 使用案例**</br>&#x200B;僅在從 Adobe Analytics 遷移時適用 | 決定如何使用 Customer Journey Analytics 中提供的匯出選項，以便用最佳方式複製您在 Adobe Analytics 中使用的資料摘要和 Data Warehouse 功能。<!-- link to docs Rob is creating --> |
| **步驟 7：遷移專案和元件**</br>&#x200B;僅在從 Adobe Analytics 遷移時適用 | Adobe Analytics 中的元件遷移區域可讓您將專案及其關聯元件從 Adobe Analytics 遷移到 Customer Journey Analytics。<p>移轉過程包括：</p><ul><li>在 Customer Journey Analytics 中重新建立 Adobe Analytics 專案。</li><li>將 Adobe Analytics 報表套件中的維度和指標對應到 Customer Journey Analytics 資料視圖中的維度和指標。</li></ul><p>在開始移轉之前，首先[準備將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/tw/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)。</p><p>完成所有必要的準備工作後，您可以[將元件和專案從 Adobe Analytics 移轉到 Customer Journey Analytics](https://experienceleague.adobe.com/tw/docs/analytics/admin/admin-tools/component-migration/component-migration.html)。</p> |
| **第 8 步：規劃使用者上線** | 如同在 Adobe Analytics 一樣，Analysis Workspace 是 Customer Journey Analytics 中面向使用者的主要工具。不過，在 Customer Journey Analytics 中使用 Analysis Workspace 時，使用者需要注意一些主要差異。<p>您應該給使用者充足的時間 (3 - 6 個月) 來熟悉 Analysis Workspace 在 Customer Journey Analytics 中的主要差異。</p><p>有關 Adobe Analytics 和 Customer Journey Analytics 之間一些主要差異的資訊，請參閱「[Adobe Analytics 使用者的使用手冊](/help/getting-started/aa-to-cja-user.md)」。</p> |
| **步驟 9：在 Workspace 中報告您的跨管道資料** | 建立連線和資料檢視後，運用 Analysis Workspace 的強大功能與彈性，分析您所匯入的資料。<br>請參閱[執行基本分析](/help/analysis-workspace/perform-basic-analysis.md)和[執行進階分析](/help/analysis-workspace/perform-adv-analysis.md)。 |

## 快速入門指南

[資料擷取](../data-ingestion/data-ingestion.md)章節提供上述工作流程的快速入門指南。這些快速入門指南說明如何在 Adobe Experience Platform 從各種來源 (包括 Adobe Analytics) 擷取資料，然後在 Customer Journey Analytics 中使用該資料。
