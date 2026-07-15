---
title: 子事件分析
description: 瞭解子事件分析如何讓您在Customer Journey Analytics中篩選事件內的個別產品或其他容器，消除產品報表中的歸因出血。
feature: Segmentation
hide: true
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 9%

---

# 子事件分析

{{release-limited-testing}}

子事件分析可讓您在比事件層級更精細的層級分析事件資料。 您可以對事件中的個別容器進行分段，而不需篩選整個事件。 例如：

- 依特定產品類別分段，而不包括同一訂單購買的所有其他產品
- 依內容分析資料中的特定資產類別劃分割槽段？
- 依媒體分析資料中的特定媒體頻道進行分段。


在Customer Journey Analytics中，您可以在資料檢視中定義您要使用子事件分析的容器。 若沒有子事件分析，對容器專案屬性進行分段會傳回所有事件、工作階段、人員、（全域）帳戶[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、購買群組[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、商機[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}或您定義的其他[容器](/help/data-views/create-dataview.md#containers-1)。 結果是不正確的歸因和膨脹的收入量度。 子事件分析會將篩選器範圍縮小至事件中的個別容器列，並解決這些問題。

在子事件分析中，「排除」邏輯的行為與針對容器的標準事件層級排除不同。 當您排除容器中的專案屬性時，區段會傳回容器中有&#x200B;**專案**&#x200B;但不符合排除條件的事件。 區段不會傳回完全沒有專案的事件。


## 範例

您只想測量專業西裝類別的收入。 若沒有次事件分析，套用專業套裝的區段會包含任何訂單（事件）上每項產品的收入，其中至少包含一項專業套裝類別的產品。 透過子事件分析，您可以將篩選範圍限定在產品層級，並且只傳回專業西裝類別產品的收入。

您也要測量除專業西裝類別外的所有其他類別的線上收入。

>[!BEGINTABS]

>[!TAB 事件分析]

在細分產生器中，或當作&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 事件]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![顯示產品類別專業套裝事件層級劃分的面板](./assets/product-category-segmentation-events.png)

因此，所有包含至少一個&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;的訂單都會被考慮，而且這些訂單中其他產品的收入會包含在&#x200B;**[!UICONTROL 收入]**&#x200B;量度中。當您報告類別時，會報告&#x200B;**[!UICONTROL product_category]**&#x200B;的所有其他值，這些值屬於包含&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;之產品的訂單。

>[!TAB 子事件分析]

在區段產生器中，或作為&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 產品]**&#x200B;容器上&#x200B;**[!UICONTROL 包含]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![顯示產品類別專業套裝之子事件層級區段的面板](./assets/product-category-segmentation-subevents.png)

因此，所有至少包含&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_category]**&#x200B;的訂單都會被考慮，而且在&#x200B;**[!UICONTROL 收入]**&#x200B;量度中，只會包含屬於&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL product_categorey]**&#x200B;的產品收入。當您報告類別時，僅報告&#x200B;**[!UICONTROL 專業套裝]** **[!UICONTROL Rproduct_category]**。

>[!TAB 子事件分析（排除）]

在細分產生器中，或作為&#x200B;**[!UICONTROL 快速區段]**&#x200B;的一部分，您指定在&#x200B;**[!UICONTROL 產品]**&#x200B;容器上&#x200B;**[!UICONTROL 排除]** **[!UICONTROL Dimension]** **[!UICONTROL product_category]** **[!UICONTROL 等於]** **[!UICONTROL 專業套裝]**。

![在子點選層級顯示區段的面板，以排除產品類別Men](./assets/product-category-segmentation-subevents-exclude.png)

若要在產品層級排除，至少包含一個產品的事件，然後在該範圍內套用子事件層級的排除。 此排除專案與事件層級排除專案不同，後者會排除整個事件。

>[!ENDTABS]


<!-- 

AI generated content

title: Sub-Event Analysis in Customer Journey Analytics
description: Learn how to analyze data below the event level in Customer Journey Analytics using sub-event containers to segment individual items within event arrays.
feature: Filters, Segments
role: User, Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: e5aeaef3-57b4-4cce-b025-6dea43f9e14b
    internal-label: Admin
---

# Sub-event analysis

Sub-event analysis lets you segment and analyze data at a level below the individual event — for example, a specific product within a product list, or a single item within an array field. Without this capability, all data in arrays is automatically lifted to the event level, which causes attribution bleed, inflated counts, and inaccurate metrics.

**Example:** A customer purchases three items in a single order. Without sub-event analysis, a segment for *red shoes* would match the entire event, pulling in all three products. With sub-event analysis, the segment evaluates each item in the product list individually, returning only the red shoes row.

Sub-event analysis is built on *sub-event containers* — containers that an administrator configures in the data view. Once configured, these containers are available for use in the Segment builder and in certain visualizations.

## Configure sub-event containers (administrators)

Administrators configure sub-event containers from the **[!UICONTROL Containers]** tab in the data view builder. This tab appears before the **[!UICONTROL Components]** tab.

### System containers and custom containers

The **[!UICONTROL Containers]** tab has two sections:

| Section | Description |
|---|---|
| **[!UICONTROL System]** | The standard Person, Session, and Event containers. Administrators can rename a system container's display name but cannot otherwise modify it. |
| **[!UICONTROL Custom]** | Schema-based or component-based containers that you create from your data view's schema fields. These represent the sub-event level of your data — for example, `productListItems` in an e-commerce schema. |

The **[!UICONTROL Container type]** column shows whether each custom container is **[!UICONTROL Schema-based]** or **[!UICONTROL Component-based]**. Component-based containers only appear after you add the corresponding dimension or metric to the data view.

### Curate a container

Custom containers must be curated before they are available in the Segment builder. Curating a container is an explicit opt-in: only curated containers are valid for use in segments.

To curate a custom container, select the container in the **[!UICONTROL Custom]** table and enable it for segmentation.

>[!NOTE]
>
>A maximum of 100 custom containers can be curated per data view, across all Customer Journey Analytics SKUs. This limit may change in the future. Any auto-generated occurrence metrics from curated containers count toward the 5,000 component limit per data view.

### Container display names

The container's internal name is immutable after creation. Only the display name is editable. You can also add context labels and hide a container from reporting without removing it.

## Use sub-event containers in segments

Once an administrator has curated at least one sub-event container, it is available in the Segment builder as a new container option alongside Person, Session, and Event.

### Container auto-inference

When you drag a dimension that belongs to a sub-event container (for example, `productID`) into the Segment builder canvas, the builder automatically selects the most granular applicable sub-event container rather than defaulting to the Event container. This means the segment evaluates at the sub-event level without any additional configuration.

>[!NOTE]
>
>Container auto-inference applies when the dimension is exclusively part of one sub-event container. If a dimension appears in multiple containers, you must select the container manually.

### Mixed containers

When you add dimensions or metrics from different sub-event containers in a single segment rule, the builder uses the highest (least granular) container that covers all components. If all components share the same sub-event container, that shared container is used.

### Exclude logic

Exclusion at the sub-event level works differently from event-level exclusion. To exclude a specific sub-event condition, the system first includes events that contain a matching sub-event, then applies the exclusion within those events. This means the segment identifies *events that have the sub-event* and then removes the matching sub-event rows — rather than excluding all events where the sub-event does not exist.

This behavior is intentional but counterintuitive. Use explicit **[!UICONTROL Include]** and **[!UICONTROL Exclude]** containers when building sub-event exclusion logic to make the intent clear.

### Filter by container in the left rail

The Segment builder left rail includes a new option to filter the component list by container. Selecting a container shows only the dimensions and metrics that belong to that container, making it easier to build focused sub-event segment conditions.

This container filter is available in the Segment builder only. It is not currently available in other left rail panels.

## Auto-generated occurrence metrics

When an administrator curates a sub-event container, an **Occurrences** metric is automatically generated for that container. This metric counts the number of sub-event rows that match the container and appears in the left rail as a selectable metric when building segments.

These auto-generated metrics behave like the standard Person, Session, and Event count metrics:

- They cannot be duplicated or structurally modified.
- You can rename them, add context labels, and hide them from reporting.
- If you rename the curated container, the auto-generated metric name updates automatically — unless you have already manually renamed the metric.

## Histogram visualization

The Histogram is the only visualization that requires you to select a sub-event container explicitly. A container drop-down menu appears in the Histogram panel when sub-event containers are available in the data view, allowing you to scope the distribution to a specific container level.

No other panels or visualizations require changes to support sub-event containers.

-->
