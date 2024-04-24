---
title: 移轉至Customer Journey Analytics時將資料對應至XDM結構描述
description: 瞭解在移轉至Customer Journey Analytics時如何將資料對應至XDM結構描述
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 86ce60cf-b3c7-43b5-aa18-9e16fa942e54
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 0%

---

# 步驟4：移轉至Customer Journey Analytics時將資料對應至XDM結構描述

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟4，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉路徑](/help/getting-started/cja-migration/cja-migration-path.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| <span class="preview">**步驟3： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分移轉路徑都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p></span> |
| **步驟4： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的移轉路徑而有所不同。 |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

[XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分移轉路徑都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p>

並非所有移轉路徑都需要您將您的Adobe Analytics資料對應到XDM結構描述。 下表顯示哪些實作方法需要XDM結構描述對應：


| 移轉路徑 | 需要XDM對應？ | 詳細資訊 |
|---------|----------|---------|
| **Experience Platform Web SDK的新實作**<p>基本步驟為：</p><ol><li>為您的組織建立XDM結構描述</li><li>實作Web SDK</li><li>傳送資料至Platform</li></ol> | 否 | 不需要對應，因為您已經 [設定新的XDM結構描述](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 做為新實作的一部分。 |
| **移轉您的Adobe Analytics實作以使用Web SDK**<p>基本步驟為：</p><ol><li>將您現有的Adobe Analytics實作專案移至Web SDK，並驗證那裡的所有專案運作正常。</li><li>儘可能為您的組織建立XDM結構描述。</li><li>使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。</li><li>傳送資料至Platform</li></ol> | 是 | 與您的資料團隊合作，識別您組織適用於Customer Journey Analytics的理想結構描述設計，然後決定將如何將eVar和Prop對應到XDM。</br>[使用「資料準備」將資料物件中的所有欄位對應到您的XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **設定您現有的Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics**<p>基本步驟為：</p><ol><li>開始傳送資料給Customer Journey Analytics。<!-- What's involved here? Just point it at CJA? --></li><li>（選用）隨時為您的組織建立XDM結構描述。</li><li>使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。</li></ol> | 是 | 與您的資料團隊合作，識別您組織適用於Customer Journey Analytics的理想結構描述設計，然後決定將如何將eVar和Prop對應到XDM。</br>[使用「資料準備」將資料物件中的所有欄位對應到您的XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Analytics來源聯結器**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以開始以Customer Journey Analytics傳送資料至資料檢視。<p>這是將資料匯入Customer Journey Analytics的最簡單方法，但長遠而言是最不可行的方法。</p> | 否 | 不需要對應，因為Analytics來源聯結器會使用您現有的Adobe Analytics結構描述，而非XDM結構描述。 |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## 接著，將資料傳送至Adobe Experience Platform

使用上述資訊選擇移轉路徑後，瞭解如何 [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 依您選擇的移轉路徑而定。
