---
title: 在Customer Journey Analytics中建立資料檢視
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 23%

---

# 在Customer Journey Analytics中建立資料檢視

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

建立資料視圖需要從綱要元素建立量度和維度或使用標準元件。大多數結構描述元素可以是維度或量度，具體取決於您的業務需求。 將綱要元素拖到資料視圖中後，右側會出現選項，您可以在其中調整維度或量度在 Customer Journey Analytics 中的執行方式。

若要建立資料檢視：

1. 登入 [Customer Journey Analytics](https://analytics.adobe.com) 並移至「**[!UICONTROL 資料視圖]**」索引標籤。

1. 選取&#x200B;**[!UICONTROL 建立新資料檢視]**。 或者，您可以從資料視圖清單中選取現有資料視圖進行編輯。

1. 在&#x200B;[!UICONTROL **設定**]&#x200B;索引標籤上，指定資料檢視的名稱，並設定其基本設定、元件和行事曆選項。

   如需每個欄位的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[設定](/help/data-views/create-dataview.md#configure)。

   ![設定資料視圖](assets/dataview-configure.png)

1. 選取「[!UICONTROL **元件**]」索引標籤。

   [!UICONTROL **元件**]&#x200B;索引標籤是您設定資料檢視元件的位置，這表示您可以從結構描述元素建立量度和維度。 您也可以使用標準元件。

   ![元件標籤](assets/dataview-components.png)

1. 從&#x200B;[!UICONTROL **元件**]&#x200B;索引標籤，將結構描述元素從左側邊欄拖曳至&#x200B;[!UICONTROL **Metrics**]&#x200B;區段或&#x200B;[!UICONTROL **Dimension**]&#x200B;區段。 新增的結構元素會在資料檢視中變成量度或維度。

   如需有關將元件新增至資料檢視時可用選項的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[元件](/help/data-views/create-dataview.md#components)。

1. 選取「[!UICONTROL **設定**]」索引標籤。從這裡，您可以設定篩選器以套用至整個資料檢視，並設定工作階段逾時和量度。

   如需有關設定資料檢視的設定時可用的選項的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[設定](/help/data-views/create-dataview.md#settings)。

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存資料檢視的組態。

1. 指定所有所需設定後，選取&#x200B;**[!UICONTROL 儲存並完成]**。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。

