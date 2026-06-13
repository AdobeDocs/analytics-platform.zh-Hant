---
title: 從Google Analytics 4轉換成Customer Journey Analytics
description: 以熟悉Google Analytics 4的分析師為對象，說明在Customer Journey Analytics中取得報表的重要概念。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# 從Google Analytics 4轉換成Customer Journey Analytics

本指南可協助熟悉Google Analytics 4的分析師瞭解Adobe Customer Journey Analytics中的相同概念和報表。 如果您負責技術實作而非報告，請參閱[從協力廠商分析解決方案升級至Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md)，以取得有關Web SDK設定和資料擷取的指引。 如果貴組織仍需將現有Google Analytics資料移轉至Adobe Experience Platform，請參閱[從Google Analytics移轉資料](/help/use-cases/third-party/ga/overview.md)。

## GA4與Customer Journey Analytics之間的主要差異

GA4和Customer Journey Analytics具有相同的基本理念：每個使用者互動都是一個事件，而分析是在空白畫布工具中執行，您可在此拖放維度和量度以建立自訂檢視。 如果您熟悉GA4 Explore，Analysis Workspace很可能就能立即辨識。

最顯著的差異在於Customer Journey Analytics超越了GA4的領域：

* **跨管道資料**： Customer Journey Analytics可在相同分析中結合網頁分析與離線資料來源（例如客服中心記錄、CRM活動、忠誠度計畫或電子郵件參與）。 GA4僅限於透過其SDK收集的數位互動。
* **報表時間處理**： Customer Journey Analytics會在查詢時（而非收集時）套用歸因模型、工作階段定義和區段規則等邏輯。 對工作階段定義或歸因模型所做的變更會回溯套用至所有歷史資料，而不會重新處理。
* **彈性的工作階段定義**：工作階段逾時期間、工作階段開始事件和工作階段結束事件都可以根據Customer Journey Analytics中的資料檢視設定。 GA4的工作階段逾時可調整（預設為30分鐘，最長7小時55分鐘），但會套用屬性範圍，且其工作階段開始和工作階段結束行為會固定。
* **身分拼接**： Customer Journey Analytics的拼接功能可將跨裝置和跨頻道互動連結到同一個人，產生比GA4的混合身分模型更準確的人數。

## 帳戶和資料結構

GA4和Customer Journey Analytics在平台層級以不同方式組織資料。

| GA4 | Customer Journey Analytics |
|---|---|
| Google帳戶 | Adobe IMS組織 |
| 屬性 | 連線+資料檢視 |
| 資料流 | Platform中的[!UICONTROL 事件資料集] |
| 資料篩選器 | 資料檢視元件篩選器 |
| 子屬性 | 已套用篩選器的個別資料檢視 |
| 彙總屬性 | 結合多個資料集的連線 |

最重要的結構差異在於GA4屬性會以單一物件處理資料佈線和報表。 Customer Journey Analytics將這些概念分成兩個不同的層：

* **連線**&#x200B;會將一或多個Adobe Experience Platform資料集連結至Customer Journey Analytics。 此步驟會以針對報表最佳化的格式將資料內嵌至Customer Journey Analytics。
* **資料檢視**&#x200B;建置在連線上，並定義哪些維度、量度和設定可用於報告。 這是報表設定層。

在Customer Journey Analytics中分析資料之前，兩者都必須存在。 Customer Journey Analytics中沒有報表套裝。

## Analysis Workspace快速入門

GA4 Explore和Analysis Workspace都是空白畫布拖放分析工具。 互動模式相同，術語稍有不同。

| GA4探索 | Analysis Workspace |
|---|---|
| 探索畫布 | 面板 |
| 圖表或視覺效果型別 | 視覺效果 |
| 維度 | 維度 |
| 量度 | 量度 |
| 區段或篩選 | 區段 |
| 事件計數 | [!UICONTROL 事件] |
| 使用者 | [!UICONTROL 人員] |
| 工作階段 | [!UICONTROL 工作階段] |

>[!TIP]
>
>GA4區段容器命名為「使用者」、「工作階段」和「事件」。 在Customer Journey Analytics中，對等容器為&#x200B;**[!UICONTROL Person]**、**[!UICONTROL 工作階段]**&#x200B;和&#x200B;**[!UICONTROL Event]**。 範圍邏輯相同。

>[!MORELIKETHIS]
>
>* [從Google Analytics移轉資料](/help/use-cases/third-party/ga/overview.md)
