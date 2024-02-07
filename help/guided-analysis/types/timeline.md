---
title: 時間表檢視
description: 探索工作階段活動中的模式。
feature: Guided Analysis
keywords: 產品分析
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# [!UICONTROL 時間表] 檢視

此 **[!UICONTROL 時間表]** 檢視可讓您分析個別工作階段，以判斷行為模式。 右側邊欄可讓您選取要分析的人員ID。 中心區域會顯示該人員每個事件的時間、選取的屬性值及持續時間。

此分析需要您新增 **[!UICONTROL 人員ID]** 將標準元件移至 [資料檢視](/help/data-views/component-reference.md#optional). 如果您沒有 [!UICONTROL 人員ID] 元件新增至資料檢視時，會顯示下列訊息：

> 此分析需要PersonID屬性。請新增人員ID至資料檢視。

## 使用案例

此檢視型別的使用案例包括：

* **摩擦探索**：如果您在 [摩擦](friction.md) 檢視，您可以使用此檢視來調查掉落的可能原因。
* **錯誤行為**：如果使用者在產品中遇到錯誤，您可以探索使用者在看到該錯誤之前或之後做什麼。
* **資料收集驗證**：資料管理員可篩選此檢視以隔離自己。 此檢視提供明確的方法，可確保貴組織的實作如預期般運作。

## 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 屬性]**：您要檢視其值的屬性。 中心的工作階段分析會顯示此處選取之屬性的值。 您也可以依選取的屬性篩選資料。 篩選的有效運運算元包括 [!UICONTROL 等於]， [!UICONTROL 不等於]， [!UICONTROL 開頭為]， [!UICONTROL 結尾為]， [!UICONTROL 包含]， [!UICONTROL 不包含]， [!UICONTROL 存在]、和 [!UICONTROL 不存在].
* **[!UICONTROL 區段]**：您要測量的區段。 所選的區段會篩選您的資料，以僅聚焦於符合您區段條件的個人。 此檢視支援一個區段。

## 圖表設定

此 [!UICONTROL 時間表] 檢視提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 顯示為]**：顯示所需的屬性值。
   * [!UICONTROL 全部顯示]
   * [!UICONTROL 反白顯示]
   * [!UICONTROL 僅供檢視]

## 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要用來檢視趨勢資料的日期詳細程度。 此設定不會影響非趨勢檢視，例如時間軸。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。
