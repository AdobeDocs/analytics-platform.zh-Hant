---
title: 報告Marketo Engage資料
description: 瞭解如何在Customer Journey Analytics中報告Marketo Engage資料
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
TQID: https://experienceleague.adobe.com/UXeVx5LF0ww0guz-62swqmGapSfjiTduYjojcZqqIYQ
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: e430f26e2b6357a288adb4389a266f26acab68c4
workflow-type: tm+mt
source-wordcount: 1448
ht-degree: 8%

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


若要在Customer Journey Analytics中報告Marketo Engage資料，請遵循下列步驟：

+++選取ID策略

如果您想要將Marketo活動資料擷取至Customer Journey Analytics，您必須選取適當的ID策略，以確保可將Marketo資料連結至Customer Journey Analytics資料。

Marketo資料本身不包含ECID，但ECID欄位可以新增為與`munchkin.js`資料庫一起收集的自訂欄位。 新增內容會在Marketo和現有Customer Journey Analytics網頁資料之間建立共用識別碼。

若要連結Marketo和Customer Journey Analytics資料，請在相關資料集上使用[圖表式拼接](/help/stitching/gbs.md)。 您可以根據實施使用數個可用的ID：

* ECID，由Experience Platform Identity Service提供
* 電子郵件
* Munchkin ID，由Marketo Engage提供
* 經銷商ID
* 鄧恩布萊德街鄧斯\#
* Demandbase ID
* （可能為其他人）

圖表式拚接有助於以下方面：

* 保留網頁事件上的永久ID。
* 儘可能使用身分圖表來解析已知的身分（如電子郵件）。
* 如果不存在確定性比對，圖表式拚接會回覆為永久ID，而非捨棄事件。

圖表式拚接是連結Marketo和Customer Journey Analytics資料的可行解決方案，原因如下：

* Web事件資料在每一列都有永續性ID （例如ECID）。
* Marketo資料中的Munckin ID、ECID和電子郵件都是可靠的ID。
* 圖表式拚接會決定性地將ECID橋接至Munchkin ID、電子郵件或Marketo資料中可用的任何其他識別碼。
* 圖表式拚接使用明確設定的身分圖表連結規則和名稱空間。

若要驗證此ID策略，您應該執行受控的圖表式銜接試驗。

1. 在Marketo中新增ECID作為自訂欄位，並將自訂欄位新增到munckin.js使用者端JavaScript程式碼，以進行Marketo Engage資料收集。
1. 設定暫時的Customer Journey連線，其中至少包含Marketo資料集和Web事件資料集。
1. 定義狹窄的資料範圍，以帶入有限且可呈現的資料量。
1. 透過Workspace中資料檢視和報告的設定驗證彙整。 如需詳細資訊，請參閱下列步驟。

+++

+++將Marketo來源資料欄位對應至其XDM目標

將[人員](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)和[活動](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo)物件對應至它們各自的 XDM 結構描述目標欄位。

+++

+++將Marketo資料擷取至Adobe Experience Platform

使用[Marketo Engage聯結器](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo)將資料從Marketo帶到Experience Platform，並使用Experience Platform應用程式保持這些資料在最新狀態。

+++

+++ 在Customer Journey Analytics中設定此資料集的連線

若要針對Experience Platform資料集製作報表，必須先為Experience Platform和Customer Journey Analytics中的資料集建立連線。 請參閱[建立或編輯連線](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection)。

+++


+++建立一或多個資料檢視

[資料檢視](/help/data-views/data-views.md)是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。 它會指定 Analysis Workspace 中可用的所有維度和量度 (在此案例中則是 Marketo 特定的量度和維度)。 它會這些維度和量度從哪些欄取得資料。 資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

+++ 

+++Analysis Workspace中的報表

您可能會探索的一個使用案例是：您在2020年4月至6月期間潛在客戶瀏覽了多少網頁？

1. 開啟[Analytics Workspace](/help/analysis-workspace/home.md)並建立新專案。
擁有B2B/B2P CDP的客戶可以在Customer Journey Analytics中進行B2C樣式的分析。尚未提供B2B物件。

1. 為網頁檢視建立[區段](/help/components/segments/seg-create.md)，如下所示：事件型別= web.webpagedetails.pageViews：

   顯示事件和事件型別的![定義視窗](../assets/marketo-filter.png)

1. 將您建立的區段提取至自由表格 — 網頁檢視中，然後提取「月份」日期範圍。 此動作會提供您每個月潛在客戶的網頁瀏覽次數：

   ![自由表格，依月份顯示事件。](../assets/marketo-freeform.png)

1. 或提取以下維度：人員金鑰或工作電子郵件地址。 此動作會提供每個潛在客戶的網頁瀏覽次數：

   ![顯示事件和workEmail.Address及網頁檢視的自由格式表格。](../assets/marketo-freeform2.png)

Customer Journey Analytics中的Marketo Engage資料可能會與Marketo Engage報表中的內容不同。

+++


## 報表比較

以下是Customer Journey Analytics和Marketo Engage中報表的比較，詳細說明分析功能、彈性、真相來源和使用案例方面的一些重要差異。

### Customer Journey Analytics

Customer Journey Analytics是以Adobe Experience Platform為建置基礎的進階跨管道分析工具。 Customer Journey Analytics是專為需要跨數位和離線資料來源提供強大、彈性且可自訂的報表的企業團隊所設計。

#### 主要功能

* **資料來源**：可以合併多個資料集（網頁、CRM、電子郵件、客服中心、離線、Marketo等） 360°客戶歷程報告。
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
* **以行銷為中心**：著重於需要透明化funnel的行銷使用者：電子郵件統計資料、表單、智慧行銷活動以及收入影響。


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
| **量度重複資料刪除** | 對於電子郵件效能報表，量度會依潛在客戶ID、促銷活動ID及電子郵件資產ID自動進行重複資料刪除。 如果從相同電子郵件資產建立多封電子郵件，並從相同計畫傳送給相同潛在客戶，則這些電子郵件將僅計為一封電子郵件。 | 若未套用其他篩選器和量度，電子郵件報告資料會報告為沒有[量度重複資料刪除](/help/data-views/component-settings/metric-deduplication.md)的電子郵件效能總數。 |

{style="table-layout:fixed"}
