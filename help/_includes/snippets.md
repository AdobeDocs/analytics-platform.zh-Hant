---
source-git-commit: a7350b6fc8fa75de07238543ed0db48af42b7577
workflow-type: tm+mt
source-wordcount: '5207'
ht-degree: 39%

---
# 程式碼片段

## 發佈階段有限測試 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。

## 發佈階段有限測試部份 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。

## 選取封裝 {#select-package}

>[!NOTE]
>
>您必須有&#x200B;**Select**&#x200B;封裝或更新版本，才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## Prime套件 {#prime-package}

>[!NOTE]
>
>您必須有&#x200B;**Prime**&#x200B;套件或更新版本，才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## Ultimate套件 {#ultimate-package}

>[!NOTE]
>
>您必須有&#x200B;**Ultimate**&#x200B;套件，才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## 元件排序選項 {#components-sort-options}

| 選項 | 功能 |
|---------|----------|
| **[!UICONTROL 建議]** | 根據元件的建議排序每種型別（維度、量度、區段和日期範圍）的元件。 您或組織中的其他人最常使用且最近使用的元件，會在每個清單中顯示在較高的位置。 |
| **[!UICONTROL 上次修改日期]** | 根據元件的上次修改日期，排序每個型別（維度、量度、區段和日期範圍）的元件。 最近修改的元件會顯示在每個清單中較高的位置。 |
| **[!UICONTROL 字母順序]** | 依遞增字母順序排序每個型別（維度、量度、區段和日期範圍）的元件。 |
| **[!UICONTROL 分類]** | 根據元件的類別來排序每個型別（維度、量度、區段和日期範圍）的元件。 例如已監管與未監管的資料檢視元件。 |

{style="table-layout:auto"}

## 時間比較 {#apply-time-comparison}

您可以將目前的時段與先前的時段進行比較。 如果您在此選單中選取選項，每個資料點都會收到類似顏色的虛線對應專案。 此對應專案代表所選先前日期範圍內的相同量度。 設定此選項可將圖表上的專案數和表格中的列數加倍。

可用的時間比較選項包括上一個期間、13週前、52週前以及自訂日期範圍。 如果您選取「自訂日期範圍」 ，會出現其他選項，供您選取數字和粒度。 如果您選取「無」，則會移除日期比較。


## 影片示範Adobe Analytics {#videoaa}

*此影片示範使用Adobe Analytics的功能。 不過，此功能在 Customer Journey Analytics 中也同樣可用。請注意Adobe Analytics和Customer Journey Analytics之間的術語差異（例如「造訪」與「工作階段」）。*


## 標籤篩選區段 {#tagfiltersection}

| 標記 | 說明 |
|---|---|
| ![標記](/help/assets/filter-tag.png){width="300"} | 「**[!UICONTROL 標記]**」部分可讓您按標記進行篩選。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋標籤*&#x200B;來搜尋您可用來篩選的標籤。</li><li>您可以選取多個標記。適用標記取決於篩在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(1)**：選取的標籤數目（如果選取一或多個標籤）。</li><li>**2︎⃣**：目前篩選產生的專案可用的標籤數目。</li><li>⃣7︎：與特定標籤相關聯的專案數。</li></ul></li></ul> |


## 資料檢視篩選區段 {#dataviewfiltersection}

| 資料檢視 | 說明 |
|---|---|
| ![資料檢視](/help/assets/filter-dataview.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;部分可讓您篩選資料檢視。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋資料檢視*&#x200B;以搜尋您可用來篩選的資料檢視。</li><li>您可以選取多個資料檢視。適用資料檢視取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(2)**：選取的資料檢視數目（如果選取一或多個資料檢視）。</li><li>**3︎⃣**：目前篩選產生的專案可用的資料檢視數目。</li><li>⃣4︎：與特定資料檢視相關聯的專案數。</li></ul></li></ul> |

## 已啟用狀態篩選區段 {#enabledstatusfiltersection}

| 啟用狀態 | 說明 |
|---|---|
| ![已啟用狀態](/help/assets/filter-enabledstatus.png){width="300"} | **[!UICONTROL 啟用狀態]**&#x200B;區段可讓您篩選啟用狀態。 <ul><li>您可以選取多個狀態。</li><li>這些數字是表示：<ul><li>**(2)**：選取的狀態數目（如果選取了一或多個狀態）。</li><li>**2︎⃣**：目前篩選產生的專案可用的狀態數目。</li><li>⃣1︎：與特定狀態相關聯的專案數。</li></ul></li></ul> |

## 輸入篩選區段 {#typefiltersection}

| 類型 | 說明 |
|---|---|
| ![Type](/help/assets/filter-type.png){width="300"} | **[!UICONTROL 型別]**&#x200B;區段可讓您依型別篩選。 <ul><li>您可以選取多個型別。</li><li>這些數字是表示：<ul><li>**(2)**：選取的型別數目（如果選取一或多個型別）。</li><li>**1︎⃣**：目前篩選產生的專案可用的型別數目。</li><li>⃣3︎：與特定型別相關聯的專案數。</li></ul></li></ul> |

## 「擁有者篩選」區段 {#ownerfiltersection}

| 所有者 | 說明 |
|---|---|
| ![所有者](/help/assets/filter-owners.png){width="300"} | 「**[!UICONTROL 所有者]**」部分可讓您篩選所有者。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋擁有者*&#x200B;來搜尋您可用來篩選的擁有者。</li><li>您可以選取多個所有者。適用的所有者取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(2)**：選取的擁有者數目（如果選取一或多個擁有者）。</li><li>**3︎⃣**：目前篩選產生的專案可用的擁有者數目。</li><li>⃣4︎：與特定擁有者相關聯的專案數。</li></ul></li></ul> |

## 其他篩選器篩選器區段 {#otherfiltersfiltersection}

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](/help/assets/filter-other.png){width="300"} |  **[!UICONTROL 其他篩選器]**&#x200B;部分可讓您根據其他預先定義的篩選器進行篩選。<ul><li>您可以選取下列其中一個或更多選項:<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的內容取決於您的角色和權限。</li><li>您可以選取多個其他篩選器。適用的其他篩選器取決於在篩選器面板其他部分所做的選擇。</li><li>這些數字是表示：<ul><li>**(1)**：選取的其他篩選數目（如果選取一或多個其他篩選）。</li><li>**5︎⃣**：目前篩選產生的專案可用的其他篩選數目。</li><li>⃣4︎：與特定其他篩選器相關聯的專案數。</li></ul></li></ul> |

## 日期範圍篩選區段  {#daterangefiltersection}

| 套用的日期範圍 | 說明 |
|---|---|
| ![日期範圍](/help/assets/filter-daterange.png){width="300"} | 「套用的日期範圍」區段可讓您篩選適用於專案的日期範圍。<ol><li>選取日期範圍。</li><li>在日曆快顯視窗中定義日期範圍，或選取其中一個可用的預設集。<br>或者，您也可以直接在[篩選]面板的[日期範圍]區段中指定日期範圍。</li></ol><ul><li>這些數字是表示：<ul><li>**(1)**：從預設預設集修改的修改日期範圍數。</li><li>**5︎⃣**：目前篩選產生的專案可用的日期範圍數。</li></ul> |


## 歸因模型 {#attribution-models-details}

在量度的回顧期間中看到多個值時，歸因模型會決定哪些維度專案會獲得量度的評分。 歸因模型僅適用於回顧期間中設定了多個維度專案時。 如果僅設定單一維度專案，則無論使用何種歸因模型，該維度專案都會獲得100%的評分。

| 圖示 | 歸因模型 | 定義 |
| :---: | :--- | --- |
| ![上次接觸](/help/assets/icons/AttributeLastTouch.svg) | 上次接觸 | 會將100%的評分給予轉換前發生的最近一次接觸點。 如果沒有另外指定歸因模型，此歸因模型通常是任何量度的預設值。 組織通常會在轉換時間相對較短的情況下使用此模型，例如分析內部搜尋關鍵字。 |
| ![首次接觸](/help/assets/icons/AttributeFirstTouch.svg) | 首次接觸 | 會將100%的評分給予歸因回顧期間中首個出現的接觸點。 組織通常會使用此模型來瞭解品牌知名度或客戶贏取。 |
| ![線性](/help/assets/icons/AttributeLinear.svg) | 線性 | 會將相等的評分歸給每個帶來轉換的接觸點。 當轉換週期較長或需要更頻繁的客戶參與時，這個變數很有用。 組織通常會使用此歸因模型，來衡量行動應用程式通知效果或訂閱型產品。 |
| ![參與率](/help/assets/icons/AttributeParticipation.svg) | 參與率 | 會將 100% 的評分給予所有不重複接觸點。由於每個接觸點都會獲得100%的評分，量度資料的總和通常會超過100%。 如果維度專案出現多次而促成轉換，則會將值刪除重複資料至100%。 如果您想要瞭解客戶最常接觸到哪些接觸點，此歸因模型是理想的選擇。 媒體組織通常會使用此模型來計算內容速度。 零售組織通常會使用此模型來瞭解網站的哪些部分是帶來轉換的關鍵。 |
| ![同一次接觸](/help/assets/icons/AttributeSameTouch.svg) | 同一次接觸 | 會將100%的評分給予轉換發生的相同事件。 如果接觸點並未在同一次轉換事件中發生，則會歸類在「無」當中。 此歸因模型有時等於完全沒有歸因模型。 若您不希望其他會影響量度將評分給予維度專案之事件的值，這個選項就十分實用。 產品或設計團隊可以使用此模型來評估轉換發生的頁面帶來的成效。 |
| ![U形](/help/assets/icons/AttributeUShaped.svg) | U 型 | 會將 40% 的評分給予第一次互動，再將 40% 的評分給予上次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，兩者會各獲得50%的評分。 此歸因模型最適合用於您最重視第一個和最後一個互動，但不想完全排除兩者之間的其他互動的情境。 |
| ![J曲線](/help/assets/icons/AttributeJCurve.svg) | J 曲線 | 會將 60% 的評分給予上次互動，再將 20% 的評分給予第一次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，上次互動會獲得75%的評分，第一次則獲得25%。 此歸因模型與U形模型類似，偏向於首次和最後一次互動，但較偏向於最後一次互動。 |
| ![反向 J](/help/assets/icons/AttributeInverseJ.svg) | 反向 J | 會將 60% 的評分給予第一個接觸點，再將 20% 的評分給予上個接觸點，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，第一次互動會獲得75%的評分，上次則獲得25%。 此歸因模型類似於J形，偏好第一次和最後一次互動，但較偏好第一次互動。 |
| ![時間耗損](/help/assets/icons/AttributeTimeDecay.svg) | 時間耗損 | 會以自訂的半衰期參數 (預設為 7 天) 進行指數耗損。每個管道的權重須視接觸點啟動和最終轉換之間所經過的時間量而定。用於判斷評分的公式為 `2^(-t/halflife)`，`t` 代表接觸點和轉換之間的時間量。 所有接觸點隨後都會標準化為100%。 最適合您要針對特定且重要事件測量歸因的情況。 在此事件之後發生轉換的時間越長，獲得的評分就越少。 |
| ![自訂](/help/assets/icons/AttributeCustom.svg) | 自訂 | 可讓您指定要賦予給第一個接觸點、最後一個接觸點以及兩者之間的任何接觸點的權重。 如果您輸入的自訂數字加總並非 100，系統也會將指定值標準化為 100%。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的互動，系統會忽略中間參數，然後將第一個和最後一個接觸點標準化為100%，再據此指派評分。 如果您想要完整控制歸因模型，且具有其他歸因模型無法滿足的特定需求，則這個模型是分析師的理想選擇。 |
| ![演算法](/help/assets/icons/AttributeAlgorithmic.svg) | 演算法 | 使用統計技術動態判斷所選量度的最佳評分配置。 用於歸因的演算法以合作賽局理論中的 Harsanyi 利益為基礎。Harsanyi 利益是 Shapley 值解法 (命名自諾貝爾經濟學獎得主 Lloyd Shapley) 的泛論，即在一場對結果貢獻不均等的賽局中，在玩家之間分配評分。<br>歸因的高層級計算方式為必須公平分配盈餘的玩家聯盟。 每個聯盟的盈餘分配則根據每個子聯盟先前產生的盈餘（或先前參與的維度專案）遞回決定。 如需更多詳細資訊，請參閱John Harsanyi和Lloyd Shapley的原稿：<br>Shapley， Lloyd S. (1953)。 A value for n-person games。*Contributions to the Theory of Games, 2(28)*, 307-317。<br>Harsanyi， John C. (1963)。 A simplified bargaining model for the n-person cooperative game。*International Economic Review 4(2)*, 194-220。 |

{style="table-layout:auto"}

## 歸因回顧期間 {#attribution-lookback-window}

回顧期間是指轉換要納入接觸點時需要回顧的時間量。如果在回顧期間之外設定維度專案，此值不會納入任何歸因計算中。

* **14天**：從轉換發生時算起，最多可回顧14天。
* **30天**：從轉換發生時起，回顧最多30天。
* **60天**：回顧轉換發生後的60天。
* **90天**：回顧轉換發生後的90天。
* **13個月** [!BADGE B2B edition]{type=Informative}：回顧轉換發生後的13個月。
* **工作階段**：回顧到轉換發生的工作階段開始。 工作階段回顧期間遵循資料檢視中修改的[工作階段逾時](/help/data-views/create-dataview.md#session-settings)。
* **人員（報告期間）**：回顧目前日期範圍當月第一個月的所有造訪。 例如，如果報表日期範圍為9月15日到9月30日，則人員回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **全域帳戶（報告期間）** [!BADGE B2B edition]{type=Informative}：回顧到目前日期範圍當月第一個月的所有全域帳戶。 例如，如果報表日期範圍為9月15日到9月30日，則全域帳戶回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **帳戶（報告期間）** [!BADGE B2B edition]{type=Informative}：回顧到目前日期範圍當月第一個月的所有帳戶。 例如，如果報表日期範圍為9月15日到9月30日，則帳戶回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **機會（報告期間）** [!BADGE B2B edition]{type=Informative}：回顧目前日期範圍當月第一個月的所有機會。 例如，如果報表日期範圍為9月15日到9月30日，則機會回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **購買群組（報告期間）** [!BADGE B2B edition]{type=Informative}：回顧到目前日期範圍當月第一個月的所有購買群組。 例如，如果報表日期範圍為9月15日到9月30日，購買群組回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **自訂時間：**&#x200B;可讓您從轉換發生時設定自訂回顧期間。 您可以指定分鐘數、小時數、日數、周數、月數或季數。 例如，如果轉換發生在2月20日，5天的回顧期間將會評估歸因模型中2月15日至2月20日的所有維度接觸點。

## 歸因範例 {#attribution-example}

考量下列範例：

1. 9 月 15 日當天，某人透過付費搜尋廣告前往您的網站後離開。
1. 9 月 18 日當天，此人透過來自朋友的社交媒體連結再次造訪您的網站。對方在購物車中加入數個商品，但並未購買任何商品。
1. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

根據您的回顧期間和歸因模型，管道會獲得不同的評分。以下為幾個範例：

* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「工作階段回顧期間」**，歸因只會計入第三次造訪。在電子郵件和顯示廣告兩者之間，訪客優先接觸到電子郵件，因此電子郵件在這次 $50 美元的購買動作中有 100% 的評分。

* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「個人回顧期間」**，歸因會計入全部三次造訪。付費搜尋是第一次接觸，因此在這次 $50 美元的購買動作中有 100% 的評分。

* 如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「工作階段回顧期間」**，評分會由電子郵件和顯示廣告拆分，兩個管道各有 $25 美元的評分。如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告平分，每個管道在這次購買中各有 $12.50 的評分。

* 如果採用&#x200B;**「J 形」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分，

   * 60% 歸給顯示廣告，價值 $30 美元，
   * 20% 歸給付費搜尋，價值 $10 美元，
   * 剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。

* 如果採用&#x200B;**「時間耗損」**&#x200B;和&#x200B;**「個人回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分。以預設的 7 天半衰期計算，結果如下：

   * 顯示廣告接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 電子郵件接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 社交媒體接觸點與轉換之間的間隔為六天。`2^(-6/7) = 0.552`
   * 付費搜尋接觸點與轉換之間的間隔為九天。`2^(-9/7) = 0.41`
   * 將這些值標準化會產生下列結果：

      * 顯示廣告：33.8%，價值 $16.88 美元
      * 電子郵件：33.8%，價值 $16.88 美元
      * 社交媒體：18.6%，價值 $9.32 美元
      * 付費搜尋：13.8%，價值 $6.92 美元

 如果評分屬於多個管道，則轉換事件數 (通常為整數) 將拆分。舉例來說，如果兩個管道對某個使用線性歸因模型的訂單都有貢獻，則兩個管道各會從該訂單中獲得 0.5 評分。這些部分量度在經過所有人的加總後，會四捨五入為最接近的整數，顯示於報表中。

## 歷程視覺效果比較 {#journey-visualization-comparisons}

Customer Journey Analytics中的各種視覺效果都是為了分析您提供給客戶的歷程。

使用下列資訊來選擇最符合您需求的視覺效果。

| 函數 | 歷程畫布 | 流失 | 流量 |
|---------|----------|---------|---------|
| **預先定義的頁面順序** | 是</br>結合預先定義與探索分析。 在路徑上使用預先定義的節點時，會使用最終路徑（只要訪客最終從一個預先定義的節點移動到另一個節點，就會計算訪客）。 [也可以根據現有節點](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)顯示排名最前的節點，來顯示立即（非最終）的下一個節點。 | 是</br>路徑可以是最終路徑或可限製為下一個接觸點 | 否 |
| **頁面的探索順序(Ad Hoc Analysis)** | 是</br>結合預先定義與探索分析。 在路徑上使用預先定義的節點時，會使用最終路徑（只要訪客最終從一個預先定義的節點移動到另一個節點，就會計算訪客）。 [也可以根據現有節點](/help/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md#show-the-top-nodes-based-on-existing-nodes)顯示排名最前的節點，來顯示立即（非最終）的下一個節點。 | Limited</br>可讓您按一下滑鼠右鍵並在自由表格中檢視立即流失。 | 是</br>僅限探索性分析。 永遠在節點之間的一個維度例項內。 這表示每個節點都會顯示路徑上的即時（非最終）下一個接觸點。 |
| **顯示人員從何處離開（流失）或繼續通過（流過）** | 是</br>針對預先定義及探索歷程顯示。 | 是</br>顯示預先定義的歷程 | 是</br>探索歷程的節目 |
| **線性歷程** | 有 | 是 | 無 |
| **具有多個進入點和路徑的非線性歷程** | 有 | 否 | 是 |
| **主要量度** | 任何量度，包括計算量度。 | 僅限工作階段或人員 | 僅限發生次數（路徑檢視） |
| **次要量度** | 是<p>任何量度，包括計算量度。</p> | 否 | 否 |
| 節點或接觸點中的&#x200B;**元件支援** | 量度、維度專案、區段和日期範圍。 | 量度、維度專案、區段和日期範圍。 | 僅限維度專案（開始和結束接觸點除外） |
| **比較區段** | 無 | 是<p>在同一份報告中，執行兩個不同區段的並排比較。</p> | 否 |
| **拖放元件互動** | 有 | 是 | 無 |
| **Adobe Journey Optimizer歷程** | 是</br>從Journey Optimizer開啟歷程，以進行更深入的分析及自訂。 | 否 | 否 |

{style="table-layout:auto"}

## 升級檢查清單備註 {#upgrade-note}

>[!NOTE]
> 
>在Customer Journey Analytics升級指南中回答問題時，請使用本頁上的資訊。 <br><br>若要從Customer Journey Analytics存取指南，請選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 接著按照畫面上的指示進行操作。

## 升級檢查清單備註後續步驟 {#upgrade-note-step}

>[!NOTE]
> 
>只有在完成所有先前的升級步驟後，才可按照此頁面所列的步驟進行。您可以遵循建議的升級步驟（建議大多陣列織使用），也可以使用Customer Journey Analytics升級指南來遵循為您的組織動態產生的步驟。 <ul><li>**建議的升級步驟** （建議大多陣列織使用）<p>引導您實現理想Customer Journey Analytics實作的一組步驟。</p><p>如需詳細資訊，請參閱[從Adobe Analytics升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升級指南** （根據您組織的特定需求量身打造的自訂步驟）<p>新的升級指南現已推出，可動態產生適合您組織和獨特情況的升級步驟。</p><p>若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。</p></li></ul>

## 升級檢查清單最後步驟 {#upgrade-final-step}

1. 繼續遵循Customer Journey Analytics升級指南中的[建議升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或動態產生的升級步驟。 若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。


## Content Analytics檔案草稿 {#draft-aca}

>[!WARNING]
>
>本文是Content Analytics檔案草稿的一部分。 所有Content Analytics檔案草稿仍可能會有所變更，且目前版本的本文或Content Analytics檔案包含的任何其他文章均不會產生任何法律義務。
>


## Customer Journey Analytics B2B edition檔案草稿 {#draft-b2b}

>[!AVAILABILITY]
>
>本文所述的功能，以及任何其他以[!BADGE B2B edition]{type=Informative}標示的功能都處於發行的有限測試階段，可能尚未在您的環境中提供。 <br/>此外，[!BADGE B2B edition]{type=Informative} [!BADGE B2B edition]{type=Informative}功能的功能和檔案可能會有所變更，因此無法從中衍生任何法律義務。<br/>此附註將在功能正式可用時移除。 如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。
>


## B2B edition {#b2b-edition}

>[!INFO]
>
>在此檔案中，僅適用於Customer Journey Analytics B2B edition的特定B2B文章或功能會標示[!BADGE B2B edition]{type=Informative}。


## 通用資料集設定 {#common-dataset-settings}

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 匯入新資料]** | 如果您想建立持續的連線，請啟用此選項。透過持續連線，新增至資料集中的新資料批次將在 Workspace 中自動可用。 |
| **[!UICONTROL 資料集回填]** | 啟用「**[!UICONTROL 回填所有現有資料]**」以確保回填所有現有資料。<br/><br/>選取「**[!UICONTROL 要求回填]**」以回填特定期間的歷史資料。您最多可以定義 10 個資料集回填期間。<ol><li>透過輸入開始和結束資料或使用 ![日曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)選取日期來定義期間。</li><li>選取「**[!UICONTROL 將回填排入佇列]**」將回填加入清單，或選取「**[!UICONTROL 取消]**」以取消。</li></ol>對於每個項目，選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)以編輯期間，或選取 ![刪除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg)以刪除該項目。<br/><br/>關於回填：<ul><li>您可以個別回填每個資料集。</li><li>系統會優先處理新增至連線中資料集的新資料，因此新資料的延遲最低。</li><li>所有回填 (歷史) 資料的匯入速度都會比較慢。歷史資料多寡會影響延遲長度。</li><li>Analytics 來源連接器可為生產沙箱可匯入最多 13 個月的資料 (不論資料量多寡)。非生產沙箱的回填期限制為 3 個月。</li></ul> |
| **[!UICONTROL 批次狀態]** | 可能的狀態指標包括：<ul><li>成功</li><li>正在處理 X 個回填</li><li>關閉</li></ul> |
| **[!UICONTROL 資料集 ID]** | 此 ID 是自動產生的。 |
| **[!UICONTROL 說明]** | 建立資料集時為資料集提供的說明。 |
| **[!UICONTROL 記錄數量]** | 資料集的大小。 |
| **[!UICONTROL 結構描述]** | 在 Adobe Experience Platform 中建立資料集所根據的結構描述。 |
| **[!UICONTROL 資料集]** | 資料集的名稱。 |
| **[!UICONTROL 預覽：*資料集名稱&#x200B;*]** | 預覽資料集的前 10 列和前 10 欄。 |
| ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) **[!UICONTROL 移除]** | 您可以[刪除資料集](/help/connections/create-connection.md#delete-a-dataset)，而不刪除整個連線。 從連線中刪除資料集可減少資料擷取的相關成本，以及重新建立整個連線和相關資料檢視的繁複流程。 |

## 標準維度 {#standard-dimensions}

| 元件名稱 | 附註 |
|---|---|
| 15 分鐘 | 指定事件發生的每15分鐘（無條件舍去）。 第一個維度專案是日期範圍中的前15分鐘，最後一個維度專案是日期範圍中的前15分鐘。 |
| 30 分鐘 | 指定事件發生的每30分鐘（無條件舍去）。 第一個維度專案是日期範圍中的前30分鐘，最後一個維度專案是日期範圍中的前30分鐘。 |
| 5 分鐘 | 指定事件發生後的每5分鐘（無條件舍去）。 第一個維度專案是日期範圍中的前15分鐘，最後一個維度專案是日期範圍中的前5分鐘。 |
| [!UICONTROL 日] | 指定事件發生的天。第一個維度項目是日期範圍中的第一天，最後一個維度項目是日期範圍中的最後一天。 |
| [!UICONTROL 日期] | 指定量度在一個月中發生的日期。 第一個維度專案是日期範圍中該月的第一天，最後一個維度專案是日期範圍中該月的最後一天。 |
| [!UICONTROL 星期] | 指定量度在一週中發生的日子。 第一個維度專案是日期範圍中一週的第一天，最後一個維度專案是日期範圍中一週的最後一天。 |
| [!UICONTROL 日期] | 指定量度在一個月中發生的日期。 第一個維度專案是日期範圍中該月的第一天，最後一個維度專案是日期範圍中該月的最後一天。 |
| 事件深度 | 將循序數值（1、2、3等）指派給工作階段中的每個事件互動。 您可以使用此維度，在您為資料檢視[&#128279;](/help/data-views/session-settings.md#session-settings)定義的限定體驗工作階段中，針對使用者互動的循序流程中，啟用特定事件發生的詳細追蹤和分析。 您可以在限定工作階段中追蹤事件的從開始到結束的進度。 例如：訪客登陸您的首頁（事件1、工作階段開始）、使用搜尋功能（事件2）、檢視產品詳細資料頁面（事件3）、新增到購物車（事件4）、繼續結帳（事件5），以及完成購買（事件6、工作階段結束）。 您現在可以在區段定義中使用[!UICONTROL 事件深度]，根據互動深度來劃分資料。 |
| [!UICONTROL 小時] | 指定事件發生的小時 (無條件捨去)。第一個維度項目是日期範圍中的第一小時，最後一個維度項目是日期範圍中的最後一小時。 |
| [!UICONTROL 小時] | 指定事件在一天中發生的小時（無條件舍去）。 第一個維度專案是日期範圍中一天的第一小時，最後一個維度專案是日期範圍中一天的最後一小時。 |
| [!UICONTROL 分鐘] | 指定事件發生的分鐘 (無條件捨去)。第一個維度項目是日期範圍中的第一分鐘，最後一個維度項目是日期範圍中的最後一分鐘。 |
| [!UICONTROL 分鐘小時] | 指定事件發生的一小時中的分鐘（無條件舍去）。 第一個維度專案是日期範圍中該小時的第一分鐘，最後一個維度專案是日期範圍中該小時的最後一分鐘。 |
| [!UICONTROL 月] | 指定量度發生的月。第一個維度項目是日期範圍中的第一個月，最後一個維度項目是日期範圍中的最後一個月。 |
| [!UICONTROL 月份] | 指定量度發生的月份。 第一個維度專案是日期範圍中一年的第一個月，最後一個維度專案是日期範圍中一年的最後一個月。 |
| [!UICONTROL 季度] | 指定量度發生的季。第一個維度項目是日期範圍中的第一季，最後一個維度項目是日期範圍中的最後一季。 |
| [!UICONTROL 季別] | 指定量度發生的季別。 第一個維度專案是日期範圍中一年的第一個季度，最後一個維度專案是日期範圍中一年的最後一個季度。 |
| [!UICONTROL 秒] | 指定事件發生的秒數 (無條件捨去)。第一個維度項目是日期範圍中的第一秒，最後一個維度項目是日期範圍中的最後一秒。 |
| [!UICONTROL 週] | 指定量度發生的週。第一個維度項目是日期範圍中的第一週，最後一個維度項目是日期範圍中的最後一週。 |
| [!UICONTROL 一年中的週數] | 指定量度發生的周別。 第一個維度專案是日期範圍中一年的第一週，最後一個維度專案是日期範圍中一年的最後一週。 |
| [!UICONTROL 年] | 指定量度發生的年。第一個維度項目是日期範圍中的第一年，最後一個維度項目是日期範圍中最近的一年。 |


## 標準量度 {#standard-metrics}

| 元件名稱 | 附註 |
| --- | --- |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 帳戶] | 根據[!UICONTROL 連線]中所指定的帳戶 ID。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 購買群組] | 購買群組，根據[!UICONTROL 連線]中所指定的購買群組 ID。 |
| [!UICONTROL 事件] | [!UICONTROL 連線]中所有事件資料集的列數。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 全域帳戶] | 根據[!UICONTROL 連線]中所指定的全域帳戶 ID。 |
| [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL 機會] | 機會，根據[!UICONTROL 連線]中所指定的機會 ID。 |
| [!UICONTROL 人員] | 根據[!UICONTROL 連線]中所指定的人員 ID。 |
| [!UICONTROL 工作階段結束] | 工作階段中最後一個事件的事件數。類似於[!UICONTROL 工作階段開始]，其也可用於區段定義中，以劃分至每個工作階段的最後一個事件。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>工作階段結束率</li></p> |
| [!UICONTROL 工作階段開始] | 工作階段中第一個事件的事件數。在用於區段定義時 (例如「[!UICONTROL 工作階段開始]存在」)，其只劃分出每個工作階段的第一個事件。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>工作階段開始率</li></p> |
| [!UICONTROL 工作階段] | 根據資料檢視的工作階段設定。 |
| [!UICONTROL 逗留時間 (秒)] | 為維度加總兩個不同值之間的時間。<p>此元件必須納入您的資料檢視中，以便工作區可使用以下[計算量度](/help/components/calc-metrics/default-calcmetrics.md)： <ul><li>每人逗留時間</li><li>每工作階段逗留時間</li></p> |
