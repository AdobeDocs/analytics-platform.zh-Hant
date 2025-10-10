---
title: 時間軸分析
description: 觀察一段時間內的使用者層級工作階段事件以找到體驗模式。
feature: Adobe Product Analytics, Guided Analysis
keywords: 產品分析
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---

# [!UICONTROL 時間軸]分析 {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="時間軸"
>abstract="觀察一段時間內的使用者層級工作階段事件。"

<!-- markdownlint-enable MD034 -->

![時間軸](/help/assets/icons/Timeline.svg) **[!UICONTROL 時間軸]**&#x200B;分析可讓您觀察一段時間內使用者層級工作階段事件，以找到體驗模式並講述更好的使用者故事。左側邊欄可讓您按屬性值和區段篩選資料流。右側邊欄可讓您從符合篩選條件的隨機使用者清單中選取。中心區域會依工作階段顯示所選使用者的資料流，包括時間戳記、屬性值和持續時間。特定工作階段中最後一個事件不適用持續時間。


>[!NOTE]
>
>[!UICONTROL 時間軸]分析要求[資料檢視](/help/data-views/component-reference.md#optional)中有&#x200B;**[!UICONTROL 個人 ID]** 標準元件。在資料檢視中包含個人 ID 是由您的 Customer Journey Analytics 管理員管理，這樣可讓您的組織能夠完全控制可存取這些資料者的隱私權。
>><br/>如果資料檢視沒有[!UICONTROL 個人 ID] 元件新增，以下訊息即會顯示：
>
>* **管理員**： *此分析需要有 PersonID 屬性。請將個人 ID 新增至資料檢視。*
>* **非管理員**：*此分析需要有 PersonID 屬性。請與您的 Customer Journey Analytics 管理員合作，將個人 ID 新增至資料檢視。*

>[!VIDEO](https://video.tv.adobe.com/v/3435778/?quality=12&learn=on&captions=chi_hant)



## 使用案例

該分析的使用案例包括：

* **摩擦探索**：如果您在[漏斗分析](funnel.md)中發現急劇下降，您可以建立這些使用者的客戶細分，並在本次分析中應用該細分來調查潛在原因。
* **錯誤行為**：如果使用者遇到產品錯誤，您可以探索使用者在看到該錯誤之前或之後做了什麼。
* **資料收集驗證**：資料管理員可以根據自己的個人 ID 對此分析進行篩選，以驗證他們組織的實施是否如預期進行。

## 介面

請參閱「[介面](../overview.md#interface)」，了解引導式分析介面概觀。以下是針對此分析的設定：

### 查詢邊欄

查詢邊欄允許您設定以下元件：

* **[!UICONTROL 維度]**：您想要查看的資料流值維度。中心資料流會顯示所選維度的值。您也可以套用篩選器來縮小資料流的範圍，即可取得更相關的資料。篩選器的有效運算子包括[!UICONTROL 等於]、[!UICONTROL 不等於]、[!UICONTROL 開頭為]、[!UICONTROL 結尾為]、[!UICONTROL 包含]、[!UICONTROL 不包含]、[!UICONTROL 存在]和[!UICONTROL 不存在]。
* **[!UICONTROL 區段]**：您要分析的區段。選取的區段會篩選您的資料，以便只著重符合您區段條件的個人。如果您想將分析範圍縮小到特定的個人 ID，您可以在右側面板中篩選該個人 ID。此分析支援一個區段。

### 圖表設定

[!UICONTROL 時間軸]分析提供以下圖表設定；此設定可在圖表上方的選單中調整：

* **[!UICONTROL 顯示為]**：顯示所需的屬性值。
   * [!UICONTROL 顯示全部]：顯示工作階段中所有屬性值。
   * [!UICONTROL 醒目顯示]：以視覺效果醒目顯示工作階段中與查詢篩選器匹配的屬性值。
   * [!UICONTROL 僅檢視]：僅會顯示工作階段中與查詢篩選器相符的屬性值。

### 日期範圍

您想要分析的日期範圍。此設定有兩個元件：

* **[!UICONTROL 間隔]**：您想要查看趨勢資料所用的日期細度。此設定不會影響時間軸等非趨勢分析。
* **[!UICONTROL 日期]**：開始和結束日期。為方便您使用，我們提供滾動日期範圍預設和先前儲存的自訂範圍，或者您可以使用行事曆選擇器來選擇固定的日期範圍。


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
