---
description: Adobe提供您可以使用的各種計算量度。 此頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 25%

---

# 預設計算量度

Customer Journey Analytics提供各種計算量度，涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度清單，以及其預期函式及用來計算該函式的基礎公式：

>[!NOTE]
>
>除了本頁面所述的預設計算量度外，您也可以新增其他計算量度至資料檢視。
>
>您可以：
> * 為串流媒體新增預設計算量度，如所述 [計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 從現有量度建立自訂計算量度，如所述 [計算與進階計算（衍生）量度](/help/components/calc-metrics/cm-adv-functions.md).



| 計算量度名稱 | 函數 | 公式 |
|---------|----------|---------|
| 反彈率 | 包含單一事件的造訪次數與該頁面上的造訪次數之間的比率。 這可協助您瞭解哪些維度專案具有最高的跳出率，或檢視網站在一段時間內彙總的跳出率。 | `[Bounces] / [Entries]` |
| 收入/訪客 | 網站每位個人產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 訂購量/訪客量 | 每個個人對網站產生的訂單或交易平均數量 | `[Orders] / [Unique Visitors]` |
| 收入/造訪 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訂單 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 訂購量/瀏覽次數 | 促使完成交易的網站造訪的百分比。 | `[Orders] / [Visits]` |
| 頁面檢視次數/瀏覽次數 | 使用者在單次造訪網站期間檢視的平均頁面數量。 | `[Page Views] / [Visits]` |
| 造訪/訪客 | 不重複人員造訪網站的平均次數。 | `[Visits] / [Unique Visitors]` |
| 重新載入/頁面檢視 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 訂購協助 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 在檢視特定頁面後離開網站的使用者百分比。 | `[Exits] / [Visits]` |
| 登入率 | 在指定頁面上進入網站的人員相對於網站上工作階段總數的百分比。 | `[Entries] / [Visits]` |
| 網站平均逗留時間 | 離開或瀏覽離開之前在網站上逗留的平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留時間/使用者（州） | 平均個人在網站上逗留於特定州的時間長度 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 狀態檢視 | 應用程式不同狀態或畫面的檢視次數 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 動作 | 應用程式中執行的動作總數 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 贏取連結點按次數 | 人們點按旨在增加網站流量的連結的次數。 | `[Campaign Click-throughs]` |
| 頁面速度 | 一段內容產生的其他頁面檢視次數。 這可協助您判斷哪些內容可促進更多參與。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作（例如購買）的人員百分比。 | `[Orders] / [Visits]` |
| 平均工作階段長度（行動） | 個人在單一工作階段中花費在網站上的平均時間。 | 空白 |
| Experience Cloud ID 涵蓋範圍 | 擁有Experience CloudID的人員的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 使用受ITP 2.1 Cookie限制影響的瀏覽器不重複使用者的百分比。 換句話說，是指不使用CNAME實作的客戶。 （這適用於透過使用者端JavaScript設定Cookie的客戶。） | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 不重複訪客/7天後回訪的不重複訪客 | 經過7天或更長時間後回訪的不重複人員百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 頁面檢視/不重複訪客 | 網站每位不重複人員的平均檢視頁面數。 | `[Page Views] / [Unique Visitors]` |
| 造訪/訪客 | 不重複人員造訪網站的平均次數。 | `[Visits] / [Unique Visitors]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP人員（使用Safari瀏覽器的使用者），請將不重複訪客除以2或更少。 此計算量度假設您是使用使用者端JavaScript （而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用使用者端JavaScript設定Cookie的實施會受到影響。另請參閱 [智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以取得詳細資訊。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 頁面檢視/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
