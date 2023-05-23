---
source-git-commit: 901ddcd814c71504ff056d91fd25445d94a6f56e
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 69%

---
# 程式碼片段

## 發佈階段有限測試 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關Customer Journey Analytics發佈流程的資訊，請參見 [Customer Journey Analytics功能版本](/help/release-notes/releases.md)。

## 發佈階段有限測試部份 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關Customer Journey Analytics發佈流程的資訊，請參見 [Customer Journey Analytics功能版本](/help/release-notes/releases.md)。

## 資料字典篩選條件 {#dd-filter-criteria}

1. (可選) 選取 **篩選器** 圖示 ![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然後選擇以下任一篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/components/overview.md)。 |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **篩選條件**] | 僅顯示屬於「篩選器」的元件。 (當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) <!--this is Filters in CJA--> |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **缺少說明**] | 僅顯示在說明欄位中還沒有說明的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **顯示重複項目**] | 僅顯示與所選資料視圖中另一個元件具有相同名稱或相同說明的元件。 這包括您建立的元件以及由Adobe提供的元件。 名稱或說明必須完全匹配才能顯示為重複項。 此選項僅提供給管理員使用。 |
   | [!UICONTROL **無最近的資料**] | 僅顯示在過去 90 天內未收集任何資料的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **建立者：Adobe**] <!-- I don't see this option--> | 僅顯示由 Adobe 建立的元件。並不會顯示由管理員或您組織中的其他使用者建立的元件。 |

   {style="table-layout:auto"}

## 資料字典元件資訊 {#dd-component-information}

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **已核准**] | <p>指出該元件已經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **取消核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「未核准」。</p> |
| [!UICONTROL **未核准**] | <p>指出該元件尚未經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「已核准」。</p> |
| [!UICONTROL **說明**] | 描述元件的預定功能。(此資訊由 Analytics 管理員新增，如[新增元件說明](/help/components/add-component-descriptions.md)中所述。) |
| [!UICONTROL **經常與下列項目搭配使用**] | <p>顯示您正在查看的元件最常與哪些元件一起使用。</p><p>在5個主要元件類型中最多顯示5個元件：度量、計算的度量、Dimension、篩選和日期範圍。</p><p>此清單顯示過去 90 天的資料。只會顯示您有權檢視的元件。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在建立用戶看到的元件之前，首先應用 **全部顯示** 篩選器，確保您看到未與您共用的任何元件，這些元件可能已被其他管理員添加。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **類似於**] | <p>顯示與您正在查看的元件具有相似名稱的元件。</p><p>在5個主要元件類型中最多顯示5個元件：度量、計算的度量、Dimension、篩選和日期範圍。</p><p>只會顯示您有權檢視的元件。</p><p>資料視圖中的任何重複元件都將顯示在此處。 Analytics 管理員應識別並移除所有重複的元件，如[監視資料字典健康情況](/help/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在建立用戶看到的元件之前，首先應用 **全部顯示** 篩選器，確保您看到未與您共用的任何元件，這些元件可能已被其他管理員添加。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：**&#x200B;目前，「**類似於**」區段僅包括您建立的元件，不包括 Adobe 提供的元件。Adobe 提供的元件會在未來版本中新增。</p> |
| [!UICONTROL **標記**] | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
| [!UICONTROL **元件類型**] | 列出它的元件類型，無論是Dimension、度量、篩選器還是日期範圍。 |
| [!UICONTROL **建立者**] | 顯示建立元件的使用者名稱。 |
| [!UICONTROL **預覽**] | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
| [!UICONTROL **上次修改日期**] | 顯示上次修改元件的日期。查看篩選器、度量、計算度量和日期範圍時將顯示此部分。 |

{style="table-layout:auto"}

## 元件排序選項 {#components-sort-options}

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **建議**] | 將元件與清單頂部推薦的元件排序。 您或您組織中的其他人使用的頻率最高且最近的元件在清單中顯示得更高。 |
| [!UICONTROL **字母順序**] | 按字母順序對元件排序。 |
| [!UICONTROL **分類**] | 根據元件類型（維、度量、段、日期範圍）對元件進行排序。 |

{style="table-layout:auto"}

