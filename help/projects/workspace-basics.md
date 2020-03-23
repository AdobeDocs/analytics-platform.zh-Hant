---
title: 工作區基本資訊
description: 說明如何在工作區中提取基本報表
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# 工作區基本資訊

如果您還不熟悉「工作區」工具，請以下是一些入門秘訣。

工作區是Adobe的主要工具，可協助您的組織做出可操作的資料決策。 自由表格這項最常用的視覺效果，可讓您運用維度、量度、區段和日期範圍輕鬆建立自訂報表。

## 在 Workspace 中提取基本排名報表

排名報表會顯示每個維度值的匯總完整數據檢視，從最大的數值開始依序顯示。這類報表類型有助於查看您網站的哪些元件成效最佳，例如哪些頁面獲得最多流量或哪些產品銷售最多。

1. 請確定您已登入 [analytics.adobe.com](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. 按一下 **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 左側應會顯示含有維度、量度、區段和日期範圍的清單。找到「頁面」維度 (顯示為橙色)，將該維度拖曳至畫布上顯示「將維度放置在此處」的位置。
1. 您會看到顯示本月最上層頁面的報表。Analysis Workspace 會自動在報表中填入[「發生次數」](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html)量度。
1. 找出「造訪次數」量度 (顯示為綠色)，並將此量度拖曳到「發生次數」量度標頭&#x200B;**中**&#x200B;或&#x200B;**旁邊** (請避免放到量度上方)。如果將「造訪次數」量度拖曳到「發生次數」上，前者就會在報表中取代後者。如果將「造訪次數」量度拖曳到「發生次數」旁，兩個量度會並排顯示。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## 在 Workspace 中提取基本趨勢報表

趨勢報表會依據所選日期範圍顯示一段時間以來的量度檢視。這類報表有助於識別一段期間內的趨勢，且可用於評估業務決策的成功與否。舉例來說，您可以檢視一段期間內的頁面檢視趨勢報表，評估網站的重新設計是否造成流量的增減。

1. 請確定您已登入 [analytics.adobe.com](https://analytics.adobe.com)。
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. 按一下 **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. 左側應會顯示含有維度、量度、區段和日期範圍的清單。Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. 請避免放置在維度專用的空間 (至少在本次練習中不要這麼做)。
1. 請注意，如果報表套裝中含有資料，您應該會看到目前月份的基本頁面檢視趨勢報表。Analysis Workspace 會自動加入「天」日期範圍，以便您查看當月的頁面檢視趨勢。
1. 在左側日期範圍元件清單中找到「週」日期範圍 (顯示為紫色)。按一下日期範圍標題以展開並查看所有日期範圍元件，或使用搜尋列搜尋元件。
1. 將「週」日期範圍拖曳至畫布上的「天」日期範圍標頭上方，藉此取代「天」。
1. 請注意，此時趨勢報表會按週彙總資料，而非按天。
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## 透過工具進行實驗

 Workspace 是報表工具，對於資料收集沒有影響。任意將元件拖曳到專案中查看何者有效，並不會造成任何不良影響。您可以將不同的維度與量度組合拖曳到 Workspace 專案中，了解哪一種組合適合自己。

如果您意外將無效的元件拖曳到 Workspace 專案中，或者想要返回之前的步驟，請按下 ctrl+Z (Windows) 或 cmd+Z (Mac)，藉此還原上一次執行的動作。You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## 疑難排解

### 我將量度拖曳到專案後，系統顯示「資料無效」。

資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。

### 我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。

如果您成功建立了工作區報表，但當中沒有任何資料，建議您檢查以下幾個事項：

* 再次檢查報表套裝，確認報表中已填入資料。
* 如果報表中有使用區段，可能是區段標準與任何資料皆不符。請嘗試移除區段或調整區段定義。
* 檢查右上方的日期範圍，確認已設為您需要的值。
* 導覽至您的網站，使用除錯程式來驗證系統確實開始收集所需資料。

## 其他資源

請注意，以下資源可能是指在傳統Adobe Analytics產品中使用工作區，而非在客戶歷程分析中。

* 部落格貼文：
   * [使用更聰明的分析強化組織](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/)
   * [分析工作區：秘密醬汁越來越美味](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [為何應使用 Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/)
   * [使用 Analysis Workspace 充分發揮生產力的 5 個祕訣](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/)

## 後續步驟

如要加深對 Workspace 的理解，您有許多方向可走。以下是 Adobe 建議的幾個基本方向：

### 如果您是想要擴充 Workspace 使用方式相關知識的使用者

* [Workspace UI 的詳細資料](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html)：既然您已建立基本報表，接下來請進一步熟悉介面的其餘部分。
* [Workspace 的視覺效果](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)：自由表格僅僅是 Analysis Workspace 資料視覺效果的其中一種類型。請進一步了解如何使用其他視覺效果，例如折線圖、長條圖和地理分佈圖。
* [Workspace 的維度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html)：進一步了解各項維度，以及如何在排名報表之外使用這些維度。
* [Workspace 的量度](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html)：進一步了解各項量度，以及如何在自由表格的其他部分使用這些量度。
* [區段簡介](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html)：了解各項區段，並使用區段提取基本報表。
* [Workspace 的日期範圍](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html)：了解相對日期和滾動日期，並在 Workspace 專案中使用這些設定。
* [共用 Workspace 中的專案：向同事展示您建立的出色 Workspace 專案。](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### 如果您是想要改善組織工作區品質的分析師和管理員

* [Analysis Workspace 權限](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)：透過 Adobe Admin Console 在 Workspace 中指派使用者權限。
* [Workspace 中的範本](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html)：建立範本，方便讓同事根據自己的需求量身打造專案空間。
* [Workspace 組織](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)：建立一項可用元件有限的專案，讓不熟悉工具的人更容易存取工作區。
