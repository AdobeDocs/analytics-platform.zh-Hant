---
description: 在適用於 Customer Journey Analytics 的 Analysis Workspace 中使用快速篩選
title: 快速篩選
feature: Workspace Basics
role: User
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 53d367e51f739ebf324390ba4114ddb58138fac8
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 39%

---

# 快速篩選

快速篩選可讓您輕鬆探索指定專案中的資料，而不需在[篩選產生器](/help/components/filters/create-filters.md)中建立更複雜的元件清單篩選。

建立快速篩選時，請考量下列事項：

* 快速篩選只適用於建立所在的專案。 您無法在其他專案中取得這些區段，且無法和其他使用者共用這些區段。
* 最多允許訂定 3 條規則。
* 不支援巢狀容器或循序規則。
* 如果您與其他使用者共用專案，這些使用者可以編輯快速篩選以及內嵌在共用專案中的其他僅限專案元件。

下列影片示範如何使用快速篩選。 (注意：本影片使用「快速區段」一詞而非「快速篩選」。 但功能相同。)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 建立快速篩選 {#create}

Analysis Workspace中的任何使用者都可以建立快速篩選。

若要建立快速篩選：

1. 選擇下列其中一種方法，開始建立快速篩選：

   * **臨機（拖放）：**&#x200B;從左側邊欄，將元件拖曳至面板標頭的篩選拖放區域。

     ![將區段放入放置區](assets/filter-dropzone.png)

     您可以編輯快速篩選，如[編輯快速篩選](#edit-a-quick-filter)中所述。

     >[!NOTE]
     >
     > 臨機建立快速篩選時，請考量下列事項（拖放）：
     > * 不支援下列元件型別：計算量度和維度，以及無法建立篩選器的量度。
     > * 為了取得完整的維度和事件，Analysis Workspace會建立「存在」事件篩選器。 範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
     > * 如將「未指定」或「無」拖放至篩選拖放區，就會自動轉換成「不存在」篩選，以便系統可正確處理篩選。


   * **使用篩選器圖示：**&#x200B;在自由格式表格中，選取面板標頭中的&#x200B;**篩選器**&#x200B;圖示。

     ![區段篩選](assets/quick-seg1.png)

1. 調整以下任何設定：

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 篩選的預設名稱是篩選器中規則名稱的組合。您可將篩選器重新命名為更好記的名稱。 |
   | [!UICONTROL 包含/排除] | 您可以在篩選定義中包含或排除元件，但不能同時包含和排除。 |
   | [!UICONTROL 點擊/造訪/訪客]容器 | 快速篩選僅包含一個[篩選容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，可讓您在篩選中包含（或從中排除）維度/量度/日期範圍。[!UICONTROL 訪客]包含該人員在不同瀏覽和頁面檢視間專屬的總體資料。 [!UICONTROL 造訪]容器可讓您設定規則，以根據造訪來劃分人員的資料，而[!UICONTROL 點選]容器則可讓您根據個別頁面檢視來劃分人員資訊。 預設容器為[!UICONTROL 點擊]。 |
   | [!UICONTROL 元件] (維度/量度/日期範圍) | 透過新增元件 (維度、量度、日期範圍或維度值) 來定義最多 3 個規則。有 3 種方法可以找到正確的元件:<ul><li>開始輸入，然後快速篩選產生器就會自動找到合適的元件。</li><li>使用下拉式清單來尋找元件。</li><li>從左側邊欄拖放元件。</li></ul> |
   | [!UICONTROL 運算子] | 使用下拉式選單尋找標準運算子和[!UICONTROL 相異計數]運算子。參閱[篩選運算子](operators.md)。 |
   | 加 (+) 號 | 新增另一個規則 |
   | AND/OR 限定詞 | 您可以對規則加入「AND」或「OR」的限定詞，但不能在單一篩選定義中混合使用「AND」和「OR」。 |
   | [!UICONTROL 套用] | 將此篩選套用在面板上。如果篩選不包含任何資料，系統會詢問您是否要繼續。 |
   | [!UICONTROL 開啟產生器] | 開啟篩選產生器。在篩選產生器中儲存或套用篩選後，將無法再考慮「快速篩選」。 它會成為元件清單篩選資料庫的一部分。 <p>若要讓元件可在您所有專案和左側邊欄中使用，請選取&#x200B;[!UICONTROL **讓此篩選器可用於您的所有專案，並將其新增至您的元件清單**]。</p><p>如需詳細資訊，請參閱本文中的[將快速篩選儲存為元件清單篩選](#save-a-quick-filter-as-a-component-list-filter)一節。</p><p>**注意：**&#x200B;只有在[Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html)中擁有區段建立許可權的使用者才能開啟篩選產生器。</p> |
   | [!UICONTROL 取消] | 取消此快速篩選（不要套用它）。 |
   | [!UICONTROL 日期範圍] | 驗證器使用面板日期範圍進行資料查詢。但是在快速篩選中套用的任何日期範圍都會覆寫面板頂端的面板日期範圍。 |
   | 預覽 (右上角) | 讓您查看是否有有效的篩選以及篩選的範圍。代表您套用此篩選器時可預期看到的資料集劃分。 您可能會收到一則通知，指出此篩選器沒有資料。這種情況下，您可繼續或變更篩選器定義。 |

1. 選取「[!UICONTROL **套用**]」以儲存您的變更。

## 編輯快速篩選 {#edit}

1. 將滑鼠停留在您要編輯的快速篩選上，然後選取&#x200B;**編輯**&#x200B;圖示。

   ![編輯臨時篩選器](assets/filter-adhoc-edit.png)

1. 編輯篩選定義或篩選名稱。
1. 選取「[!UICONTROL **套用**]」以儲存您的變更。

## 將快速篩選儲存為元件清單篩選 {#save}

>[!IMPORTANT]
>
> 儲存快速篩選時，請考量下列事項：
> 
> * 若要儲存快速篩選，您需要[Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html)中的區段建立許可權。
> 
> * 儲存或套用篩選後，無法在快速篩選產生器中對其進行編輯。 您必須改用一般篩選產生器。

您可以選擇將快速篩選儲存為元件清單篩選。 元件清單篩選器的優點包括：

* 所有 Workspace 專案的適用性
* 支援更複雜的篩選器以及循序篩選器

您可以從快速篩選產生器或[!UICONTROL 篩選產生器]儲存篩選。

### 儲存在快速篩選產生器中 {#save2}

1. 套用快速篩選後，將滑鼠懸停在其上並選取資訊(「i」)圖示。
1. 選取「**[!UICONTROL 設為可用於所有專案，並新增至您的元件清單]**」。
1. (選擇性) 重新命名篩選。
1. 選取「**[!UICONTROL 儲存]**」。

   該篩選器現在會顯示在左側欄的元件清單中。 另請注意，篩選的側邊欄會從淺藍色變更為深藍色，表示無法在快速篩選產生器中再編輯或開啟篩選。

### 儲存在篩選產生器中 {#save3}

1. 套用快速篩選後，將滑鼠懸停在其上並選取資訊(「i」)圖示。
1. 選取「**[!UICONTROL 儲存篩選]**」
1. （選擇性）重新命名篩選，然後選取&#x200B;[!UICONTROL **套用**]。

   返回Workspace並注意篩選的側邊欄會從淺藍色變更為深藍色，表示無法在快速篩選產生器中再編輯或開啟篩選。 而透過將其儲存，該區段會成為元件清單的一部分。

   ![篩選器元件清單](assets/quick-seg4.png)

套用篩選後，您可以選擇將其新增到篩選元件清單中，並使其可用於所有專案。

1. 將滑鼠懸停在已儲存的篩選上，並選取鉛筆圖示。

1. 選取「[!UICONTROL **開啟產生器**]」。

1. 在篩選產生器頂端，請注意這個對話框：

   ![篩選器對話](assets/project-only-filter-dialog.png)

1. 選取&#x200B;**[!UICONTROL 讓此篩選器可用於您的所有專案並將其新增至您的元件清單旁的核取方塊。]**

1. 選取「**[!UICONTROL 儲存]**」。

   該篩選器現在會顯示在您所有專案的篩選器元件清單中。
您也可以和組織中的其他人[共用篩選](/help/components/filters/filters-share.md)。

## 快速篩選範例

下列篩選範例結合使用維度和量度：

![篩選器定義範例](assets/quick-seg2.png)

