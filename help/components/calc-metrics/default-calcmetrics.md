---
description: Adobe提供您可使用的各種計算量度。 本頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 56%

---

# 預設計算量度

Customer Journey Analytics提供各種計算量度，以涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度的清單，以及其預期的函式和用於計算的基礎公式：

>[!NOTE]
>
>除了本頁所述的預設計算量度外，您也可以新增其他計算量度至資料檢視。
>
>您可以：
> * 新增串流媒體的預設計算量度，如 [計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 從現有量度建立自訂計算量度，如 [計算與進階計算（衍生）量度](/help/components/calc-metrics/cm-adv-functions.md).



| 計算量度名稱 | 函數 | 公式 |
|---------|----------|---------|
| 反彈率 | 只有一次點擊的造訪次數與該頁面造訪次數的比率。這可幫助您了解哪些維度項目的跳出率最高，或者查看您網站在一段時間的總跳出率。 | `[Bounces] / [Entries]` |
| 收入/訪客 | 每個網站訪客所產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 訂購量/訪客量 | 網站每位個別訪客產生的訂單或交易平均數量 | `[Orders] / [Unique Visitors]` |
| 收入/造訪 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訂購 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 訂購量/瀏覽次數 | 促使完成交易的網站造訪的百分比。 | `[Orders] / [Visits]` |
| 頁面檢視次數/瀏覽次數 | 使用者在單次造訪網站期間檢視的平均頁面數量。 | `[Page Views] / [Visits]` |
| 瀏覽/訪客 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 重新載入/頁面檢視 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 訂購協助 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 檢視特定頁面後離開網站的訪客的百分比。 | `[Exits] / [Visits]` |
| 登入率 | 在給定頁面上進入網站的訪客佔網站上工作階段總數的百分比。 | `[Entries] / [Visits]` |
| 網站平均逗留時間 | 訪客在離開或導覽離開之前在網站上逗留的平均時間量。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留時間/使用者（狀態） | 訪客在網站上逗留於特定狀態的時間長度 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 州檢視 | 應用程式的不同狀態或畫面的檢視次數 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 動作 | 應用程式中採取的動作總數 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 贏取連結點按次數 | 人們點按旨在增加網站流量的連結的次數。 | `[Campaign Click-throughs]` |
| 頁面速度 | 內容片段產生的其他頁面檢視次數。 這可協助您判斷哪些內容可促進額外參與。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作 (例如購買) 的訪客的百分比。 | `[Orders] / [Visits]` |
| 平均工作階段長度（行動） | 在單一工作階段內訪客在網站上逗留的平均時間量。 | 空白 |
| Experience Cloud ID 涵蓋範圍 | 擁有 Experience Cloud ID 的訪客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 使用受 ITP 2.1 Cookie 限制所影響的瀏覽器的不重複訪客的百分比。換句話說，客戶未使用 CNAME 實作。(這適用於透過用戶端 JavaScript 設定 Cookie 的客戶。) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 獨特訪客/7天後回訪的獨特訪客 | 在 7 天或更長時間後回訪的不重複訪客的百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 頁面檢視/不重複訪客 | 網站的每個不重複訪客的平均頁面檢視次數。 | `[Page Views] / [Unique Visitors]` |
| 造訪/訪客 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP訪客（Safari瀏覽器上的使用者），則將獨特訪客除以2或更少。 此計算量度假設您是使用用戶端JavaScript（而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用用戶端JavaScript設定Cookie的實作會受到影響。請參閱 [智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以取得詳細資訊。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 頁面檢視/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
