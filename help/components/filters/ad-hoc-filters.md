---
description: 在 Analysis Workspace 中使用臨時篩選。
title: 臨時專案篩選
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 17030d5ac3b488a6c628e6de7aab8b710e5c175a
workflow-type: ht
source-wordcount: '302'
ht-degree: 100%

---

# 臨時專案篩選

臨時專案篩選可讓您將任何元件直接拖放到面板放置區域中以建立篩選。 此篩選會成為目前專案的本機[專案層級篩選](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html)。

以下是有關建立臨時專案篩選的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 將任何元件類型 (維度、維度項目、事件、量度、區段、區段範本、日期範圍) 拖曳到面板頂端的篩選放置區域中。 元件類型如果相容的話，會自動轉換為臨時篩選或[快速篩選](/help/components/filters/quick-filters.md)。

   以下是如何為 Twitter 反向連結網域建立篩選的範例：

   ![](assets/ad-hoc1.png)

   您的面板會自動套用此篩選，而且您可以即刻看到結果。

1. 您可以對面板新增不限數量的篩選器。
1. 如果您決定要儲存此篩選，請參閱以下章節。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至篩選器拖放區域：計算量度以及無法建立篩選條件的維度/量度。
* 為建立完整的維度和事件，Analysis Workspace 建立了「存在」點擊篩選條件。範例：`Hit where eVar1 exists` 或 `Hit where event1 exists`。
* 如將「未指定」或「無」拖放至篩選拖放區，就會自動轉換成「不存在」篩選，以便系統可正確處理篩選。

## 儲存臨時專案篩選 {#ad-hoc-save}

您可選擇完成以下步驟以儲存這些篩選：

1. 在拖放區域中的篩選條件上暫留，並按一下「i」圖示。
1. 按一下編輯鉛筆，即可前往篩選產生器。
1. 勾選&#x200B;**[!UICONTROL 「設為可用於所有專案，並新增至您的元件清單」]**。
1. 按一下&#x200B;**[!UICONTROL 儲存]**。

儲存後，即可在左側欄元件清單中取得該篩選器，並可和篩選管理員的其他使用者共用。

