---
title: 管理區段
description: 瞭解如何在Customer Journey Analytics中管理區段
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: 66ec61ea64f1265d887d4941a22e1f9757120daa
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 32%

---

# 管理區段


您可以從中央的[!UICONTROL 區段]管理介面[共用](filters-share.md)、[區段](filters-filter.md)、[標籤](filters-tag.md)、[核准](filters-approve.md)、重新命名、[複製](filters-copy.md)、刪除、匯出區段並將區段標示為[我的最愛](filters-favorite.md)。 若要管理區段：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 區段]**。


>[!NOTE]
>
>您在特定Workspace專案中建立的快速區段不會顯示在[!UICONTROL 篩選器]管理員中，除非您讓此區段可用於您的所有專案。
>

## 區段管理員

「區段管理員」有下列介面元素：

![區段介面](assets/filters-manager.png)

### 區段清單

區段清單➊會顯示您擁有的所有區段、已設定至您所有專案範圍的區段，以及已與您共用的區段。 清單有以下欄位：

| 欄 | 說明 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)區段。 檢視[將區段標示為我的最愛](/help/components/filters/filters-favorite.md) |
| **[!UICONTROL 標題和說明]** | 若要編輯區段，請選取標題連結，以開啟[篩選器產生器](filter-builder.md)。 共用區段以![共用](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 資料檢視]** | 套用此區段的資料檢視。 |
| **[!UICONTROL 所有者]** | 區段的擁有者。 身為使用者，您只會看到您擁有的區段或與您共用的註解。 |
| **[!UICONTROL 標記]** | 此區段的標籤。 |
| **[!UICONTROL 共用對象]** | 您與多少個人或群組共用區段。 選取開啟「**[!UICONTROL 共用元件]**」對話框。如需詳細資訊，請參閱[共用區段](filters-share.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改區段的日期和時間。 |
| **[!UICONTROL 使用於]** | 顯示目前區段的使用位置以及在每個區域中使用區段的次數。 <p>例如，如果區段用於40個專案和2個警示，則此欄的值顯示為&#x200B;[!UICONTROL **42個元件**]。</p> <p>選取此欄中的值，以檢視使用區段的劃分(例如，[!UICONTROL **專案(40)**]、[!UICONTROL **行動計分卡(2)**])。 此外，您可以檢視使用區段的專案清單。 例如，若要查看正在使用篩選器的專案清單，請選取&#x200B;[!UICONTROL **專案 (40)**] 連結。</p><p>下列各區顯示在該區域使用的區段例項數：</p>  <ul><li>[!UICONTROL **專案**]<p>包含[在區段產生器](/help/components/filters/filter-builder.md#)中建立且適用於所有專案的區段。</p></li><li>[!UICONTROL **臨時元件**]<p>包含[建立為快速區段](/help/components/filters/quick-filters.md)的區段，且僅適用於單一專案。</p></li><li>[!UICONTROL **已排程的專案**]</li><li>[!UICONTROL **行動計分卡**]</li><li>[!UICONTROL **註解**]</li><li>[!UICONTROL **計算量度**]</li><li>[!UICONTROL **Report Builder**]<p>選取此選項會下載包含以下列資料的 CSV 檔案：</p><ul><li>Report Builder 名稱</li><li>最後存取時間</li><li>最後存取的 IMS 使用者 ID</li><li>最後存取的使用者名稱</li></ul></li></ul><p>此資訊可協助您判斷某個元件對組織中的使用者是否有價值、元件使用的地方，以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊僅適用於系統管理員。</li><li>依預設，「[!UICONTROL **使用於**]」欄不會顯示。使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 來設定此欄的顯示。</li><li>此資訊不包括 API 或 Data Warehouse 的使用情況。</li><li>如果此欄沒有持定元件的資料，但該元件有&#x200B;[!UICONTROL **上次使用**]&#x200B;的日期，則該元件可能已在分析中使用但未被儲存。</li><li>使用情況資訊從 2023 年 9 月開始提供。</li></ul><p>您可以將[資料字典](/help/components/data-dictionary/data-dictionary-overview.md)與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。</p> |
| **[!UICONTROL 上次使用]** | 上次使用此區段的時間。 |

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列對區段進➋行動作。 動作列包含以下動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]** | 使用[篩選產生器](filter-builder.md)新增另一個區段。 |
| ![搜尋](/help/assets/icons/Search.svg) [!UICONTROL *按標題搜尋*] | 當清單中未選取任何區段時，請使用此搜尋欄位來搜尋區段。 |
| ![Label](/help/assets/icons/Label.svg)**[!UICONTROL 標記]** | 標籤選取的區段。 在&#x200B;**[!UICONTROL 標籤區段]**&#x200B;對話方塊中，選取或取消選取所選區段的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選區段的標籤。 如需詳細資訊，請參閱[標籤區段](/help/components/filters/filters-tag.md)。 |
| ![Share](/help/assets/icons/ShareAlt.svg)**[!UICONTROL 共用]** | 共用選取的區段。 在&#x200B;**[!UICONTROL 共用區段]**&#x200B;對話方塊中，您可以![搜尋](/help/assets/icons/Search.svg) *搜尋個人或群組*，也可以選取&#x200B;**[!UICONTROL 組織]**&#x200B;或&#x200B;**[!UICONTROL 群組]**。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選區段的共用詳細資料。 如需詳細資訊，請參閱[共用區段](filters-share.md)。 |
| ![Delete](/help/assets/icons/Delete.svg)**[!UICONTROL 刪除]** | 刪除選取的區段。 系統會提示您進行確認。 |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名單一選取的區段。 選取後，您可以重新命名內嵌區段。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 核准]** | 核准所選的區段。 如需詳細資訊，請參閱[核准區段](filters-approve.md)。 |
| ![複製](/help/assets/icons/Copy.svg)  **[!UICONTROL 複製]** | 複製選取的區段。 已建立具有相同名稱和尾碼`(Copy)`的新區段。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出為 CSV]** | 將區段匯出至`Filters List.csv`檔案。 |

### 作用中區段列

區段列➌會顯示從區段面板套用至區段清單（如果有的話）的作用中區段。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除區段。 如果指定了多個區段，您可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有區段。

### 區段面板

您可以使用左側面板![區段](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;來區段清單➍。 區段面板會顯示區段型別，以及遵循特定區段的區段數。 選取![區段](/help/assets/icons/Filter.svg)以切換區段面板的顯示。

如需詳細資訊，請參閱[篩選區段清單](filters-filter.md)。
