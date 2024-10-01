---
title: 建立註解
description: 如何在 Workspace 中建立註解。
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 17%

---

# 建立註解

依預設，只有管理員才能建立註解。 使用者有權檢視註解，其方式與使用者檢視其他元件的方式（例如篩選器、計算量度等）類似。

但是，管理員可以透過Admin Console將&#x200B;**[!UICONTROL CJA Workspace存取權]**&#x200B;的「編輯」許可權中&#x200B;**[!UICONTROL 報告工具]**&#x200B;的&#x200B;**[!UICONTROL 註解建立]**&#x200B;許可權授予使用者。 如需詳細資訊，請參閱[使用者層級存取控制](/help/technotes/access-control.md#user-level-access)。

您可以透過下列方式建立註釋：

![建立附註](assets/create-annotation.png)

* ??在主介面中，選取&#x200B;**[!UICONTROL 元件]**&#x200B;並選取&#x200B;**[!UICONTROL 註解]**。 從[[!UICONTROL 註解]管理員](/help/components/annotations/manage-annotations.md)選取![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]。
* ??在Workspace專案中，從視覺效果的內容功能表中，選取&#x200B;**[!UICONTROL 從選取範圍建立附註]**。
* ??在Workspace專案中，從折線圖的內容功能表中，選取&#x200B;**[!UICONTROL 附註選取範圍]**。
* ??在Workspace專案中，從功能表選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 建立附註]**。
* ??在Workspace專案中，使用捷徑&#x200B;**[!UICONTROL ctrl+shift+o]** (Windows)或&#x200B;**[!UICONTROL shift+command+o]** (macOS)

若要定義註解，請使用[[!UICONTROL 註解產生器]](#annotation-builder)：

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 註解產生器 {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_details"
>title="附註詳細資料"
>abstract="註解讓您能夠有效地將內容相關的資料細微差別和深入解析傳達給您的組織。 註解可讓您將行事曆事件和特定的維度/量度連結起來。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_components_annotations_scope"
>title="範圍"
>abstract="範圍可讓您自訂要加上註解的資料。 計算量度和區段不會自動繼承套用到元件之定義的註解。 您可以將新的計算量度新增至現有註解的範圍區段。 新區段需要新附註。"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 註解產生器]**&#x200B;對話方塊可用來建立新註解或編輯現有註解。 此對話方塊的標題為&#x200B;**[!UICONTROL 新註解]**&#x200B;或&#x200B;**[!UICONTROL 編輯註解]**，此註解是您從[[!UICONTROL 註解]管理員](/help/components/annotations/manage-annotations.md)建立或管理的註解。


>[!BEGINTABS]

>[!TAB 註解產生器]

![註解詳細資料視窗，顯示下一節中說明的欄位和選項。](assets/annotation-builder.png)

>[!TAB 建立/編輯附註]

![註解詳細資料視窗，顯示下一節中說明的欄位和選項。](assets/create-edit-annotation.png)

>[!ENDTABS]

1. 指定下列詳細資料（![必要](/help/assets/icons/Required.svg)為必要）：

   | 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料視圖]** | 您可以選取註釋的資料檢視。 根據所選的資料檢視，您定義的註解可在Workspace專案中作為註解使用。 當您啟用[!UICONTROL 套用至所有資料檢視]時，此選取範圍會被覆寫。 |
   | **[!UICONTROL 僅限專案的註解]** | 說明您所建立之註解僅會顯示在您正在處理的Workspace專案中的資訊方塊。 啟用&#x200B;**[!UICONTROL 讓此註解可用於您的所有專案]**，讓註解可用於您的所有專案。 此資訊方塊只有在您從Workspace專案建立註解時才會顯示。 |
   | **[!UICONTROL 標題]** ![必要](/help/assets/icons/Required.svg) | 為註解命名，例如`Needs further investigation`。 |
   | **[!UICONTROL 說明]** | 提供註解的描述，例如，`We never expected such a fluctuation in numbers.`。 |
   | **[!UICONTROL 標記]** | 透過建立或套用一個或多個標籤來組織註釋。 開始輸入以尋找現有可選取的標籤。 或按&#x200B;**[!UICONTROL Enter]**&#x200B;以新增標籤。 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標籤。 |
   | **[!UICONTROL 套用的日期]** ![必要](/help/assets/icons/Required.svg) | 選取需要出席的活動日期或日期範圍，使註解能夠顯示。 使用捷徑建立註解時，註解預設為僅一天內的資料範圍。 當您使用視覺效果中的選取專案建立註解時，註解會根據視覺效果所屬面板的日期範圍預設為資料範圍。 |
   | **[!UICONTROL 顏色]** | 在註解上套用顏色。註解會顯示在所選取顏色的專案中。顏色可用於將註解分類，例如，國定假日、外部活動、追蹤問題等。 |
   | **[!UICONTROL 範圍]** | 從元件面板拖放會觸發註解的量度。 例如人員、工作階段和事件。 然後，從元件面板拖放作為篩選器的任何維度或篩選器，以決定是否顯示附註。 如果您未指定範圍，註解會套用至您所有的資料。 <br/>您有兩個選項：<ul><li>**[!UICONTROL 出現這些量度的任一項]**：最多拖放10個可觸發註解顯示的量度。<br/>例如，收入量度已停止收集特定日期範圍的資料。 將收入量度拖曳至此方塊。</li><li>**[!UICONTROL 包含所有這些篩選器]**：最多拖放10個維度或篩選器，以篩選是否顯示註解。</li></ul><p><p>**注意：**&#x200B;套用到元件然後當作計算量度或篩選器定義使用的任何註解都不會自動繼承該註解。 必須也將所需的計算量度新增到範圍區段中，才能顯示該註解。不過，應該針對您想要加入相同資訊當作註解的任何篩選器建立新的註解。 例如，您會在特定日期將附註套用至[!UICONTROL 訂單]。 然後您可將計算量度中的[!UICONTROL 訂單]用於相同日期範圍。 新的計算量度不會自動顯示訂單的附註。 也將計算量度新增到範圍區段中，以便註解顯示。 |
   | **[!UICONTROL 套用至所有資料視圖]** | 預設情況下，註解會套用到原始的資料視圖。勾選此方塊後，您就可以將註解套用至公司的所有資料視圖。 |

   {style="table-layout:auto"}

1. 選擇
   * **[!UICONTROL 儲存]**&#x200B;以儲存附註。
   * **[!UICONTROL 另存新檔]**&#x200B;以儲存註解的復本。
   * **[!UICONTROL 刪除]**&#x200B;以刪除附註。
   * **[!UICONTROL 取消]**&#x200B;以取消您對註解所做的任何變更，或取消建立新註解。
