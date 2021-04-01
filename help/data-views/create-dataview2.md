---
title: 如何在Customer Journey Analytics中建立新的資料檢視。
description: 說明建立新資料檢視所需的所有設定。
translation-type: tm+mt
source-git-commit: 5de8faaf750dacaafe885f0c475f7240126f302f
workflow-type: tm+mt
source-wordcount: '2607'
ht-degree: 6%

---


# 建立新的資料檢視

>[!IMPORTANT]
>
>此功能將於2021年4月22日正式推出。

建立資料檢視需要從架構元素建立度量和維度或使用標準元件。 建立量度或維度可為您提供極大的彈性。 以前，假設您在Adobe Experience Platform有資料集，則會使用字串欄位做為維度，而數值欄位作為度量。 為了變更這些欄位，您必須在「平台」中編輯您的架構。 資料檢視UI現在允許[更自由定義量度和維度](/help/data-views/data-views.md)。 如需更多使用案例，請參閱[資料檢視使用案例](/help/data-views/data-views-usecases.md)。

## 1.設定資料檢視設定和容器

1. 在 Customer Journey Analytics 中，前往&#x200B;**[!UICONTROL 「資料檢視」]**&#x200B;標籤。
2. 按一下&#x200B;**[!UICONTROL 添加]**&#x200B;以建立新資料視圖並配置其設定。

![](assets/new-data-view.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 連線] | 此欄位會將資料檢視連結至您先前建立的連線，其中包含一或多個Adobe Experience Platform資料集。 |
| [!UICONTROL 名稱] | 必須為資料檢視命名。 |
| [!UICONTROL 說明] | 詳細說明並非必要，但建議使用。 |
| [!UICONTROL 時區] | 選擇您要在哪個時區顯示資料。 |
| [!UICONTROL 標記] | 標記可用來將資料檢視整理到不同類別中。 |
| [!UICONTROL 容器] | 您可以在此處重新命名容器，這是容器在任何以此資料檢視為基礎的工作區專案中的顯示方式。 容器用於篩選和流失／流量等，以定義範圍或內容的寬度或範圍。 [深入了解](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| [!UICONTROL 人員容器名稱是……] | [!UICONTROL 人員] （預設）。[!UICONTROL Person]容器包含指定時間範圍內訪客的每次瀏覽和頁面檢視。 您可以將它重新命名為「使用者」或您偏好的任何其他詞語。 |
| [!UICONTROL 作業容器名稱是……] | [!UICONTROL 工作階段] （預設值）。[!UICONTROL Session]容器可讓您識別特定作業的頁面互動、促銷活動或轉換。 您可將它重新命名為「造訪」或您偏好的任何其他詞語。 |
| [!UICONTROL 事件容器名稱是……] | [!UICONTROL Event] （預設）。[!UICONTROL Event]容器定義您要在篩選器中包含或排除哪些頁面事件。 |

接下來，您可以從架構元素建立度量和維度。 您也可以使用標準元件。

## 2.從架構元素建立度量和維度

1. 在[!UICONTROL Customer Journey Analytics] > [!UICONTROL 資料視圖]中，按一下[!UICONTROL 元件]頁籤。

![](assets/components-tab.png)

您可以在左上角看到[!UICONTROL Connection]，其中包含資料集，以及下面的[!UICONTROL Schema欄位]。 已存在的元件是標準必需的元件（系統生成）。

1. 現在，從左側導軌拖曳架構欄位（例如[!UICONTROL pageTitle]）至「量度」或「Dimension」區段。

   您可以多次將相同的架構欄位拖曳至維度或量度區段，並以不同的方式設定相同的維度或量度。
例如，從**[!UICONTROL pageTitle]**&#x200B;欄位，您可以重新命名右側的&#x200B;**[!UICONTROL 元件名稱]**，以建立名為「產品頁面」的維度，以及另一個「錯誤頁面」等。 從&#x200B;**[!UICONTROL pageTitle]**;欄位中，您也可以從字串值建立量度。 例如，您可以建立一或多個具有不同歸因設定且不同包含／排除值的&#x200B;**[!UICONTROL 訂購]**&#x200B;量度。

   ![](assets/components-tab-3.png)

   >[!NOTE]
   >
   >您可以從左側導軌拖曳整個架構欄位資料夾，並自動將它們排序為傳統區段。 字串欄位會結束在[!UICONTROL Dimension]區段中，而數字會出現在[!UICONTROL 量度]區段中。 或者，您可以按一下「新增所有&#x200B;]**」，並新增所有架構欄位。**[!UICONTROL 

1. 選取元件後，右側會出現許多設定。 使用下述設定來設定元件。

### 配置元件設定

![](assets/component-settings.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 元件類型] | 必填.可讓您將元件從「量度」變更為「Dimension」，反之亦然。 |
| [!UICONTROL 元件名稱] | 必填.可讓您指定出現在Analysis Workspace的好記名稱。 您可以重新命名元件，以為其指定資料檢視特定名稱。 |
| [!UICONTROL 說明] | 可選，但建議提供其他使用者有關元件的資訊。 |
| [!UICONTROL 標記] | 選填。可讓您使用自訂或現成可用的標籤來標籤元件，以便在Analysis WorkspaceUI中更輕鬆地搜尋／篩選。 |
| [!UICONTROL 欄位名稱] | 架構欄位的名稱。 |
| [!UICONTROL 資料集類型] | 必填.不可編輯的欄位，顯示元件來自的資料集類型（事件、查閱或描述檔）。 |
| [!UICONTROL 資料集] | 必填.不可編輯的欄位，顯示元件來自的欄位類型（例如字串、整數等）。 此欄位可包含多個資料集，例如當您要結合多個報表套裝時。 |
| [!UICONTROL 結構類型] | 指元件是否為字串、整數等。 |
| [!UICONTROL 元件 ID] | 必填.[CJA API](https://adobe.io/cja-apis/docs)使用此欄位來參考元件。 您可以按一下編輯圖示並修改此元件ID。 不過，變更此元件ID會中斷包含此元件的所有現有工作區專案。<br>如果您曾為pageTitle維度建立其他使用不同欄位的資料檢視，則可以重新命名該檢視，並讓維度跨資料檢視相容。 |
| [!UICONTROL 路徑] | 必填.一個不可編輯的欄位，顯示元件來自的架構路徑。 |
| [!UICONTROL 隱藏報表中的元件] | 預設= off。 可讓您在報告中使用元件時，將元件組織出「資料檢視」。 這不會影響權限，只影響元件組織。 換言之，您可以在報告中隱藏元件，使其不受非管理員的影響。 管理員仍可以按一下Analysis Workspace專案中的「顯示所有元件」來存取它。 |

### 配置格式設定

格式設定僅適用於量度。

![](assets/format-settings.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL Format] | 可讓您指定量度的格式，如小數、時間、百分比或貨幣。 |
| [!UICONTROL 小數位數] | 可讓您指定量度應顯示的小數位數。 |
| [!UICONTROL 顯示上升趨勢的方式] | 可讓您指定此量度的上升趨勢應被視為好（綠色）或壞（紅色）。 |
| [!UICONTROL 貨幣] | 此設定僅在選取的量度格式為[!UICONTROL Currency]時顯示。 提供貨幣選項清單。 預設為無貨幣。 這可讓您以報告中所選擇的貨幣來表示收入。 這不是貨幣轉換，只是UI格式選項。 |

### 設定歸因設定

![](assets/attribution-settings.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 設定歸因] | 可讓您指定使用此量度時，預設要套用至此量度的歸因設定。 此預設值可在自由表格或計算量度中覆寫。 |
| [!UICONTROL 歸因模型] | 可讓您指定預設歸因模型——僅在您開啟[!UICONTROL 使用非預設歸因模型]設定時啟用。 預設為[!UICONTROL 上次接觸]。 選項包括：上次接觸，首次接觸，線性，參與率，相同觸控， U形， J曲線，反J，時間衰減，自訂，演算法。 有些選項會建立其他需要填寫的欄位——例如自訂或時間衰減。 您可以使用相同欄位建立多個量度——這表示您可以有一個[!UICONTROL 上次接觸]收入量度和一個[!UICONTROL 首次接觸]收入量度，但是以結構中相同的收入欄位為基礎。 |
| [!UICONTROL 回顧期間] | 可讓您指定量度的預設回顧視窗——僅在您開啟[!UICONTROL 使用非預設歸因模型]設定時啟用。 選項包括：人員（報告視窗）、工作階段、自訂。 在選取「自訂」時，我們也會提供您選項，以選取任何天數／周/月等。 （最多90天），就像Attribution IQ。 您可以使用相同的架構欄位來擁有多個量度，但每個量度都有個別的回顧視窗。 |

### 設定包含／排除值設定

此設定允許您在查詢時修改要報告的基礎資料。 它與篩選器（先前稱為區段）不同。 但篩選器會尊重這個新維度，路徑和歸因也會如此。

例如，您可以在pageTitle欄位中建立維度，但將其稱為&quot;error pages&quot;，並包含[!UICONTROL 包含片語] &quot;error&quot;的任何頁面。

![](assets/include-exclude.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 區分大小寫] | 預設=開啟。 此設定僅適用於[!UICONTROL 包含／排除值]區段。 它可讓您判斷您套用的包含／排除規則是否應區分大小寫。 |
| [!UICONTROL 符合] | 可讓您指定在歸因和區段之前要考慮的報表值（例如，僅使用包含片語「error」的值）。 您可以指定：**[!UICONTROL 如果滿足所有標準]**&#x200B;或&#x200B;**[!UICONTROL 如果滿足任何標準]**。 |
| [!UICONTROL 標準] | 可讓您指定應套用至特定篩選規則的符合邏輯。<ul><li>**字串**:包含片語、包含任何詞語、包含所有詞語、不包含任何詞語、不包含片語、等於、不等於、開頭為、結尾為</li><li>**雙／整數**:等於、不等於、大於、小於、大於或等於、小於或等於</li><li>**日期**:等於、不等於、晚於、等於、發生於</li></ul> |
| [!UICONTROL 匹配操作數] | 可讓您指定應套用符合運算子的符合運算元。<ul><li>**字串**:文字欄位</li><li>**雙／整數**:文字欄位，其上／下箭頭代表數值</li><li>**日期**:日詳細程度選擇器（日曆）</li><li>**日期時間**:日期和時間粒度選擇器</li></ul> |
| [!UICONTROL 新增規則] | 可讓您指定額外的符合運算元和運算元。 |

### 設定行為設定

![](assets/behavior-settings.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 計數實例] | 可讓您指定用作度量的數值或日期類型欄位是否應計算其設定時間，而非值本身。<br> 如果您想要新增數值欄位的例項，而只想新增欄位比內部實際值 ** 的次數。<br>例如，這對於從「收  入」欄位建  立「訂購量度」非常有用。如果已設定收入，則我們想要計算1份單一訂單，而非數值收入金額。 |

### 配置[!UICONTROL 無值選項]設定

[!UICONTROL 「無值選] 項」設定類似於報  告中的「未  指定」或「未評估」。在資料檢視UI中，您可以依元件來決定要在報表中如何處理這些值。 您也可以將[!UICONTROL No value]重新命名為更適合您環境的項目，例如[!UICONTROL Null]、[!UICONTROL Not set]或其他項目。

另請注意，您在此欄位中指定的任何項目，都可用於報告中「無值[!UICONTROL 」行項目的特殊UI處理，如「無值選項]」設定所述。][!UICONTROL 

![](assets/no-value-options.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 如果顯示，請呼叫「無值……」] | 您可以在此處將&#x200B;**[!UICONTROL No value]**&#x200B;更名為其他值。 |
| [!UICONTROL 預設不顯示「無」值] | 不會在報表中顯示此值。 |
| [!UICONTROL 預設顯示無值] | 確實會在報表中顯示此值。 |
| [!UICONTROL 將無值視為值] | 此設定會以您在[!UICONTROL 下指定的文字取代資料中的空白值，如果顯示，請呼叫無值……]。 例如，如果您以行動裝置類型為維度，您可將&#x200B;**[!UICONTROL No value]**&#x200B;項目重新命名為「Desktop」。 請注意，當您將此欄位變更為自訂值時，自訂值會被視為合法字串值。 因此，如果在此欄位中輸入&quot;Red&quot;值，資料中出現的字串&quot;Red&quot;例項也會在您所指定的相同行項目下滾動。 |

### 配置持久性設定

![](assets/persistence.png)

這些設定類似於傳統Adobe Analytics的eVar設定。

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 設定持續性] | 切換鍵 |
| [!UICONTROL 配置] | 可讓您指定用於維度的永續性分配模型。 選項包括：[!UICONTROL 最近]、[!UICONTROL Original]、[!UICONTROL Instance]、[!UICONTROL All]。 如果您想要保留值（類似於傳統Analytics中的eVar），您會在這裡設定值。 唯一的關鍵區別是，您可以設定的最大持久性為90天。 此外，[!UICONTROL Never expire]不是選項。 |
| [!UICONTROL 過期] | 可讓您指定維度的永續性視窗。 選項包括：[!UICONTROL 會話]（預設）、[!UICONTROL Person]、[!UICONTROL Time]、[!UICONTROL Metric]。 您可能需要能夠使購買的維度過期（例如內部搜尋詞或其他銷售使用案例）。 [!UICONTROL 量] 度可讓您指定任何已定義量度作為此維度的有效期(例如購買  量度)。 |

### 設定值分組設定

例如，「5到10之間」的時段會在「工作區」報表中顯示為「5到10」的行項目。

![](assets/value-bucketing.png)

| 設定 | 說明／使用案例 |
| --- | --- |
| [!UICONTROL 貯體值] | 可讓您建立數值維度的分區版本。 這可讓您報告收入區間或其他數值作為報告中的維度。 |
| [!UICONTROL 最多] | 可讓您指定第一個數值維度儲存段的邊界。 這僅適用於數值維度。 |
| [!UICONTROL 介於和最多] | 可讓您指定後續數值維度區間的邊界。 |
| [!UICONTROL 新增貯體] | 可讓您新增另一個儲存貯體至數值維度分區。 |

### 使用[!UICONTROL 標準元件]

除了從結構元素建立量度和維度外，您也可以在資料檢視中使用標準元件。

[!UICONTROL 標準] 元件是不是從資料集架構欄位產生，而是系統產生的元件。在任何資料檢視中都需要一些系統元件，以利Analysis Workspace的報告功能，而其他系統元件則是選用的。

![](assets/standard-components.png)

必要的標準元件

| 元件名稱 | Dimension或量度 | 附註 |
| --- | --- | --- |
| [!UICONTROL 人物] | 量度 | 在傳統Analytics中，先前稱為[!UICONTROL 獨特訪客]。 此量度以連線中指定的人員ID為基礎。 |
| [!UICONTROL 工作階段] | 量度 | 在傳統Analytics中，先前稱為[!UICONTROL 瀏覽]。 此量度以下指定的作業化設定為基礎。 |
| [!UICONTROL 事件] | 量度 | 在傳統Analytics中，先前稱為[!UICONTROL Occurrences]。 此度量表示Connection中所有事件資料集的行數。 |
| [!UICONTROL 日] | 維度 |  |
| [!UICONTROL 週] | 維度 |  |
| [!UICONTROL 月] | 維度 |  |
| [!UICONTROL 季度] | 維度 |  |
| [!UICONTROL 年] | 維度 |  |
| [!UICONTROL 小時] | 維度 |  |
| [!UICONTROL 分鐘] | 維度 |  |

### 可選標準元件

在任何資料檢視中都需要一些系統元件，以方便在Analysis Workspace建立報告功能，而下列元件則是選用的。

| 元件名稱 | Dimension或量度 | 附註 |
| --- | --- | --- |
| [!UICONTROL 作業開始] | 量度 | 此度量會計算作業中第一個事件的事件數。 當用於篩選定義時(例如「[!UICONTROL 會話開始]存在」)，它只篩選到每個會話的第一個事件。 請注意，這與[!UICONTROL Entries]不同，因為它一律會計算作業的第一個事件——而非作業中維度的第一個值。 |
| [!UICONTROL 作業結束] | 量度 | 此度量會計算作業的最後一個事件的數目。 與[!UICONTROL Session Starts]類似，它也可用於篩選定義中，以篩選至每個作業的最後一個事件。 請注意，這與[!UICONTROL Exits]的行為不同，因為它一律會計算作業的最後一個事件——而非作業中維度的最後一個值。 |
| [!UICONTROL 逗留時間 (秒)] | 量度 | [!UICONTROL 逗留時間]度量的運作方式與傳統Adobe Analytics類似——將維度的兩個不同值之間的時間相加。 不過，使用「工作階段開始和工作階段結束」量度，客戶可以自行建構「每位使用者逗留時間]」和「每個工作階段逗留時間]」計算量度（請參閱下方的OOTB篩選器和計算量度）。[!UICONTROL [!UICONTROL  |
| [!UICONTROL 每個事件逗留時間] | 維度 | 從功能上講，這其實只是上述量度的區隔。 我們提供預設時段，但允許您將時段變更為您喜歡的。 |
| [!UICONTROL 每個作業逗留時間] | 維度 |  |
| [!UICONTROL 每人逗留時間] | 維度 |  |
| [!UICONTROL 批次ID] | 維度 |  |
| [!UICONTROL 資料集 ID] | 維度 |  |

### 篩選結構欄位和維度／量度

您可以依下列資料類型篩選左側導軌中的架構欄位：

![](assets/filter-fields.png)

您也可以依資料集和模式欄位是否包含資料或是否是身分來篩選：

![](assets/filter-other.png)

## 3.新增全域篩選至您的資料檢視

您可以新增套用至整個資料檢視的篩選器（先前稱為區段），類似於虛擬報表套裝(傳統的Adobe Analytics)中資料的篩選檢視。

1. 按一下[!UICONTROL 資料視圖]中的[!UICONTROL 設定]頁籤。
1. 從左側導軌的清單拖曳篩選器至「新增篩選器]」欄位。[!UICONTROL 
