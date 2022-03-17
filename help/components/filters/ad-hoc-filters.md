---
description: 在 Analysis Workspace 中使用臨時篩選。
title: 臨時專案篩選
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 5743bece216431fecc073528ca2509cd2ed72f2b
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 54%

---

# 臨時專案篩選

即席項目篩選器允許您直接將任何元件拖放到面板拖放區域以建立篩選器。 過濾器變成 [項目級篩選器](https://experienceleague.adobe.com/docs/analytics-platform/analysis-workspace/components/filters/quick-filters.html?#what-are-project-only-segments) 本地到當前項目。

以下是有關建立臨時專案篩選的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. 將任何元件類型（維、維項、事件、度量、段、段模板、日期範圍）拖放到面板頂部的篩選器拖放區域。 元件類型將自動轉換為即席篩選器或 [快速篩選器](/help/components/filters/quick-filters.md) 。

   以下是如何為 Twitter 反向連結網域建立篩選的範例：

   ![](assets/ad-hoc1.png)

   您的面板會自動套用此篩選，而且您可以即刻看到結果。

1. 可以向面板添加無限數量的篩選器。
1. 如果您決定要儲存此篩選，請參閱以下章節。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至篩選器拖放區域：計算量度以及無法建立篩選條件的維度/量度。
* 為建立完整的維度和事件，Analysis Workspace 建立了「存在」點擊篩選條件。範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如將「未指定」或「無」拖放至篩選拖放區，就會自動轉換成「不存在」篩選，以便系統可正確處理篩選。

## 儲存臨時專案篩選 {#ad-hoc-save}

您可選擇完成以下步驟以儲存這些篩選：

1. 在拖放區域中的篩選條件上暫留，並按一下「i」圖示。
1. 按一下編輯鉛筆可轉到「篩選器生成器」。
1. 檢查 **[!UICONTROL 使所有項目都可用並添加到元件清單]**。
1. 按一下 **[!UICONTROL 保存]**。

保存後，過濾器將在左側導軌元件清單中可用，並可與「過濾器管理器」中的其他用戶共用。

