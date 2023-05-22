---
description: Adobe提供各種可使用的計算度量。 此頁列出這些度量及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 50%

---

# 預設計算量度

Customer Journey Analytics提供各種計算度量，以涵蓋最常見的使用情形。 這些計算的度量在Analysis Workspace預設可用。

以下是Adobe提供的每個計算度量的清單，以及其預期函式和用於計算它的基礎公式：

>[!NOTE]
>
>除了此頁中描述的預設計算度量外，您還可以向資料視圖添加其他計算度量。
>
>您可以：
> * 添加流媒體的預設計算度量，如所述 [計算的度量](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 根據現有度量建立自定義計算的度量，如中所述 [計算和高級計算（派生）度量](/help/components/calc-metrics/cm-adv-functions.md)。



| 計算的度量名稱 | 函數 | 公式 |
|---------|----------|---------|
| 反彈率 | 與該頁上的訪問次數相比，僅包含一個事件的訪問次數。 這有助於您瞭解哪些維度物料的彈跳率最高，或查看站點隨時間推移的總彈跳率。 | `[Bounces] / [Entries]` |
| 收入/訪問者 | 每個網站訪客所產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 訂購量/訪客量 | 每個訪問站點的個人生成的訂單或事務處理的平均數 | `[Orders] / [Unique Visitors]` |
| 收入/訪問 | 單次造訪網站所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訂單 | 網站上每筆完成的交易或訂單所產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 訂購量/瀏覽次數 | 促使完成交易的網站造訪的百分比。 | `[Orders] / [Visits]` |
| 頁面檢視次數/瀏覽次數 | 使用者在單次造訪網站期間檢視的平均頁面數量。 | `[Page Views] / [Visits]` |
| 訪問/訪問者 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 重裝/頁面視圖 | 導致頁面重新載入或重新整理的頁面檢視的百分比。 | `[Reloads] / [Page Views]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 訂單助攻 | 管道或來源促成客戶的購買歷程但未促成最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 檢視特定頁面後離開網站的訪客的百分比。 | `[Exits] / [Visits]` |
| 登入率 | 在給定頁面上進入網站的訪客佔網站上工作階段總數的百分比。 | `[Entries] / [Visits]` |
| 現場平均時間 | 訪客在離開或導覽離開之前在網站上逗留的平均時間量。 | `[Average Time Spent on Site (Seconds)]` |
| 花費的時間/用戶（狀態） | 訪問者在某一特定國家在站點上的平均時間 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 用戶（移動） | 移動應用的用戶總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 應用用戶 | 移動應用的用戶總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 州視圖 | 應用的不同狀態或螢幕的視圖數 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 動作 | 應用中執行的操作總數 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 獲取連結按一下 | 人們點按旨在增加網站流量的連結的次數。 | `[Campaign Click-throughs]` |
| 頁速 | 內容生成的附加頁面視圖數。 這有助於您確定哪些內容推動了更多項目。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作 (例如購買) 的訪客的百分比。 | `[Orders] / [Visits]` |
| 平均會話長度（移動） | 在單一工作階段內訪客在網站上逗留的平均時間量。 | 空白 |
| Experience Cloud ID 涵蓋範圍 | 擁有 Experience Cloud ID 的訪客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及新內容產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| ITP 2.1獨特訪問者/獨特訪問者 | 使用受 ITP 2.1 Cookie 限制所影響的瀏覽器的不重複訪客的百分比。換句話說，客戶未使用 CNAME 實作。(這適用於透過用戶端 JavaScript 設定 Cookie 的客戶。) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 7天後返回的唯一訪問者/唯一訪問者 | 在 7 天或更長時間後回訪的不重複訪客的百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 頁面視圖/唯一訪問者 | 網站的每個不重複訪客的平均頁面檢視次數。 | `[Page Views] / [Unique Visitors]` |
| 造訪/訪客 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 估計的唯一訪問者(ITP 2.1) | 對於ITP訪問者（Safari瀏覽器上的用戶），將Unique Visitor分為2個或更少。 此計算度量假定您使用客戶端JavaScript（不使用CNAME實現）設定Cookie。 從ITP 2.1開始，使用客戶端JavaScript設定Cookie的實現受到影響。請參閱 [智慧跟蹤防範](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 的雙曲餘切值。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 頁面檢視/預估的不重複訪客 (ITP 2.1) | 預估的不重複訪客 (ITP 2.1) 的平均頁面檢視次數。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
