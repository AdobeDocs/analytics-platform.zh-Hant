---
title: 在 Customer Journey Analytics 中建立資料檢視
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: eb9b749a5c61da3b4b5d2eeeed93bf5e4702a415
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 90%

---

# 在 Customer Journey Analytics 中建立資料檢視 {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="在 Customer Journey Analytics 中建立資料檢視"
>abstract="資料視圖是 Customer Journey Analytics 的專用容器，讓您決定如何解讀來自連線的資料。<br><br>雖然初次建立資料視圖只需幾分鐘，但使用所需的元件設定來設定每個維度和量度則需要幾天的時間。調整這些設定會追溯適用，因此您的組織可以隨著時間調整設定。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

建立資料檢視需要從結構描述元素建立量度和維度或使用標準元件。大多數結構描述元素可以是維度或量度，具體取決於您的業務需求。將結構描述元素拖到資料檢視中後，右側會出現選項，您可以在其中調整維度或量度在 Customer Journey Analytics 中的執行方式。

若要建立資料檢視：

1. 登入[Customer Journey Analytics](https://analytics.adobe.com)，並選取頂端功能表中的&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。

1. 選取「**[!UICONTROL 建立新的資料檢視]**」。或者，您可以從資料檢視清單中選取現有資料檢視進行編輯。

1. 在「[!UICONTROL **設定**]」索引標籤上，指定資料檢視的名稱並設定其基本設定、元件和行事曆選項。

   有關每個欄位的詳細資訊，請參閱「[建立或編輯資料檢視」](/help/data-views/create-dataview.md)中的「[設定](/help/data-views/create-dataview.md#configure)」。

   ![設定資料檢視](assets/dataview-configure.png)

1. 選取「[!UICONTROL **元件**]」索引標籤。

   「[!UICONTROL **元件**]」索引標籤是您設定資料檢視的元件所在處，這表示您可以從結構描述元素建立量度和維度。您也可以使用標準元件。

   ![元件標籤](assets/dataview-components.png)

1. 從「[!UICONTROL **元件**]」索引標籤中，將結構描述元素從左側欄拖曳到「[!UICONTROL **量度**]」部分或「[!UICONTROL **維度**]」部分。您新增的結構描述元素將成為資料檢視中的量度或維度。

   有關新增元件至資料檢視時可用選項的詳細資訊，請參閱「[建立或編輯資料檢視](/help/data-views/create-dataview.md)」中的「[元件](/help/data-views/create-dataview.md#components)」。

1. 選取「[!UICONTROL **設定**]」索引標籤。從這裡，您可以設定區段以套用至整個資料檢視，並設定工作階段逾時和量度。

   有關進行資料檢視設定時可用選項的詳細資訊，請參閱「[建立或編輯資料檢視](/help/data-views/create-dataview.md)」中的「[設定](/help/data-views/create-dataview.md#settings)」。

1. 選取「**[!UICONTROL 儲存]**」，儲存您資料檢視的設定。

1. 指定所有所需設定後，選取「**[!UICONTROL 儲存並完成]**」。

{{upgrade-final-step}}
