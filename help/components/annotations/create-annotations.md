---
title: 建立註解
description: 如何在 Workspace 中建立註解。
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: c56c77079aa21fb740fda6bec333731a1f82a48f
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 94%

---

# 建立註解

根據預設，只有管理員才能建立註解。使用者有權檢視註解，類似於使用者檢視其他元件 (例如篩選器、計算量度等) 方式。

不過，管理員可透過 Admin Console，在&#x200B;**[!UICONTROL 編輯 CJA Workspace 存取權限]**&#x200B;中為使用者提供&#x200B;**[!UICONTROL 報告工具]**&#x200B;的&#x200B;**[!UICONTROL 註解建立]**&#x200B;權限。請參閱[使用者層級存取控制](/help/technotes/access-control.md#user-level-access)，以了解更多資訊。

您可以透過以下方式建立註解：

![Create an annotation](assets/create-annotation.png)

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 註解]**。從[[!UICONTROL 註解]管理員](/help/components/annotations/manage-annotations.md)中選取![AddCircle](/help/assets/icons/AddCircle.svg)[!UICONTROL **[!UICONTROL 新增]**]。
* 在 Workspace 專案中，從視覺化呈現的內容選單中，選取&#x200B;**[!UICONTROL 從選取範圍中建立註解]**。
* 在 Workspace 專案中，從折線圖的內容選單中選取&#x200B;**[!UICONTROL 註解選取範圍]**。
* 在 Workspace 專案中，從選單中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 建立註解]**。
* 在 Workspace 專案中，使用快速鍵 **[!UICONTROL Ctrl+Shift+O]** (Windows) 或 **[!UICONTROL Shift+Command+O]** (macOS)

您可以使用[[!UICONTROL 註解產生器]](#annotation-builder)來定義註解。

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 註解產生器 {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="註解詳細資料"
>abstract="註解讓您能夠有效地將內容相關的資料細微差別和深入解析傳達給您的組織。 註解讓您將行事曆事件和特定的維度/量度連結起來。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="範圍"
>abstract="您可以透過範圍自訂將要新增註解的資料。計算量度和區段不會自動繼承套用至其定義中所用元件的註解。您可以將新的計算量度新增至現有註解的範圍區段。新區段需要新的註解。"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 註解產生器]**&#x200B;對話框用於建立新註解或編輯現有註解。對於您從[[!UICONTROL 註解]管理員](/help/components/annotations/manage-annotations.md)建立或管理的註解，對話方塊標題為&#x200B;**[!UICONTROL 新增註解]**&#x200B;或&#x200B;**[!UICONTROL 編輯註解]**。


>[!BEGINTABS]

>[!TAB 註解產生器]

![註解詳細資料視窗，顯示下一節中說明的欄位和選項。](assets/annotation-builder.png)

>[!TAB 建立/編輯註解]

![註解詳細資料視窗，顯示下一節中說明的欄位和選項。](assets/create-edit-annotation.png)

>[!ENDTABS]

1. 指定以下詳細資料 (![Required](/help/assets/icons/Required.svg) 是必要的)：

   | 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料釋圖]** | 您可以選取註解的資料釋圖。您定義的註解可以根據所選取的資料視圖，用作 Workspace 專案中的註解。當您啟用[!UICONTROL 套用至所有資料釋圖]時，此選取範圍將失效。 |
   | **[!UICONTROL 僅限專案的註解]** | 唯有在您正在處理的 Workspace 專案中，才能看見用來解釋您建立的註解之資訊框。啟用&#x200B;**[!UICONTROL 您的所有專案可使用此註解]**，讓您的所有專案皆可看見註解。唯有您在 Workspace 專案中建立註解時，此資訊框才可見。 |
   | **[!UICONTROL 標題]**![Required](/help/assets/icons/Required.svg) | 為註解命名，例如，`Needs further investigation`。 |
   | **[!UICONTROL 說明]** | 提供註解說明，例如，`We never expected such a fluctuation in numbers.`。 |
   | **[!UICONTROL 標記]** | 透過建立或套用一個或多個標記來組織註解。開始輸入內容以尋找您可以選取的現有標記。或按一下 **[!UICONTROL Enter]** 以新增新標記。選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標記。 |
   | **[!UICONTROL 套用的日期]**![Required](/help/assets/icons/Required.svg) | 選取註解要顯示時所需的日期或日期範圍。使用捷徑建立註解時，註解預設為僅一天的日期範圍。 當您使用視覺效果中的選取專案建立註解時，註解會根據視覺效果所屬面板的日期範圍預設為日期範圍。 |
   | **[!UICONTROL 顏色]** | 在註解上套用顏色。註解會顯示在所選取顏色的專案中。顏色可用於將註解分類，例如，國定假日、外部活動、追蹤問題等。 |
   | **[!UICONTROL 範圍]** | 從元件面板拖放會觸發註解的量度。例如人員、工作階段和事件。然後從元件面板拖放任何維度或篩選條件作為篩選條件，以確定註解顯示與否。如果您不指定範圍，註解將套用至您的所有資料。<br/>您有兩個選項︰<ul><li>**[!UICONTROL 出現這些量度的任一項]**：最多拖放 10 個可觸發註解顯示的量度。<br/>例如，「收入」量度已停止收集指定日期範圍內的資料。將收入量度拖曳到此框中。</li><li>**[!UICONTROL 包括所有篩選器]**：最多可拖放 10 個維度或篩選器，可篩選註解顯示與否。</li></ul><p><p>**請注意：**&#x200B;任何套用到元件且之後作為計算量度或篩選器定義一部分來使用的註解，都不會自動繼承該註解。必須將所需的計算量度也新增到範圍區段中，才能顯示該註解。但是，對於您希望使用相同資訊來註解的任何篩選器，都應該建立新的註解。例如，您可將註解套用到特定日子的[!UICONTROL 訂單]。然後您在相同的日期範圍中，在計算量度中使用[!UICONTROL 訂單]。新的計算量度不會自動顯示訂單的註解。也需將計算量度新增至範圍區段中，才能顯示該註解。 |
   | **[!UICONTROL 套用至所有資料視圖]** | 預設情況下，註解會套用到原始的資料視圖。勾選此方塊後，您就可以將註解套用至公司的所有資料視圖。 |

   {style="table-layout:auto"}

1. 選取
   * **[!UICONTROL 儲存]**&#x200B;以儲存註解。
   * **[!UICONTROL 另存新檔]**&#x200B;以保存註解的副本。
   * **[!UICONTROL 刪除]**&#x200B;以刪除註解。
   * **[!UICONTROL 取消]**&#x200B;以取消對註解所做的任何變更或取消建立新註解。
