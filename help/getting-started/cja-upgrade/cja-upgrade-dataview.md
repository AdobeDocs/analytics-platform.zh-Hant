---
title: 在 Customer Journey Analytics 中建立資料視圖
description: 瞭解從Adobe Analytics升級至Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 45%

---

# 在 Customer Journey Analytics 中建立資料視圖 {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="在 Customer Journey Analytics 中建立資料視圖"
>abstract="資料視圖是 Customer Journey Analytics 的專用容器，讓您決定如何解讀來自連線的資料。<br><br>雖然初次建立資料視圖只需幾分鐘，但使用所需的元件設定來設定每個維度和量度則需要幾天的時間。調整這些設定會追溯適用，因此您的組織可以隨著時間調整設定。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

建立資料視圖需要從結構描述元素建立量度和維度或使用標準元件。大多數結構描述元素可以是維度或量度，具體取決於您的業務需求。 將結構描述元素拖到資料視圖中後，右側會出現選項，您可以在其中調整維度或量度在 Customer Journey Analytics 中的執行方式。

若要建立資料檢視：

1. 登入 [Customer Journey Analytics](https://analytics.adobe.com) 並移至「**[!UICONTROL 資料視圖]**」索引標籤。

1. 選取&#x200B;**[!UICONTROL 建立新資料檢視]**。 或者，您可以從資料視圖清單中選取現有資料視圖進行編輯。

1. 在&#x200B;[!UICONTROL **設定**]&#x200B;索引標籤上，指定資料檢視的名稱，並設定其基本設定、元件和行事曆選項。

   如需每個欄位的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[設定](/help/data-views/create-dataview.md#configure)。

   ![設定資料視圖](assets/dataview-configure.png)

1. 選取「[!UICONTROL **元件**]」索引標籤。

   [!UICONTROL **元件**]&#x200B;索引標籤是您設定資料檢視元件的位置，這表示您可以從結構描述元素建立量度和維度。 您也可以使用標準元件。

   ![元件標籤](assets/dataview-components.png)

1. 從&#x200B;[!UICONTROL **元件**]&#x200B;索引標籤，將結構描述元素從左側邊欄拖曳至&#x200B;[!UICONTROL **Metrics**]&#x200B;區段或&#x200B;[!UICONTROL **Dimensions**]&#x200B;區段。 新增的結構元素會在資料檢視中變成量度或維度。

   如需有關將元件新增至資料檢視時可用選項的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[元件](/help/data-views/create-dataview.md#components)。

1. 選取「[!UICONTROL **設定**]」索引標籤。從這裡，您可以設定篩選器以套用至整個資料檢視，並設定工作階段逾時和量度。

   如需有關設定資料檢視的設定時可用的選項的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md)中的[設定](/help/data-views/create-dataview.md#settings)。

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存資料檢視的組態。

1. 指定所有所需設定後，選取&#x200B;**[!UICONTROL 儲存並完成]**。

{{upgrade-final-step}}
