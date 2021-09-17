---
title: 建立或編輯資料檢視
description: 您可以調整以建立或編輯資料檢視的所有設定。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 36b7cc72c34e27f90af29146f7a32c525b279b9b
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 16%

---

# 建立或編輯資料檢視

建立資料檢視需要從結構元素建立量度和維度或使用標準元件。根據您的業務需求，大部分的結構元素可以是維度或量度。 將結構元素拖曳至資料檢視後，右側會顯示選項，您可以在其中調整維度或量度在CJA中的運作方式。

## 設定資料檢視

1. 登入[Customer Journey Analytics](https://analytics.adobe.com)並前往&#x200B;**[!UICONTROL 資料檢視]**&#x200B;標籤。
2. 按一下&#x200B;**[!UICONTROL 新增]**&#x200B;以建立資料檢視，或按一下現有資料檢視加以編輯。

![新資料視圖](assets/new-data-view.png)

### 設定

提供資料檢視的整體設定。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 連線] | 此欄位會將資料檢視連結至您先前建立的連線，其中包含一或多個Adobe Experience Platform資料集。 |
| [!UICONTROL 名稱] | 必填。資料檢視的名稱。 此值會顯示在Analysis Workspace的右上下拉式清單中。 |
| [!UICONTROL 說明] | 選填。Adobe建議提供詳細說明，讓使用者了解資料檢視為何存在，以及其設計對象。 |

### 容器

指定資料檢視的容器名稱。 容器名稱常用於[篩選器](/help/components/filters/filters-overview.md#Filter-containers)中。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 人員容器名稱] | 「[!UICONTROL 人員]」(預設)。[!UICONTROL 人員]容器包含指定時間範圍內訪客的每個工作階段和事件。 如果您的組織使用不同的詞語（例如「訪客」或「使用者」），您可以在此重新命名容器。 |
| [!UICONTROL 工作階段容器名稱] | 「[!UICONTROL 工作階段]」(預設)。「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。您可以將此容器重新命名為「造訪」，或貴組織偏好使用的任何其他詞語。 |
| [!UICONTROL 事件容器名稱] | 「[!UICONTROL 事件]」(預設)。[!UICONTROL Event]容器定義資料集中的個別事件。 如果您的組織使用不同的詞語（例如「點擊」或「頁面檢視」），您可以在此重新命名容器。 |

### 行事曆

指示您希望資料檢視遵循的日曆格式。 您可以根據相同的[Connection](/help/connections/create-connection.md)擁有多個資料檢視，並為其指定不同的日曆類型或時區。 這些資料檢視可讓使用不同日曆類型的團隊，透過相同的基礎資料滿足其各自的需求。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 時區] | 選擇要顯示資料的時區。如果您選擇在日光節約時間運作的時區，資料會自動調整以反映。 在春季，當時鐘提前1小時調整時，會出現1小時的間隔。 時鐘在後面調整一小時時，在DST班次期間會重複一小時。 |
| [!UICONTROL 日曆類型] | 確定月中的周的分組方式。<br>**西曆：** 標準日曆格式。季度按月分組。<br>**4-5-4零售：** 標準化的4-5-4零售日曆。該季度的第一個月和最後一個月包含4週，而該季度的第二個月包含5週。<br>**自訂(4-5-4):** 與4-5-4日曆類似，但您可以選擇一年中的第一天，以及「額外」一週發生的年份。<br>**自訂(4-4-5):** 每季的第一個月和第二個月包含4週，而每季的最後一週包含5週。<br>**自訂(5-4-4):** 每季的第一個月包含5週，而每季的第二個月和第三個月包含4週。 |
| [!UICONTROL 一年的第一] 個月 [!UICONTROL 和一週的第一天] | 西曆類型可見。 指定您希望日曆年度開始的月份，以及每週要開始的日期。 |
| [!UICONTROL 當年的第一天] | 對自訂日曆類型可見。 指定您要從今年的哪一天開始。 日曆會根據此值自動設定每週第一天的格式。 |
| [!UICONTROL 「額外」週發生的年份] | 多數364天的日曆（每年52週7天），每年累計剩餘天數，直到形成一個額外周。 然後，這個額外的周又增加到該年的最後一個月。 指定您要新增額外周的年份。 |

## 設定資料檢視的元件

接著，您可以從結構元素建立量度和維度。您也可以使用標準元件。

1. 登入[Customer Journey Analytics](https://analytics.adobe.com)並前往&#x200B;**[!UICONTROL 資料檢視]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL 新增]**&#x200B;以建立資料檢視，或按一下現有資料檢視加以編輯。
1. 按一下&#x200B;**[!UICONTROL 元件]**&#x200B;標籤。

   ![元件索引標籤](assets/components-tab.png)

   您可以在左上角看到「[!UICONTROL 連線]」，其中包含資料集，以及下面的[!UICONTROL 「結構」欄位]。請注意，已包含的元件是所有資料檢視的標準必要元件（系統產生）。 Adobe還預設應用篩選器&#x200B;**[!UICONTROL 包含資料]**，以便僅顯示包含資料的架構欄位。 如果您想要不包含資料的欄位，請移除此篩選器。

1. 從左側邊欄將結構欄位（例如`pageTitle`）拖曳至「量度」或「Dimension」區段。

   您可以多次將相同的結構欄位拖曳至維度或量度區段，並以不同的方式設定相同的維度或量度。例如，從`pageTitle`欄位中，您可以使用右側的不同[元件設定](component-settings/overview.md)，建立名為「Product Pages」的維度，以及另一個名為「Error pages」的維度。

   ![標籤3](assets/components-tab-3.png)

   如果您從左側欄拖曳結構欄位資料夾，系統會自動將其排序為典型區段。 字串欄位結尾在[!UICONTROL Dimension]區段，數值結構類型最終在[!UICONTROL 量度]區段。 您也可以按一下「**[!UICONTROL 新增全部]**」，所有架構欄位都會新增至其個別位置。

1. 選取元件後，右側會顯示許多設定。 使用[元件設定](component-settings/overview.md)配置元件。 可用的元件設定視元件是否為維度/量度，以及結構資料類型而定。 設定包括：

   * [[!UICONTROL 出處]](component-settings/attribution.md)
   * [[!UICONTROL 行為]](component-settings/behavior.md)
   * [[!UICONTROL 格式]](component-settings/format.md)
   * [[!UICONTROL 包含排除值]](component-settings/include-exclude-values.md)
   * [[!UICONTROL 量度重複資料刪除]](component-settings/metric-deduplication.md)
   * [[!UICONTROL 沒有值選項]](component-settings/no-value-options.md)
   * [[!UICONTROL 持續性]](component-settings/persistence.md)
   * [[!UICONTROL 值分組配置]](component-settings/value-bucketing.md)

如有需要，您可以使用下列功能：

* **[!UICONTROL 複製]**:從單一結構欄位複製量度或維度，然後修改特定設定是建立多個量度或維度的簡單方式。選取右上方量度或維度名稱下方的[!UICONTROL 複製]設定。 修改新維度或量度，並以較清楚描述的名稱儲存。

   ![複製](assets/duplicate.png)

* **[!UICONTROL 篩選]**:您可以依下列資料類型篩選左側邊欄的結構欄位：

   ![篩選欄位](assets/filter-fields.png)

   您也可以依資料集以及結構欄位是否包含資料或是否為身分來篩選。依預設，Adobe最初會將&#x200B;**[!UICONTROL 包含資料]**&#x200B;篩選器套用至所有資料檢視。

   ![篩選其他](assets/filter-other.png)

## 設定

1. 登入[Customer Journey Analytics](https://analytics.adobe.com)並前往&#x200B;**[!UICONTROL 資料檢視]**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL 新增]**&#x200B;以建立資料檢視，或按一下現有資料檢視加以編輯。
1. 按一下&#x200B;**[!UICONTROL Settings]**&#x200B;標籤。

### 全域篩選器

您可以新增套用至整個資料檢視的篩選器。 此篩選器會套用至您在工作區中執行的任何報表。 從左側邊欄的清單拖曳篩選器至「[!UICONTROL 新增篩選器]」欄位。

### 工作階段設定

決定工作階段過期和啟動新事件之前事件之間閒置的時間。

需要時段。 您也可以選擇在事件包含特定量度時，強制開始新的工作階段。

指定所有所需設定後，按一下「保存並完成&#x200B;]**」。**[!UICONTROL 
