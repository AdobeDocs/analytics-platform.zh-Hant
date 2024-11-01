---
source-git-commit: a6f543d3b6aab06593d9fa40a5d3d6bbf4aa7c32
workflow-type: tm+mt
source-wordcount: '3977'
ht-degree: 33%

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
>您必須有&#x200B;**Prime**&#x200B;或更新版本的套件，才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

## Ultimate套件 {#ultimate-package}

>[!NOTE]
>
>您必須有&#x200B;**Ultimate**&#x200B;封裝，才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。


## 資料字典篩選條件 {#dd-filter-criteria}

1. (可選) 選取 **篩選器** 圖示 ![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然後選擇以下任一篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/components/overview.md)。 |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **篩選器**] | 僅顯示屬於篩選器的元件。 (當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **缺少說明**] | 僅顯示在說明欄位中還沒有說明的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **顯示重複項目**] | 僅顯示與所選資料檢視中其他元件具有相同名稱或相同說明的元件。 這包括您建立的元件以及Adobe提供的元件。 名稱或說明必須完全相符，才能顯示為重複專案。 此選項僅提供給管理員使用。 |
   | [!UICONTROL **無最近的資料**] | 僅顯示在過去 90 天內未收集任何資料的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **由Adobe建立**] <!-- I don't see this option--> | 僅顯示由 Adobe 建立的元件。並不會顯示由管理員或您組織中的其他使用者建立的元件。 |

   {style="table-layout:auto"}

## 資料字典元件資訊 {#dd-component-information}

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **已核准**] | <p>指出該元件已經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **取消核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「未核准」。</p> |
| [!UICONTROL **未核准**] | <p>指出該元件尚未經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「已核准」。</p> |
| [!UICONTROL **說明**] | 描述元件的預定功能。(此資訊由 Analytics 管理員新增，如[新增元件說明](/help/components/add-component-descriptions.md)中所述。) |
| [!UICONTROL **經常與下列項目搭配使用**] | <p>顯示您正在查看的元件最常與哪些元件一起使用。</p><p>在這5種主要元件型別中最多可顯示5種元件：量度、計算量度、Dimension、篩選和日期範圍。</p><p>此清單顯示過去 90 天的資料。只會顯示您有權檢視的元件。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在您組織使用者看到的元件之前，請先套用&#x200B;**全部顯示**&#x200B;篩選器，以確保您看到任何未與您共用的元件，這些元件可能已由其他管理員新增。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **類似於**] | <p>顯示與您正在查看的元件具有相似名稱的元件。</p><p>在這5種主要元件型別中最多可顯示5種元件：量度、計算量度、Dimension、篩選和日期範圍。</p><p>只會顯示您有權檢視的元件。</p><p>資料檢視中的任何重複元件都會顯示在這裡。 Analytics 管理員應識別並移除所有重複的元件，如[監視資料字典健康情況](/help/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在您組織使用者看到的元件之前，請先套用&#x200B;**全部顯示**&#x200B;篩選器，以確保您看到任何未與您共用的元件，這些元件可能已由其他管理員新增。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：**&#x200B;目前，「**類似於**」區段僅包括您建立的元件，不包括 Adobe 提供的元件。Adobe 提供的元件會在未來版本中新增。</p> |
| [!UICONTROL **產品相容性**] | 指出此計算量度可在Customer Journey Analytics中使用的位置。 <p>可能的值包括：</p><ul><li>[!UICONTROL **Customer Journey Analytics中的所有位置**]：計算量度可用於所有Customer Journey Analytics，包括Analysis Workspace、Report Builder等。</li><li>[!UICONTROL **Customer Journey Analytics中的所有位置（實驗除外）**]：計算度量可用於所有Customer Journey Analytics，實驗面板除外。</li> <p>如需判斷計算量度是否可用於實驗之條件的詳細資訊，請參閱[實驗面板](/help/analysis-workspace/c-panels/experimentation.md)中的[在Experimentation面板](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel)中使用計算量度。</p></ul> |
| [!UICONTROL **標記**] | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
| [!UICONTROL **元件類型**] | 列出其元件型別，不論是Dimension、量度、篩選器或日期範圍。 |
| [!UICONTROL **建立者**] | 顯示建立元件的使用者名稱。 |
| [!UICONTROL **預覽**] | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
| [!UICONTROL **上次修改日期**] | 顯示上次修改元件的日期。檢視篩選器、量度、計算量度和日期範圍時，會顯示此區段。 |

{style="table-layout:auto"}

## 元件排序選項 {#components-sort-options}

| 選項 | 功能 |
|---------|----------|
| **[!UICONTROL 建議]** | 根據元件的建議排序每種型別（維度、量度、篩選器和日期範圍）的元件。 您或組織中的其他人最常使用且最近使用的元件，會在每個清單中顯示在較高的位置。 |
| **[!UICONTROL 上次修改日期]** | 根據元件的上次修改日期，排序每個型別（維度、量度、篩選器和日期範圍）的元件。 最近修改的元件會顯示在每個清單中較高的位置。 |
| **[!UICONTROL 字母順序]** | 依遞增字母順序排序每個型別（維度、量度、篩選器和日期範圍）的元件。 |
| **[!UICONTROL 分類]** | 根據元件的類別來排序每個型別（維度、量度、篩選器和日期範圍）的元件。 例如已監管與未監管的資料檢視元件。 |

{style="table-layout:auto"}

## 時間比較 {#apply-time-comparison}

您可以將目前的時段與先前的時段進行比較。 如果您在此選單中選取選項，每個資料點都會收到類似顏色的虛線對應專案。 此對應專案代表所選先前日期範圍內的相同量度。 設定此選項可將圖表上的專案數和表格中的列數加倍。

可用的時間比較選項包括上一個期間、13週前、52週前以及自訂日期範圍。 如果您選取「自訂日期範圍」 ，會出現其他選項，供您選取數字和粒度。 如果您選取「無」，則會移除日期比較。


## 影片示範Adobe Analytics {#videoaa}

此影片示範使用Adobe Analytics的功能。 不過，Customer Journey Analytics也提供類似功能。 請留意下列術語差異。

| Adobe Analytics | Customer Journey Analytics |
|:---:|:---:|
| 區段 | 篩選器 |
| 訪客 | 人員 |
| 造訪 | 工作階段 |
| 點擊 | 事件 |


## 篩選器面板 {#filterspanel}

1. 選取![篩選器](/help/assets/icons/Filter.svg)開啟「篩選器」面板。如果您需要更多空間顯示篩選器清單，可以再次選取![篩選器](/help/assets/icons/Filter.svg)來關閉面板。
1. 從任何可用的篩選器區段中選取篩選器。


## 標籤篩選區段 {#tagfiltersection}

| 標記 | 說明 |
|---|---|
| ![標記](/help/assets/filter-tag.png){width="300"} | **[!UICONTROL 標籤]**&#x200B;區段可讓您依標籤篩選。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋標籤*&#x200B;來搜尋您可用來篩選的標籤。</li><li>您可以選取多個標籤。 可用的標籤取決於篩選面板中其他區段所做的選取。</li><li>數字表示：<ul><li>**(1)**：選取的標籤數目（如果選取一或多個標籤）。</li><li>**2︎⃣**：目前篩選產生的專案可用的標籤數目。</li><li>⃣7︎：與特定標籤相關聯的專案數。</li></ul></li></ul> |


## 資料檢視篩選區段 {#dataviewfiltersection}

| 資料視圖 | 說明 |
|---|---|
| ![資料檢視](/help/assets/filter-dataview.png){width="300"} | **[!UICONTROL 資料檢視]**&#x200B;區段可讓您篩選資料檢視。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋資料檢視*&#x200B;以搜尋您可用來篩選的資料檢視。</li><li>您可以選取多個資料檢視。 可用的資料檢視視視在篩選器面板的其他區段中選取的專案而定。</li><li>數字表示：<ul><li>**(2)**：選取的資料檢視數目（如果選取一或多個資料檢視）。</li><li>**3︎⃣**：目前篩選產生的專案可用的資料檢視數目。</li><li>⃣4︎：與特定資料檢視相關聯的專案數。</li></ul></li></ul> |

## 已啟用狀態篩選區段 {#enabledstatusfiltersection}

| 啟用狀態 | 說明 |
|---|---|
| ![已啟用狀態](/help/assets/filter-enabledstatus.png){width="300"} | **[!UICONTROL 啟用狀態]**&#x200B;區段可讓您篩選啟用狀態。 <ul><li>您可以選取多個狀態。</li><li>數字表示：<ul><li>**(2)**：選取的狀態數目（如果選取了一或多個狀態）。</li><li>**2︎⃣**：目前篩選產生的專案可用的狀態數目。</li><li>⃣1︎：與特定狀態相關聯的專案數。</li></ul></li></ul> |

## 輸入篩選區段 {#typefiltersection}

| 類型 | 說明 |
|---|---|
| ![類型](/help/assets/filter-type.png){width="300"} | **[!UICONTROL 型別]**&#x200B;區段可讓您依型別篩選。 <ul><li>您可以選取多個型別。</li><li>數字表示：<ul><li>**(2)**：選取的型別數目（如果選取一或多個型別）。</li><li>**1︎⃣**：目前篩選產生的專案可用的型別數目。</li><li>⃣3︎：與特定型別相關聯的專案數。</li></ul></li></ul> |

## 「擁有者篩選」區段 {#ownerfiltersection}

| 所有者 | 說明 |
|---|---|
| ![擁有者](/help/assets/filter-owners.png){width="300"} | **[!UICONTROL 所有者]**&#x200B;區段可讓您依所有者篩選。 <ul><li>您可以![搜尋](/help/assets/icons/Search.svg) *搜尋擁有者*&#x200B;來搜尋您可用來篩選的擁有者。</li><li>您可以選取多個擁有者。 可用的擁有者取決於篩選器面板中其他區段中所做的選擇。</li><li>數字表示：<ul><li>**(2)**：選取的擁有者數目（如果選取一或多個擁有者）。</li><li>**3︎⃣**：目前篩選產生的專案可用的擁有者數目。</li><li>⃣4︎：與特定擁有者相關聯的專案數。</li></ul></li></ul> |

## 其他篩選器篩選器區段 {#otherfiltersfiltersection}

| 其他篩選器 | 說明 |
|---|---|
| ![其他篩選器](/help/assets/filter-other.png){width="300"} | **[!UICONTROL 其他篩選器]**&#x200B;區段可讓您在其他預先定義的篩選器上篩選。<ul><li>您可以選取下列一或多個選項：<ul><li> **[!UICONTROL 全部顯示]**</li><li>**[!UICONTROL 與我共用]**</li><li>**[!UICONTROL 我的]**</li><li>**[!UICONTROL 已核准]**</li><li>**[!UICONTROL 我的最愛]**</li></ul> 您可以選取的專案取決於您的角色和許可權。</li><li>您可以選取多個其他篩選器。 可用的其他篩選器取決於篩選器面板中其他區段中所做的選擇。</li><li>數字表示：<ul><li>**(1)**：選取的其他篩選數目（如果選取一或多個其他篩選）。</li><li>**5︎⃣**：目前篩選產生的專案可用的其他篩選數目。</li><li>⃣4︎：與特定其他篩選器相關聯的專案數。</li></ul></li></ul> |

## 日期範圍篩選區段  {#daterangefiltersection}

| 套用的日期範圍 | 說明 |
|---|---|
| ![日期範圍](/help/assets/filter-daterange.png){width="300"} | 「套用的日期範圍」區段可讓您篩選適用於專案的日期範圍。<ol><li>選取日期範圍。</li><li>在日曆快顯視窗中定義日期範圍，或選取其中一個可用的預設集。<br>或者，您也可以直接在[篩選]面板的[日期範圍]區段中指定日期範圍。</li></ol><ul><li>數字表示：<ul><li>**(1)**：從預設預設集修改的修改日期範圍數。</li><li>**5︎⃣**：目前篩選產生的專案可用的日期範圍數。</li></ul> |


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
| ![反向J](/help/assets/icons/AttributeInverseJ.svg) | 反向 J | 會將 60% 的評分給予第一個接觸點，再將 20% 的評分給予上個接觸點，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，第一次互動會獲得75%的評分，上次則獲得25%。 此歸因模型類似於J形，偏好第一次和最後一次互動，但較偏好第一次互動。 |
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
* **工作階段**：回顧到轉換發生的工作階段開始。 工作階段回顧期間遵循資料檢視中修改的[工作階段逾時](/help/data-views/create-dataview.md#session-settings)。
* **人員（報告期間）**：回顧目前日期範圍當月第一個月的所有造訪。 例如，如果報表日期範圍為9月15日到9月30日，則人員回顧日期範圍將包含9月1日到9月30日。 如果使用此回顧期間，您偶爾會看到維度專案歸因到報表期間之外的日期。
* **自訂時間：**&#x200B;可讓您從轉換發生時設定自訂回顧期間。 您可以指定分鐘數、小時數、日數、周數、月數或季數。 例如，如果轉換發生在2月20日，5天的回顧期間將會評估歸因模型中2月15日至2月20日的所有維度接觸點。

## 歸因範例 {#attribution-example}

考量下列範例：

1. 9月15日當天，有人透過付費搜尋廣告進入您的網站後離開。
1. 9月18日當天，該人透過朋友的社群媒體連結再次造訪您的網站。 對方在購物車中加入數個商品，但並未購買任何商品。
1. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

根據您的回顧期間和歸因模型，管道會獲得不同的評分。以下是一些範例：

* 使用&#x200B;**首次接觸**&#x200B;和&#x200B;**工作階段回顧期間**，歸因只會計入第三次造訪。 在電子郵件和顯示廣告兩者之間，訪客優先接觸到電子郵件，因此電子郵件在這次 $50 美元的購買動作中有 100% 的評分。

* 使用&#x200B;**首次接觸**&#x200B;和&#x200B;**人員回顧期間**，歸因會計入全部三次造訪。 付費搜尋是第一次接觸，因此在這次 $50 美元的購買動作中有 100% 的評分。

* 使用&#x200B;**線性**&#x200B;和&#x200B;**工作階段回顧期間**，評分會由電子郵件和顯示廣告平分。 這兩個管道各有$25美元的評分。
使用**線性**&#x200B;和&#x200B;**人員回顧期間**，評分會由搜尋付費、社群媒體、電子郵件和顯示廣告平分， 每個管道在這次購買中各有 $12.50 的評分。

* 使用&#x200B;**J形**&#x200B;和&#x200B;**個人回顧期間**，評分會由搜尋付費、社群媒體、電子郵件和顯示廣告平分。

   * 60% 歸給顯示廣告，價值 $30 美元，
   * 20% 歸給付費搜尋，價值 $10 美元，
   * 剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。

* 使用&#x200B;**時間耗損**&#x200B;和&#x200B;**人員回顧期間**，評分會由付費搜尋、社交、電子郵件和顯示廣告平分。 以預設的 7 天半衰期計算，結果如下：

   * 顯示廣告接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 電子郵件接觸點與轉換之間的間隔為零天。`2^(-0/7) = 1`
   * 社交接觸點與轉換之間的間隔為六天。`2^(-6/7) = 0.552`
   * 付費搜尋接觸點與轉換之間的間隔為九天。`2^(-9/7) = 0.41`
   * 將這些值標準化會產生下列結果：

      * 顯示廣告：33.8%，價值 $16.88 美元
      * 電子郵件：33.8%，價值 $16.88 美元
      * 社交媒體：18.6%，價值 $9.32 美元
      * 付費搜尋：13.8%，價值 $6.92 美元

如果評分屬於多個管道，則通常具有整數的轉換事件會被除。 例如，如果兩個管道對使用線性歸因模型的訂單都有貢獻，則兩個管道會分別獲得該訂單的0.5倍。 這些部分量度會在所有人員之間加總，然後舍入至最接近的整數以用於報表。

## 歷程視覺效果比較 {#journey-visualization-comparisons}

Customer Journey Analytics中的各種視覺效果都是為了分析您提供給客戶的歷程。

使用下列資訊來選擇最符合您需求的視覺效果。

| 函數 | 歷程畫布 | 流失 | 流量 |
|---------|----------|---------|---------|
| **預先定義的頁面順序** | 是</br>結合預先定義與探索分析。 在路徑上使用預先定義的節點時，會使用最終路徑（只要訪客最終從一個預先定義的節點移動到另一個節點，就會計算訪客）。 也可以顯示立即（非最終）的下一個節點。 | 是</br>路徑可以是最終路徑或可限製為下一個接觸點 | 否 |
| **頁面的探索順序(Ad Hoc Analysis)** | 是</br>結合預先定義與探索分析。 在路徑上使用預先定義的節點時，會使用最終路徑（只要訪客最終從一個預先定義的節點移動到另一個節點，就會計算訪客）。 也可以顯示立即（非最終）的下一個節點。 | Limited</br>可讓您按一下滑鼠右鍵並在自由表格中檢視立即流失。 | 是</br>僅限探索性分析。 永遠在節點之間的一個維度例項內。 這表示每個節點都會顯示路徑上的即時（非最終）下一個接觸點。 |
| **顯示人員從何處離開（流失）或繼續通過（流過）** | 是</br>針對預先定義及探索歷程顯示 | 是</br>顯示預先定義的歷程 | 是</br>探索歷程的節目 |
| **線性歷程** | 有 | 是 | 無 |
| **具有多個進入點和路徑的非線性歷程** | 有 | 否 | 是 |
| **主要量度** | 任何量度，包括計算量度 | 僅限工作階段或人員 | 僅限發生次數（路徑檢視） |
| **次要量度** | 是<p>任何量度，包括計算量度</p> | 否 | 否 |
| 節點或接觸點中的&#x200B;**元件支援** | 量度、維度專案、篩選器和日期範圍。 | 量度、維度專案、篩選器和日期範圍。 | 僅限維度專案（開始和結束接觸點除外） |
| **比較篩選器** | 無 | 是<p>在同一份報表中，執行兩個不同篩選器的並排比較。</p> | 否 |
| **拖放元件互動** | 有 | 是 | 無 |
| **Adobe Journey Optimizer歷程** | 是</br>從Journey Optimizer開啟歷程，以進行更深入的分析及自訂 | 否 | 否 |

{style="table-layout:auto"}
