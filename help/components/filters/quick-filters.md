---
description: 在適用於 Customer Journey Analytics 的 Analysis Workspace 中使用快速篩選
title: 快速篩選
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 76%

---

# 快速篩選

您可以在專案中建立快速篩選以迴避完整[篩選產生器](/help/components/filters/create-filters.md)的複雜性。快速篩選

* 應用為 [僅項目篩選器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html#project-only)。
* 最多允許 3 個規則
* 不要容納巢狀容器或循序規則。

若要比較快速篩選的功能和成熟的元件清單篩選，請至[這裡](/help/components/filters/filters-overview.md)。

下面是一個關於快速濾鏡的視頻（請注意，它改用「快速段」一詞。） 但是，功能是相同的。

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 先決條件 {#prereqs}

任何人都可以建立快速篩選器。 但是，您需要在 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) 以保存快速篩選器或在篩選器生成器中開啟它。

## 建立快速篩選 {#create}

在手繪多邊形表格中，請按一下面板標頭中的篩選器+ 圖示：

![區段篩選](assets/quick-seg1.png)

| 設定 | 說明 |
| --- | --- |
| [!UICONTROL 名稱] | 篩選的預設名稱是篩選中規則名稱的組合。您可將篩選器重新命名為更好記的名稱。 |
| [!UICONTROL 包含/排除] | 您可以在篩選定義中包含或排除元件，但不能同時包含和排除。 |
| [!UICONTROL 點擊/造訪/訪客容器] | 快速篩選僅包含一個[篩選容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，可讓您在篩選中包含（或從中排除）維度/量度/日期範圍。[!UICONTROL 訪客]包含特定於訪客所有造訪次數和頁面檢視的總體資料。[!UICONTROL 造訪次數]容器可讓您設定規則，以根據造訪次數來劃分訪客的資料，而[!UICONTROL 點擊]容器則可讓您根據個別頁面檢視來劃分訪客資訊。預設容器為[!UICONTROL 點擊]。 |
| [!UICONTROL 元件] (Dimension/度量/日期範圍) | 透過新增元件 (維度、量度、日期範圍或維度值) 來定義最多 3 個規則。有 3 種方法可以找到正確的元件：<ul><li>開始輸入，然後[!UICONTROL 快速篩選]產生器就會自動找到合適的元件。</li><li>使用下拉式清單來尋找元件。</li><li>從左側邊欄拖放元件。</li></ul> |
| [!UICONTROL 運算元] | 使用下拉式功能表尋找標準運算子和 [!UICONTROL Distinct Count] 運算子。參閱[篩選運算子](operators.md)。 |
| 加 (+) 號 | 新增另一個規則 |
| AND/OR 限定詞 | 您可以對規則加入「AND」或「OR」的限定詞，但不能在單一篩選定義中混合使用「AND」和「OR」。 |
| [!UICONTROL 套用] | 將此篩選套用在面板上。如果篩選不包含任何資料，系統將詢問您是否要繼續。 |
| [!UICONTROL 開啟產生器] | 開啟篩選產生器。在「篩選產生器」中儲存或套用篩選器後，將無法再考慮「快速篩選」。它會成為元件清單篩選資料庫的一部分。 |
| [!UICONTROL 取消] | 取消這個快速篩選 - 不要套用它。 |
| [!UICONTROL 日期範圍] | 驗證器使用面板日期範圍進行資料查詢。但是在快速篩選中套用的任何日期範圍都會覆寫面板頂端的面板日期範圍。 |
| 預覽 (右上角) | 讓您查看是否有有效的篩選以及篩選的範圍。表示您在套用此篩選時可以看到的資料集劃分。您可能會收到一則通知，指出此篩選器沒有資料。這種情況下，您可繼續或變更篩選器定義。 |

以下是結合維度和量度的篩選範例：

![篩選器定義範例](assets/quick-seg2.png)

篩選會顯示在頂端。請注意，其藍色條紋的側邊欄和左側篩選庫中元件層級篩選的藍色側邊欄相反。

![篩選器元件位置](assets/quick-seg3.png)

## 編輯快速篩選 {#edit}

1. 將滑鼠懸停在快速篩選上，並選取鉛筆圖示。
1. 編輯篩選定義或篩選名稱。
1. 按一下[!UICONTROL 「套用」]。

## 儲存快速篩選 {#save}

您可以選擇在[!UICONTROL 快速篩選產生器]或[!UICONTROL 篩選產生器]中儲存快速篩選。

>[!IMPORTANT]
>儲存或套用篩選後，您將無法在「快速篩選產生器」中對其進行編輯，而只能在一般的篩選產生器中進行編輯。

### 儲存在快速篩選產生器中 {#save2}

1. 套用快速篩選後，將滑鼠懸停在其上並選取資訊 (「i」) 圖示。
1. 按一下&#x200B;**[!UICONTROL 「設為可用於所有專案，並新增至您的元件清單」]**。
1. (選擇性) 重新命名篩選。
1. 按一下「**[!UICONTROL 儲存]**」。

請注意該篩選器的側邊欄如何從藍色條紋變成淺藍色。它現在會顯示在左側欄的元件清單中。

### 儲存在篩選產生器中 {#save3}

1. 將滑鼠懸停在快速篩選上，並選取資訊 (「i」) 圖示。
1. 選取「**[!UICONTROL 儲存篩選]**」
1. 保留名稱不變或對該篩選重新命名。

   返回「工作區」並注意該篩選器現在是否具有淺藍色側邊欄。這表示不能再在「快速篩選產生器」中編輯/開啟該篩選。而透過將其儲存，該區段會成為元件清單的一部分。

   ![篩選器元件清單](assets/quick-seg4.png)

套用篩選後，您可以選擇將其新增到篩選元件清單中，並使其可用於所有專案。

1. 將滑鼠懸停在已儲存的篩選上，並選取鉛筆圖示。

1. 在篩選產生器頂端，請注意這個對話框：

   ![篩選器對話](assets/project-only.png)

1. 選取&#x200B;**[!UICONTROL 「使其可用於您的所有專案並將其新增至您的元件清單中」旁的複選框。]**
1. 按一下「**[!UICONTROL 儲存]**」。
1. 該篩選現在會顯示在所有專案的篩選元件清單中。
1. 您也可以和組織中的其他人[共用篩選](/help/components/filters/manage-filters.md)。

## 什麼是僅限專案的篩選？ {#project-only}

僅限項目的篩選器是僅應用於在中建立的當前項目的篩選器。 在其他項目中不可用，無法與其他用戶共用。 它們旨在快速探索您的資料，而無需在左滑軌中建立和保存過濾器。 可以在面板下拉區域中使用快速篩選器或 [點對點篩選器](/help/components/filters/ad-hoc-filters.md)。

如果在 [!UICONTROL 篩選器生成器]，將顯示僅項目通知。 如果未選中「使此篩選器可用……」 按一下 **[!UICONTROL 應用]**，該段仍為僅用於項目的篩選器。

>[!NOTE]
>
>如果從篩選器生成器應用快速篩選器，則無法在 [!UICONTROL 快速篩選器生成器]。

![取消勾選僅限專案](assets/project-only-unchecked.png)

如果選中「使此篩選器可用……」 按一下 **[!UICONTROL 保存]**，過濾器將在左滑軌元件清單中可用，供其它項目使用。 也可以從過濾器管理器與其他用戶共用。

![勾選僅限專案](assets/project-only-checked.png)

