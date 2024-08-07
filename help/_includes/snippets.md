---
source-git-commit: 2f7e11106334560d3c4b54e6c5eaf84d5e1d4fb6
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 64%

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
| [!UICONTROL **標記**] | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
| [!UICONTROL **元件類型**] | 列出其元件型別，不論是Dimension、量度、篩選器或日期範圍。 |
| [!UICONTROL **建立者**] | 顯示建立元件的使用者名稱。 |
| [!UICONTROL **預覽**] | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
| [!UICONTROL **上次修改日期**] | 顯示上次修改元件的日期。檢視篩選器、量度、計算量度和日期範圍時，會顯示此區段。 |

{style="table-layout:auto"}

## 元件排序選項 {#components-sort-options}

| 選項 | 功能 |
|---------|----------|
| [!UICONTROL **建議**] | 以建議置於清單頂端的元件來對元件進行排序。您或貴組織中其他人近期最頻繁使用的元件會顯示在清單的較高位置。 |
| [!UICONTROL **字母順序**] | 依字母順序對元件進行排序。 |
| [!UICONTROL **分類**] | 根據元件型別（維度、量度、篩選器、日期範圍）來排序元件。 |

{style="table-layout:auto"}

## 時間比較 {#apply-time-comparison}

您可以將目前的時段與先前的時段進行比較。 如果您在此選單中選取選項，每個資料點都會收到類似顏色的虛線對應專案。 此對應專案代表所選先前日期範圍內的相同量度。 設定此選項可將圖表上的專案數和表格中的列數加倍。

可用的時間比較選項包括上一個期間、13週前、52週前以及自訂日期範圍。 如果您選取「自訂日期範圍」 ，會出現其他選項，供您選取數字和粒度。 如果您選取「無」，則會移除日期比較。
