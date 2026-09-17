---
title: 處理Customer Journey Analytics報表中無值
description: 瞭解Customer Journey Analytics報表中何時應該有**[!UICONTROL 沒有值]**專案，以及這些專案表示需要注意的資料收集問題。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: bc1e610ccf13ca831f40b2819a4665fe8ea21b7b
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 0%
---

# 如何處理無值

使用Customer Journey Analytics時，在報表和儀表板中遇到&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案，會產生有關資料品質、收集方法和報表正確性的重要問題。 這些執行個體需要謹慎監控，因為它們會揭示資料收集中的隱藏間隙。 難題在於區分兩種情況：當&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案需要資料來源提供者調查時，以及&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案反映資料流入Customer Journey Analytics的自然流程時。 瞭解這項差異對於維持有效率的分析作業至關重要。 本指南可協助您針對Customer Journey Analytics實作中的&#x200B;**[!UICONTROL 無值]**&#x200B;外觀做出明智的決策。

## 瞭解無值

**[!UICONTROL 如果維度沒有對應值，而事件又包含量度，則不會出現任何值]**。 在報告中看到&#x200B;**[!UICONTROL 沒有值]**&#x200B;並不一定有問題。 在許多情況下，它反映了資料集的預期結構。

Dimension專案分為三個類別之一：

* **必須是[!UICONTROL 沒有值]**：使用者移動您資料的自然結果，例如尚未登入的訪客，或不適用於每個事件的維度
* **有問題[!UICONTROL 沒有值]**：資料收集失敗或實作錯誤的結果，其中值存在但遺失
* **有效值**：維度已成功擷取值

下圖顯示當資料從您的來源移動到Adobe Experience Platform時，Customer Journey Analytics如何進入這些類別。

流程圖會說明Customer Journey Analytics評估如何先檢查值是否存在，然後判斷遺漏值是預期的還是有問題，藉此著重處理傳入資料。 此明確的評估可協助管理員和分析人員區分需要來源調查的&#x200B;**[!UICONTROL 無值]**&#x200B;案例與代表正常操作的案例。

![決定流程顯示透過Adobe Experience Platform移入Customer Journey Analytics的來源資料，這會檢查是否有維度值存在，然後檢查缺少值是否為預期的情況，導致自然的「無」值、有問題的「無」值或有效的值](assets/no-value-flow.svg)

## 當沒有預期值時

下列是&#x200B;**[!UICONTROL 沒有值]**&#x200B;出現在報表中的常見預期原因：

* 維度僅適用於特定案例，例如流量來源或裝置型別
* 尚未為首次訪客指派識別碼
* 訪客處於預先登入狀態，未提供使用者資訊
* 功能或產品互動不適用於特定使用者歷程
* 跨裝置案例不會跨裝置攜帶維度值

在這些情況下，**[!UICONTROL 沒有值]**&#x200B;表示使用者在從未識別狀態轉換為已識別狀態期間，在其驗證歷程中的位置，如下圖所示。

![使用者驗證歷程顯示使用者造訪網站並進入沒有可用使用者資訊的預先登入狀態，然後是填入使用者資訊的登入事件](assets/no-value-login-flow.svg)


## 當沒有值需要注意時

調查&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案，因為它們是以下任一專案所產生：

**資料來源的實作問題：**

* 缺少資料元素或Null值
* 不正確的變數對應
* 未正確設定的資料層
* 失敗的資料收集
* 傳入資料和定義的結構描述之間不相符

**資料品質問題：**

* 損壞的追蹤程式碼
* 不完整的資料彙集
* 整合失敗
* 資料轉換期間發生錯誤
* 資料管道中斷

## 管理資料檢視設定中的「無值」

資料檢視設定可讓您控制&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案在報表中的顯示方式，包括重新命名標籤、預設顯示或隱藏專案，以及將&#x200B;**[!UICONTROL 沒有值]**&#x200B;視為合法的字串值。 請參閱[無值選項元件設定](/help/data-views/component-settings/no-value-options.md)，以取得設定的完整清單，以及這些設定如何影響百分比分佈、篩選及分段。

設定這些設定時，請評估您的報告需求，並評估&#x200B;**[!UICONTROL 沒有值]**&#x200B;的存在對您的分析有何影響。 既要考慮對資料可見性的即時影響，也要考慮對趨勢分析和報告一致性的長期影響。 經過良好選擇的設定可提升資料清晰度，同時保持業務深入分析的可存取性和可操作性，無論&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案在您的報表中如何顯示。 理想的設定可平衡資料表示與實用的分析需求，即使在&#x200B;**[!UICONTROL 沒有值]**&#x200B;資料時，也能建立可提供正確且有意義的深入分析的報告環境。

下表摘要列出各種可用的組態。

<table>
<thead>
<tr>
<th>類別</th>
<th>設定</th>
<th>作用</th>
<th>影響</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="2">顯示選項</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">可透過自由表格搜尋篩選條件中的核取方塊選取來包含或排除。</td>
<td rowspan="2">可見性</td>
</tr>
<tr>
<td><img src="assets/dont-show-no-value-default.png"/></td>
</tr>
<tr>
<td rowspan="2">自訂命名</td>
<td><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">影響報表維度值顯示，並可能影響值合併和量度彙總。</td>
<td rowspan="2">命名</td>
</tr>
<tr>
<td><img src="assets/show-unknown-as-value.png"/></td>
</tr>
<tr>
<td rowspan="3">處理選項</td>
<td><img src="assets/treat-no-value-as-value.png"/></td>
<td>僅適用於非數值維度。
同時影響歸因和自由表格搜尋篩選器中的包含**[！UICONTROL無值]**選項。</td>
<td>值處理與可見性</td>
</tr>
<tr>
<td rowspan="2">數值維度支援：<br><img src="assets/dont-show-no-value-default.png"/><br/><img src="assets/show-no-value-default.png"/></td>
<td rowspan="2">可透過自由表格搜尋篩選條件中的核取方塊選取來包含或排除</td>
<td rowspan="2">可見性</td>
</tr>
<tr>
</tr>
</tbody>
</table>


### 如果顯示，請呼叫「無值」

此設定可讓您自訂&#x200B;**[!UICONTROL 沒有值]**&#x200B;列在報表中的顯示方式。 您可以在文字欄位中輸入&#x200B;**[!UICONTROL 無值]**&#x200B;維度專案的自訂名稱，透過&#x200B;**[!UICONTROL 提供更有意義的內容。如果顯示，請呼叫「無值」]**。 使用明確、適合商業使用的辭彙而非`No value`，可協助您的組織更清楚瞭解報表值。 雖然您無法直接使用&#x200B;**[!UICONTROL 沒有值]**&#x200B;做為區段中的字串，但您可以使用&#x200B;**[!UICONTROL 不存在]**&#x200B;運運算元來達到相同的效果。

您可以使用描述性辭彙取代`No value`，例如`Pre-login User`代表驗證狀態，`No Customer Tier`代表沒有層級的客戶，或`No Tracked Marketing Channel`代表未識別的行銷來源。 如此可建立更直覺式的報表。 `Pre-login User`清楚顯示客戶在其歷程中的位置，而`No Customer Tier`提供特定內容。 請記住，您選擇的說明適用於該維度的所有&#x200B;**[!UICONTROL 沒有值]**&#x200B;執行個體，因此請選取能正確反映缺少維度值之所有情況的辭彙。

### 預設不顯示「無」值

此設定決定是否在報告中預設隱藏&#x200B;**[!UICONTROL 沒有值]**&#x200B;列。 啟用後，這些列最初會被篩選掉，但如有需要，還是可以顯示在自由表格中，方法是選取自由表格搜尋篩選器中的核取方塊。 請注意，隱藏&#x200B;**[!UICONTROL 沒有值]**&#x200B;列會影響剩餘值的百分比分佈，因為百分比只會根據可見專案重新計算。

### 預設顯示「無」值

此設定控制報表中是否預設顯示&#x200B;**[!UICONTROL 沒有值]**。 啟用時，不會顯示&#x200B;**[!UICONTROL 任何值]**&#x200B;專案，但使用者可以使用自由表格搜尋篩選器中的核取方塊來排除這些專案。 包含或排除&#x200B;**[!UICONTROL 沒有任何值]**&#x200B;列會影響百分比分佈，因為百分比僅根據可見專案計算。

### 將「無值」視為值

此設定會將&#x200B;**[!UICONTROL 沒有值]**&#x200B;視為字串值（數值維度除外），可讓您自訂其表示為維度值。 此自訂動作會同時影響歸因和自由表格搜尋篩選器中的&#x200B;**[!UICONTROL 不包含值]**&#x200B;選項。 請記住，當您指派自訂字串值時，資料集中的所有相符值都會合併至相同的維度字串值下。

**[!UICONTROL 將「沒有值」視為值]**&#x200B;設定與預設顯示&#x200B;**[!UICONTROL 沒有值]**&#x200B;具有不同的用途。 預設情況下，只顯示可控制可見性，而視為值會變更Customer Journey Analytics邏輯處理這些專案的方式。 以下是這項區分很重要的原因：

* 它可讓您在篩選和分段時進行更細微的控制，使&#x200B;**[!UICONTROL 沒有值]**&#x200B;成為不同的、可操作的維度值。
* 它將&#x200B;**[!UICONTROL 沒有值]**&#x200B;視為歸因模型和視覺效果中的合法維度值，藉此在整個分析中維持一致的歸因和表示。

您將&#x200B;**[!UICONTROL 沒有值]**&#x200B;視為下列情況中的值：

* 缺少資料本身對您的分析很有意義（例如登入前狀態或未歸因的流量）。
* 您需要建立專門針對或排除這些情況的區段或計算量度。

相反地，預設顯示&#x200B;**[!UICONTROL 沒有值]**&#x200B;更適合需要基本的可見度遺失資料，而不需要複雜的附加邏輯和歸因（將其視為值）。

### 數值維度不支援值

對於數值維度，有數個組態選項可供使用。 在「資料檢視」維度設定中，您可以設定所有&#x200B;**[!UICONTROL 無值]**&#x200B;選項，但&#x200B;**[!UICONTROL 將「無值」視為值]**&#x200B;除外。 您也可以在自由表格搜尋篩選條件中選取核取方塊，以管理數值維度的&#x200B;**[!UICONTROL 包含「沒有值」]**。 建立區段時，您可以使用具有數值維度的&#x200B;**[!UICONTROL 存在]**&#x200B;或&#x200B;**[!UICONTROL 不存在]**&#x200B;運運算元。

### 沒有值和專案層級維度

有些維度會套用至陣列中的專案層級，而非事件的頂層。 例如，`productListItems.SKU`只有在該事件的產品清單專案存在時才有值。 這個資料粒度的差異會改變&#x200B;**[!UICONTROL 沒有值]**&#x200B;的行為。

對於標準最上層維度，每當該維度遺失或在具有量度的事件上具有Null值時，Customer Journey Analytics即可將量度置於&#x200B;**[!UICONTROL 沒有值]**&#x200B;貯體中。 專案層級維度取決於存在於第一位的專案。 如果事件包含量度但缺少產品清單專案，Customer Journey Analytics就沒有列可將該量度附加至或將資料標籤為&#x200B;**[!UICONTROL 沒有值]**。

Customer Journey Analytics不會為遺失或空白陣列建立預留位置或空白列。 因此，您可以正確設定&#x200B;**[!UICONTROL 無值]**&#x200B;資料檢視設定，但在專案層級報表中仍看不到&#x200B;**[!UICONTROL 無值]**&#x200B;專案，例如SKU劃分。 缺少專案是資料粒度差異，而非設定問題。 **[!UICONTROL 沒有值]**&#x200B;設定控制現有資料列的顯示方式，空陣列表示該資料粒度層級不存在任何資料列。

當專案層級&#x200B;**[!UICONTROL 沒有值]**&#x200B;計數看起來低於預期時，在假設您的資料檢視設定需要調整之前，請檢查遺失的陣列資料是否說明了間隙。

## 最佳做法

一旦識別出有問題的&#x200B;**[!UICONTROL 無值]**&#x200B;執行個體，您將需要開發及實作補救策略。 此補救可透過兩種方式完成：

* 調整資料檢視元件&#x200B;**[!UICONTROL 無值]**&#x200B;選項設定，或
* 修正資料收集來源的問題。

請謹慎選擇您的方法，因為每種路徑對快速修正和長期資料品質都有不同的影響。 您的實作遵循有條不紊的程式，在修正目前問題的同時避免未來的問題。 成功與否取決於規劃、系統化執行和持續監控。

以下是修正計畫的主要策略考量事項：

### 避免無值問題

* 在處理資料之前先驗證資料
* 適時設定預設維度值（人員ID永不設定）
* 記錄預期&#x200B;**[!UICONTROL 沒有值]**&#x200B;的情況
* 在資料收集點新增品質檢查
* 監控資料模型的合規性
* 資料收集期間記錄錯誤
* 為您的實作新增自動化測試
* 要求值一律存在的結構描述欄位

### 驗證報表中沒有值

* 建立區段來隔離&#x200B;**[!UICONTROL 沒有值]**&#x200B;模式
* 建立可監控&#x200B;**[!UICONTROL 無值]**&#x200B;隨時間變化趨勢的QA儀表板
* 設定追蹤&#x200B;**[!UICONTROL 無值]**&#x200B;磁碟區變更的警示
* 產生自動化報表，強調重大模式變更
* 跨相關維度的互動參照&#x200B;**[!UICONTROL 沒有值]**&#x200B;模式
* 定期稽核資料檢視設定
* 維護變更您的&#x200B;**[!UICONTROL 無值]**&#x200B;策略的變更記錄
* 為利害關係人建立標準作業程式和檔案範本

## 結論

並非每個&#x200B;**[!UICONTROL 沒有值]**&#x200B;專案都表示有問題。 正確解譯&#x200B;**[!UICONTROL 沒有值]**&#x200B;需要瞭解您的Adobe Experience Platform和Customer Journey Analytics資料架構，以及使用者在您的產品或網站中的移動方式。 不要嘗試消除&#x200B;**[!UICONTROL 沒有值]**&#x200B;的每個執行個體，而是建立有記錄的組織範圍規則，將預期的&#x200B;**[!UICONTROL 沒有值]**&#x200B;與有問題的&#x200B;**[!UICONTROL 沒有值]**&#x200B;區分開來，並以您自己的使用者歷程和業務案例為依據。

>[!MORELIKETHIS]
>
>[在Adobe Customer Journey Analytics中處理&#x200B;**[!UICONTROL 沒有值]**&#x200B;的完整行動手冊](https://experienceleaguecommunities.adobe.com/adobe-analytics-3/the-complete-playbook-for-handling-no-value-in-adobe-cja-12769)
