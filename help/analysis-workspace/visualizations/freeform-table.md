---
title: 自由表格
description: 了解自由表格和自由表格產生器
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 95%

---


# 自由表格

>[!NOTE]
>
>您正在檢視客戶歷程分析中分析工作區的檔案。 其功能集與傳統Adobe Analytics中 [的「分析工作區」略有不同](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html)。 [更多詳情...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中，自由表格不僅僅是資料表格，也是互動式視覺效果。您可以將[元件](/help/components/overview.md)組合拖放至行和欄，建立自訂表格供分析之用。放置每個元件時，表格會立即更新，以便您快速分析。

您可以透過不同方式自訂表格：

* **行**
   * 分頁之前，每個維度列最多可顯示 400 列。您可以調整專案的[檢視密度](/help/analysis-workspace/build-workspace-project/view-density.md)，在單一畫面中放入更多列。
   * 列可以依其他元件劃分。若要一次劃分許多列，只需選取多列，然後將下一個元件拖曳至選取的列上即可。進一步了解[劃分](/help/components/dimensions/t-breakdown-fa.md)。
   * 您可以[篩選](/help/analysis-workspace/build-workspace-project/pagination-filtering-sorting.md)列，以顯示縮減的項目集。[「列設定」](/help/analysis-workspace/build-workspace-project/column-row-settings/table-settings.md)底下提供其他設定。

* **欄**
   * 元件可堆疊在欄內，以建立分段量度、跨標籤分析等等。
   * [欄設定](/help/analysis-workspace/build-workspace-project/column-row-settings/column-settings.md)底下可調整每個欄的檢視方式。
   * 您可善用[滑鼠右鍵功能表](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html)執行數個動作。無論是在表格標頭、列或欄上按一下，功能表都會提供不同動作。

## 自由表格產生器

如果您偏好先將數個元件新增至表格，然後再轉譯資料，則可啟用「自由表格產生器」。啟用產生器後，許多維度、劃分、量度和區段都可直接拖放使用，方便建立表格以供回答更複雜的問題。資料不會即時更新，但當您按一下&#x200B;**[!UICONTROL 「建立」]**，資料就會更新。

當有複雜的問題需要詢問以收集資料，而且您知道要建立哪種表格才方便詢問您的問題時，表格產生器便會是省時的絕佳選項。表格產生器的其他優點包括：

* 以您所需的格式排列表格，不需等待每個動作轉譯。
* 快速執行最多 4 個劃分層級。
* 定義每個表格列和維度欄的「列」和「劃分」設定。
* 根據預設，系統會對表格的每個層級進行&#x200B;**[!UICONTROL 「依位置劃分」]** (在傳統的「自由表格」中，預設值為&#x200B;]**「依項目劃分」**[!UICONTROL )。
* 以手動方式排序表格中的靜態列。例如，如果要以特定順序顯示量度列，這就會是好方法。
* 轉譯實際資料之前，先預覽表格的格式。

若需了解「自由表格產生器」的實際運作方式，請前往[這裡](https://youtu.be/GUMWiJAmMGI)觀看。

## 匯出自由表格資料

下列幾種方式都能從 Analysis Workspace 複製自由表格中的資料：

* 以滑鼠右鍵按一下表格標頭，然後選取&#x200B;**[!UICONTROL 「複製至剪貼簿」]**。這能匯出 (可檢視的) 完整表格。
* 反白顯示表格中的特定儲存格，按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL 「複製至剪貼簿」]**，或使用 Ctrl + C 快捷鍵。
* **[!UICONTROL 「專案 > 下載 CSV」]**。這會將專案中所有可見的表格，以 CSV 格式匯出。
