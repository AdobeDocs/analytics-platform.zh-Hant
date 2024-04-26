---
title: 選擇您的Customer Journey Analytics移轉路徑
description: 瞭解移轉至Customer Journey Analytics時可能採用的移轉路徑的優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 0%

---

# 步驟2：選擇您的移轉路徑

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋移轉的步驟2，如下表標示之處：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| <span class="preview">**步驟2：選擇移轉路徑**</span> | <span class="preview">有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。</span> |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的移轉路徑而有所不同。 |
| **步驟4： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟5： [執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在移轉程式中的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外的工作適用於從Adobe Analytics的移轉以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的帳戶處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱 [Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

在您決定移轉至Customer Journey Analytics後，必須決定組織的最佳移轉路徑。

您選擇從Adobe Analytics移轉至Customer Journey Analytics的路徑取決於下列因素：

* 您現有的Adobe Analytics實作

* 您的未來目標

使用此頁面上的資訊來判斷哪種Customer Journey Analytics移轉路徑最符合貴組織目前的實施作業和未來的目標。

若要判別組織的最佳移轉路徑，請依序閱讀下列章節：

1. 首先， [瞭解可用的移轉路徑](#understand-migration-methods).

1. 然後 [評估您可用的移轉路徑](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最後， [權衡每個移轉路徑的優缺點](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## 瞭解移轉路徑

從Adobe Analytics移轉至Customer Journey Analytics有多種移轉路徑。

一般而言，每個移轉路徑在執行移轉所需的工作量層級，以及移轉完成後所實現的長期可行性都不同。

下表列出每個移轉路徑、其工作量及其長期可行性：

| 移轉路徑 | 所需投入的精力 | 長期生存能力 |
|---------|----------|---------|
| **Experience Platform Web SDK的新實作**</br>&#x200B;雖然這從技術上講並非移轉，但您可以透過執行新的Customer Journey AnalyticsWeb SDK實作來開始使用Experience Platform。 這可讓您開始傳送資料給Adobe Experience PlatformEdge Network和Customer Journey Analytics。 <p>對於尚未使用Web SDK的組織，此移轉路徑可能是將資料Edge Network的最簡單方法，因為只需最少的步驟即可；但是，由於所有工作都是預先完成（例如建立XDM結構描述），因此初期所需的工作量會比較大。</p><p>基本步驟為：</p><ol><li>為您的組織建立XDM結構描述。</li><li>實作Web SDK。</li><li>傳送資料至Platform。</li></ol> | 高 | 高 |
| **移轉您的Adobe Analytics實作以使用Web SDK**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以將其移轉為使用Adobe Experience Platform Web SDK，開始將資料傳送至Edge Network和Adobe Analytics，然後再傳送至Customer Journey Analytics。<p>對於尚未使用Web SDK的組織來說，這是將資料匯入Edge Network最簡單且最順暢的方式；它需要更多步驟，但可提供從Adobe Analytics到Customer Journey Analytics的更有條理的轉變，並具有更具體的里程碑。</p><p>基本步驟為：</p><ol><li>將您現有的Adobe Analytics實作專案移至Web SDK，並驗證一切都在Adobe Analytics中正常運作。</li><li>儘可能為您的組織建立XDM結構描述。</li><li>使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。</li><li>傳送資料至Platform。</li></ol> | 稽核 | 高 |
| **設定您現有的Adobe Analytics Web SDK實作**</br>&#x200B;如果您的Adobe Analytics實作已使用Adobe Experience Platform Web SDK，您即可開始將資料輕鬆傳送至Customer Journey Analytics。<p>在將資料傳送至Customer Journey Analytics之前，請考慮根據您的組織的特定需求以及您使用的任何其他平台應用程式，更新您的Adobe Analytics結構。</p><p>基本步驟為：</p><ol><li>開始傳送資料給Customer Journey Analytics。<!-- What's involved here? Just point it at CJA? --></li><li>（選用）隨時為您的組織建立XDM結構描述。</li><li>（條件式）如果您已建立XDM結構描述，請使用資料流對應來將資料物件中的所有欄位對應到您的XDM結構描述。</li></ol> | 低 | 高 |
| **使用Analytics來源聯結器**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以開始以Customer Journey Analytics傳送資料至資料檢視。<p>這是將資料匯入Customer Journey Analytics的最簡單方法，但長遠而言是最不可行的方法。</p> | 低 | 低 |

{style="table-layout:auto"}

使用下列圖表來協助視覺化每個移轉路徑在投入程度及長期可行性方面所處的範圍：

![cja移轉路徑](assets/cja-migration-methods.png)

## 根據您目前的Adobe Analytics實作，評估可用的移轉路徑

並非所有移轉路徑都適用於各種型別的Adobe Analytics實施。

請利用下列資訊協助您瞭解哪個移轉路徑最適合您的組織。

如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| 現有的Adobe Analytics實作 | 可用的移轉路徑 |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics來源聯結器</li></ul> |
| Adobe Analytics 擴充功能 | <ul><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics來源聯結器</li></ul> |
| Web SDK | <ul><li>設定Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## 權衡您可用的移轉路徑的優缺點

特定移轉路徑的優缺點會因您現有的Adobe Analytics實作而異。

使用下列資訊來判斷適合您的移轉路徑之前，請先檢閱以下資訊： [瞭解移轉路徑](#understand-migration-methods) 如果您尚未這樣做。

### 針對使用的Adobe Analytics實施：AppMeasurement和Adobe Analytics擴充功能

以下是已使用AppMeasurement或Adobe Analytics擴充功能實作Adobe Analytics的組織可用的移轉路徑。 展開每個區段以檢視每個移轉路徑的優缺點。

#### 移轉路徑

+++Experience Platform Web SDK新實作

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供強大功能而打造 [即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud產品（AJO、RTCDP等）之間整合Adobe Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul></li><li>**經得起未來考驗**：日後實施更新更輕鬆。</li></ul> | <ul><li>**需要從頭開始的新實作**：從頭開始進行新實作的需求代表下列缺點： </li><ul><li>**耗時**：這是最耗時、也最耗力的移轉路徑，因為您必須重新開始新的實作。</li><li>**必須在XDM中重新建立完整結構描述**：您必須在XDM中重新建立完整結構描述，才能開始實作Web SDK。</li><li>**必須重新建立規則和資料元素**：您必須從Adobe Analytics實作重新建立任何規則條件和資料元素，才能開始實作Web SDK。</li></ul></ul> |

{style="table-layout:auto"}

+++

+++將Adobe Analytics移轉至Experience PlatformWeb SDK

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供強大功能而打造 [即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud產品（AJO、RTCDP等）之間整合Adobe Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**使用您現有的實施**：雖然此方法需要一些實作變更，但不需要從頭開始全新的實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供彈性，以便日後為您的組織建立XDM結構描述**：您可以移轉現有的Adobe Analytics實作以使用Web SDK並驗證一切都在Adobe Analytics中正常運作，然後建立XDM結構描述。 此彈性可讓移轉程式更加有條不紊、考慮周到。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**技術債務**：由於此方法使用您現有實作的修改形式，日後追蹤實作邏輯並視需要執行變更會較為困難。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用Analytics來源聯結器

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>最省時又省力的移轉路徑。 <p>以最少的投資將資料快速移轉至Customer Journey Analytics</p></li></ul> | <ul><li>**資料未傳送至Edge Network**： <p>這會導致下列缺點：</p><ul><li>最高級別 [延遲](/help/admin/guardrails.md#latencies) 用於所有移轉路徑的報告；未針對即時個人化使用案例進行最佳化。</li><li>資料無法與其他Adobe Experience Platform應用程式共用；僅限於Customer Journey Analytics</li><li>依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**日後難以改用Web SDK**： </li><li>**在您的結構描述中使用Analytics體驗事件欄位群組**：此欄位群組新增許多Customer Journey Analytics結構描述中不需要的Adobe Analytics事件。  這可能會導致Customer Journey Analytics所需的結構描述更雜亂、更複雜。</li></ul> |

{style="table-layout:auto"}

+++

### 針對使用的Adobe Analytics實作： Web SDK

已使用Experience PlatformWeb SDK實作Adobe Analytics的組織可使用下列移轉路徑。

選擇此移轉路徑時，您也需要選擇結構描述。

#### 移轉路徑

+++設定Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics

| 優勢 | 缺點 |
|----------|---------|
| 如果您的Adobe Analytics實作已使用Web SDK，這是慣用的移轉路徑。<ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供強大功能而打造 [即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他Experience Cloud產品（AJO、RTCDP等）之間整合Adobe Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**使用您現有的實施**：雖然此方法需要一些實作變更，但不需要從頭開始全新的實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供使用XDM結構的選項**：您可以選擇使用現有的Adobe Analytics結構描述，或建立XDM結構描述，並將資料物件中的欄位對應到XDM結構描述。 [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 是有彈性的結構描述，可定義您需要的任何欄位，而且僅限於相關的欄位。 <p>請參閱下方的「使用您自己的XDM結構描述」，深入瞭解使用您自己的XDM結構描述的優點。</p></li><li>**保留規則和資料元素**：雖然確實需要新規則動作，但您可以以最小的變更重複使用現有的資料元素和規則條件。</li><li>**經得起未來考驗**：如果您選擇使用自己的XDM結構描述，則未來的實施更新會比較輕鬆。</li></ul> | 無 |

{style="table-layout:auto"}

+++

#### 選擇您的結構描述

如果您選取的移轉路徑可讓您設定Adobe Analytics Web SDK實作以傳送資料給Customer Journey Analytics，您可以選擇要使用的結構描述。

您可以選擇是否使用現有的Adobe Analytics結構描述，或是在您開始使用其他Platform服務時，更新為自己的XDM結構描述以更符合組織的需求。

+++將Adobe Analytics結構描述與Adobe Analytics Web SDK實作搭配使用

| 優勢 | 缺點 |
|----------|---------|
| <p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>輕鬆移轉<p>如果您已透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，以將資料傳送至Adobe Experience Platform (然後可在您的Customer Journey Analytics設定中使用)。</p></li></ul> | <p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織不太可能使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul> |

+++

+++將您自己的XDM結構描述用於Adobe Analytics Web SDK實作

| 優勢 | 缺點 |
|----------|---------|
| <ul><p>更新至您自己的XDM結構描述的優點包括：</p><ul><li>根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化方案。</li><p>當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。</p></ul> | <p>更新至您自己的XDM結構的缺點包括：</p><ul><li>在開始將資料傳送到Customer Journey Analytics之前，需要更新您的結構描述是耗時的過程。</li></ul> |

+++

## 接著，將資料傳送至Adobe Experience Platform

使用上述資訊選擇移轉路徑後，瞭解如何 [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 依您選擇的移轉路徑而定。
