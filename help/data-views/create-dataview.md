---
title: 建立或編輯資料檢視
description: 您可調整以建立或編輯資料檢視的所有設定。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 27214e6fc896243c0d29632cb0242b0d2e4f4653
workflow-type: ht
source-wordcount: '1418'
ht-degree: 100%

---

# 建立或編輯資料檢視

建立資料檢視需要從綱要元素建立量度和維度或使用標準元件。大多數綱要元素可以是維度或量度，具體取決於您的業務需求。將綱要元素拖到資料檢視中後，右側會出現選項，您可以在其中調整維度或量度在 Customer Journey Analytics 中的執行方式。

以下是有關該主題的影片：

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

建立或編輯資料檢視的方法：

1. 登入 [Customer Journey Analytics](https://analytics.adobe.com) 並移至「**[!UICONTROL 資料檢視]**」索引標籤。
1. 若要建立資料檢視，請選取「**[!UICONTROL 建立新的資料檢視]**」。或者，您可以從資料檢視清單中選取現有資料檢視進行編輯。


## 設定

設定新的或現有的資料檢視的方法：

1. 選取「**[!UICONTROL 設定]**」標籤 (如果尚未啟動)。

   ![設定資料檢視](assets/dataview-configure.png)
1. 指定「[!UICONTROL 設定]」、「[!UICONTROL 容器]」，然後指定「[!UICONTROL 行事曆]」詳細資料 (見下文)。
1. 選取「**[!UICONTROL 儲存並繼續]**」，繼續設定新的或現有的資料檢視。選取「**[!UICONTROL 儲存]**」，儲存現有資料檢視的設定。


### 設定

為資料檢視提供總體設定。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 連線] | 此欄位會將資料檢視連結至您先前建立的連線，其中包含一或多個 Adobe Experience Platform 資料集。 |
| [!UICONTROL 名稱] | 必填。資料檢視的名稱。此值顯示在 Analysis Workspace 的右上角下拉式清單中。 |
| [!UICONTROL 說明] | 選填。Adobe 建議使用詳細說明，讓用戶了解資料檢視存在的原因及其設計對象。 |

{style="table-layout:auto"}

### 容器

指定資料檢視的容器名稱。容器名稱在[篩選](/help/components/filters/filters-overview.md#Filter-containers)中經常使用。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 人員容器名稱] | 「[!UICONTROL 人員]」(預設)。「[!UICONTROL 人員]」容器包含指定時間段內人員的每個工作階段和事件。如果您的組織使用不同的術語（例如，「訪客」或「用戶」），您可以在此處重新命名容器。 |
| [!UICONTROL 工作階段容器名稱] | 「[!UICONTROL 工作階段]」(預設)。「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。您可以將此容器重新命名為「Visit」或您組織偏好的其他任何詞語。 |
| [!UICONTROL 事件容器名稱] | [!UICONTROL 事件] (預設)。[!UICONTROL 事件]容器定義資料集中的單個事件。如果您的組織使用不同的術語（例如，「點擊次數」或「頁面檢視量」），您可以在此處重新命名容器。 |

{style="table-layout:auto"}

### 行事曆

指示您希望資料檢視遵循的行事曆格式。您可以根據同一個[連線](/help/connections/create-connection.md)擁有多個資料檢視，並為它們提供不同的行事曆類型或時區。這些資料檢視可以讓使用不同行事曆類型的團隊，透過相同的基礎資料滿足各自的需求。

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 時區] | 選擇要顯示資料的時區。如果您選擇實行夏令時間的時區，則會自動調整資料以反映這一點。在春天，當時鐘向前調快一小時，會出現一小時的缺口。在秋天，當時鐘向後調慢一小時，會在夏令偏移期間重複一小時。 |
| [!UICONTROL 行事曆類型] | 決定一個月中的週如何分組。<br>**西曆：**&#x200B;標準行事曆格式。季依照月分組。<br>**4-5-4 零售業：**&#x200B;標準化的 4-5-4 零售業行事曆。本季的第一個月和最後一個月為 4 週，而本季的第二個月為 5 週。<br>**自訂 (4-5-4)：**&#x200B;類似於 4-5-4 行事曆，但您可以選取一年的第一天以及「額外」週發生的年份。<br>**自訂 (4-4-5)：**&#x200B;每個季的第一個月和第二個月為 4 週，而每個季的最後一週為 5 週。<br>**自訂 (5-4-4)：**&#x200B;每個季的第一個月為 5 週，而每個季的第二和第三個月為 4 週。 |
| [!UICONTROL 一年的第一個月]和[!UICONTROL 一週的第一天] | 對西曆行事曆類型可見。指定您希望行事曆年從哪一個月開始，以及您希望每週從哪一天開始。 |
| [!UICONTROL 當年的第一天] | 對自訂行事曆類型可見。指定您希望目前年份在一年中的哪一天開始。行事曆會根據此值自動設定每週第一天的格式。 |
| [!UICONTROL 「額外」週發生的年份] | 對於大多數 364 天行事曆 (52 週，每週 7 天)，每年都會累積剩餘的天數，直到加起來多出一週。然後將這個額外的一週新增到該年的最後一個月。指定您希望將額外一週新增到哪一年。 |

{style="table-layout:auto"}

## 元件

接下來，您可以設定資料檢視的元件，這代表您可以從綱要元素建立量度和維度。您也可以使用標準元件。

1. 選取「**[!UICONTROL 元件]**」索引標籤。

   ![元件標籤](assets/dataview-components.png)

   您可以在左上角看到「[!UICONTROL 連線]」，其中包含資料集，以及下面的[!UICONTROL 「綱要」欄位]。已包含的元件是所有資料檢視 (如事件、人員、工作階段量度以及分鐘、季度、週維度) 所需的標準元件 (系統產生)。Adobe 預設會套用篩選器「**[!UICONTROL 包含資料]**」和「**[!UICONTROL 未淘汰]**」，以僅顯示包含資料且未淘汰的綱要欄位。

1. 使用「![搜尋圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)」**[!UICONTROL 搜尋綱要欄位]**&#x200B;來搜尋綱要欄位，或者移動到任意資料集集合來尋找欄位，例如![資料夾圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg)「**[!UICONTROL 事件資料集]**」。<br/>或者，您可以使用![資料圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg)「**建立衍生欄位**」來建立衍生欄位。請參閱「[衍生欄位](./derived-fields/derived-fields.md)」以了解更多資訊。

1. 當您找到特定綱要欄位或定義衍生欄位時，拖動該欄位，例如![手柄圖示](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg)「**[!UICONTROL 頁面名稱]**」，從左邊欄進入量度或維度區段。您可以多次將相同的綱要欄位拖曳至維度或量度區段，並以不同的方式設定相同的維度或量度。例如，在 pageName 欄位，您可以使用右側不同的[元件設定](component-settings/overview.md)，以建立名為「產品頁面」的維度，以及「錯誤頁面」維度。如果從左側欄拖曳綱要欄位檔案夾，它們會自動排序為傳統區段。字串欄位會在「[!UICONTROL 維度]」區段中結束，而數字綱要類型最終出現在「[!UICONTROL 量度]」區段中。您也可以按一下「**[!UICONTROL 新增全部]**」，並新增所有綱要欄位至其各自的位置。

1. 選取元件後，右側會出現設定。

   ![已選取資料檢視元件](assets/dataview-component-pagename.png)

   使用[元件設定](component-settings/overview.md)來設定元件。可用的元件設定取決於元件是維度/量度以及綱要資料類型。設定包括：

   * [[!UICONTROL 歸因]](component-settings/attribution.md)
   * [[!UICONTROL 行為]](component-settings/behavior.md)
   * [[!UICONTROL 格式]](component-settings/format.md)
   * [[!UICONTROL 包含排除值]](component-settings/include-exclude-values.md)
   * [[!UICONTROL 量度重複資料刪除]](component-settings/metric-deduplication.md)
   * [[!UICONTROL 沒有值選項]](component-settings/no-value-options.md)
   * [[!UICONTROL 持續性]](component-settings/persistence.md)
   * [[!UICONTROL 值分組]](component-settings/value-bucketing.md)

1. 選取「**[!UICONTROL 儲存並繼續]**」，繼續設定新的或現有的資料檢視。選取「**[!UICONTROL 儲存]**」，儲存現有資料檢視的設定。

「**複製量度或維度**」

複製量度或維度，然後修改特定的設定，是從單一綱要欄位建立多個量度或維度的簡易方式。選取右上方的量度或維度名稱底下的「[!UICONTROL 複製]」設定。 修改新的量度或維度，並使用更具說明性的名稱來儲存它。

**篩選綱要欄位或資料集**

您可以依照[!UICONTROL 資料類型], [!UICONTROL 資料集]、[!UICONTROL 資料治理] 和 [!UICONTROL 其他] 條件 ([!UICONTROL 包含資料]、[!UICONTROL 識別] 和 [!UICONTROL 未淘汰]) 篩選左邊欄中的![篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)綱要欄位：

![篩選欄位](assets/dataview-components-filter.png)

>[!TIP]
>
>如果資料檢視中未能正確載入元件，而且您看到錯誤訊息，請參閱「[缺乏權限](../troubleshooting/lack-of-permissions.md)」尋找解決方案。



## 設定

1. 選取「**[!UICONTROL 設定]**」索引標籤。
1. 設定篩選器以套用於整個資料檢視。請參閱下方的「[設定 (篩選器)](#settings-filters)」。
1. 設定工作階段逾時和量度。請參閱下方的「[工作階段設定](#session-settings)」。
1. 選取「**[!UICONTROL 儲存並繼續]**」，繼續設定新的或現有的資料檢視。選取「**[!UICONTROL 儲存]**」，儲存現有資料檢視的設定。

### 設定 (篩選器)

您可以新增套用至整個資料檢視的篩選器。此篩選器將套用至您在 Workspace 中執行的任何報告。從左側邊欄的清單拖曳篩選器至「[!UICONTROL 新增篩選器]」欄位。

### 工作階段設定

決定在工作階段到期和新工作階段開始之前，事件之間的閒置時段。需要時段。您也可以選擇在事件包含特定量度時，強制啟動新工作階段。如需詳細資料，請參閱[工作階段設定](session-settings.md)。

指定所有所需設定後，按一下「**[!UICONTROL 儲存並完成]**」。
