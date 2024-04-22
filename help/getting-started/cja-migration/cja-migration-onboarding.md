---
title: 移轉至Customer Journey Analytics時規劃使用者上線
description: 移轉至Customer Journey Analytics時規劃使用者上線
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# 步驟6：在移轉至Customer Journey Analytics時規劃使用者上線

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟6，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| <span class="preview">**步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。</span> |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

Customer Journey Analytics和Adobe Analytics之間有一些使用者需要注意的關鍵差異。

就像在Adobe Analytics中一樣，Analysis Workspace是Customer Journey Analytics中主要面向使用者的工具。 不過，在Customer Journey Analytics中使用Analysis Workspace時有一些使用者需注意的主要差異。

您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。

如需Adobe Analytics和Customer Journey Analytics之間部分主要差異的詳細資訊，請參閱 [Adobe Analytics使用者使用指南](/help/getting-started/aa-to-cja-user.md).

## 接下來，連線報表API使用情況

Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md) 從Adobe Analytics報表API前往Customer Journey Analytics報表API。
