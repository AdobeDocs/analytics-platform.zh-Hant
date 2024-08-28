---
description: 瞭解如何在Customer Journey Analytics實驗面板中分析A/B測試的結果。
title: Experimentation 面板
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: 36718581c9a070bb5f5547f18be643ca91838bae
workflow-type: tm+mt
source-wordcount: '2069'
ht-degree: 29%

---

# Experimentation 面板

此 **[!UICONTROL Experimentation]** 面板可讓分析師比較不同的使用者體驗、行銷或傳送訊息變化，以確定哪一個產生特定結果的績效最好。您可以從任何實驗平台評估任何A/B實驗的提升度和信賴度 — 線上、離線、來自Target或Journey Optimizer等Adobe解決方案，甚至BYO （自備）資料。

深入瞭解Adobe Customer Journey Analytics與Adobe Target之間的[整合](https://experienceleague.adobe.com/zh-hant/docs/target/using/integrate/cja/target-reporting-in-cja)。

## 存取控制 {#access}

實驗面板可供所有Customer Journey Analytics使用者使用。 不需要管理員權限或其他權限。但是，進行設定 (下方的步驟 1 和 2) 所需的動作只有管理員才能執行。

## 計算量度中的新函式 {#functions}

已新增了兩個進階函數：[!UICONTROL 提升度]和[!UICONTROL 信賴度]。如需詳細資訊，請參閱「[參考 - 進階函數](/help/components/calc-metrics/cm-adv-functions.md)」。

## 步驟1：建立與實驗資料集的連線 {#connection}

建議的資料結構描述是針對在[「物件」陣列](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) 中的實驗資料，其中包含在二個獨立維度中的實驗與變數資料。 兩個維度都必須在&#x200B;**單一**&#x200B;物件陣列中。 如果您的實驗資料在單一維度中（實驗與變數資料在分隔字串中），您可以使用資料檢視中的[substring](/help/data-views/component-settings/substring.md)設定將維度一分為二，以便用於面板中。

在您的實驗資料已[擷取](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home)到Adobe Experience Platform之後，[在Customer Journey Analytics](/help/connections/create-connection.md)中建立與一個或多個實驗資料集的連線。

## 步驟 2：在資料檢視中新增內容標籤 {#context-labels}

在Customer Journey Analytics資料檢視設定中，管理員可以將[內容標籤](/help/data-views/component-settings/overview.md)新增至維度或量度，而Customer Journey Analytics服務（例如[!UICONTROL Experimentation]面板）可針對其目標使用這些標籤。 Experimentation 面板使用了兩個預先定義的標籤：

* [!UICONTROL 實驗中的實驗]
* [!UICONTROL 實驗中的變體]

在包含實驗資料的資料檢視中，選擇兩個維度，一個包含實驗資料，一個包含變體資料。然後使用&#x200B;**[!UICONTROL 實驗]**&#x200B;和&#x200B;**[!UICONTROL 變體]**&#x200B;標籤標記這些維度。

Experimentation和Experimentation Variant的![內容標籤選項。](assets/context-label.png)

如果沒有這些標籤，Experiment 面板會因沒有可用的實驗而無法運作。

## 步驟3：設定Experimentation面板 {#configure}

1. 在Customer Journey Analytics的Analysis Workspace中，將Experimentation面板新增至專案。 如需有關新增面板至專案的詳細資訊，請參閱[建立專案](/help/analysis-workspace/build-workspace-project/create-projects.md)中的[新增面板至專案](/help/analysis-workspace/build-workspace-project/create-projects.md#add-panels-to-the-project)。

   ![Experiention面板拖曳到專案中。](assets/experiment.png)

   >[!IMPORTANT]
   >
   >如果尚未完成Customer Journey Analytics資料檢視中的必要設定，在可以繼續之前，您會收到此訊息： &quot;[!UICONTROL 請在資料檢視中設定實驗與變體維度]&quot;。
   >

1. 進行面板輸入設定。

   | 設定 | 定義 |
   | --- | --- |
   | **[!UICONTROL 實驗]** | 一組向一般使用者展示的體驗變體，用來決定要永久儲存的最佳變體。 一個實驗由兩個或多個變體組成，其中一個會視為控制變體。此設定預先填入了資料檢視中已用&#x200B;**[!UICONTROL 實驗]**&#x200B;標籤標記的維度，以及過去 3 個月的實驗資料。 |
   | **[!UICONTROL 控制變體]** | 一般使用者體驗中的兩個或多個變動之一，它們會被比較以找出較好的替代方案。必須選擇一種變體作為對照，並且只能將一種變體視為控制變體。此設定預先填入了資料檢視中已用&#x200B;**[!UICONTROL 變體]**&#x200B;標籤標記的維度。此設定會提取與此實驗關聯的變體資料。 |
   | **[!UICONTROL 成功量度]** | 使用者用來比較變體的一個或多個量度。轉換量度 (無論是最高還是最低) 具有最理想結果的變體會宣告為實驗的「最佳表現變體」。可最多新增 5 個量度。 <p>符合必要條件的計算量度也可使用。 如需詳細資訊，請參閱[在實驗面板中使用計算量度](#use-calculated-metrics-in-the-experimentation-panel)。</p> |
   | **[!UICONTROL 標準化量度]** | 執行測試的基礎（[!UICONTROL 人員]、[!UICONTROL 工作階段]或[!UICONTROL 事件]）。 例如，測試可能會比較幾種變體的轉換率，其中&#x200B;**[!UICONTROL 轉換率]**&#x200B;是以&#x200B;**[!UICONTROL 每個工作階段轉換次數]**&#x200B;或&#x200B;**[!UICONTROL 每人轉換次數]**&#x200B;計算。 |
   | [!UICONTROL **包含信賴上/下限**] |  |
   | **[!UICONTROL 日期範圍]** | 日期範圍會根據所選取實驗在Customer Journey Analytics中收到的第一個事件自動設定。 如果需要，您可以更具體的時間範圍來限制或擴大日期範圍。 |

1. 選取「**[!UICONTROL 建立]**」。

## 步驟 4：檢視面板輸出 {#view}

Experimentation 面板會傳回一組豐富的資料和視覺效果，以幫助您更好地了解實驗的執行情況。面板頂端會提供一個摘要行，提示您所選取的面板設定。您可以隨時選取右上方的編輯鉛筆來編輯面板。

您還將收到文字摘要，以表示實驗是否具有結論性，並總結結果。結論性是以統計顯著性為基礎。(參見下方的「統計方法」。)您可以查看具有最高提升度和信賴度的最佳表現變體總結數字。

對於您所選取的每個成功量度，都會顯示一個自由表格和一個轉換率趨勢。

![實驗輸出顯示一個自由表格和一個轉換率趨勢。](assets/exp-output1.png)

[!UICONTROL 折線圖]可提供[!UICONTROL 控制]與[!UICONTROL 控制變體]的績效：

![線圖輸出顯示控制與控制變體效能。](assets/exp-output2.png)

>[!NOTE]
>
>該面板目前不支援 A/A 測試分析。

## 步驟 5：解釋結果 {#interpret}

1. **實驗已有結果**：每次檢視實驗報告時，都會分析到目前為止在實驗中累積的資料。 當隨時有效的信賴度超過&#x200B;*至少一個*&#x200B;變體的95%臨界值時，宣告實驗具有「結論性」（當超過雙臂時套用Benjamini-Hochberg校正，以校正多個假設檢驗）。

2. **最佳表現變體**：當一個實驗宣告為具有結論性時，具有最高轉換率的變體將標記為「最佳表現變體」。請注意，此變體必須是控制變體或基線變體，或者是超過95%隨時有效信賴度臨界值的變體之一（套用Benjamini-Hochberg校正）。

3. **轉換率**：顯示的轉換率是成功量度值與標準化量度值的比例。 請注意，如果量度不是二進位（實驗中的每個單位為1或0），此值有時可能大於1

4. **提升度**：實驗報告摘要會顯示提升基線，它衡量了指定變體的轉換率相對於基線的增進百分比。 準確來說，這是指定變體與基線之間的績效差異，除以基線的績效 (以百分比表示)。

5. **信賴度**：顯示的隨時有效信賴度是對有多少證據表示指定變體與控制變體相同的機率測度。 信賴度越高表示控制和非控制變體具有相同績效假設的證據越少。更準確地說，如果實際上真實的基本轉換率沒有差異，顯示的信賴度是您觀察到指定變體和控制變體之間轉換率差異較小的機率（以百分比表示）。 就 *P 值*&#x200B;而言，顯示的信賴度為 1 - *P 值*。

>[!NOTE]
>
>對結果的完整描述應考慮所有可用的證據（例如實驗設計、樣本量、轉換率、信賴度等），而不僅僅是宣告是否具有結論性。 即使結果尚未具有結論性，仍可以有令人信服的證據表示一種變體與另一種不同（例如，信賴區間幾乎不重疊）。 理想情況下，所有統計證據，在連續範圍內解釋，都應有助於決策。

## Adobe 的統計方法 {#statistics}

為了提供易於解釋和安全的統計推斷，Adobe 採用一種以[隨時有效的信賴序列](https://arxiv.org/abs/2103.06476)為基礎的統計方法

信賴序列是信賴區間的類比&#x200B;*循序*。 若要瞭解信賴序列，您可以想像重複實驗一百次，然後計算&#x200B;*每個進入實驗的新使用者*&#x200B;的平均商業量度（例如電子郵件的開啟率）估計值及其相關的95%信賴序列。

95%信賴序列包含您執行的100個實驗中的95個商業量度的「真」值。 （每個實驗只能計算一次95%信賴區間，以提供相同的95%覆蓋率保證；而不是針對每個新使用者）。 因此，信賴序列可讓您持續監視實驗，而不會增加誤判錯誤率，也就是它們允許「窺視」結果。

## 解讀非隨機維度 {#non-randomized}

Customer Journey Analytics可讓分析師選取任何維度當作「實驗」。 但是對於選擇的實驗維度不是隨機人員的分析，您該如何解讀？

例如，以個人看到的廣告為例。 如果您決定顯示人員是「廣告B」而非「廣告A」，可能會對測量某些量度的變更感興趣（例如平均收入）。 顯示廣告B來取代廣告A的因果關係，對達成行銷決策至關重要。 如果您以顯示廣告B的替代策略取代顯示廣告A的現狀，則此因果效應可測量為整個母體的平均收入。

A/B測試是業界客觀衡量此類干預措施效果的黃金標準。 A/B測試產生因果估計的重要原因是接收其中一個可能變體的人員隨機化。

現在，假設有一個不是透過隨機化實現的維度，例如個人的美國州。 假設人員主要來自兩個州：紐約和加州。 由於地區天氣差異，這兩個州冬季服裝品牌的平均銷售收入可能不同。 在這種情況下，天氣可能是冬季服裝銷售背後的真正因果因素，而不是人的地理狀態不同這一事實。

Customer Journey Analytics中的Experimentation面板可讓您依人員的狀態將資料分析為平均收入差異。 在這種情況下，輸出沒有因果解釋。 不過，此類分析可能仍值得關注。 它提供個人所在州平均收入差異的估計值（以及不確定性的測量值）。  此值也稱為「統計假設測試」。 此分析的輸出可能會很有趣，但不一定可操作，因為您沒有，有時也無法將人員隨機化為維度的可能值之一。

下圖對比了這些情況：

![顯示觀察資料和隨機實驗的圖表。](assets/randomize.png)

當您想要測量干預X對結果Y的影響時，兩者的真正原因可能是混淆因素C。如果資料不是藉由在X上隨機化人員而獲得，則影響更難測量，且分析明確說明了C。隨機化會中斷X對C的依賴，讓我們不必擔心其他變數，即可測量X對Y的影響。

## 在實驗中使用計算量度 {#use-in-experimentation}

>[!NOTE]
>
>對於同時使用Customer Journey Analytics和Adobe Journey Optimizer的組織，本節中的資訊也適用於Journey Optimizer中的實驗功能。


並非所有計算量度都與Experimentation面板相容。

包含下列任何量度或常數的計算量度與Experimentation面板不相容：

* 摘要資料集<!--add link to Rob's "Summary data" doc when it's published -->中的基礎量度
* 基礎量度彼此相除或相乘（例如，`Revenue`/`Orders`）
* 在基礎量度中新增或減去的常數（例如，`Revenue+50`）
* 下列任一基本量度：
   * 人員
   * （還有什麼？）

與Experimentation面板不相容的計算量度在建立計算量度時，[!UICONTROL **產品相容性**]&#x200B;欄位中的Customer Journey Analytics（不包括實驗）**]的值為[!UICONTROL ** Everywhere in experimentation。 如需建立計算量度的相關資訊，請參閱[建立量度](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。

## 在Experimentation面板中使用衍生度量

請參閱這篇部落格，瞭解在Experimentation面板](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119)中使用衍生量度[的相關資訊。
