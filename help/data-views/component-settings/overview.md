---
title: 元件設定
description: 檢視資料檢視元件的核心設定。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 100%

---

# 元件設定 {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="元件設定"
>abstract="檢視及設定名稱、說明和與元件相關的其他設定。勾選此方框，即可在報告中對非管理員使用者隱藏此元件。管理員仍可以選取 Workspace 專案中的「**[!UICONTROL 顯示所有元件]**」存取該元件。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="內容標籤"
>abstract="移除內容標籤可能會影響需要該元件的特定面板或報告。"

<!-- markdownlint-enable MD034 -->


以下資訊說明了資料視圖元件使用的設定。

![本節所述的元件設定](../assets/component-settings.png)

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 元件類型] | 必填。可讓您將元件從「量度」變更為「維度」，反之亦然。變更此下拉式選取選單，會將元件移動到其各自包含的元件區域。 |
| [!UICONTROL 元件名稱] | 必填。可讓您指定在 Analysis Workspace 中顯示的友好名稱。您可以重新命名元件，給它一個特定於資料檢視的名稱。 |
| [!UICONTROL 說明] | 選填，但建議。為其他使用者提供有關元件的資訊。 |
| [!UICONTROL 標記] | 選填。可讓您使用自訂或現成可用的標籤來標記元件，以便在 Analysis Workspace UI 中更輕鬆地進行搜尋/篩選。 |
| [!UICONTROL 內容標籤] | 選填。可套用至元件之可用系統定義標籤的下拉式清單。 <p>在下列情況下可能需要這些標籤：</p> <ul><li>若要定義一組元件，您可以使用 Analysis Workspace 專案中的[實驗面板](/help/analysis-workspace/c-panels/experimentation.md)，在實驗報告中使用這些元件。<p>如需詳細資訊，請參閱[與 Journey Optimizer 整合](/help/integrations/ajo.md#data-view)和 [Target 報告](/help/integrations/at.md)。</p></li><li>使用 Adob&#x200B;&#x200B;e 所提供的範本時。預設情況下，Adobe 所提供的部分範本將無法運作，因為它們包含不在您的資料檢視中的元件。<p>對於每個缺少的元件，資料檢視中都有一個相符的內容標籤。您需要將相符的內容標籤新增至資料檢視中已有的元件，或者需要將新元件新增至資料檢視並向其新增內容標籤。</p><p>如需詳細資訊，請參閱[將缺少的元件新增至特定範本的資料檢視](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) (在[建立和管理範本](/help/analysis-workspace/templates/create-templates.md)一文中)。</p> |
| [!UICONTROL 結構描述欄位名稱] | 結構描述欄位的名稱。 |
| [!UICONTROL 資料集類型] | 必填。不可編輯的欄位，顯示元件來自的資料集類型 (事件、查詢或輪廓)。 |
| [!UICONTROL 資料集] | 不可編輯的欄位，顯示元件來自的資料集。此欄位可包含多個資料集。 |
| [!UICONTROL 結構描述類型] | 不可編輯的欄位，顯示元件的資料類型。雖然您可以在 Platform 中使用任何支援的結構描述欄位類型，但並非所有欄位類型都在 Customer Journey Analytics 中獲得支援。以下是支援的資料類型：`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` 和 `Boolean`。目前在查詢資料集中只允許使用 `String` 結構描述資料類型。 |
| [!UICONTROL 元件 ID] | 必填。[Customer Journey Analytics API](https://adobe.io/cja-apis/docs) 會使用此欄位來參照元件。資料檢視中的每個元件都必須是唯一的。Adobe 會自動為每個元件產生一個 ID；但是，您可以按一下編輯圖示並修改元件 ID。變更元件 ID 會中斷包含此元件的所有現有 Workspace 專案。雖然每個元件在單個資料檢視中都需要一個唯一 ID，但您可以在其他資料檢視中使用相同的元件 ID。如果您在其他資料視圖中使用相同的元件 ID，您可以使 Workspace 專案跨資料視圖相容。<br/>對於以輪廓和查詢為基礎的元件，元件 ID 具有以資料集 ID 為依據的 ID 首碼 (例如：`642b28fcc1f0ee1c074265a0.person.name.firstName`)。您想要在 Workspace 專案中重複使用以輪廓或查詢為基礎的元件 (例如 `person.name.firstName`)，並在不同的資料視圖中設定該元件時，請確保在資料視圖中以不重複的方式重新命名元件 ID (例如：`myUniqueID.person.name.firstName`)。 |
| [!UICONTROL 路徑] | 必填。不可編輯的欄位，顯示元件來自的結構描述路徑。 |
| [!UICONTROL 資料使用情況標籤] | 指派給 Adobe Experience Platform 中此元件的任何資料使用標籤。[了解更多](/help/data-views/data-governance.md)。 |
| [!UICONTROL 隱藏報告中的元件] | 可讓您從非管理員的資料檢視中組織出元件。管理員仍可以按一下 Analysis Workspace 專案中的「[!UICONTROL 顯示所有元件]」來存取它。 |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [元件類型設定](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


