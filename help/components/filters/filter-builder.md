---
description: 區段產生器提供畫布來拖放量度維度、區段和事件，以便根據容器階層邏輯、規則和運運算元來區分人員。 此整合式開發工具可讓您建立並儲存簡單或複雜的區段，用以識別跨造訪及事件的人員屬性和動作。
title: 建立區段
feature: Filters
role: User
exl-id: 160021f1-6942-4682-9114-d375307d9912
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1571'
ht-degree: 45%

---

# 建立區段 {#build-segments}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_createaudience"
>title="建立對象"
>abstract="對象可以從區段建立，並與Adobe Experience Platform共用以啟用。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_datapreview"
>title="資料預覽"
>abstract="將此區段的資料與資料檢視的資料進行比較。 此預覽百分比是根據資料檢視中&#x200B;**過去 90 天**&#x200B;的總數。<br><br/>如果預覽未載入，您的連線可能仍在進行回填。"

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 區段產生器]**&#x200B;對話方塊可用來建立新區段或編輯現有區段。 對話方塊的標題為&#x200B;**[!UICONTROL 新區段]**&#x200B;或&#x200B;**[!UICONTROL 編輯您從[[!UICONTROL 區段]管理員](/help/components/filters/manage-filters.md)建立或管理的區段]**。

>[!BEGINTABS]

>[!TAB 區段產生器]

![區段詳細資訊視窗，顯示下一節中說明的欄位和選項。](assets/filter-builder.png)

>[!TAB 建立或編輯區段]

![區段詳細資訊視窗，顯示下一節中說明的欄位和選項。](assets/create-edit-filter.png)

>[!ENDTABS]

1. 指定以下詳細資料 (![Required](/help/assets/icons/Required.svg) 是必要的)：

   | 元素 | 說明 |
   | --- | --- |
   | **[!UICONTROL 資料檢視]** | 您可以選取區段的資料檢視。  您定義的區段可在資料檢視的[設定](/help/data-views/create-dataview.md#settings-filters)標籤中作為區段使用。 |
   | **[!UICONTROL 僅限專案的區段]** | 說明區段僅會顯示在建立該區段的專案中的資訊方塊，且不會將該區段新增至您的元件清單的資訊方塊。 啟用&#x200B;**[!UICONTROL 讓此區段可用於您的所有專案，並將其新增至您的元件清單]**&#x200B;以變更該設定。 只有當您使用[!UICONTROL 快速區段]介面中的&#x200B;**[!UICONTROL Open builder]**&#x200B;建立[快速區段](quick-filters.md)，並將快速區段資訊轉換為一般區段時，才會顯示此資訊方塊。 |
   | **[!UICONTROL 標題]**![必填](/help/assets/icons/Required.svg) | 為區段命名，例如`Last month mobile customers`。 |
   | **[!UICONTROL 說明]** | 提供區段的說明，例如`Segment to define the mobile customers for the last month`。 |
   | **[!UICONTROL 標記]** | 透過建立或套用一個或多個標籤來組織區段。 開始輸入內容以尋找您可以選取的現有標記。或按一下 **[!UICONTROL ENTER]** 以新增新標記。選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除標記。 |
   | **[!UICONTROL 定義]** ![規定必要](/help/assets/icons/Required.svg) | 使用[定義產生器](#definition-builder)定義您的區段。 |

   {style="table-layout:auto"}

1. 若要確認區段定義是否正確，請使用右上方的區段結果持續更新預覽。
1. 若要從區段建立對象並與Experience Platform共用對象，請選取「**[!UICONTROL 從區段建立對象]**」。 請參閱「[建立並發佈客群](/help/components/audiences/publish.md)」，了解更多資訊。
1. 選取：
   * **[!UICONTROL 儲存]**&#x200B;以儲存區段。
   * **[!UICONTROL 另存新檔]**&#x200B;以儲存區段的復本。
   * **[!UICONTROL 刪除]**&#x200B;以刪除區段。
   * **[!UICONTROL 取消]**&#x200B;以取消您對區段所做的任何變更，或取消建立新區段。


## 定義產生器

您可以使用定義產生器來建構區段定義。 在該構造中，您可以使用元件、容器、運算子和邏輯。

您可以設定定義的類型和範圍：

1. 若要指定定義的類型，請指定是否要建立一個包含定義或一個排除定義。選取「![設定](/help/assets/icons/Setting.svg)**[!UICONTROL 選項]**」，並從下拉式選單切換「**[!UICONTROL 包含]**」或「**[!UICONTROL 排除]**」。
1. 若要指定定義的範圍，請從&#x200B;**[!UICONTROL 包含]**&#x200B;或&#x200B;**[!UICONTROL 排除]**&#x200B;下拉式清單中選取，以決定您要定義的範圍是&#x200B;**[!UICONTROL 事件]**、**[!UICONTROL 工作階段]**、**[!UICONTROL 人員]**、**[!UICONTROL 全域帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}、**[!UICONTROL 機會]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}或&#x200B;**[!UICONTROL 購買群組]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}

您稍後可以隨時變更這些設定。

### 元件

建構區段定義的重要部分是使用維度、量度、現有區段和日期範圍。 所有這些元件都可從區段產生器的元件面板使用。

![開始建置定義](assets/start-building-filter.gif){width=100%}

若要新增元件：

1. 將元件從元件面板拖放至&#x200B;**[!UICONTROL 將量度、區段和/或維度拖放到這裡]**。 您可以使用元件列中的「![搜尋](/help/assets/icons/Search.svg)」來搜尋特定元件。
1. 指定元件的詳細資訊。例如，從「**[!UICONTROL 選擇值]**」中選取一個值。或輸入一個值。指定一個或多個值的內容和方式取決於元件和運算子。
1. 可選擇修訂預設的運算子。例如，從「**[!UICONTROL 等於]**」改為「**[!UICONTROL 等於任何]**」。請參閱「[運算子](operators.md)」，了解可用運算子詳細概觀。

若要編輯元件：

* 從運算子下拉式選單中為元件選取新的運算子。
* 若可以，請為運算子選取或指定不同的值。
* 如果元件類型是維度，則可以定義歸因模型。如需詳細資訊，請參閱「[歸因模型](#attribution-models)」。

若要刪除元件：

* 在元件中選取 ![CrossSize75](/help/assets/icons/CrossSize75.svg)。

### 容器

您可以將多個元件分組在一個或多個容器中，並定義容器內和容器之間的邏輯。容器可讓您為區段建立複雜的定義。

![新增容器](assets/add-container.gif){Width=100%}

* 若要新增容器，請選取「**[!UICONTROL 新增容器]**」(從 ![環境](/help/assets/icons/Setting.svg) **[!UICONTROL 選項]**)。
* 若要將現有元件新增至容器中，請將元件拖曳到容器中。
* 若要為容器新增另一個元件，請將元件從元件面板拖曳到容器中。使用藍色插入線作為準則。
* 若要在容器外部新增另一個元件，請將元件從元件面板拖曳到容器外部，但拖曳到主定義容器內部。使用藍色插入線作為準則。
* 若要修改容器內元件之間、容器之間或容器與元件之間的邏輯，請選取適當的「**[!UICONTROL 以及]**」(And)、「**[!UICONTROL 或]**」(Or)、「**[!UICONTROL 然後]**」(Then)。選取「然後」時，將區段轉換為循序區段。 如需詳細資訊，請參閱[建立循序區段](seg-sequential-build.md)。
* 若要切換容器層級，請選取![全球](/help/assets/icons/Globe.svg) **[!UICONTROL 全域帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，![帳戶](/help/assets/icons/Account.svg) **[!UICONTROL 帳戶]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，![機會](/help/assets/icons/Opportunity.svg) **[!UICONTROL 機會]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，![購買群組](/help/assets/icons/BuyingGroup.svg) **[!UICONTROL 購買群組]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}，![網頁](/help/assets/icons/WebPage.svg) **[!UICONTROL 事件]**，![訪問](/help/assets/icons/Visit.svg) **[!UICONTROL 會話]**&#x200B;或![使用者](/help/assets/icons/User.svg) **[!UICONTROL 人員]**。

您可以在容器中使用 ![設定](/help/assets/icons/Setting.svg) 來執行下列動作：

| 容器動作 | 說明 |
|---|---|
| **[!UICONTROL 新增容器]** | 新增巢狀容器至容器中。 |
| **[!UICONTROL 排除]** | 從區段定義中的容器排除結果。 左側的細紅色條是指排除容器。 |
| **[!UICONTROL 包括]** | 在區段定義中包含來自容器的結果。 包含為預設值。左側的細灰色條是指包含容器。 |
| **[!UICONTROL 容器名稱]** | 根據容器的預設說明為容器重新命名。在文字欄位中輸入名稱。如果您未輸入任何資料，則使用預設說明。 |
| **[!UICONTROL 刪除容器]** | 根據定義來刪除容器。 |


## 日期範圍

您可以建立包含滾動式日期範圍的區段。 如此一來，您就能回答與持續性促銷活動或事件有關的問題。 例如，您可以建置一個區段，包含&#x200B;*過去60天內進行線上購買的所有人*。

![使用滾動日期範圍的區段](assets/filter-rolling-date-range.gif)


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在區段捲動日期範圍](https://video.tv.adobe.com/v/25403/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## 棧疊區段 {#stack}

您可以使用區段來建立區段。 在區段中使用區段時，您可以最佳化區段並降低複雜性。

想像您想要依裝置型別(2)和美國狀態(50)的組合進行分段。 您可以建立100個區段，每個區段都適用於裝置型別（行動電話與平板電腦）和美國州的獨特組合。 若要在加州取得平板電腦使用者，您可以使用下列100個區段之一：

![加州和平板電腦的簡單區段](assets/filter-ca-tablet-single.png)

或者，您可以定義52個區段：50個區段適用於美國各州，一個適用於行動電話，一個適用於平板電腦。 然後棧疊區段以獲得相同的結果。 若要取得California平板電腦使用者，您可棧疊兩個區段：

CA和平板電腦的![棧疊區段](assets/filter-ca-tablet-stacked.png)


## 歸因 {#attribution}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_repeating"
>title="重複"
>abstract="包括維度的例項和持續值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_instance"
>title="例項"
>abstract="包括維度的例項和持續值。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_filters_attribution_nonrepeatinginstance"
>title="非重複的例項"
>abstract="包括維度的唯一例項 (非重複) 例項。"

<!-- markdownlint-enable MD034 -->



在「區段產生器」中使用維度時，您可以選擇指定該維度的歸因模型。 您選取的歸因模型會決定資料是否符合您為維度元件指定的條件。

在維度元件中選取「![設定](/help/assets/icons/Setting.svg)」，然後從快顯視窗中選取一個歸因模型：

| 模型 | 說明 |
|---|---|
| **[!UICONTROL 重複模型 (預設)]** | 包含維度的實例和持續值來確定資格。 |
| **[!UICONTROL 例項]** | 僅包含維度的實例值來確定資格。 |
| **[!UICONTROL 非重複的例項]** | 包含維度的唯一實例 (非重複) 值來確定資格。 |


建立區段時![維度上的歸因模型](assets/filter-dimension-attribution.png)

### 範例

在區段定義中，您已指定下列條件：「頁面名稱」等於「女性」。 與上述範例類似。 您會使用其他兩個歸因模型來重複此區段定義。 因此，您有三個區段，每個區段都有各自的歸因模型：

* 女性頁面 - 歸因 - 重複 (預設)
* 女性頁面 - 歸因 - 實例
* 女性頁面 - 歸因 - 非重複實例


下表說明每個歸因模型，其中傳入的事件是符合該條件的 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)。


| 女性頁面 - 歸因 - <br/>*歸因模型* | 事件 1：<br/>頁面名稱等於<br/>女性 | 事件 2：<br/>頁面名稱等於<br/>男性 | 事件 3：<br/>頁面名稱等於<br/>女性 | 事件 4：<br/>頁面名稱等於<br/>女性<br/> (持續) | 事件 5：<br/>頁面名稱等於<br/>結帳 | 事件 6：<br/>頁面名稱等於<br/>女性 | 事件 7：<br/>頁面名稱等於<br/>首頁 |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:--:|
| 重複 (預設) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) |
| 例項 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) |
| 非重複的例項 | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) | ![移除](/help/assets/icons/Remove.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![移除](/help/assets/icons/Remove.svg) |

有關使用三個區段的事件的範例報表看起來如下所示：

![區段歸因模型結果](assets/filter-dimension-attribution-results.png)
