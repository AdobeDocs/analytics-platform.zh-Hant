---
title: 選擇您的Customer Journey Analytics移轉方法
description: 瞭解移轉至Customer Journey Analytics時，可能採用的移轉方法的優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 2%

---

# 步驟2：選擇您的Customer Journey Analytics移轉方法

+++展開本區段，瞭解本頁資訊適用於大型移轉程式的位置。 請確定所有先前的移轉步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的移轉工作。

本頁資訊涵蓋步驟2，如下表所示：

| 移轉任務 | 詳細資料 |
|---------|----------|
| **步驟1： [開始使用移轉](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | 瞭解移轉至Adobe Analytics的好處及基本移轉程式。 |
| <span class="preview">**步驟2： [選擇移轉方法](/help/getting-started/cja-migration/cja-migration-method.md)**</span> | <span class="preview">有多種方法可用來移轉至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。</span> |
| **步驟3： [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟1中選擇的移轉方法而有所不同。 |
| **步驟4： [將資料對應至XDM結構描述](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) 在Adobe Experience Platform中使用，以一致且可重複使用的方式說明資料結構。 藉由定義跨系統的一致資料，將更容易保留意義，進而從資料中獲得價值。<p>大部分的移轉方法都需要您建立新的XDM結構描述，或使用資料流對應將現有的Adobe Analytics結構描述對應到XDM。</p> |
| **步驟5： [保留歷史資料](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟6： [計畫使用者上線](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | 您應該給予使用者充裕的時間（3至6個月），以熟悉Analysis Workspace在Customer Journey Analytics中的主要差異。 |
| **步驟7： [連線報表API使用情況](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analytics報表API採用相同格式，但使用不同的端點。 將報表API使用量從Adobe Analytics報表API移轉到Customer Journey Analytics報表API。 |
| **步驟8： [取代資料摘要和Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | 決定如何使用Customer Journey Analytics中可用的匯出選項，以取代您在Adobe Analytics中使用的資料摘要和Data Warehouse功能。 |
| **步驟9： [移轉專案和元件](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analytics中的「元件移轉」區域可讓您將專案及其相關元件從Adobe Analytics移轉到Customer Journey Analytics。 |

{style="table-layout:auto"}

+++

在您決定移轉至Customer Journey Analytics後，必須決定組織的最佳移轉方法。

您選擇從Adobe Analytics移轉至Customer Journey Analytics的方法取決於下列因素：

* 您現有的Adobe Analytics實作

* 您的未來目標

使用此頁面上的資訊來判斷哪種Customer Journey Analytics移轉方法最符合您組織目前的實施作業和未來的目標。

請依序閱讀下列章節，為您的組織決定最佳移轉方法：

1. 首先， [瞭解可用的移轉方法](#understand-migration-methods).

1. 然後 [評估您可用的移轉方法](#assess-the-migration-methods-available-to-you-based-on-your-current-adobe-analytics-implementation).

1. 最後， [權衡每種移轉方法的優缺點](#weigh-the-advantages-and-disadvantages-of-the-migration-methods-available-to-you).

## 瞭解移轉方法

從Adobe Analytics移轉至Customer Journey Analytics有多種移轉方法。

一般而言，每種移轉方法執行移轉所需的工作量層級，以及移轉完成後所實現的長期可行性都不同。

下表列出每種移轉方法、其工作量及其長期可行性：

| 移轉方法 | 所需投入的精力 | 長期生存能力 |
|---------|----------|---------|
| **Web SDK的新實作**</br>&#x200B;您可以執行新的Adobe Experience Platform Web SDK實作，以開始傳送資料至Adobe Experience PlatformEdge Network <!-- what is the correct branding -->. <p>對於尚未使用Web SDK的組織，此移轉方法可能是最直接將資料Edge Network的程式（只需要最少的步驟數），但由於所有工作都是預先完成（例如建立XDM結構描述），因此初期所需的工作量會比較大。</p><p>基本步驟為：</p><ol><li>為您的組織建立XDM結構描述。</li><li>實作Web SDK。</li><li>傳送資料至Platform。</li></ol> | 高 | 高 |
| **移轉您的Adobe Analytics實作以使用Web SDK**</br>&#x200B;如果您的Adobe Analytics實作AppMeasurement或Analytics擴充功能，您可以將其移轉為使用Adobe Experience Platform Web SDK，在傳送資料給Customer Journey Analytics之前開始傳送資料給Edge Network。 <!-- what else? --><p>這是將資料匯入Edge Network的最簡單且最流暢的方式；它需要更多步驟，但可提供更系統地轉換，具有更具體的里程碑。</p><p>基本步驟為：</p><ol><li>將您現有的Adobe Analytics實作專案移至Web SDK，並驗證那裡的所有專案運作正常。</li><li>儘可能為您的組織建立XDM結構描述。</li><li>使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。</li><li>傳送資料至Platform。</li></ol> | 稽核 | 高 |
| **設定您現有的Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics**</br>&#x200B;如果您的Adobe Analytics實作已經在使用Web SDK，您就可以開始將資料輕鬆傳送至Customer Journey Analytics。<p>在將資料傳送至Customer Journey Analytics之前，請考慮根據您組織的特定需求以及您將使用的任何其他平台應用程式，更新您的Adobe Analytics結構描述。</p><p>基本步驟為：</p><ol><li>開始傳送資料給Customer Journey Analytics。<!-- What's involved here? Just point it at CJA? --></li><li>（選用）隨時為您的組織建立XDM結構描述。</li><li>（條件式）如果您已建立XDM結構描述，請使用資料流對應來將資料物件中的所有欄位對應到您的XDM結構描述。</li></ol> | 低 | 高 |
| **Analytics來源聯結器**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以開始以Customer Journey Analytics傳送資料至資料檢視。<p>這是將資料匯入Customer Journey Analytics的最簡單方法，但長遠而言是最不可行的方法。</p> | 低 | 低 |

{style="table-layout:auto"}

使用下列圖表來協助視覺化每個移轉方法在工作量及長期可行性方面所處的範圍：

![cja移轉方法](assets/cja-migration-methods.png)

## 根據您目前的Adobe Analytics實作，評估可用的移轉方法

並非所有移轉方法都適用於每種型別的Adobe Analytics實施。

請利用下列資訊協助您瞭解最適合貴組織的移轉方法。

如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| Adobe Analytics實施 | 可用的移轉方法 |
|---------|----------|
| AppMeasurement | <ul><li>Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics來源聯結器</li></ul> |
| Adobe Analytics 擴充功能 | <ul><li>Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics來源聯結器</li></ul> |
| Web SDK | <ul><li>設定Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics</li></ul> |

{style="table-layout:auto"}

## 權衡您可用的移轉方法的優缺點

特定移轉方法的優缺點會依您現有的Adobe Analytics實作而有所不同。

使用下列資訊來判斷適合您的移轉方法之前，請先檢閱下列資訊： [瞭解移轉方法](#understand-migration-methods) 如果您尚未這樣做。

### 針對使用的Adobe Analytics實施：AppMeasurement和Adobe Analytics擴充功能

下表顯示適用於已使用AppMeasurement或Adobe Analytics擴充功能實作Adobe Analytics的組織之移轉方法：

| 移轉方法 | 優勢 | 缺點 |
|---------|----------|---------|
| **Web SDK的新實作** | <ul><li>使用XDM結構描述、彈性的結構描述來定義您需要的任何欄位，並且僅定義相關的欄位(可讓您離開Adobe Analytics體驗事件欄位群組)</li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li><li>無字元限制問題 (prop 有 100 個字元)</li><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供強大功能而打造 [即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>經得起未來考驗（將獲得所有最新功能）</li><li>在其他Experience Cloud產品（AJO、RTCDP等）之間合併Adobe Experience Cloud資料收集的標籤</li><li>[第一方裝置 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html)，用於強化訪客識別的準確性</li></ul> | <ul><li>最耗時、最苛刻的移轉方法<p>您必須在XDM中重新建立完整結構描述，才能開始實作Web SDK</p></li></ul> |
| **將Adobe Analytics移轉至Web SDK** | <ul><li>保留您的Adobe Analytics實作中已設定的規則和資料元素。</li><li>可讓您改用Web SDK，而不會影響現有的Adobe Analytics報表。</li><li>提供彈性，以便日後為您的組織建立XDM結構描述：彈性的結構描述可定義您需要的任何欄位，而且僅限於相關的欄位。</br>不需要Adobe Analytics體驗事件欄位群組為Customer Journey Analytics。 <!-- With the new implementation, you're double-counting with 2 implementation; with the migration, you're double-counting, but both of them are through Edge Network. --></li><li>不依賴Adobe Analytics命名法(屬性、eVar、事件等)</li><li>無字元限制問題 (prop 有 100 個字元)</li><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為提供強大功能而打造 [即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>經得起未來考驗（將獲得所有最新功能）</li><li>在其他Experience Cloud產品（AJO、RTCDP等）之間合併Adobe Experience Cloud資料收集的標籤</li><li>[第一方裝置 ID](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html)，用於強化訪客識別的準確性</li></ul> | <ul><li>未來某個時候必須符合XDM結構描述，使用資料流對應。</li><li>產生一些技術債。 例如，可以保留舊版AppMeasurement或Analytics擴充功能程式碼。 </li></ul> |
| **Analytics來源聯結器** | <ul><li>最省時又省力的移轉方法。 <p>以最少的投資將資料快速移轉至Customer Journey Analytics</p></li></ul> | <ul><li>資料不會傳送至Edge Network，且無法與其他Adobe Experience Platform應用程式共用；其僅限於Customer Journey Analytics<li>日後難以改用Web SDK</li><li>使用結構描述中的「Analytics體驗事件」欄位群組。</br>此欄位群組新增許多Customer Journey Analytics結構描述中不需要的Adobe Analytics事件。  這可能會導致Customer Journey Analytics所需的結構描述更雜亂、更複雜。</li><li>最高級別 [延遲](/help/admin/guardrails.md#latencies) 橫跨所有實作方法</li></ul> |

{style="table-layout:auto"}

### 針對使用的Adobe Analytics實作： Web SDK

下表顯示已使用Web SDK實作Adobe Analytics的組織可用的移轉方法：

| 移轉方法 | 優勢 | 缺點 |
|---------|----------|---------|
| **設定Adobe Analytics Web SDK實作，將資料傳送至Customer Journey Analytics** | 如果您的Adobe Analytics實作已使用Web SDK，這是慣用的移轉方法。 <p>使用此實作方法時，您可以選擇是否使用現有的Adobe Analytics結構描述，或是更新為XDM結構描述，以便在您開始使用其他Platform應用程式時更符合組織的需求。</p><p>**使用Adobe Analytics結構描述**</p><p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>輕鬆移轉<p>如果您已透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，以將資料傳送至Adobe Experience Platform (然後可在您的Customer Journey Analytics設定中使用)。</p></li></ul><p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織可能不會使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul><p>**使用XDM結構描述**</p><p>更新XDM結構描述的優點包括：</p><ul><li>根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化方案。</li><p>當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。</p></ul><p>更新XDM結構的缺點包括：</p><ul><li>在開始將資料傳送到Customer Journey Analytics之前，需要更新您的結構描述是耗時的過程。</li></ul> | 無 |

{style="table-layout:auto"}

## 接著，將資料傳送至Adobe Experience Platform

使用上述資訊選擇移轉方法後，瞭解如何 [傳送資料至Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md) 取決於您選擇的移轉方法。
