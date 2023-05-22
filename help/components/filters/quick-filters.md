---
description: 在適用於 Customer Journey Analytics 的 Analysis Workspace 中使用快速篩選
title: 快速篩選
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 41%

---

# 快速篩選

快速篩選器使您能夠輕鬆地瀏覽給定項目中的資料，而無需在 [篩選器生成器](/help/components/filters/create-filters.md)。

建立快速篩選器時，請考慮以下事項：

* 快速篩選器僅適用於建立它們的項目。 您無法在其他專案中取得這些篩選器，且無法和其他使用者共用。
* 最多允許3個規則。
* 不支援嵌套容器或順序規則。

以下視頻演示了如何使用快速濾鏡。 (注：此視頻使用「快速段」而不是「快速過濾器」。 但是，功能是相同的。)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## 建立快速篩選 {#create}

分析工作區中的任何用戶都可以建立快速篩選器。

要建立快速篩選器：

1. 選擇以下方法之一開始建立快速篩選器：

   * **即席（拖放）:** 從左滑軌，將元件拖動到 **篩選** 表徵圖，然後選擇 **編輯** 表徵圖以調整濾鏡。

      ![編輯即席篩選器](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > 建立快速過濾器即席（拖放）時，請考慮以下事項：
      > * 不支援以下元件類型：計算的度量和維，以及無法構建篩選器的度量。
      > * 對於完整維和事件，Analysis Workspace會建立「存在」事件篩選器。 範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
      > * 如將「未指定」或「無」拖放至篩選拖放區，就會自動轉換成「不存在」篩選，以便系統可正確處理篩選。



   * **使用篩選器表徵圖：** 在自由形式表中，選擇 **篩選** 表徵圖。

      ![區段篩選](assets/quick-seg1.png)

1. 調整下列任何設定：

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 篩選的預設名稱是篩選器中規則名稱的組合。您可將篩選器重新命名為更好記的名稱。 |
   | [!UICONTROL 包含/排除] | 您可以在篩選定義中包含或排除元件，但不能同時包含和排除。 |
   | [!UICONTROL 點擊/造訪/訪客]容器 | 快速篩選僅包含一個[篩選容器](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html#filter-containers)，可讓您在篩選中包含（或從中排除）維度/量度/日期範圍。[!UICONTROL 訪客]包含特定於訪客所有造訪次數和頁面檢視的總體資料。[!UICONTROL 造訪次數]容器可讓您設定規則，以根據造訪次數來劃分訪客的資料，而[!UICONTROL 點擊]容器則可讓您根據個別頁面檢視來劃分訪客資訊。 預設容器為[!UICONTROL 點擊]。 |
   | [!UICONTROL 元件] (維度/量度/日期範圍) | 透過新增元件 (維度、量度、日期範圍或維度值) 來定義最多 3 個規則。有 3 種方法可以找到正確的元件:<ul><li>開始鍵入，快速篩選器生成器會自動找到相應的元件。</li><li>使用下拉式清單來尋找元件。</li><li>從左側邊欄拖放元件。</li></ul> |
   | [!UICONTROL 運算子] | 使用下拉式選單尋找標準運算子和[!UICONTROL 相異計數]運算子。參閱[篩選運算子](operators.md)。 |
   | 加 (+) 號 | 新增另一個規則 |
   | AND/OR 限定詞 | 您可以對規則加入「AND」或「OR」的限定詞，但不能在單一篩選定義中混合使用「AND」和「OR」。 |
   | [!UICONTROL 套用] | 將此篩選套用在面板上。如果篩選器不包含任何資料，則系統會詢問您是否要繼續。 |
   | [!UICONTROL 開啟產生器] | 開啟篩選產生器。在篩選器生成器中保存或應用篩選器後，它不再被視為「快速篩選器」。 它會成為元件清單篩選資料庫的一部分。 <p>要使元件在所有項目和左滑軌中都可用，請選擇 [!UICONTROL **使此篩選器可用於所有項目，並將其添加到元件清單**]。</p><p>有關詳細資訊，請參閱 [將快速篩選器另存為元件清單篩選器](#save-a-quick-filter-as-a-component-list-filter) 在本文中。</p><p>**注：** 僅在中具有「篩選器建立」權限的用戶 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools) 可以開啟篩選器生成器。</p> |
   | [!UICONTROL 取消] | 取消此快速篩選器（不要應用它）。 |
   | [!UICONTROL 日期範圍] | 驗證器使用面板日期範圍進行資料查詢。但是在快速篩選中套用的任何日期範圍都會覆寫面板頂端的面板日期範圍。 |
   | 預覽 (右上角) | 讓您查看是否有有效的篩選以及篩選的範圍。表示應用此篩選器時可望看到的資料集的細分。 您可能會收到一則通知，指出此篩選器沒有資料。這種情況下，您可繼續或變更篩選器定義。 |

1. 選擇 [!UICONTROL **應用**] 的子菜單。

## 編輯快速篩選器 {#edit}

1. 將滑鼠懸停在要編輯的快速篩選器上，然後選擇 **編輯** 表徵圖

   ![編輯即席篩選器](assets/filter-adhoc-edit.png)

1. 編輯篩選定義或篩選名稱。
1. 選擇 [!UICONTROL **應用**] 的子菜單。

## 將快速篩選器另存為元件清單篩選器 {#save}

>[!IMPORTANT]
>
> 保存快速篩選器時，請考慮以下事項：
> 
> * 要保存快速篩選器，您需要在 [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html#analytics-tools)。
> 
> * 保存或應用篩選器後，將無法再在快速篩選器生成器中對其進行編輯。 而必須使用常規篩選器生成器。


可以選擇將快速篩選器另存為元件清單篩選器。 元件清單過濾器的優點包括：

* 所有Workspace項目的可用性
* 支援更複雜的過濾器以及順序過濾器

可以從快速篩選器生成器或 [!UICONTROL 篩選器生成器]。

### 在快速篩選器生成器中保存 {#save2}

1. 應用快速篩選器後，將滑鼠懸停在該篩選器上並選擇資訊(「i」)表徵圖。
1. 選擇 **[!UICONTROL 使所有項目都可用並添加到元件清單]**。
1. (選擇性) 重新命名篩選。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   過濾器現在出現在左側滑軌的元件清單中。 另請注意，濾鏡的側欄從淡藍色變為深藍色，表明無法再在快速濾鏡生成器中編輯或開啟濾鏡。

### 在篩選器生成器中保存 {#save3}

1. 應用快速篩選器後，將滑鼠懸停在該篩選器上並選擇資訊(「i」)表徵圖。
1. 選取「**[!UICONTROL 儲存篩選]**」
1. （可選）更名篩選器，然後選擇 [!UICONTROL **應用**]。

   返回「工作區」(Workspace)，並注意濾鏡的側欄從淡藍色變為深藍色，表明無法再在快速濾鏡生成器中編輯或開啟濾鏡。 而透過將其儲存，該區段會成為元件清單的一部分。

   ![篩選器元件清單](assets/quick-seg4.png)

應用篩選器後，您可以選擇將其添加到篩選器元件清單中，並使其可用於所有項目。

1. 將滑鼠懸停在已儲存的篩選上，並選取鉛筆圖示。

1. 選擇 [!UICONTROL **開啟生成器**]。

1. 在篩選產生器頂端，請注意這個對話框：

   ![篩選器對話](assets/project-only-filter-dialog.png)

1. 選中旁邊的複選框 **[!UICONTROL 將此檔案可用於所有項目，並將其添加到元件清單中。]**

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   該篩選現在會顯示在所有專案的篩選元件清單中。您也可以和組織中的其他人[共用篩選](/help/components/filters/manage-filters.md)。

## 快速篩選示例

以下篩選器示例組合了維和度量：

![篩選器定義範例](assets/quick-seg2.png)

