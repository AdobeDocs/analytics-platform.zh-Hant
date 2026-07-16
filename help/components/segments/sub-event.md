---
title: 子事件分析
description: 瞭解子事件分析如何讓您在Customer Journey Analytics中篩選事件內的個別產品或其他容器，消除產品報表中的歸因出血。
feature: Segmentation
hide: true
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: babf5a87458103ca962113114d18b9dd8e1ab303
workflow-type: tm+mt
source-wordcount: 680
ht-degree: 8%

---

# 子事件分析

{{release-limited-testing}}

子事件分析可讓您在比事件層級更精細的層級分析事件資料。 您可以對事件中的個別容器進行分段，而不需篩選整個事件。 例如：

* 依特定產品類別分段，而不包括同一訂單購買的所有其他產品。
* 在內容分析資料中依特定資產類別分段。
* 依媒體分析資料中的特定媒體頻道進行分段。

在Customer Journey Analytics中，您可以在資料檢視中定義您要使用子事件分析的容器。 若沒有子事件分析，對容器專案屬性進行分段會傳回所有事件、工作階段、人員、（全域）帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、商機[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}或您定義的其他[容器](/help/data-views/create-dataview.md#containers-1)。 結果是不正確的歸因和膨脹的收入量度。 子事件分析會將篩選器範圍縮小至事件中的個別容器列，並解決這些問題。

在子事件分析中，「排除」邏輯的行為與針對容器的標準事件層級排除不同。 當您排除容器中的專案屬性時，區段會傳回容器中有&#x200B;**專案**&#x200B;但不符合排除條件的事件。 區段不會傳回完全沒有專案的事件。


## 範例

您只想測量專業西裝類別的收入。 若沒有次事件分析，套用專業套裝的區段會包含任何訂單（事件）上每項產品的收入，其中至少包含一項專業套裝類別的產品。 透過子事件分析，您可以將篩選範圍限定在產品層級，並且只傳回專業西裝類別產品的收入。

您也要測量除專業西裝類別外的所有其他類別的線上收入。

>[!BEGINTABS]

>[!TAB 事件分析]

在細分產生器中，或當作&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 事件]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![顯示產品類別專業套裝事件層級劃分的面板](./assets/product-category-segmentation-events.png)

因此，所有包含至少一個&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;的訂單都會被考慮，而且這些訂單中其他產品的收入會包含在&#x200B;**[!UICONTROL 收入]**量度中。
當您報告類別時，會報告**[!UICONTROL product_category]**&#x200B;的所有其他值，這些值屬於包含&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;之產品的訂單。

>[!TAB 子事件分析]

您已在資料檢視中定義了&#x200B;**[!UICONTROL 產品詳細資料]** [自訂容器](/help/data-views/create-dataview.md#containers)，以對產品進行子事件分析。

![產品詳細資料容器](assets/product-details-container.png)

在區段產生器中，或作為&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 產品詳細資料]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![顯示產品類別專業套裝之子事件層級區段的面板](./assets/product-category-segmentation-subevents.png)

因此，所有至少包含&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;的訂單都會被考慮，而且在&#x200B;**[!UICONTROL 收入]**&#x200B;量度中，只會包含屬於&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_categorey]**的產品收入。
當您報告類別時，僅報告**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**。

>[!TAB 子事件分析（排除）]

您已在資料檢視中定義了&#x200B;**[!UICONTROL 產品詳細資料]** [自訂容器](/help/data-views/create-dataview.md#containers)，以對產品進行子事件分析。

![產品詳細資料容器](assets/product-details-container.png)

在細分產生器中，或作為&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 產品詳細資料]**&#x200B;容器上&#x200B;**[!UICONTROL 排除]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![在子點選層級顯示區段的面板，以排除產品類別Men](./assets/product-category-segmentation-subevents-exclude.png)

若要在產品層級排除，至少包含一個產品的事件，然後在該範圍內套用子事件層級的排除。 此排除專案與事件層級排除專案不同，後者會排除整個事件。

>[!ENDTABS]
