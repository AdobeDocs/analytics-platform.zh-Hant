---
title: 建立篩選器
description: 了解建立篩選器的使用者介面。
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---

# 建立篩選器

篩選器產生器提供的畫布可拖放量度、維度、篩選器和事件，以便根據容器階層邏輯、規則和運算子來篩選訪客。這個整合式開發工具可讓您建立並儲存簡單或複雜的篩選器，用於識別跨造訪及頁面點擊的訪客屬性和動作。

您可以將任何元件類型 (維度、維度項目、事件、量度、篩選器、篩選器範本、日期範圍) 拖曳至面板頂端篩選器的拖放區域，建立即時篩選機制。

元件類型會自動轉換成篩選條件。或者，您也可以按一下&#x200B;**[!UICONTROL 「新增篩選條件」]**&#x200B;拖放方塊中的「+」標誌。

請記住：

* 下列元件類型&#x200B;**無法**&#x200B;拖曳至篩選器拖放區域：計算量度以及無法建立篩選條件的維度/量度。
* 為建立完整的維度和事件，Analysis Workspace 建立了「存在」點擊篩選條件。例子：「點撃 eVar1 存在的位置」或「點撃 event1 存在的位置」。
* 如將「未指定」或「無」拖曳至篩選器拖放區，該項目會自動轉換成「不存在」篩選條件，以利系統正確處理。

![](assets/segment-dropzone.png)

>[!NOTE]
>
>此為專案內部專用的篩選條件建立方式。

您可以遵循下列步驟，將這些篩選條件設為公用 (全域)：

1. 在拖放區域中的篩選條件上暫留，並按一下「i」圖示。
1. 在顯示的資訊面板中，按一下&#x200B;**[!UICONTROL 「設為公用」]**。

   ![](assets/segment-info.png)

## 套用篩選條件的其他方法

另有幾個為專案套用篩選條件的方法：

| 動作 | 說明 |
| --- | --- |
| 從選取項目建立篩選條件 | 建立內嵌篩選條件。此篩選器僅套用至開啟的專案，不會儲存為 CJA 篩選器。<p> 1. 請選取您要哪些表格列成為篩選器的一部分。  2. 以滑鼠右鍵按一下選取項目。  3. 按一下&#x200B;*「從選取項目建立篩選條件」*。 |
| 「工作區 [!UICONTROL 元件] > [!UICONTROL 新增篩選器]」 | 顯示篩選條件產生器。 如需篩選功能的詳細資訊，請參閱[篩選條件產生器](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=zh-Hant)。 |
| 「共用 > 共用專案」或「共用 > 組織專案資料」 | 在[「組織與共用」](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hant#concept_4A9726927E7C44AFA260E2BB2721AFC6)中，您可以了解套用至專案的篩選條件可如何供收件者在共用分析中使用。 |
| 將篩選條件作為維度使用 | 請觀看下方的影片：在 Analysis Workspace 中使用篩選器作為維度 |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
