---
title: 時間表檢視
description: 觀察一段時間內的使用者層級工作階段事件，以尋找體驗模式。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: e9721eaf993175dd46e9d8edf9176d7c00308e8c
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# [!UICONTROL 時間表]檢視

**[!UICONTROL 時間表]**&#x200B;檢視可讓您觀察使用者層級的工作階段事件在一段時間內的變化，以尋找體驗模式並訴說更好的使用者故事。 左側邊欄可讓您依據屬性值和區段來篩選資料流。 右側欄可讓您從符合篩選條件的隨機使用者清單中選取。 中央區域會依工作階段顯示所選使用者的資料流，包含時間戳記、屬性值和持續時間。 持續時間不適用於指定工作階段中的最後一個事件。

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>時間軸檢視要求[資料檢視](/help/data-views/component-reference.md#optional)中必須有&#x200B;**[!UICONTROL 人員ID]**&#x200B;標準元件。 在資料檢視中加入人員ID是由Customer Journey Analytics管理員管理，讓您的組織能夠完全控制誰可以存取此資料的隱私權。

如果資料檢視未新增[!UICONTROL 人員ID]元件，則會顯示下列訊息：

* **管理員**： *此分析需要PersonID屬性。 請新增人員ID至資料檢視。*
* **非管理員**： *此分析需要PersonID屬性。 請與您的Customer Journey Analytics管理員合作，將人員ID新增至資料檢視。*

## 使用案例

此檢視型別的使用案例包括：

* **摩擦探索**：如果您在[摩擦](friction.md)檢視中發現陡降，您可以建立這些使用者的區段，並在此檢視中套用區段以調查可能的原因。
* **錯誤行為**：如果使用者遇到產品錯誤，您可以探索使用者在看到該錯誤之前或之後正在做什麼。
* **資料彙集驗證**：資料管理員可以篩選此檢視以取得他們自己的人員ID，以驗證其組織的實作是否如預期般運作。

## 查詢邊欄

查詢邊欄可讓您設定以下元件：

* **[!UICONTROL 屬性]**：您要檢視其串流值的屬性。 中央的資料流會顯示所選屬性的值。 您也可以套用篩選器，將資料流縮小至更相關的資料。 篩選器的有效運運算元包括[!UICONTROL 等於]、[!UICONTROL 不等於]、[!UICONTROL 開頭為]、[!UICONTROL 結尾為]、[!UICONTROL 包含]、[!UICONTROL 不包含]、[!UICONTROL 存在]以及[!UICONTROL 不存在]。
* **[!UICONTROL 區段]**：您要分析的區段。 所選的區段會篩選您的資料，以僅聚焦於符合您區段條件的個人。 如果您想要將檢視範圍縮小至特定人員ID，可以在這裡篩選為該人員ID。 此檢視支援一個區段。

## 圖表設定

[!UICONTROL 時間表]檢視提供下列圖表設定，可在圖表上方的功能表中調整：

* **[!UICONTROL 顯示為]**：顯示所需的屬性值。
   * [!UICONTROL 全部顯示]：顯示工作階段中的所有屬性值。
   * [!UICONTROL 醒目提示]：以視覺化方式醒目提示符合查詢篩選條件的工作階段中的屬性值。
   * [!UICONTROL 僅檢視]：只顯示符合查詢篩選條件的工作階段中的屬性值。

## 日期範圍

分析所需的日期範圍。 此設定包含兩個元件：

* **[!UICONTROL 間隔]**：您要依據檢視趨勢資料的日期詳細程度。 此設定不會影響非趨勢檢視，例如時間軸。
* **[!UICONTROL 日期]**：開始和結束日期。 您可方便使用滾動日期範圍預設集和先前儲存的自訂範圍，或使用日曆選擇器來選擇固定日期範圍。
