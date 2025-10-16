---
description: 了解如何在 Customer Journey Analytics Experimentation 面板中分析 A/B 測試的結果。
title: 實驗面板
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: b013518d8f1782219dd2cf9e5b5a89b877e3b92d
workflow-type: tm+mt
source-wordcount: '2175'
ht-degree: 98%

---

# Experimentation 面板 {#experimentation-panel}

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="實驗"
>abstract="建立一個面板來比較不同的使用者體驗、行銷或傳送訊息變化版本。並確定哪種變化版本最能產生特定結果。"

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="實驗"
>abstract="比較不同的使用者體驗、行銷或傳送訊息變化版本，確定哪一種最能達成特定結果。指定實驗、進行對照的控制變數、成功量度和正規化量度。或者，也可以設定信賴度的上限及下限。"


>[!BEGINSHADEBOX]

_本文記錄了_![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 中的實驗面板。_<br/>_請參閱「[Analytics for Target 面板](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/panels/a4t-panel)」，了解有關如何分析 Adob&#x200B;&#x200B;e Target 活動和_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的體驗。_

>[!ENDSHADEBOX]


此&#x200B;**[!UICONTROL 實驗]**&#x200B;面板可讓分析師比較不同的使用者體驗、行銷或傳送訊息變化，以確定哪一個產生特定結果的績效最好。您可以透過任何實驗平台 (線上、離線)、透過 Target 或 Journey Optimizer 等 Adobe 解決方案，甚至透過 BYO (自備) 資料來評估任何 A/B 實驗的提升度和信賴度。

閱讀更多關於 [Adobe Customer Journey Analytics 與 Adob&#x200B;&#x200B;e Target 之間的整合](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/cja/target-reporting-in-cja)。

## 存取控制 {#access}

所有 Customer Journey Analytics 的使用者都能使用實驗面板。不需要管理員權限或其他權限。然而，先決條件會規定只有管理員才能執行的操作。

## 計算量度中的函數

有兩個進階函數可使用：提升度和信賴度。如需詳細資訊，請參閱「[參考 - 進階函數](/help/components/calc-metrics/cm-adv-functions.md)」。

## 先決條件

若要使用實驗面板，請確保依以下先決條件進行：

### 建立與實驗資料集的連接

建議的資料結構描述是針對在[「物件」陣列](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/array) 中的實驗資料，其中包含在二個獨立維度中的實驗與變數資料。 兩個維度都需要在&#x200B;**單一**&#x200B;物件陣列中。如果您的實驗資料是在一個單獨的維度內 (且實驗與變數資料在分隔字串內)，您可以使用資料檢視中的[子字串](/help/data-views/component-settings/substring.md)將維度一分為二，以便用於面板中。


將您的實驗資料[攝取](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)至 Adobe Experience Platform 後，[在 Customer Journey Analytics 中建立與一個或多個實驗資料集的連接](/help/connections/create-connection.md)。

### 在資料檢視中新增內容標籤

在 Customer Journey Analytics 資料檢視設定中，管理員可以將[內容標籤](/help/data-views/component-settings/overview.md)新增到維度或量度，Customer Journey Analytics 服務 (如[!UICONTROL 實驗]面板) 可針對其目標使用這些標籤。實驗面板使用了兩個預先定義的標籤：

* [!UICONTROL 實驗中的實驗]
* [!UICONTROL 實驗中的變體]

在包含實驗資料的資料檢視中，選擇兩個維度，一個包含實驗資料，一個包含變體資料。然後使用&#x200B;**[!UICONTROL 實驗中的實驗]**&#x200B;和&#x200B;**[!UICONTROL 實驗變體]**&#x200B;標籤標記這些維度。

![實驗和實驗變體的內容標籤選項。](assets/context-label.png)

如果沒有這些標籤，Experiment 面板會因沒有可用的實驗而無法運作。

## 使用

若要使用&#x200B;**[!UICONTROL 實驗]**&#x200B;面板：

1. 建立&#x200B;**[!UICONTROL 實驗]**&#x200B;面板。有關如何建立面板的資訊，請參閱[建立面板](panels.md#create-a-panel)。


1. 指定面板的[輸入](#panel-input)。

1. 觀察面板的[輸出](#panel-output)。

   >[!IMPORTANT]
   >
   >如果尚未完成 Customer Journey Analytics 資料檢視中的必要設定，在可以繼續之前，您會收到此訊息：「[!UICONTROL 請在「資料檢視」中設定實驗與變體維度]」。
   >

### 面板輸入

若要使用實驗面板：

1. 進行面板輸入設定：

   ![將實驗面板拖放至專案中。](assets/experiment-input.png)

   | 設定 | 定義 |
   | --- | --- |
   | **[!UICONTROL 日期範圍]** | 根據 Customer Journey Analytics 中收到所選實驗的第一個事件，系統會自動設定實驗面板的日期範圍。如果需要，您可以更具體的時間範圍來限制或擴大日期範圍。 |
   | **[!UICONTROL 實驗]** | 一組向一般使用者展示的體驗變體，用來決定要永久保存的最佳變體。一個實驗由兩個或多個變體組成，其中一個會視為控制變體。此設定預先填入了資料檢視中已用&#x200B;**[!UICONTROL 實驗]**&#x200B;標籤標記的維度，以及過去 6 個月的實驗資料。 |
   | **[!UICONTROL 控制變體]** | 一般使用者體驗中的兩個或多個變動之一，它們會被比較以找出較好的替代方案。必須選擇一種變體作為對照，並且只能將一種變體視為控制變體。此設定預先填入了資料檢視中已用&#x200B;**[!UICONTROL 變體]**&#x200B;標籤標記的維度。此設定會提取與此實驗關聯的變體資料。 |
   | **[!UICONTROL 成功量度]** ➊ | 使用者用來比較變體的一個或多個量度。轉換量度 (無論是最高還是最低) 具有最理想結果的變體會宣告為實驗的「*最佳表現變體*」。可最多新增 5 個量度。 |
   | **[!UICONTROL 標準化量度]** ➋ | 測試運行的基礎 (**[!UICONTROL 全域帳戶]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 帳戶]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 機會]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 購買群組]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 人員]**、**[!UICONTROL 工作階段]**&#x200B;或&#x200B;**[!UICONTROL 事件]**)。例如，測試可以比較幾種變體的轉換率，其中&#x200B;**[!UICONTROL 轉換率]**&#x200B;是按照頁面檢視所計算。 |
   | **[!UICONTROL 包括信賴上邊界/下邊界]** | 啟用此選項以顯示信賴水準的上限和下限。 |


1. 選取「**[!UICONTROL 建置]**」。

### 面板輸出

實驗面板會傳回一組豐富的資料和視覺效果，以幫助您更好地了解實驗的執行情況。面板頂端會有[摘要變更](../visualizations/summary-number-change.md)視覺效果，為您提示您所選取的面板設定。您可以隨時選取右上方的編輯鉛筆來編輯面板。

您還將收到文字摘要，以表示實驗是否具有結論性，並總結結果。結論性是以統計顯著性為基礎 (參閱「[統計方法](#adobes-statistical-methodology)」)。您可以查看具有最高提升度和信賴度的最佳表現變體總結數字。

對於您選取的每個成功量度，[自由格式表格](../visualizations/freeform-table/freeform-table.md)視覺效果和轉換率[折線圖](../visualizations/line.md)視覺效果會顯示。

![實驗輸出會顯示一個自由格式表格和一個轉換率趨勢。](assets/experiment-output.png)


>[!NOTE]
>
>該面板目前不支援 A/A 測試分析。

#### 解釋結果

1. **實驗結具結論性**：每次查看實驗報告時，目前為止在實驗中累積的資料都會進行分析。當&#x200B;*至少一個*&#x200B;變體的&#x200B;*隨時*&#x200B;有效信賴度超過 95% 臨界值時，此分析可宣告實驗為具有「結論性」。對於兩個以上的臂，應用 Benjamini-Hochberg 校正來修正多重假設檢驗。

2. **最佳表現變體**：當一個實驗宣告為具有結論性時，具有最高轉換率的變體將標記為最佳表現變體。請注意，此變體必須是控制變體或基線變體，或者是超過 95% *隨時*&#x200B;有效信賴度臨界值的變體之一 (套用 Benjamini-Hochberg 校正)。

3. **轉換率**：顯示的轉換率是成功量度值➊與標準化量度值➋的比率。 請注意，如果量度不是二進位 (實驗中的每個單位為 1 或 0)，則此值可能大於 1

4. **提升度**：實驗報告摘要會顯示提升基線，這可測量指定變體的轉換率相對於基線的增進百分比。準確來說，這是指定變體與基線之間的績效差異，除以基線的績效 (以百分比表示)。

5. **信賴度**：顯示的隨時有效信賴度是對有多少證據表示指定變體與控制變體相同的機率測度。信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。信賴度是一個機率 (以百分比表示)，您會觀察到指定變體和控制變體之間轉換率差異較小。但實際上，真實的潛在轉換率沒有差異。就 *P 值*&#x200B;而言，顯示的信賴度為 1 - *P 值*。

>[!NOTE]
>
>對結果的完整描述應考慮所有可用的證據 (例如，實驗設計、樣本量、轉換率、信賴度及其他)，而不僅僅是宣告是否具有結論性。即使結果尚未具有「結論性」，仍可以有令人信服的證據表示變體之間各有相異信賴區間 (例如，信賴區間幾乎不重疊)。理想情況下，所有統計證據 (在連續範圍內進行解釋) 都應該會影響決策。

## Adobe 的統計方法 {#statistics}

為了提供易於解釋和安全的統計推斷，Adobe 採用一種以[隨時有效的信賴序列](https://arxiv.org/abs/2103.06476)為基礎的統計方法

信賴序列是信賴區間的模擬「*順序*」。若要了解什麼是信賴序列，您可以想像重複實驗一百次。同時，計算&#x200B;*每個進入實驗新使用者*&#x200B;的平均商業量度 (例如電子郵件的開啟率) 估計值及其相關的 95% 信賴序列。

95% 信賴序列是指在您執行 100 個實驗中有 95 個包含商業量度「確判為真」值。(為了提供相同的 95% 覆蓋率保證，每個實驗只能計算一次 95% 信賴區間；而不是針對每個新使用者計算)。因此，信賴序列可讓您持續監視實驗，而不會增加「誤判為真」的錯誤率，也就是這會允許「偷看」結果。

## 解釋非隨機維度 {#non-randomized}

Customer Journey Analytics 允許分析師選取任何維度作為實驗。但是，如果所選的實驗維度不是對人員進行隨機分組，那麼該如何解釋分析呢？

例如，考慮一個人看到的廣告。如果您決定向大家展示&#x200B;*廣告 B* 而不是&#x200B;*廣告 A，您可能會對測量某些量度 (例如平均收入) 的變化感興趣*。展示廣告 B 而不是廣告 A 的因果效應對於做出行銷決策至關重要。如果以展示廣告 B 的替代策略取代展示廣告 A 的現狀，那麼這種因果效應可以用整個人口的平均收入來測量。

A/B 測試是業界客觀測量此類干預效果的黃金標準。A/B 測試產生因果估計的關鍵原因是由於人們隨機接收其中一種可能的變體。

現在，考慮一個無法透過隨機化達到的維度，例如此人所在的美國州別。人們主要來自兩個州，紐約和加州。由於地區氣候差異，冬季服裝品牌在兩州的平均銷售收&#x200B;&#x200B;入可能會有所不同。在這種情況下，天氣可能是冬季服裝銷售的真正影響因素，而不是人們的地理位置不同。

Customer Journey Analytics 中的實驗面板可讓您分析不同人所在州的平均收入差異資料。在這種情況下，輸出沒有因果解釋。然而，這樣的分析可能仍然有趣。它提供了各州平均收入差異的估計值 (以及不確定性量度)。該值也稱為&#x200B;*統計假設檢驗*。這種分析的結果可能很有趣，但不一定具有可操作性。只是因為您未隨機化，有時也無法將人們隨機化為維度的可能值之一。

下圖對比了這些情況：

![顯示觀察資料和隨機實驗的圖表。](assets/randomize.png)

當你想衡量干預 X 對結果 Y 的影響時，可能兩者的真正原因都是混雜因素 C。如果資料不是通過對 X 進行隨機化而獲得，則影響更難衡量，分析明確地說明了 C。隨機化打破了 X 對 C 的依賴，使我們能夠衡量 X 對 Y 的影響，而不必擔心其他變數。

## 在實驗中使用計算量度 {#use-in-experimentation}

>[!NOTE]
>
>對於同時使用 Customer Journey Analytics 和 Adob&#x200B;&#x200B;e Journey Optimizer 的組織，本節中的資訊也適用於 Journey Optimizer 中的實驗功能。

並非所有計算量度都與實驗面板相容。

包含以下任何量度或常數的計算指標均與實驗面板不相容：

* 基本量度來自[摘要資料集](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dataviews/summary-data)
* 彼此相除以或相乘一起的基本量度 (例如， `Revenue`/`Orders`)
* 在基本度量中加上或減去的常數 (例如， `Revenue+50`)
* 以下任何基本量度：
   * 人員

與實驗面板不相容的計算量度在建立計算量度時，在&#x200B;[!UICONTROL **產品相容性**]&#x200B;欄位中的值為 [!UICONTROL **Customer Journey Analytics 中各處 (不包括實驗)**]。有關建立計算量度的資訊，請參閱「[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)」。

## 在實驗面板中使用計算量度

有關[在實驗面板中使用計算量度](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119)的資訊，請參閱此部落格文章。

>[!MORELIKETHIS]
>[掌握 Adobe Customer Journey Analytics 實驗](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
