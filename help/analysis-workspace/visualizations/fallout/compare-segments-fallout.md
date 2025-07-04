---
description: 瞭解如何在Analysis Workspace中從接觸點建立區段、新增區段做為接觸點，以及比較各種區段之間的關鍵工作流程。
keywords: 流失和分段, 流失分析中的區段, 比較流失中的區段
title: 在流失分析中套用區段
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 34%

---

# 在流失分析中套用區段

您可以從接觸點建立區段、新增區段作為接觸點，以及在 Analysis Workspace 的各種區段間比較關鍵工作流程。

>[!IMPORTANT]
>
>在流失分析中當作查核點使用的區段，其所用容器的層級必須低於流失視覺效果的整體設定。分析個人內容流失時，當作查核點使用的區段必須是工作階段或事件型區段。 分析工作階段相關流失率時，當作查核點使用的區段必須為事件相關區段。 如果使用無效的組合，流失率為100%。 當您新增不相容的區段作為接觸點時，流失視覺效果中會顯示警告。 特定的無效區段容器組合會產生無效的流失率圖表，例如：
>
>* 使用以人物為基礎的區段，作為個人內容流失視覺效果內的接觸點。
>* 使用以人為基礎的區段，作為工作階段內容流失視覺效果內的接觸點。
>* 使用工作階段型區段，作為工作階段內容流失視覺效果內的接觸點。

<!-- Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* -->

## 從接觸點建立區段

1. 從您特別感興趣的某個接觸點建立區段，之後您可以將此區段套用於其他報表。以滑鼠右鍵按一下接觸點並選取&#x200B;**[!UICONTROL 從接觸點建立區段]**。

   ![反白顯示「從接觸點建立區段」的「接觸點」下拉式功能表。](assets/fallout-createsegment.png)

   [!UICONTROL 區段產生器]隨即開啟，預先填入符合您所選接觸點的預先建立連續區段：

   ![區段產生器會顯示預先填入和預先建立的循序區段。](assets/fallout-definesegment.png)

1. 提供區段的標題和描述，然後將其儲存。

   您現在可以在任何需要的專案中使用此區段。

## 將區段新增為接觸點

如果您想查看美國用戶 (舉例來說) 的趨勢以及如何影響流失，只需將美國用戶區段拖曳至流失中：

![已選取並反白顯示美國使用者區段，以拖曳至流失中。](assets/fallout-addfilter.png)

或者，您也可以將美國用戶區段拖曳至其他檢查點尚，用以建立 AND 接觸點。

## 比較流失率中的區段

您可以在「流失」視覺效果中比較無數區段。

1. 從左側的[!UICONTROL 區段]面板選取您要比較的區段。 在此範例中，選取了三個區段： *小眾測試版詳細資料：頁面版本A*、*小眾測試版詳細資料：頁面版本B*&#x200B;和&#x200B;*小眾測試版詳細資料：頁面版本C*。
1. 將三個區段拖曳至視覺效果頂端的區段放置區。


1. 選用性：您可以保留&#x200B;*所有人員*&#x200B;作為預設容器，或刪除容器。

   ![在上一步中拖曳的「流失」顯示「所有造訪」以及兩個區段。](assets/fallout-multiplefilters.png)

1. 您現在可以比較三個區段的流失，例如某個區段在哪裡表現較另一個區段優秀，或是使用其他分析角度。
