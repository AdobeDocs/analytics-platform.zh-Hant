---
source-git-commit: 02ff498456fb3d770b9e3c73c3847ac5a55cd705
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 83%

---
# 程式碼片段

## 發佈階段有限測試 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關 Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

## 發佈階段有限測試部份 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關 Analytics 發佈流程的資訊，請參閱 [Customer Journey Analytics 功能發佈](/help/release-notes/releases.md)。

## 資料字典篩選條件 {#dd-filter-criteria}

1. (可選) 選取 **篩選器** 圖示 ![資料字典篩選器圖示](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png)，然後選擇以下任一篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
   | [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/components/overview.md)。 |
   | [!UICONTROL **維度**] | 僅顯示維度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **量度**] | 僅顯示量度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **篩選條件**] | 僅顯示屬於「篩選」的元件。 (當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) <!--this is Filters in CJA--> |
   | [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
   | [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **缺少說明**] | 僅顯示在說明欄位中還沒有說明的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **顯示重複項目**] | 僅顯示與所選報告套裝中的另一個元件具有相同標籤或相同說明的元件。這包括您建立的元件，以及由Adobe提供的元件。 標籤或說明必須完全相符才能顯示為重複項目。此選項僅提供給管理員使用。 |
   | [!UICONTROL **無最近的資料**] | 僅顯示在過去 90 天內未收集任何資料的元件。此選項僅提供給管理員使用。 |
   | [!UICONTROL **建立者：Adobe**] <!-- I don't see this option--> | 僅顯示由 Adobe 建立的元件。並不會顯示由管理員或您組織中的其他使用者建立的元件。 |

   {style="table-layout:auto"}

## 資料字典元件資訊 {#dd-component-information}

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **已核准**] | <p>指出該元件已經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **取消核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「未核准」。</p> |
| [!UICONTROL **未核准**] | <p>指出該元件尚未經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「已核准」。</p> |
| [!UICONTROL **說明**] | 描述元件的預定功能。(此資訊由 Analytics 管理員新增，如[新增元件說明](/help/components/add-component-descriptions.md)中所述。) |
| [!UICONTROL **經常與下列項目搭配使用**] | <p>顯示您正在查看的元件最常與哪些元件一起使用。</p><p>在5種主要元件類型中，最多會顯示5個元件：量度、計算量度、Dimension、篩選和日期範圍。</p><p>此清單是根據前 90 天的資料。只會顯示您有存取檢視權限的元件。</p><p>管理員可檢視 [!UICONTROL **一律包括**] 和 [!UICONTROL **一律排除**]. 這些選項可讓管理員組織使用者在本區段中看到的元件。</p> |
| [!UICONTROL **類似於**] | <p>顯示與您正在查看的元件具有相似標籤的元件。</p><p>在5種主要元件類型中，最多會顯示5個元件：量度、計算量度、Dimension、篩選和日期範圍。</p><p>只會顯示您有存取檢視權限的元件。</p><p>報告套裝中的任何重複元件都將顯示在此處。Analytics 管理員應識別並移除所有重複的元件，如[監視資料字典健康情況](/help/components/data-dictionary/monitor-data-dictionary-health.md).中所述</p><p>管理員可檢視 [!UICONTROL **一律包括**] 和 [!UICONTROL **一律排除**]. 這些選項可讓管理員組織使用者在本區段中看到的元件。</p> |
| [!UICONTROL **標記**] | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
| [!UICONTROL **元件類型**] | 列出其元件的類型，包括Dimension、量度、篩選或日期範圍。 |
| [!UICONTROL **建立者**] | 顯示建立元件的使用者名稱。 |
| [!UICONTROL **預覽**] | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
| [!UICONTROL **上次修改日期**] | 顯示上次修改元件的日期。檢視篩選器、量度、計算量度和日期範圍時，會顯示此區段。 |

{style="table-layout:auto"}