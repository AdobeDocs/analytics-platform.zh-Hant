---
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '4947'
ht-degree: 99%

---
# 程式碼片段

## 發佈階段有限測試 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能普遍開放使用時，便會移除此注意事項。有關 Customer Journey Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

## 發佈階段有限測試部份 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能普遍開放使用時，便會移除此注意事項。有關 Customer Journey Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

## 選取套件 {#select-package}

>[!NOTE]
>
>您必須擁有 **Select** 套件或更高版本才能使用本節所述的功能。如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## Prime 套件 {#prime-package}

>[!NOTE]
>
>您必須擁有 **Prime** 套件或更高版本才能使用本節所述的功能。如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## Ultimate 套件 {#ultimate-package}

>[!NOTE]
>
>您必須擁有 **Ultimate** 套件才能使用本節所述的功能。如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## 元件排序選項 {#components-sort-options}

| 選項 | 功能 |
|---------|----------|
| **[!UICONTROL 建議]** | 根據其建議對每種類型 (維度、量度、區段和日期範圍) 的元件進行排序。您或貴組織的其他人近期使用最頻繁的元件會顯示在每份清單的較高位置。 |
| **[!UICONTROL 上次修改日期]** | 根據其上次修改日期對每種類型 (維度、量度、區段和日期範圍) 的元件進行排序。最近修改的元件顯示於每份清單的較高位置。 |
| **[!UICONTROL 字母順序]** | 按字母升序對每種類型 (維度、量度、區段和日期範圍) 的元件進行排序。 |
| **[!UICONTROL 分類]** | 根據其類別對每種類型 (維度、量度、區段和日期範圍) 的元件進行排序。例如，已組織與非組織的資料視圖元件。 |

{style="table-layout:auto"}

## 時間比較 {#apply-time-comparison}

您可以比較目前的時段與先前的時段。如果您在此選單中選取一個選項，則每個資料點都會收到顏色類似的虛線對應項目。此對應項目代表所選取先前日期範圍內的相同量度。設定此選項將使圖表的項目數量和表格中的列數加倍。

可用的時間比較選項包括前一時段、13 週前、52 週前和自訂日期範圍。如果您選取自訂日期範圍，則會出現其他選項讓您選取數量和詳細程度。如果選取「無」，則會移除日期比較。


## 影片示範 Adobe Analytics {#videoaa}

此影片示範了使用 Adobe Analytics 的功能。不過，此功能在 Customer Journey Analytics 中也同樣可用。請注意Adobe Analytics和Customer Journey Analytics之間的術語差異（例如&#x200B;*造訪*&#x200B;與&#x200B;*工作階段*）。


## 標記篩選器區段 {#tagfiltersection}

| 標記 | 說明 |
|---|---|
| ![標記](/help/assets/filter-tag.png){width="300"} | 「**[!UICONTROL 標記]**」部分可讓您按標記進行篩選。 <ul><li>您可以使用「![搜尋](/help/assets/icons/Search.svg)」「*搜尋標記*」來搜尋可以用於篩選的標記。</li><li>您可以選取多個標記。適用標記取決於篩在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(1)**：選取的標記數量 (如果選取一個或多個標記)。</li><li>**2︎⃣**：可用於目前篩選器所產生項目的標記數量。</li><li>7︎⃣：與特定標記相關聯的項目數量。</li></ul></li></ul> |


## 資料視圖篩選器區段 {#dataviewfiltersection}

| 資料檢視 | 說明 |
|---|---|
| ![資料檢視](/help/assets/filter-dataview.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;部分可讓您篩選資料檢視。 <ul><li>您可以使用「![搜尋](/help/assets/icons/Search.svg)」「*搜尋資料檢視*」來搜尋可以用於篩選的資料檢視。</li><li>您可以選取多個資料檢視。適用資料檢視取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(2)**：選取的資料檢視的數量 (如果選取一個或多個資料檢視)。</li><li>**3︎⃣**：可用於目前篩選器所產生項目的資料檢視數量。</li><li>4︎⃣：與特定資料檢視相關聯的項目數量。</li></ul></li></ul> |

## 啟用狀態過濾器區段 {#enabledstatusfiltersection}

| 已啟用狀態 | 說明 |
|---|---|
| ![已啟用狀態](/help/assets/filter-enabledstatus.png){width="300"} | **[!UICONTROL 已啟用狀態]**&#x200B;區段讓您依照已啟用狀態進行篩選。 <ul><li>您可以選取多個狀態。</li><li>這些數字是表示：<ul><li>**(2)**：選取狀態的數量 (如果選取一個或多個狀態)。</li><li>**2︎⃣**：可用於目前篩選器所產生項目的狀態數量。</li><li>1︎⃣：與特定狀態相關聯的項目數量。</li></ul></li></ul> |

## 類型篩選器區段 {#typefiltersection}

| 類型 | 說明 |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | 「**[!UICONTROL 類型]**」區段可讓您按類型進行篩選。 <ul><li>您可以選取多個類型。</li><li>這些數字是表示：<ul><li>**(2)**：選取的類型數量 (如果選取一個或多個類型)。</li><li>**1︎⃣**：可用於目前篩選器所產生項目的類型數量。</li><li>3︎⃣：與特定類型相關聯的項目數量。</li></ul></li></ul> |

## 所有者篩選器區段 {#ownerfiltersection}

| 所有者 | 說明 |
|---|---|
| ![所有者](/help/assets/filter-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」部分可讓您篩選所有者。 <ul><li>您可使用「![搜尋](/help/assets/icons/Search.svg)」「*搜尋所有者*」來搜尋可以用於篩選的所有者。</li><li>您可以選取多個所有者。適用的所有者取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(2)**：選取所有者的數量 (如果選取一個或多個所有者)。</li><li>**3︎⃣**：可用於目前篩選器所產生項目的所有者數量。</li><li>4︎⃣：與特定所有者相關聯的項目數量。</li></ul></li></ul> |

## 其他篩選器篩選區段 {#otherfiltersfiltersection}

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](/help/assets/filter-other.png){width="300"} |  **[!UICONTROL 其他篩選器]**&#x200B;部分可讓您根據其他預先定義的篩選器進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的內容取決於您的角色和權限。</li><li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(1)**：選取的其他篩選器數量 (如果選取一個或多個其他篩選器)。</li><li>**5︎⃣**：可用於目前篩選器所產生項目的其他篩選器數量。</li><li>4︎⃣：與特定其他篩選器相關聯的項目數量。</li></ul></li></ul> |

## 日期範圍篩選器區段  {#daterangefiltersection}

| 套用的日期範圍 | 說明 |
|---|---|
| ![日期範圍](/help/assets/filter-daterange.png){width="300"} | 套用的日期範圍區段可讓您根據適用於該項目的日期範圍進行篩選。<ol><li>選取日期範圍。</li><li>在行事曆快顯視窗中定義日期範圍，或選取其中一個可用的預設集。<br>或者，您也可以直接在篩選器面板的日期範圍區段指定日期範圍。</li></ol><ul><li>這些數字是表示：<ul><li>**(1)**：從預設的預設集修改的已修改日期範圍數量。</li><li>**5︎⃣**：可用於目前篩選器所產生項目的日期範圍數量。</li></ul> |


## 歸因模型 {#attribution-models-details}

當量度的回顧期間內出現多個值時，歸因模型決定哪些維度項目可以取得該量度的評分。只有在回顧期間內設定多個維度項目時，歸因模型才適用。如果只設定一個維度項目，則無論使用何種歸因模型，該維度項目都會獲得 100% 的評分。

| 圖示 | 歸因模型 | 定義 |
| :---: | :--- | --- |
| ![上次接觸](/help/assets/icons/AttributeLastTouch.svg) | 上次接觸 | 在歸因回顧期間中首個出現的接觸點會給予 100% 的評分。對於未另行指定歸因模型的任何量度，此歸因模型通常是預設值。各組織通常在轉換時間較短的情況下使用此模型，例如分析內部搜尋關鍵字。 |
| ![首次接觸](/help/assets/icons/AttributeFirstTouch.svg) | 首次接觸 | 在歸因回顧期間中首個出現的接觸點會給予 100% 的評分。組織通常會使用此模型了解品牌認知度或客戶贏取。 |
| ![線性](/help/assets/icons/AttributeLinear.svg) | 線性 | 每個導致轉換的接觸點會給予相等的評分。那在轉換週期較長或需要較頻繁的客戶參與度時會很有用。組織通常會使用此歸因模型來衡量行動應用程式通知的有效性或訂閱型的產品。 |
| ![參與率](/help/assets/icons/AttributeParticipation.svg) | 參與率 | 會將 100% 的評分給予所有不重複接觸點。由於每個接觸點都獲得 100% 的評分，因此量度資料加總通常會超過 100%。如果維度項目在造成轉換之前多次出現，則值將重複刪除至 100%。在想要了解客戶接觸最多的接觸點時，這種歸因模型是理想的選擇。媒體組織通常會使用此模型來計算內容速度。零售組織則通常會使用此模型來瞭解其網站的哪些部分是帶來轉換的關鍵。 |
| ![同一次接觸](/help/assets/icons/AttributeSameTouch.svg) | 同一次接觸 | 在轉換發生當下的相同事件會給予 100% 的評分。如果接觸點並未在相同事件發生轉換，就會歸類於「無」之下。這種歸因模型有時等於根本沒有歸因模型。那在不希望其他事件的值影響量度如何給予維度項目評分時，就很有價值。產品或設計團隊可以使用此模型來評估轉換發生的頁面成效。 |
| ![U 型](/help/assets/icons/AttributeUShaped.svg) | U 型 | 會將 40% 的評分給予第一次互動，再將 40% 的評分給予上次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，兩者會平均獲得 50% 的評分。這種歸因模型最適合用於最重視第一次和最後一次互動，但又不想完全忽略在之間其他互動的情況。 |
| ![J 曲線](/help/assets/icons/AttributeJCurve.svg) | J 曲線 | 會將 60% 的評分給予上次互動，再將 20% 的評分給予第一次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，上次互動會獲得 75% 的評分，第一次則獲得 25%。與 U 型類似，此歸因模型偏好第一次和最後一次互動，但更加側重最後一次互動。 |
| ![反向 J](/help/assets/icons/AttributeInverseJ.svg) | 反向 J | 會將 60% 的評分給予第一個接觸點，再將 20% 的評分給予上個接觸點，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，第一次互動會獲得 75% 的評分，上次則獲得 25%。與 J 型類似，此歸因模型偏好第一次和最後一次互動，但更加側重第一次互動。 |
| ![時間耗損](/help/assets/icons/AttributeTimeDecay.svg) | 時間耗損 | 會以自訂的半衰期參數 (預設為 7 天) 進行指數耗損。每個管道的權重須視接觸點啟動和最終轉換之間所經過的時間量而定。用於判斷評分的公式為 `2^(-t/halflife)`，`t` 代表接觸點和轉換之間的時間量。 所有接觸點隨後都會標準化至 100%。適用於需要衡量特定且重要事件歸因的情境。在此事件之後發生轉換的時間愈久，給予的評分就愈少。 |
| ![自訂](/help/assets/icons/AttributeCustom.svg) | 自訂 | 可指定想給予第一個接觸點、最後一個接觸點以及兩者之間任何接觸點的權重。如果您輸入的自訂數字加總並非 100，系統也會將指定值標準化為 100%。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的互動，系統會忽略中間參數，然後將第一和最後一個接觸點標準化為 100%，再按照設定分配評分。如果您想要完整控制其歸因模型，並具有其他歸因模型無法滿足的特定需求，這個模型最理想。 |
| ![演算法](/help/assets/icons/AttributeAlgorithmic.svg) | 演算法 | 使用統計技巧動態決定所選量度的最佳評分配置。用於歸因的演算法以合作賽局理論中的 Harsanyi 利益為基礎。Harsanyi 利益是 Shapley 值解法 (命名自諾貝爾經濟學獎得主 Lloyd Shapley) 的泛論，即在一場對結果貢獻不均等的賽局中，在玩家之間分配評分。<br>從高層次來看，歸因是以玩家的聯盟計算，其中盈餘必須公平地分配。每個聯盟的盈餘分配則是根據每個子聯盟先前產生的盈餘 (或先前參與的維度項目) 遞迴決定。如需詳細資訊，請參閱 John Harsanyi 和 Lloyd Shapley 的原稿：<br>Shapley, Lloyd S. (1953)。A value for n-person games。*Contributions to the Theory of Games, 2(28)*, 307-317。<br>Harsanyi, John C. (1963)。A simplified bargaining model for the n-person cooperative game。*International Economic Review 4(2)*, 194-220。 |

{style="table-layout:auto"}

## 歸因容器 {#attribution-container}

歸因容器定義了歸因的所需範圍。可能的選項包括：

* **工作階段**：回顧至轉換發生當下該工作階段的起始處。工作階段回顧期間採用資料檢視中經過修改的[工作階段逾時](/help/data-views/create-dataview.md#session-settings)。
* **人員**：從人員容器的範圍檢視轉換情況。
* **全域帳戶** [!BADGE B2B Edition]{type=Informative}：從全域帳戶容器範圍檢視轉換情況。
* **帳戶** [!BADGE B2B Edition]{type=Informative}：從人員容器的範圍檢視轉換情況。
* **機會** [!BADGE B2B Edition]{type=Informative}：從機會容器的範圍檢視轉換情況。
* **購買群組** [!BADGE B2B Edition]{type=Informative}：從購買群組容器範圍檢視轉換情況。

## 歸因回顧期間 {#attribution-lookback-window}

歸因回顧期間是指轉換要納入接觸點時需要回顧的時間量。如果維度項目設定在回顧期間之外，則該值不會納入任何歸因計算。

* **14 天**：回顧自轉換發生時間起最多 14 天。
* **30 天**：回顧自轉換發生時間起最多 30 天。
* **60 天**：回顧自轉換發生時間起最多 60 天。
* **90 天**：回顧自轉換發生時間起最多 90 天。
* **13 個月** [!BADGE B2B Edition]{type=Informative}：回顧自轉換發生時間起最多 13 個月。
* **自訂時間：**&#x200B;讓您設定轉換發生當下的自訂回顧期間。您可以指定分鐘數、小時數、天數、週數、月數或季數。例如，如果轉換發生在 2 月 20 日，則五天的回顧期間將評估歸因模型中從 2 月 15 日到 2 月 20 日的所有維度接觸點。

## 歸因範例 {#attribution-example}

考量下列範例：

1. 9 月 15 日當天，某人透過付費搜尋廣告前往您的網站後離開。
1. 9 月 18 日當天，此人透過來自朋友的社交媒體連結再次造訪您的網站。對方在購物車中加入數個商品，但並未購買任何商品。
1. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

視您的歸因模型而定，容器和管道會得到不同的貢獻度。請參閱下表的範例：

| 模型 | 容器 | 回顧期間 | 說明 |
|---|---|---|---|
| 首次接觸 | 工作階段 | 30 天 | 歸因只會檢視第三次造訪。在電子郵件和顯示廣告兩者之間，訪客先接觸到電子郵件，因此電子郵件在這次 50 美元的購買動作中獲得 100% 的貢獻度。 |
| 首次接觸 | 人員 | 30 天 | 歸因會檢視所有三次造訪。付費搜尋是第一次接觸，因此在這次 50 美元的購買動作中獲得 100% 貢獻度。 |
| 線性 | 工作階段 | 30 天 | 貢獻度由電子郵件和顯示廣告平分。兩個管道各獲得 25 美元的貢獻度。 |
| 線性 | 人員 | 30 天 | 貢獻度由付費搜尋、社交媒體、電子郵件和顯示廣告平分。每個管道在這次購買中各獲得 12.50 美元的貢獻度。 |
| J 形 | 人員 | 30 天 | 貢獻度由付費搜尋、社交媒體、電子郵件和顯示廣告平分。<ul><li>60% 歸給顯示廣告，價值 $30 美元，</li><li>20% 歸給付費搜尋，價值 $10 美元，</li><li>剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。</li></ul> |
| 時間耗損 | 人員 | 30 天 | <ul><li>顯示廣告接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`</li><li>電子郵件接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`</li><li>社交媒體接觸點與轉換之間的間隔為六天。`2^(-6/7) = 0.552`</li><li>付費搜尋接觸點與轉換之間的間隔為九天。`2^(-9/7) = 0.41`</li>將這些值標準化會產生下列結果：<ul><li>顯示廣告：33.8%，價值 $16.88 美元</li><li>電子郵件：33.8%，價值 $16.88 美元</li><li>社交媒體：18.6%，價值 $9.32 美元</li><li>付費搜尋：13.8%，價值 $6.92 美元</li></ul></li></ul> |

 如果評分屬於多個管道，則轉換事件數 (通常為整數) 將拆分。舉例來說，如果兩個管道對某個使用線性歸因模型的訂單都有貢獻，則兩個管道各會從該訂單中獲得 0.5 評分。這些部分量度在經過所有人的加總後，會四捨五入為最接近的整數，顯示於報表中。

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} 使用特定的 B2B 容器 (例如帳戶或機會) 以及更合適的回顧期間 (最多 13 個月)，在典型的 B2B 情境中套用上述歸因模型。

## 歷程視覺化比較 {#journey-visualization-comparisons}

Customer Journey analytics 的各種視覺化是為分析您提供給客戶的歷程所設計的。

使用以下資訊選擇最符合需求的視覺化。

| 函數 | 歷程畫布 | 流失 | 流量 |
|---------|----------|---------|---------|
| **預先定義的頁面序列** | 是</br>結合預先定義的探索性分析。在使用路徑上預先定義的節點時，將使用最終路徑 (只要訪客最終從一個預先定義的節點移到另一個預先定義的節點，就會納入計算)。可以透過[根據現有節點顯示頂端節點](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)來顯示立即 (非最終) 的下一個節點。 | 是</br>此路徑可以是最終路徑，也可以受限到下一個接觸點 | 否 |
| **頁面的探索性序列 (臨時分析)** | 是</br>結合預先定義的探索性分析。在使用路徑上預先定義的節點時，將使用最終路徑 (只要訪客最終從一個預先定義的節點移到另一個預先定義的節點，就會納入計算)。可以透過[根據現有節點顯示頂端節點](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)來顯示立即 (非最終) 的下一個節點。 | 有限的</br>讓您按一下右鍵並在自由格式表中檢視立即的流失。 | 是</br>僅探索性分析。始終在節點之間的一個維度執行個體內。這表示每個節點顯示的是路徑上立即 (非最終) 的下一個接觸點。 |
| **顯示人們離開 (流失) 和繼續前進 (流過) 之處** | 是</br>顯示預先定義的探索性歷程。 | 是</br>顯示預先定義的歷程 | 是</br>顯示探索性歷程 |
| **線性歷程** | 有 | 是 | 無 |
| **具有多個進入點和路徑的非線性歷程。** | 有 | 否 | 是 |
| **主要量度** | 任何量度，包括計算量度。 | 僅工作階段或人員 | 僅發生次數 (路徑檢視) |
| **次要量度** | 是<p>任何量度，包括計算量度。</p> | 否 | 否 |
| **節點或接觸點中的元件支援** | 量度、維度項目、區段和日期範圍。 | 量度、維度項目、區段和日期範圍。 | 僅限於維度項目 (起始和結束接觸點除外) |
| **比較區段** | 無 | 是<p>在同一份報告中，執行兩個不同區段的並排比較。</p> | 否 |
| **拖放元件互動** | 有 | 是 | 無 |
| **Adobe Journey Optimizer 歷程** | 是</br>從 Journey Optimizer 打開歷程以進行更深入的分析和自訂。 | 否 | 否 |

{style="table-layout:auto"}

## 升級檢查清單註釋 {#upgrade-note}

>[!NOTE]
> 
>回答 Customer Journey Analytics 升級指南的問題時，請使用本頁面上的資訊。<br><br>若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL Workspace]** 」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。

## 升級檢查清單註釋後續步驟 {#upgrade-note-step}

>[!NOTE]
> 
>只有在完成所有先前的升級步驟後，才可按照此頁面所列的步驟進行。您可以依建議的升級步驟進行 (適用於大多數組織的建議)，也可以依照使用 Customer Journey Analytics 升級指南為貴組織動態產生的步驟進行。 <ul><li>**建議的升級步驟** (適用於大多數組織的建議)<p>引導至理想的 Customer Journey Analytics 實作的一組步驟。</p><p>如需詳細資訊，請參閱[從 Adobe Analytics 升級至 Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics 升級指南**(針對貴組織具體需求所量身打造的自訂步驟)<p>新的升級指南現已推出，可動態產生適合您組織和獨特情況的升級步驟。</p><p>若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。</p></li></ul>

## 升級檢查清單最後步驟 {#upgrade-final-step}

1. 繼續依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或 Customer Journey Analytics 升級指南所動態產生的升級步驟。若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。


## 草稿版的 Content Analytics 文件。 {#draft-aca}

>[!WARNING]
>
>本文是草稿版 Content Analytics 文件的一部分。所有草稿版的 Content Analytics 文件仍然會變更，且本文的目前版本或任何屬於 Content Analytics 文件的其他文章均不具法律效力。
>


## 草稿版的 Customer Journey Analytics B2B Edition 文件 {#draft-b2b}

>[!AVAILABILITY]
>
>本文所描述的功能，以及任何標記為 [!BADGE B2B Edition]{type=Informative} 的文章或功能，目前上處於發佈的有限測試階段，且可能尚未提供於您的環境中。<br/>此外，[!BADGE B2B Edition]{type=Informative} 的功能以及 [!BADGE B2B Edition]{type=Informative} 功能的文件可能會變更，且不會衍生任何法律義務。<br/>此功能開放使用時，便會移除此備註。有關 Customer Journey Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。
>


## B2B Edition {#b2b-edition}

>[!INFO]
>
>在此文件中，特定 B2B 文章或功能 (僅適用於 Customer Journey Analytics B2B Edition) 會標記為 [!BADGE B2B 版本]{type=Informative}。


## 常用資料集設定 {#common-dataset-settings}

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 匯入新資料]** | 如果您想建立持續的連線，請啟用此選項。透過持續連線，新增至資料集中的新資料批次將在 Workspace 中自動可用。 |
| **[!UICONTROL 資料集回填]** | 啟用「**[!UICONTROL 回填所有現有資料]**」以確保回填所有現有資料。<br/><br/>選取「**[!UICONTROL 要求回填]**」以回填特定期間的歷史資料。您最多可以定義 10 個資料集回填期間。<ol><li>透過輸入開始和結束資料或使用 ![日曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)選取日期來定義期間。</li><li>選取「**[!UICONTROL 將回填排入佇列]**」將回填加入清單，或選取「**[!UICONTROL 取消]**」以取消。</li></ol>對於每個項目，選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)以編輯期間，或選取 ![刪除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg)以刪除該項目。<br/><br/>關於回填：<ul><li>您可以個別回填每個資料集。</li><li>系統會優先處理新增至連線中資料集的新資料，因此新資料的延遲最低。</li><li>所有回填 (歷史) 資料的匯入速度都會比較慢。歷史資料多寡會影響延遲長度。</li><li>Analytics 來源連接器可為生產沙箱可匯入最多 13 個月的資料 (不論資料量多寡)。非生產沙箱的回填期限制為 3 個月。</li><li>對於生產沙箱，如果您已獲得額外 SKU 授權，使您能匯入超過 13 個月的歷史回填資料，請聯絡 Adobe 以請求擴充的回填。</li></ul> |
| **[!UICONTROL 批次狀態]** | 可能的狀態指標包括：<ul><li>成功</li><li>正在處理 X 個回填</li><li>關閉</li></ul> |
| **[!UICONTROL 資料集 ID]** | 此 ID 是自動產生的。 |
| **[!UICONTROL 說明]** | 建立資料集時為資料集提供的說明。 |
| **[!UICONTROL 記錄數量]** | 資料集的大小。 |
| **[!UICONTROL 結構描述]** | 在 Adobe Experience Platform 中建立資料集所根據的結構描述。 |
| **[!UICONTROL 資料集]** | 資料集的名稱。 |
| **[!UICONTROL 預覽：*資料集名稱&#x200B;*]** | 預覽資料集的前 10 列和前 10 欄。 |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 移除]** | 無需刪除整個連線就可以[刪除資料集](/help/connections/create-connection.md#delete-a-dataset)。從連線刪除資料集可降低資料攝取的相關成本，以及重新建立整個連線和相關資料檢視的繁複流程。 |

## 標準維度 {#standard-dimensions}

| 元件名稱 | 備註 |
|---|---|
| 15 分鐘 | 發生指定事件的每個 15 分鐘區間 (無條件捨去)。第一個維度項目是日期範圍中的第一個 15 分鐘，最後一個維度項目是日期範圍中的最後一個 15 分鐘。 |
| 30 分鐘 | 發生指定事件的每個 30 分鐘區間 (無條件捨去)。第一個維度項目是日期範圍中的第一個 30 分鐘，最後一個維度項目是日期範圍中的最後一個 30 分鐘。 |
| 5 分鐘 | 發生指定事件的每個 5 分鐘區間 (無條件捨去)。第一個維度項目是日期範圍中的第一個 5 分鐘，最後一個維度項目是日期範圍中的最後一個 5 分鐘。 |
| [!UICONTROL 日] | 指定事件發生的日。第一個維度項目是日期範圍中的第一天，最後一個維度項目是日期範圍中的最後一天。 |
| [!UICONTROL 星期幾] | 指定事件發生的日子是星期幾。第一個維度項目是日期範圍中的第一天是星期幾，最後一個維度項目是日期範圍中的最後一天是星期幾。 |
| [!UICONTROL 幾月幾號] | 指定事件發生的日子是幾月幾號。第一個維度項目是日期範圍中該月的第一天，最後一個維度項目是日期範圍中該月的最後一天。 |
| 事件深度 | 對工作階段中的每個事件互動指派連續的數值 (1、2、3 等)。透過此維度，您可以針對特定事件在[您為資料視圖所定義的有期限的體驗工作階段](/help/data-views/session-settings.md#session-settings)內，在使用者互動順序流程中出現的位置，進行詳細追蹤和分析。您可以追蹤有期限的工作階段內事件從開始到完成的進展。比如：訪客登陸您的首頁 (事件 1，工作階段開始)，使用搜尋功能 (事件 2)，檢視產品詳細資料頁面 (事件 3)，加入到購物車 (事件 4)，前往結帳 (事件 5)，然後完成購買 (事件 6，工作階段結束)。現在，您可以在區段定義中，根據互動深度使用[!UICONTROL 事件深度]來將資料細分。 |
| [!UICONTROL 小時] | 指定事件發生的小時 (無條件捨去)。第一個維度項目是日期範圍中的第一小時，最後一個維度項目是日期範圍中的最後一小時。 |
| [!UICONTROL 當天幾點] | 指定事件發生在當天幾點 (無條件捨去)。第一個維度項目是日期範圍中當日的第一個小時，最後一個維度項目是日期範圍中當日的最後一個小時。 |
| [!UICONTROL 分鐘] | 指定事件發生的分鐘 (無條件捨去)。第一個維度項目是日期範圍中的第一分鐘，最後一個維度項目是日期範圍中的最後一分鐘。 |
| [!UICONTROL 一小時中的分鐘] | 指定事件發生的那個小時的分鐘 (無條件捨去)。第一個維度項目是日期範圍中那個小時的第一分鐘，最後一個維度項目是日期範圍中那個小時的最後一分鐘。 |
| [!UICONTROL 月] | 指定量度發生的月。第一個維度項目是日期範圍中的第一個月，最後一個維度項目是日期範圍中的最後一個月。 |
| [!UICONTROL 一年中的月份] | 發生指定事件那一年的月份。第一個維度項目是日期範圍中那一年的第一個月，最後一個維度項目是日期範圍中那一年的最後一個月。 |
| [!UICONTROL 季] | 指定量度發生的季。第一個維度項目是日期範圍中的第一個季節，最後一個維度項目是日期範圍中的最後一個季度。 |
| [!UICONTROL 一年中的季度] | 發生指定事件那一年的季度。第一個維度項目是日期範圍中那一年的第一季，最後一個維度項目是日期範圍中那一年的最後一季。 |
| [!UICONTROL 秒] | 指定事件發生的秒數 (無條件捨去)。第一個維度項目是日期範圍中的第一秒，最後一個維度項目是日期範圍中的最後一秒。 |
| [!UICONTROL 週] | 指定量度發生的週。第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。 |
| [!UICONTROL 一年中的週] | 發生指定事件那一年的週。第一個維度項目是日期範圍中那一年的第一週，最後一個維度項目是日期範圍中那一年的最後一週。 |
| [!UICONTROL 年] | 指定量度發生的年。第一個維度項目是日期範圍中的第一年，最後一個維度項目是日期範圍中最近的一年。 |


## 標準量度 {#standard-metrics}

| 元件名稱 | 備註 |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 帳戶] | 根據 [!UICONTROL Connection] 中所指定的帳戶 ID。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 購買群組] | 購買群組，根據 [!UICONTROL Connection] 中指定的購買群組 ID。 |
| [!UICONTROL 事件] | [!UICONTROL Connection] 中所有事件資料集的列數。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 全域帳戶] | 根據 [!UICONTROL Connection] 中指定的全域帳戶 ID。 |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 機會] | 機會，根據 [!UICONTROL Connection] 中指定的機會 ID。 |
| [!UICONTROL 人員] | 根據 [!UICONTROL Connection] 中指定的人員 ID。 |
| [!UICONTROL 工作階段結束] | 工作階段中作為最後一個事件的事件數目。類似於[!UICONTROL 工作階段開始]，其也可用於區段定義中，以劃分至每個工作階段的最後一個事件。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>工作階段結束率</li></p> |
| [!UICONTROL 工作階段開始] | 工作階段中作為第一個事件的事件數目。在用於區段定義時 (例如「[!UICONTROL 工作階段開始]存在」)，其只劃分出每個工作階段的第一個事件。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>工作階段開始率</li></p> |
| [!UICONTROL 工作階段] | 根據資料視圖的工作階段設定。 |
| [!UICONTROL 逗留時間 (秒)] | 將維度中兩個不同數值之間的時間加總。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>每人逗留時間</li><li>每工作階段逗留時間</li></p> |
