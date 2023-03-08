---
description: Adobe提供您可使用的各種計算量度。 本頁面列出這些量度及其預期用途。
title: 預設計算量度
feature: Calculated Metrics
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 4%

---

# 預設計算量度

Customer Journey Analytics提供各種計算量度，以涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度的清單，以及其預期的函式和用於計算的基礎公式：

>[!NOTE]
>
>除了本頁所述的預設計算量度外，您也可以新增其他計算量度至報表套裝。
>
>您可以：
> * 新增串流媒體的預設計算量度，如 [計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 從現有量度建立自訂計算量度，如 [計算與進階計算（衍生）量度](/help/components/calc-metrics/cm-adv-functions.md).



| 計算量度名稱 | 函數 | 公式 |
|---------|----------|---------|
| 反彈率 | 包含單一點擊的造訪次數與該頁面上的造訪次數之比。 這可協助您了解哪些維度項目具有最高的跳出率，或查看網站在一段時間內的匯總跳出率。 | `[Bounces] / [Entries]` |
| 收入/訪客 | 網站每位訪客產生的平均收入金額。 | `[Revenue] / [Unique Visitors]` |
| 訂購量/訪客量 | 網站每位個別訪客產生的訂單或交易平均數量 | `[Orders] / [Unique Visitors]` |
| 收入/造訪 | 對網站進行單次造訪所產生的平均收入金額。 | `[Revenue] / [Visits]` |
| 收入/訂購 | 網站上每個已完成的交易或訂單產生的平均收入金額。 | `[Revenue] / [Orders]` |
| 訂購量/瀏覽次數 | 導致完成交易的網站瀏覽次數的百分比。 | `[Orders] / [Visits]` |
| 頁面檢視次數/瀏覽次數 | 使用者在單次造訪網站期間檢視的平均頁面數。 | `[Page Views] / [Visits]` |
| 瀏覽/訪客 | 不重複訪客對網站的平均造訪次數。 | `[Visits] / [Unique Visitors]` |
| 重新載入/頁面檢視 | 導致重新載入或重新整理頁面的頁面檢視百分比。 | `[Reloads] / [Page Views]` |
| 加權反彈率 | 函數 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 訂購協助 | 管道或來源對客戶進行購買的歷程有貢獻，但並未導致最終購買的次數。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 檢視特定頁面後離開網站的訪客百分比。 | `[Exits] / [Visits]` |
| 登入率 | 在指定頁面上進入網站的訪客百分比，與網站上的工作階段總數相比。 | `[Entries] / [Visits]` |
| 網站平均逗留時間 | 訪客離開或離開網站前在網站上逗留的平均時間。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留時間/使用者（狀態） | 訪客在網站上逗留於特定狀態的時間長度 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 州檢視 | 應用程式的不同狀態或畫面的檢視次數 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 動作 | 應用程式中採取的動作總數 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 贏取連結點按次數 | 訪客點按專為推動網站流量而設計之連結的次數。 | `[Campaign Click-throughs]` |
| 頁面速度 | 內容片段產生的其他頁面檢視次數。 這可協助您判斷哪些內容可促進額外參與。 | `[Page Views] / [Visits]` |
| 轉換率 | 採取所需動作（例如購買）的訪客百分比。 | `[Orders] / [Visits]` |
| 平均工作階段長度（行動） | 訪客在單一工作階段期間在網站上逗留的平均時間。 | 空白 |
| Experience CloudID涵蓋範圍 | 具有Experience CloudID的訪客百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 內容速度 | 在網站上建立和發佈新內容的速度，以及其產生使用者參與的速度。 | `[Page Views] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 受ITP 2.1 Cookie限制影響的使用瀏覽器的獨特訪客百分比。 換言之，未使用CNAME實作的客戶。 （這適用於透過用戶端JavaScript設定Cookie的客戶。） | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 獨特訪客/7天後回訪的獨特訪客 | 7天或更多天後回訪的不重複訪客百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 頁面檢視/不重複訪客 | 網站每位獨特訪客的平均檢視頁數。 | `[Page Views] / [Unique Visitors]` |
| 瀏覽/訪客 | 獨特訪客對網站的平均瀏覽次數。 | `[Visits] / [Unique Visitors]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP訪客（Safari瀏覽器上的使用者），則將獨特訪客除以2或更少。 此計算量度假設您是使用用戶端JavaScript（而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用用戶端JavaScript設定Cookie的實作會受到影響。請參閱 [智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以取得詳細資訊。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 頁面檢視/預估獨特訪客(ITP 2.1) | 「預估獨特訪客」的平均檢視頁數(ITP 2.1)。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
