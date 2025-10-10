---
description: Analysis Workspace 中的資料字典允許使用者對 Analysis Workspace 中的各種元件建立目錄和追蹤，包括其預定用途、已核准的元件、重複的元件等等。
title: 編輯元件專案
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
source-git-commit: f940e5cba11df0ff158093a503213ff1641b1c5d
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 69%

---

# 編輯元件專案

Customer Journey Analytics管理員可以在資料字典中編輯指定資料檢視的元件專案。 所有資料檢視的使用者皆可檢視所做的任何變更。

若要編輯資料字典中的元件條目：

1. 前往包含要編輯之元件的 Analysis Workspace 專案。

1. 選取Analysis Workspace按鈕面板中的&#x200B;**資料字典**&#x200B;圖示。 (存取資料字典的替代方法說明請見[資料字典概觀](/help/components/data-dictionary/data-dictionary-overview.md)中的「存取資料字典」。)

   顯示資料字典視窗。

   ![資料字典管理員檢視顯示字典健康狀態](assets/data-dictionary-admin.png)

1. 確定在下拉式選單中選取了正確的資料檢視。 依預設，會顯示您已所在的資料檢視。

1. (可選) 開始在搜尋欄位中鍵入要編輯的元件名稱。

   元件的類型可依據顏色和圖示加以識別。**維度**![維度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)是橙色的，**區段**![區段圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg)是藍色的，**日期範圍**![日期範圍圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)是紫色的，而&#x200B;**量度**![量度圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg)是綠色的。Adobe 圖示代表計算量度範本或區段範本，計算機圖示![計算機圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)則代表由貴組織中的 Analytics 管理員所建立的計算量度。

1. (可選) 選取 **篩選器** 圖示 ![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然後選擇以下任一篩選器選項以篩選元件清單：

   | 選項 | 函數 |
   |---------|----------|
   | **[!UICONTROL 已核准]** | 僅顯示標記為由管理員核准的元件。 |
   | **[!UICONTROL 我的最愛]** | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/components/overview.md)。 |
   | **[!UICONTROL 維度]** | 僅顯示維度的元件。（當您首次存取資料字典時，**[!UICONTROL 快速區段]**&#x200B;索引標籤中也會提供此選項。） |
   | **[!UICONTROL 量度]** | 僅顯示量度的元件。（當您首次存取資料字典時，**[!UICONTROL 快速區段]**&#x200B;索引標籤中也會提供此選項。） |
   | **[!UICONTROL 區段]** | 僅顯示區段的元件。（當您首次存取資料字典時，**[!UICONTROL 快速區段]**&#x200B;索引標籤中也會提供此選項。） |
   | **[!UICONTROL 日期範圍]** | 僅顯示日期範圍的元件。（當您首次存取資料字典時，**[!UICONTROL 快速區段]**&#x200B;索引標籤中也會提供此選項。） |
   | **[!UICONTROL 全部顯示]** | 顯示所有元件。此選項僅提供給管理員使用。 |
   | **[!UICONTROL 未經核准]** | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |
   | **[!UICONTROL 缺少說明]** | 僅顯示在說明欄位中還沒有說明的元件。此選項僅提供給管理員使用。 |
   | **[!UICONTROL 顯示重複項目]** | 僅顯示與所選資料檢視中其他元件具有相同名稱或相同說明的元件。 這包括您建立的元件以及Adobe提供的元件。 名稱或說明必須完全相符，才能顯示為重複專案。 此選項僅提供給管理員使用。 |
   | **[!UICONTROL 無最近的資料]** | 僅顯示在過去 90 天內未收集任何資料的元件。此選項僅提供給管理員使用。 |
   | **[!UICONTROL 由Adobe建立]** <!-- I don't see this option--> | 僅顯示由 Adobe 建立的元件。例如，**[!UICONTROL Adobe Target]**。 並不會顯示由管理員或您組織中的其他使用者建立的元件。 |

   {style="table-layout:auto"}

1. （選擇性）選取&#x200B;**排序**&#x200B;圖示![排序元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)，然後選取下列任一區段選項來排序元件清單：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **建議**] | 以建議置於清單頂端的元件來對元件進行排序。您或貴組織中其他人近期最頻繁使用的元件會顯示在清單的較高位置。 |
   | [!UICONTROL **字母順序**] | 依字母順序對元件進行排序。 |
   | [!UICONTROL **分類**] | 根據元件類型 (維度、量度、區段、日期範圍) 對元件進行排序。 |

   {style="table-layout:auto"}

1. 從元件清單中選取您要編輯的元件。

1. 選擇元件名稱旁邊的&#x200B;**編輯**&#x200B;圖示![資料字典編輯圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)。

1. 編輯有關元件的以下任何資訊：

   | 選項 | 函數 |
   |---------|----------|
   | **[!UICONTROL 已核准]** | <p>指出該元件已經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;**[!UICONTROL 取消核准]**&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「未核准」。</p> |
   | **[!UICONTROL 未核准]** | <p>指出該元件尚未經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;**[!UICONTROL 核准]**&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「已核准」。</p> |
   | **[!UICONTROL 說明]** | 描述元件的預定功能。(此資訊由 Analytics 管理員新增，如[新增元件說明](/help/components/add-component-descriptions.md)中所述。) |
   | **[!UICONTROL 經常與下列項目搭配使用]** | <p>顯示您正在查看的元件最常與哪些元件一起使用。</p><p>在 5 種主要元件類型中最多顯示 5 個元件：量度、計算量度、維度、區段和日期範圍。</p><p>此清單顯示過去 90 天的資料。只會顯示您有權檢視的元件。</p><p>管理員可以在「**[!UICONTROL 永遠包含]**」和「**[!UICONTROL 永遠排除]**」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在您組織使用者看到的元件之前，請先套用&#x200B;**全部顯示**&#x200B;區段，以確保您看到任何未與您共用的元件，這些元件可能已由其他管理員新增。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | **[!UICONTROL 類似於]** | <p>顯示與您正在查看的元件具有相似名稱的元件。</p><p>在 5 種主要元件類型中最多顯示 5 個元件：量度、計算量度、維度、區段和日期範圍。</p><p>只會顯示您有存取檢視權限的元件。</p><p>資料檢視中的任何重複元件都會顯示在這裡。 Analytics 管理員應識別並移除所有重複的元件，如[監視資料字典健康情況](/help/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理員可以在「**[!UICONTROL 永遠包含]**」和「**[!UICONTROL 永遠排除]**」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在您組織使用者看到的元件之前，請先套用&#x200B;**全部顯示**&#x200B;區段，以確保您看到任何未與您共用的元件，這些元件可能已由其他管理員新增。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**注意：**&#x200B;目前，「**類似於**」區段僅包括您建立的元件，不包括 Adobe 提供的元件。Adobe 提供的元件會在未來版本中新增。</p> |
   | **[!UICONTROL 產品相容性]** | 指出此計算量度可在Customer Journey Analytics中使用的位置。 <p>可能的值包括：</p><ul><li>**[!UICONTROL Customer Journey Analytics中的所有地方]**：計算量度可用於所有Customer Journey Analytics，包括Analysis Workspace、Report Builder等。</li><li>**[!UICONTROL 在 Customer Journey Analytics 中各處 (不包括實驗)]**：計算量度可用於除實驗面板之外的所有 Customer Journey Analytics 部分。</li> <p>如需判斷計算量度是否可用於實驗之條件的詳細資訊，請參閱[實驗面板](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel)中的[在Experimentation面板](/help/analysis-workspace/c-panels/experimentation.md)中使用計算量度。</p></ul> |
   | **[!UICONTROL 標記]** | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
   | **[!UICONTROL 元件類型]** | 列出元件的類型，無論是維度、指標、區段還是日期範圍。 |
   | **[!UICONTROL 建立者]** | 顯示建立元件的使用者名稱。 |
   | **[!UICONTROL 預覽]** | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
   | **[!UICONTROL 上次修改日期]** | 顯示上次修改元件的日期。檢視區段、量度、計算量度和日期範圍時，會顯示此區段。 |

   {style="table-layout:auto"}

1. 按一下&#x200B;**儲存**&#x200B;圖示![資料字典儲存圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg)以儲存您的變更。
