---
title: 元件設定
description: 檢視資料檢視元件的核心設定。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c0a3fd138b21c2aa0ac6c11e182f58f57a056b42
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 77%

---

# 元件設定

資料檢視元件使用的核心設定。

![元件設定](../assets/component-settings.png)

| 設定 | 說明/使用案例 |
| --- | --- |
| [!UICONTROL 元件類型] | 必填。可讓您將元件從「量度」變更為「Dimension」，反之亦然。 變更此下拉式選取範圍會將元件移至其各自包含的元件區域。 |
| [!UICONTROL 元件名稱] | 必填。可讓您指定在 Analysis Workspace 中顯示的友好名稱。您可以重新命名元件，給它一個特定於資料檢視的名稱。 |
| [!UICONTROL 說明] | 選填，但建議。為其他使用者提供有關元件的資訊。 |
| [!UICONTROL 標籤] | 選填。可讓您使用自訂或現成可用的標籤來標記元件，以便在 Analysis Workspace UI 中更輕鬆地進行搜尋/篩選。 |
| [!UICONTROL 內容標籤] | 選填。可套用至元件的可用系統定義標籤下拉式清單。 可能需要用這些標籤來定義一組用於在 Analysis Workspace 專案或面板中報告的元件。 |
| [!UICONTROL 結構欄位名稱] | 結構欄位的名稱。 |
| [!UICONTROL 資料集類型] | 必填。不可編輯的欄位，顯示元件來自的資料集類型 (事件、查詢或設定檔)。 |
| [!UICONTROL 資料集] | 不可編輯的欄位，顯示元件來自的資料集。此欄位可包含多個資料集。 |
| [!UICONTROL 結構描述類型] | 不可編輯的欄位，顯示元件的資料類型。雖然您可以在 Platform 中使用任何支援的結構描述欄位類型，但不是所有欄位類型都在 CJA 中受到支援。 以下是支援的資料類型：`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` 和 `Boolean`。 僅限 `String` 目前在查詢資料集中允許結構描述資料型別。 |
| [!UICONTROL 元件 ID] | 必填。[CJA API](https://adobe.io/cja-apis/docs) 使用此欄位來參考元件。資料檢視中的每個元件都必須是唯一的。Adobe 會自動為每個元件產生一個 ID；但是，您可以按一下編輯圖示並修改元件 ID。變更元件 ID 會中斷包含此元件的所有現有 Workspace 專案。雖然每個元件在單個資料檢視中都需要一個唯一 ID，但您可以在其他資料檢視中使用相同的元件 ID。如果您在其他資料檢視中使用相同的元件 ID，您可以使 Workspace 專案跨資料檢視相容。<br/>對於設定檔和查詢型元件，元件ID會以資料集ID為基礎加上ID首碼(例如： `642b28fcc1f0ee1c074265a0.person.name.firstName`)。 當您想要重複使用設定檔或查詢型元件時，例如 `person.name.firstName`，並在不同的資料檢視中設定此元件，請確定您以唯一方式重新命名元件ID (例如： `myUniqueID.person.name.firstName`)。 |
| [!UICONTROL 路徑] | 必填。不可編輯的欄位，顯示元件來自的結構路徑。 |
| [!UICONTROL 資料使用情況標籤] | 指派給 Adobe Experience Platform 中此元件的任何資料使用標籤。[了解更多](/help/data-views/data-governance.md) |
| [!UICONTROL 隱藏報告中的元件] | 可讓您從非管理員的資料檢視中組織出元件。管理員仍可以按一下 Analysis Workspace 專案中的「[!UICONTROL 顯示所有元件]」來存取它。 |

{style="table-layout:auto"}

以下為有關資料檢視中元件設定的影片：

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
