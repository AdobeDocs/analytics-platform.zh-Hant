---
title: 元件概觀
description: 了解 CJA 提供哪些元件，以及如何在報表中使用這些元件。
translation-type: tm+mt
source-git-commit: c1699c4319b3b840d8420f3ffa1a4bd1c1d9a4d4
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 57%

---


# 元件概觀

元件功能可用於 Customer Journey Analytics 中報表或補充報表功能。您可以使用下列步驟管理這些元件：

1. 使用您的 Adobe ID 憑證登入 [analytics.adobe.com](https://analytics.adobe.com)。
2. 導覽至頁首功能表中的[!UICONTROL 「元件] > [!UICONTROL  元件」]。

您可以管理下列元件：

* [**篩選器**](filters/filters-overview.md)：排除部分資料，以聚焦於常見的維度項目
* [**計算量度**](calc-metrics/calc-metr-overview.md)：將量度和公式作為新元件用於報告中
* [**日期範圍**](date-ranges/overview.md)：自訂和調整 Analysis Workspace 提供的日期範圍
* [**專案**](/help/analysis-workspace/home.md)：在 Analysis Workspace 中組織和維護專案

## Analysis Workspace 元件

Analysis Workspace 中的元件包含量度、維度、區段及時間粒度，您可將它們拖放至專案上。您建立的自訂元件會加入至這些面板，例如自訂日期範圍。

若要存取「元件」面板，請按一下左側邊欄中的&#x200B;**[!UICONTROL 「元件」]**&#x200B;圖示。您可以利用左欄圖示或[快捷鍵](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，在各面板 (空白面板、[自由表格面板](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)、[快速深入分析面板](/help/analysis-workspace/c-panels/quickinsight.md)或[歸因 IQ](/help/analysis-workspace/c-panels/attribution.md) 面板)、[視覺化效果](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)和元件之間來回切換。

![](assets/components.png)

請參閱[建立專案](/help/analysis-workspace/home.md)，以了解在專案中使用元件的詳細資訊。

## 元件動作

您可以透過多種方式管理元件 (個別或選取多個元件)。以滑鼠右鍵按一下元件，或按一下元件清單頂端的&#x200B;**[!UICONTROL 「動作」]**。

>[!NOTE]
>
>此類動作不適用於「時間」元件。

| 元件動作 | 說明 |
|--- |--- |
| 標記 | 以套用標記的方式組織或管理元件。接著元件會在相關元件管理員中顯示，例如「分析 > 元件 > 區段」或「分析 > 元件 > 專案」 |
| 我的最愛 | 新增元件至我的最愛清單。接著元件會在相關元件管理員中顯示，例如「分析 > 元件 > 區段」或「分析 > 元件 > 專案」。 |
| 核准 | 核准元件使其成為正式項目。接著元件會在相關元件管理員中顯示，例如「分析 > 元件 > 區段」或「分析 > 元件 > 專案」 |
| 共用 | 僅套用至區段。 |
| 刪除 | 僅套用至區段。 |

觀看建立量度、區段和日期的說明影片：

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## 元件存取權限

管理員可以(透過[Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en#manage-users-and-products))組織哪些元件會對報告中的使用者開放。 下表顯示這些元件存取權限的行為：

| 組織類型 | 管理員可以看到 | 非管理員專案擁有者（或編輯角色）可以看到 | 非管理員重複角色 |
| --- | --- | --- | --- |
| **從資料檢視中「隱藏」元件** | 所有資料檢視元件都可用於報告（隱藏元件需要按一下「全部顯示」） | 無法用於報告 | 無法用於報告 |
| **從資料檢視新增或移除的元件** | 僅新增至資料檢視的元件（隱藏或未隱藏）。 管理員無法報告資料檢視未定義的欄位或元件。 | 只有新增至資料檢視的元件，或使用者擁有或共用的元件。 隱藏元件不可用（例如VRS組織）。 | 只有新增至DV的元件不會隱藏，而且已包含在專案組織中。 |
| **專案中的組織元件** | 所有資料檢視元件都可用於報告（隱藏元件需要按一下「全部顯示」） | 所有非隱藏的資料檢視元件（需要按一下「全部顯示」） | 僅限策劃的元件，加上使用者擁有或共用的任何元件 |
| **使用含隱藏元件的資料檢視來組織專案** | 所有可用於報告的資料元件（隱藏和未組織的元件需要按一下「全部顯示」） | 所有非組織的專案元件、所有非隱藏的資料檢視元件，以及使用者擁有或共用的任何元件 | 僅限策劃的元件，加上使用者擁有或共用的任何元件 |

