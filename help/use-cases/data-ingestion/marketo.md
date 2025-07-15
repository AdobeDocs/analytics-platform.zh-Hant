---
title: 報告Marketo Engage資料
description: 瞭解如何在Customer Journey Analytics中報告Marketo Engage資料
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 82aefce30834d6400d338896dc1968e37596393e
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 14%

---

# 報告Marketo Engage資料

您可以善用Experience Platform中可用的Marketo Engage資料集，為B2B行銷人員提供有價值的分析和報告解決方案。 然後在Customer Journey Analytics中報告這些資料集。

請注意：

* Marketo Engage報告最適合直接在Marketo中測量及最佳化行銷方案，並且快速、規範化且對行銷人員友好。
* Customer Journey Analytics為橫跨多個管道、產品和業務部門的客戶歷程提供更廣泛且可自訂的分析解決方案，包括但不限於使用Marketo資料。

如需詳細資訊，請參閱[報表比較](#reporting-comparison)。

>[!NOTE]
>
>若想從Marketo Engage資料中獲得更多價值，您不妨考慮[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)。 您可以將Marketo Engage資料集與帳戶和查詢資料集結合使用。 以及報告Customer Journey Analytics B2B edition中的帳戶和機會層級。
>


若要在Customer Journey Analytics中報告Marketo Engage日期：

+++ 1.將Marketo來源資料欄位對應至其XDM目標

將[人員](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)和[活動](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)物件對應至它們各自的 XDM 結構描述目標欄位。

+++

+++ 2.將Marketo資料擷取至Adobe Experience Platform

使用 [Marketo Engage 連接器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo)將資料從 Marketo 帶到 Experience Platform，並使用平台連線的應用程式保持這些資料在最新狀態。

+++

+++ 3.在Customer Journey Analytics中設定此資料集的連線

若要針對Experience Platform資料集製作報表，必須先為Experience Platform和Customer Journey Analytics中的資料集建立連線。 請參閱[建立或編輯連線](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection)。

+++


+++ 4.建立一或多個資料檢視

[資料檢視](/help/data-views/data-views.md)是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。它會指定 Analysis Workspace 中可用的所有維度和量度 (在此案例中則是 Marketo 特定的量度和維度)。它會這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

+++

+++ 5.Analysis Workspace中的報表

您可能會探索的一個使用案例是：您在2020年4月至6月期間潛在客戶瀏覽了多少網頁？

1. 請開啟 [Analytics Workspace](/help/analysis-workspace/home.md) 並建立新專案。擁有B2B/B2P CDP的客戶可以在Customer Journey Analytics中進行B2C樣式的分析。 尚未提供 B2B 物件。

1. 為網頁檢視建立[區段](/help/components/segments/seg-create.md)，如下所示：事件型別= web.webpagedetails.pageViews：

   顯示事件和事件型別的![定義視窗](../assets/marketo-filter.png)

1. 將您建立的區段提取至自由表格 — 網頁檢視中，然後提取「月份」日期範圍。 此動作會提供您每個月潛在客戶的網頁瀏覽次數：

   ![自由表格，依月份顯示事件。](../assets/marketo-freeform.png)

1. 或提取以下維度：人員金鑰或工作電子郵件地址。此動作會提供每個潛在客戶的網頁瀏覽次數：

   ![顯示事件和workEmail.Address及網頁檢視的自由格式表格。](../assets/marketo-freeform2.png)

Customer Journey Analytics中的Marketo Engage資料可能會與Marketo Engage報表中的內容不同。

+++


## 報表比較

以下是Customer Journey Analytics和Marketo Engage中報表的比較，詳細說明分析功能、彈性、真相來源和使用案例方面的一些重要差異。

### Customer Journey Analytics

Customer Journey Analytics是以Adobe Experience Platform為建置基礎的進階跨管道分析工具。 Customer Journey Analytics是專為需要跨數位和離線資料來源提供強大、彈性且可自訂的報表的企業團隊所設計。

#### 主要功能

* **資料來源**：可合併多個資料集(網頁、CRM、電子郵件、客服中心、離線、Marketo等)，以進行360°客戶歷程報告。
* **自助分析**：使用高度互動且可自訂儀表板和視覺效果的拖放工作區。
* **進階歸因**：支援所有連線資料的複雜、多重接觸和自訂歸因模型，而不只是行銷方案。
* **對象與路徑分析**：跨購買者歷程的深層細分、同類群組和路徑分析。
* **可操作的深入分析**：啟用資料導向的協調（例如，將深入分析傳回行銷或個人化引擎）。
* **企業規模**：適合需要企業治理、多種品牌和高資料量的組織。

#### 典型Customer Journey Analytics使用案例

* 跨多個管道和接觸點的進階客戶歷程對應。
* 複雜的分段及混合線上和離線資料。
* 用於執行層級和營運報告的自訂KPI儀表板。
* 整體歸因模型（不僅限於數位或電子郵件）。


### Marketo Engage

Marketo Engage提供應用程式內報告，著重於行銷自動化KPI、方案和行銷活動測量，以及行銷影響分析。 所有此報告都會直接繫結至Marketo中的活動。

#### 主要功能

* **原生行銷分析**：電子郵件、登陸頁面、行銷活動、銷售機會、商機、管道和收入歸因的標準報表（首次接觸、上次接觸、多重接觸）。
* **進階BI分析（附加元件）**：拖放、按一下自訂Report Builder，以分析程式/帳戶/潛在客戶資料（請參閱最近的進階BI分析概觀）。
* **預先建立儀表板**：針對行銷活動績效、管道效益、管道/收入貢獻。
* **方案和管道分析**： Marketo管理的歷程專屬歸因和ROI。
* **以行銷為中心**：著重於需要行銷漏斗透明度的使用者：電子郵件統計資料、表單、智慧行銷活動以及收入影響。


#### 典型Marketo Engage使用案例

* 追蹤並最佳化電子郵件、方案和行銷活動績效。
* 將銷售線索和管道歸因於行銷策略。
* 監控參與趨勢和對潛在客戶評分。
* 在沒有資料工程資源的情況下與銷售/行銷團隊分享見解。
* 存取立即可用、行銷人員友善的報告。


請參閱下方的Marketo Engage與Customer Journey Analytics報告功能快速比較表：

| 功能 | Marketo Engage | Customer Journey Analytics |
|---|---|---|
| **主要焦點** | 行銷方案和以行銷活動為中心的報表。 | 整體、全管道歷程和行為分析和報告。 |
| **資料來源** | 在中及透過Marketo Engage產生的資料。 | 結合來自任何Experience Platform啟用資料的資料，包括Marketo、網站、行動應用程式、離線頻道等。 |
| **歸因** | Marketo資料的單一和多點觸控歸因。 | 解決方案中任何可用資料的自訂、跨管道歸因。 |
| **自訂報告和彈性** | 適用於方案和帳戶深入剖析的進階BI （附加元件）。 | 在如何使用所有可用資料建立自訂工作區、儀表板或報表方面有高度彈性。 |
| **對象分析** | 篩選和劃分方案清單、參與和智慧清單。 | 豐富的角色和歷程視覺效果、受眾路徑分析和區段重疊分析。 |
| **目標使用者** | 行銷人員、行銷操作員、需求產生背景工作者和收入主管。 | 分析人員、資料科學家、行銷策略師、客戶體驗專業人員。 |
