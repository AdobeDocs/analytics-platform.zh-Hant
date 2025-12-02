---
description: 瞭解如何使用區段管理器來管理區段，例如共用、篩選、標籤、核准、複製、刪除區段，以及將區段標示為我的最愛。
title: 管理區段
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters, Segments
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 75%

---

# 管理區段


您可以[共用](seg-share.md)、[劃分](seg-filter.md)、[標記](seg-tag.md)、[核准](seg-approve.md)、重新命名、[複製](seg-copy.md)、刪除、匯出區段以及將區段標示為[我的最愛](seg-favorite.md) (從統一的[!UICONTROL 區段]管理介面進行)。若要管理區段：

* 在主介面中選取「**[!UICONTROL 元件]**」，然後選取「**[!UICONTROL 區段]**」。


>[!NOTE]
>
>您在特定Workspace專案中建立的快速區段不會出現在[!UICONTROL 區段]管理員中，除非您讓該區段可用於您的所有專案。
>

## 區段管理員

區段管理員有以下介面元素：

![區段介面](assets/filters-manager.png)

### 區段清單

區段清單➊會顯示您擁有的所有區段、已設定您所有專案範圍的區段，以及已與您共用的區段。 清單有以下欄位：

| 欄 | 說明 |
| --- | --- |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以將區段設為我的最愛 ![Star](/help/assets/icons/Star.svg) 或取消我的最愛 ![StarOutline](/help/assets/icons/StarOutline.svg)。請參閱[將區段標示為我的最愛](/help/components/segments/seg-favorite.md) |
| **[!UICONTROL 標題和說明]** | 若要編輯區段，請選取標題連結，以開啟[區段產生器](seg-builder.md)。 共用的區段會以![共用](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 資料檢視]** | 此區段所套用的資料檢視。 |
| **[!UICONTROL 所有者]** | 區段的所有者。做為使用者，您只能看到您擁有的區段或與您共用的註解。 |
| **[!UICONTROL 標記]** | 此區段的標記。 |
| **[!UICONTROL 共用對象]** | 您將區段與之共用的人數或群組數。選取開啟「**[!UICONTROL 共用元件]**」對話框。如需詳細資訊，請參閱[共用區段](seg-share.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改區段的日期和時間。 |
| **[!UICONTROL 使用於]** | 顯示區段目前的使用位置，以及在每個區域中所使用的次數。 <p>例如，若區段被 40 項專案和 2 個警報使用，則此欄位的值會顯示為 [!UICONTROL **42 個元件**]。</p> <p>選取此欄位中的值可以查看區段使用位置的劃分 (例如，[!UICONTROL **專案 (40)**]、[!UICONTROL **行動記分卡 (2)**])。此外，您也可以檢視區段使用位置的項目清單。例如，若要查看正在使用篩選器的專案清單，請選取「[!UICONTROL **專案 (40)**]」連結。</p><p>以下每個區域會呈現該區域中使用的區段執行個體數量：</p>  <ul><li>[!UICONTROL **專案**]<p>包含[在區段產生器中所建立](/help/components/segments/seg-builder.md#)且可用於所有專案的區段。</p></li><li>[!UICONTROL **臨時元件**]<p>包含[建立為快速區段](/help/components/segments/seg-quick.md)且僅能用於單一專案中的區段。</p></li><li>[!UICONTROL **已排程的專案**]</li><li>[!UICONTROL **行動計分卡**]</li><li>[!UICONTROL **註解**]</li><li>[!UICONTROL **計算量度**]</li><li>[!UICONTROL **Report Builder**]<p>選取此選項會下載包含以下列資料的 CSV 檔案：</p><ul><li>Report Builder 名稱</li><li>最後存取時間</li><li>最後存取的 IMS 使用者 ID</li><li>最後存取的使用者名稱</li></ul></li></ul><p>此資訊可協助您判斷某個元件對組織中的使用者是否有價值、元件使用的地方，以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊僅適用於系統管理員。</li><li>依預設，「[!UICONTROL **使用於**]」欄不會顯示。使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 來設定此欄的顯示。</li><li>此資訊不包括 API 或 Data Warehouse 的使用情況。</li><li>如果此欄沒有持定元件的資料，但該元件有&#x200B;[!UICONTROL **上次使用**]&#x200B;的日期，則該元件可能已在分析中使用但未被儲存。</li><li>使用情況資訊從 2023 年 9 月開始提供。</li></ul><p>您可以將[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。</p> |
| **[!UICONTROL 上次使用]** | 區段上次使用的時間。 |

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列➋對區段進行動作。 動作列包含以下動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]** | 使用[區段產生器](seg-builder.md)新增另一個區段。 |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *根據標題搜尋*] | 當未選取清單中任何區段時，請使用此搜尋欄位搜尋區段。 |
| ![標籤](/help/assets/icons/Label.svg)**[!UICONTROL 標記]** | 標記所選取之區段。在&#x200B;**[!UICONTROL 標記區段]**&#x200B;對話框中，選取或取消選取所選取之區段的標記。選取「**[!UICONTROL 儲存]**」，儲存所選取之區段的標記。如需詳細資訊，請參閱[標記區段](/help/components/segments/seg-tag.md)。 |
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共用]** | 共用所選取之區段。在&#x200B;**[!UICONTROL 共用區段]**&#x200B;對話框中，您可以 ![Search](/help/assets/icons/Search.svg) *搜尋個人或群組*，或者您可以選取「**[!UICONTROL 組織]**」或「**[!UICONTROL 群組]**」。選取「**[!UICONTROL 儲存]**」，儲存所選取之區段的共用詳細資訊。如需詳細資訊，請參閱[共用區段](seg-share.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]** | 刪除所選取之區段。系統會提示您進行確認。 <br/>當您刪除區段時，請注意： <ul><li>已套用此區段的排程報表和專案仍可正常運作。</li><li> 編輯同名區段時，排程報表不會更新。</li> </ul> |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名所選取之單一區段。選取後，您可以重新命名內嵌區段。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 核准]** | 核准所選取之區段。如需詳細資訊，請參閱[核准區段](seg-approve.md)。 |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL 複製]** | 複製所選取之區段。使用相同的名稱和字尾建立新區段`(Copy)`。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出為 CSV]** | 將區段匯出為 `Segments List.csv` 檔案。 |

### 使用中的篩選欄

篩選列➌顯示從篩選面板套用至區段清單（如果有的話）的作用中區段。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選條件。如果指定了多個篩選器，您可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有篩選器。

### 篩選面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選區段清單。 篩選器面板會顯示篩選器的型別以及遵循特定篩選器的區段數。 選取![篩選器](/help/assets/icons/Filter.svg)以切換篩選器面板的顯示。

如需詳細資訊，請參閱[篩選區段清單](seg-filter.md)。
