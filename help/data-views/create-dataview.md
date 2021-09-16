---
title: 建立資料檢視
description: 您可以調整以建立或編輯資料檢視的所有設定。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 77%

---

# 建立資料檢視

建立資料檢視需要從結構元素建立量度和維度或使用標準元件。根據您的業務需求，大部分的結構元素可以是維度或量度。 將結構元素拖曳至資料檢視後，右側會顯示選項，您可以在其中調整維度或量度在CJA中的運作方式。

## 設置資料檢視設定和容器

1. 在 Customer Journey Analytics 中，前往「**[!UICONTROL 資料檢視]**」索引標籤。
2. 按一下「**[!UICONTROL 新增]**」以建立和設定新資料檢視。

![新資料視圖](assets/new-data-view.png)

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 連線] | 此欄位會將資料檢視連結至您先前建立的連線，其中包含一或多個 Adobe Experience Platform 資料集。 |
| [!UICONTROL 名稱] | 必須為資料檢視命名。 |
| [!UICONTROL 說明] | 詳細說明非必填，但建議使用。 |
| [!UICONTROL 時區] | 選擇要顯示資料的時區。 |
| [!UICONTROL 標籤] | [!UICONTROL 標籤]可讓您將資料檢視整理到不同類別中。 |
| [!UICONTROL 容器] | 您可以在此處重新命名容器，以決定容器在任何以此資料檢視為基礎的 Workspace 專案中的顯示方式。 [!UICONTROL 容器]會用於篩選和流失/流量等，以定義範圍或內容的寬度或窄度。 [了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=zh-Hant#filter-containers) |
| [!UICONTROL 「人員」容器名稱是……] | 「[!UICONTROL 人員]」(預設)。「[!UICONTROL 人員]」容器包含指定時段內訪客的每次瀏覽和頁面檢視。您可以將此容器重新命名為「User」或您偏好的其他任何詞語。 |
| [!UICONTROL 「工作階段」容器名稱是……] | 「[!UICONTROL 工作階段]」(預設)。「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。您可以將此容器重新命名為「Visit」或您偏好的其他任何詞語。 |
| [!UICONTROL 「事件」容器名稱是……] | 「[!UICONTROL 事件]」(預設)。「[!UICONTROL 事件]」容器定義您要在篩選器中包含或排除哪些頁面事件。 |

接著，您可以從結構元素建立量度和維度。您也可以使用標準元件。

## 從結構元素建立量度和維度

1. 在 [!UICONTROL Customer Journey Analytics] > 「[!UICONTROL 資料檢視]」中，按一下「[!UICONTROL 元件]」索引標籤。

![元件索引標籤](assets/components-tab.png)

您可以在左上角看到「[!UICONTROL 連線]」，其中包含資料集，以及下面的[!UICONTROL 「結構」欄位]。請記住以下事項：

* 已包含的元件是標準必需元件 (系統生成)。
* Adobe 預設會套用&#x200B;**[!UICONTROL 包含資料]**&#x200B;篩選條件，以便只顯示包含資料的結構描述欄位。 如果您要尋找不含資料的欄位，請移除此篩選條件。

1. 現在，從左側邊欄拖曳結構欄位 (例如 [!UICONTROL pageTitle]) 至 Metrics 或 Dimensions 區段。

   您可以多次將相同的結構欄位拖曳至維度或量度區段，並以不同的方式設定相同的維度或量度。例如，從 **[!UICONTROL &#x200B;pageTitle]** &#x200B;欄位，您可以重新命名右側的 **[!UICONTROL Component Name]**，以建立名為「Product Pages」的維度，以及另一個「Error pages」等。從 **[!UICONTROL pageTitle]** 結構欄位中，您也可以從字串值建立量度。例如，您可以建立一或多個具有不同歸因設定和不同包含/排除值的「**[!UICONTROL 訂單]**」量度。

   ![標籤3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >您可以從左側邊欄拖曳整個架構欄位資料夾，並自動將資料夾排序為傳統區段。 字串欄位結尾在[!UICONTROL Dimension]區段，而數字在[!UICONTROL 量度]區段。 或者，您也可以按一下「**[!UICONTROL 新增全部]**」，然後新增所有架構欄位。

1. 選取元件後，右側會出現許多設定。使用中所述的設定來配置元件

* [ 元件設定概述](/help/data-views/component-settings/overview.md)
* [ 屬性元件設定](/help/data-views/component-settings/attribution.md)
* [ 行為元件設定](/help/data-views/component-settings/behavior.md)
* [ Formatcomponent設定](/help/data-views/component-settings/format.md)
* [[!UICONTROL 包含|排] 除元件設定](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL 量度] 重複資料刪除元件設定](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL 無] 值元件設定](/help/data-views/component-settings/no-value-options.md)
* [ Persistencomponent設定](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL 值] 分段元件設定](/help/data-views/component-settings/value-bucketing.md)

## 使用「[!UICONTROL 複製]」功能

複製量度或維度然後修改特定的設定是從單一結構描述欄位建立多個量度或維度的簡易方式。 只需選取右上方的量度或維度名稱底下的「[!UICONTROL 複製]」設定。 然後修改新的量度或維度，並使用更具說明性的名稱來儲存它。

![複製](assets/duplicate.png)

## 篩選結構欄位和維度/量度

您可以依下列資料類型篩選左側邊欄中的結構欄位：

![篩選欄位](assets/filter-fields.png)

您也可以依資料集以及結構欄位是否包含資料或是否為身分來篩選。依預設，我們會將&#x200B;**[!UICONTROL &#x200B;包含資料]**&#x200B;篩選套用至所有資料檢視。

![篩選其他](assets/filter-other.png)

## 新增全域篩選器至資料檢視

您可以新增套用至整個資料檢視的篩選器。 此篩選器會套用至您在工作區中執行的任何報表。

1. 按一下「[!UICONTROL 資料檢視]」中的「[!UICONTROL 設定]」索引標籤。
1. 從左側邊欄的清單拖曳篩選器至「[!UICONTROL 新增篩選器]」欄位。
