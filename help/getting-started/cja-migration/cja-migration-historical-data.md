---
title: 移轉至Customer Journey Analytics時保留歷史資料
description: 瞭解在移轉至Customer Journey Analytics時如何保留歷史資料
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 0%

---

# 步驟5：移轉至Customer Journey Analytics時保留歷史資料

+++本頁資訊是較大移轉程式的一部分。 展開本區段，瞭解此資訊在移轉程式中的適用位置。 </br></br>您必須先完成所有先前的移轉步驟，才能繼續本頁上的資訊。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟5，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| **步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)** | 有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。 |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [規劃資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| <span class="preview">**步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)**</span> | <span class="preview">大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。</span> |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

選擇下列其中一個選項，以便在從Adobe Analytics移至Customer Journey Analytics時保留歷史資料：

## 利用Analytics來源聯結器

您可以利用 [Analytics來源聯結器](/help/data-ingestion/analytics.md) 以保留歷史資料。 無論您選擇何種移轉方法（即使您使用Web SDK移轉），都可使用Analytics來源聯結器保留Adobe Analytics環境中的歷史資料。

您可以使用Analytics來源聯結器透過下列方式保留歷史資料：

* 將歷史資料匯入專屬的位置，與您目前的資料分開。

* 以可讓您將歷史資料連結至新資料的方式對應歷史資料。 <!-- Possible? Explain -->

## 維護您現有的Adobe Analytics實作

您可以針對特定時間範圍（例如1年）維護現有的Adobe Analytics實作與新的Customer Journey Analytics實作。 選擇此選項時，您必須在Customer Journey Analytics中有足夠的資料後，計畫將Adobe Analytics實作解除委任。

請聯絡您的Adobe客戶代表，以決定此選項的定價。

## 接下來，計畫使用者上線

[規劃使用者上線到Customer Journey Analytics](/help/getting-started/cja-migration/cja-migration-onboarding.md). 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。
