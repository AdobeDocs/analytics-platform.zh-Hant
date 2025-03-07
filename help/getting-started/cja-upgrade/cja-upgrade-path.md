---
title: 選擇您的Customer Journey Analytics升級路徑
description: 瞭解升級到Customer Journey Analytics時可能升級路徑的優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '2981'
ht-degree: 0%

---

# 步驟2：選擇您的升級路徑

+++展開本節，瞭解此頁面上的資訊在大型升級程式中的適用位置。 請確定所有先前的升級步驟均已完成。

繼續本節之前，請先確認您已完成所有先前的升級工作。

本頁資訊涵蓋升級程式的步驟2，如下表所示：

| 升級任務 | 詳細資料 |
|---------|----------|
| **步驟1：[開始升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 瞭解升級至Customer Journey Analytics的好處和基本升級程式。 |
| <span class="preview">**步驟2：選擇升級路徑**</span> | <span class="preview">有多種方法可用來升級至Customer Journey Analytics。 根據您組織目前的Adobe Analytics環境和長期目標，選擇最適合您組織的方法。</span> |
| **步驟3：[傳送資料至Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 傳送資料至Adobe Experience Platform的程式會依您在步驟2中選擇的升級路徑而有所不同。 |
| **步驟4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多陣列織都需將其歷史Adobe Analytics資料保留一段時間。 有多種選項可達成此目的。 |
| **步驟5：[執行其他實作工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段，您需要在Customer Journey Analytics環境準備好使用之前執行各種工作。<p>這些額外工作適用於Adobe Analytics的升級以及新的Customer Journey Analytics實作。</p><p>這些工作包括：</p><ul><li>將其他資料帶入Experience Platform</li><li>在Platform資料集和Customer Journey Analytics之間建立連線</li><li>建立資料檢視</li><li>移植報表API使用量</li><li>資料摘要和Data Warehouse的會計處理</li><li>移轉專案和元件</li><li>Planning使用者上線</li></ul> <p>如需詳細資訊，請參閱[Customer Journey Analytics快速入門](/help/getting-started/cja-getting-started.md)。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>本頁資訊已取代為下列更完整的升級資訊： <ul><li>**建議的升級步驟**<p>如需詳細資訊，請參閱[從Adobe Analytics升級為Customer Journey Analytics時的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升級指南**<p>有新的升級指南可供使用，動態產生針對貴組織和獨特環境量身打造的升級步驟。</p><p>若要從Customer Journey Analytics存取指南，請選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 請依照熒幕上的指示操作。</p></li></ul>


決定升級至Customer Journey Analytics後，您需要為組織決定最佳升級路徑。

您選擇從Adobe Analytics升級至Customer Journey Analytics的路徑取決於下列因素：

* 您現有的Adobe Analytics實作

* 您的未來目標

使用此頁面上的資訊來判斷哪種Customer Journey Analytics升級路徑最符合您組織目前的實施作業和未來的目標。

若要判別組織的最佳升級路徑，請依序閱讀下列章節：

1. 首先，[瞭解可用的升級路徑](#understand-upgrade-paths)。

1. 然後，[評估您可用的升級路徑](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)。

1. 最後，[會權衡每個升級路徑](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)的優點和缺點。

## 瞭解升級路徑

從Adobe Analytics升級至Customer Journey Analytics有多種升級路徑。

一般而言，每個升級路徑在執行升級所需的工作量層級，以及升級完成後所實現的長期可行性都不同。

下表列出每個升級路徑、其工作量及其長期可行性：

| 升級路徑 | 所需投入的精力 | 長期生存能力 |
|---------|----------|---------|
| **使用Analytics來源聯結器新實作Experience Platform Web SDK**</br>&#x200B;您可以透過新實作Experience Platform Web SDK來開始使用Customer Journey Analytics。 這可讓您開始傳送資料至Adobe Experience Platform Edge Network和Customer Journey Analytics。 此外，您可以使用Analytics來源聯結器將歷史資料匯入Customer Journey Analytics。<p>對於尚未使用Web SDK的組織，此升級路徑可能是將資料傳入Edge Network最直接的方法，因為只需最少的步驟即可完成；但由於所有工作都是預先完成（例如建立XDM結構描述），因此初期所需的工作量會比較大。</p><p>基本步驟為：</p><ol><li>為您的組織建立XDM結構描述。</li><li>實作Web SDK。</li><li>傳送資料至Platform。</li><li>設定Analytics來源聯結器。</br>Analytics來源聯結器用於將歷史Adobe Analytics資料匯入Customer Journey Analytics。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 高 | 高 |
| **新的Experience Platform Web SDK實作**</br>&#x200B;您可以透過新的Experience Platform Web SDK實作來開始使用Customer Journey Analytics。 這可讓您開始傳送資料至Adobe Experience Platform Edge Network和Customer Journey Analytics。 <p>對於尚未使用Web SDK的組織，此升級路徑可能是將資料傳入Edge Network最直接的方法，因為只需最少的步驟即可完成；但由於所有工作都是預先完成（例如建立XDM結構描述），因此初期所需的工作量會比較大。</p><p>基本步驟為：</p><ol><li>為您的組織建立XDM結構描述。</li><li>實作Web SDK。</li><li>傳送資料至Platform。</li></ol> | 高 | 高 |
| **移轉您的Adobe Analytics實作以使用網頁SDK**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以移轉它以使用Adobe Experience Platform Web SDK，在傳送資料至Edge Network和Adobe Analytics之前，先開始傳送資料Customer Journey Analytics。<p>對於尚未使用Web SDK的組織來說，這是將資料傳入Edge Network最簡單且最順暢的方式；它需要更多步驟，但可提供從Adobe Analytics到Customer Journey Analytics更系統的轉換，具有更具體的里程碑。</p><p>基本步驟為：</p><ol><li>將您現有的Adobe Analytics實作專案移至網路SDK，並驗證Adobe Analytics中的所有專案皆正常運作。</li><li>儘可能為您的組織建立XDM結構描述。</li><li>使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。</li><li>傳送資料至Platform。</li></ol> | 稽核 | 高 |
| **設定您現有的Adobe Analytics Web SDK實作**</br>&#x200B;如果您的Adobe Analytics實作已經在使用Adobe Experience Platform Web SDK，您可以透過設定資料串流開始傳送資料至Platform。 或者，如果您已將資料傳送至Platform，只需在Platform資料集和Customer Journey Analytics之間建立連線即可。<p>在將資料傳送至Platform以在Customer Journey Analytics中使用之前，請考慮根據您組織和您使用的任何其他平台應用程式的特定需求更新Adobe Analytics結構描述。</p><p>基本步驟為：</p><ol><li>開始傳送資料至Platform。<p>如果您已使用Adobe Analytics實作將資料傳送至Platform，則不需要執行此步驟。 您只需要在Platform資料集和Customer Journey Analytics之間建立連線，如本流程稍後所述。</p></li><li>（選用）隨時為您的組織建立XDM結構描述。</li><li>（條件式）如果您已建立XDM結構描述，請使用資料流對應來將資料物件中的所有欄位對應到您的XDM結構描述。</li></ol> | 低 | 高 |
| **使用Analytics Source Connector**</br>&#x200B;如果您的Adobe Analytics實作是AppMeasurement或Analytics擴充功能，您可以開始傳送資料至Customer Journey Analytics中的資料檢視。<p>這是將資料傳入Customer Journey Analytics最簡單的方法，但長遠而言是最不可行的方法。</p> <p>**注意：**&#x200B;此升級路徑可單獨使用。 不過，為達到最佳效果，我們建議將此升級路徑與Experience Platform WebSDK的新實作搭配使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 低 | 低 |

{style="table-layout:auto"}

使用下列圖表來協助視覺化每個升級路徑在投入程度和長期可行性方面所處的範圍：

![cja升級路徑](assets/cja-upgrade-path-chart.png)

## 根據您目前的Adobe Analytics實作，評估可用的升級路徑

並非所有升級路徑都適用於每種型別的Adobe Analytics實作。

請利用下列資訊協助您瞭解哪個升級路徑最適合您的組織。

如果您需要更具體的建議、指引或支援，請聯絡您的Adobe代表。

| 現有的Adobe Analytics實作 | 可用的升級路徑 |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics Source聯結器</li><li>（建議）透過Analytics Source Connector新實作Experience Platform Web SDK</li></ul> |
| Adobe Analytics 擴充功能 | <ul><li>Experience Platform Web SDK的新實作</li><li>將Adobe Analytics移轉至Web SDK</li><li>Analytics Source聯結器</li><li>（建議）透過Analytics Source Connector新實作Experience Platform Web SDK</li></ul> |
| Web SDK | <ul><li>設定Adobe Analytics Web SDK實作，將資料傳送至Platform</li><li>（建議）透過Analytics Source Connector新實作Experience Platform Web SDK</li></ul> |

{style="table-layout:auto"}

## 權衡可供您使用的升級路徑的優缺點

特定升級路徑的優缺點會依您現有的Adobe Analytics實作而有所不同。

在使用下列資訊來判斷適合您的升級路徑之前，請先檢閱[瞭解升級路徑](#understand-migration-methods)中的資訊（若尚未瞭解）。

>[!NOTE]
>
>雖然以下幾節中說明的每個升級路徑都可以獨立使用，但是Adobe建議在從Adobe Analytics升級至Customer Journey Analytics時採取兩頭並進的升級方法，無論您目前的Adobe Analytics實作為何： **Adobe Analytics來源聯結器**&#x200B;和&#x200B;**Experience Platform WebSDK的新實作**。
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### 針對使用的Adobe Analytics實施： AppMeasurement和Adobe Analytics擴充功能

以下是已使用AppMeasurement或Adobe Analytics擴充功能實施Adobe Analytics的組織可用的升級路徑。 展開每個區段以檢視每個升級路徑的優缺點。

#### 升級路徑

+++Experience Platform Web SDK的新實作

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul></li><li>**未來校訂**：未來的實作更新更容易。</li></ul> | <ul><li>**需要從頭開始的新實作**：需要從頭開始執行新實作表示下列缺點： </li><ul><li>**耗時**：這是最耗時、要求最高的升級路徑，因為需要您重新開始新的實作。</li><li>**必須在XDM中重新建立完整結構描述**：您必須在XDM中重新建立完整結構描述，才能開始實作Web SDK。</li><li>**必須重新建立規則和資料元素**：您必須從Adobe Analytics實作重新建立任何規則條件和資料元素，才能開始實作Web SDK。</li></ul><li>**不建議保留歷史資料：** Adobe建議將Analytics來源聯結器與Experience Platform Web SDK的新實作搭配使用，以便在升級至Customer Journey Analytics後保留歷史資料。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**不考慮將原始實作的資料與新實作的資料進行比較：** Adobe建議將Analytics來源聯結器與Experience Platform Web SDK的新實作搭配使用，以便在升級至Customer Journey Analytics後比較資料。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++將Adobe Analytics移轉至Experience Platform Web SDK

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供彈性，以便稍後為您的組織建立XDM結構描述**：您可以移轉現有的Adobe Analytics實作以使用Web SDK並驗證一切都在Adobe Analytics中正常運作，然後建立XDM結構描述。 此彈性讓您可以更循序漸進、以更周到的方式升級至Customer Journey Analytics。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**技術債**：因為此方法使用您現有實作的修改形式，所以可能更難追蹤實作邏輯並在日後需要時執行變更。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用Analytics Source聯結器

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>最省時又省力的升級路徑。 <p>以最少的投資快速將資料移轉至Customer Journey Analytics</p></li></ul> | <ul><li>**資料未傳送至Edge Network**： <p>這會導致下列缺點：</p><ul><li>所有升級路徑的報告中[延遲](/help/technotes/guardrails.md#latencies)的最高層級；未針對即時個人化使用案例進行最佳化。</li><li>資料無法與其他Adobe Experience Platform應用程式共用；僅限於Customer Journey Analytics</li><li>依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**日後很難改用Web SDK**：最終，您可能會想要使用Experience Platform Web SDK所提供的優點。 若要開始使用Experience Platform Web SDK，您必須執行新的實作。</li><li>**在您的結構描述中使用Analytics體驗事件欄位群組**：此欄位群組新增許多Customer Journey Analytics結構描述中不需要的Adobe Analytics事件。  這可能會導致Customer Journey Analytics的結構描述更雜亂、更複雜。</li></ul><p>由於這些缺點，Adobe建議將Analytics來源聯結器與Experience Platform Web SDK的新實作搭配使用。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### 針對使用的Adobe Analytics實作：Web SDK

下列升級路徑適用於已透過Experience Platform Web SDK實施Adobe Analytics的組織。

選擇此升級路徑時，您還需要選擇您的結構描述。

#### 升級路徑

+++設定Adobe Analytics Web SDK實作，將資料傳送至Platform

| 優勢 | 缺點 |
|----------|---------|
| 如果您的Adobe Analytics實作已使用Web SDK，此為首選升級路徑。<ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供使用XDM結構描述的選項**：您可以選擇使用現有的Adobe Analytics結構描述，或是建立XDM結構描述，並將資料物件中的欄位對應到您的XDM結構描述。 [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)是彈性的結構描述，可定義您需要的任何欄位，並且僅定義相關的欄位。 <p>請參閱下方的「使用您自己的XDM結構描述」，深入瞭解使用您自己的XDM結構描述的優點。</p></li><li>**保留規則和資料元素**：雖然它確實需要新的規則動作，但您可以重複使用現有的資料元素和規則條件，只需很少的變更。</li><li>**未來校訂**：如果您選擇使用自己的XDM結構描述，則未來的實作更新會比較容易。</li></ul> | 無 |

{style="table-layout:auto"}

+++

#### 選擇您的結構描述

如果您選取的升級路徑可讓您設定Adobe Analytics Web SDK實作以傳送資料至Platform，您可以選擇要使用的結構描述。

您可以選擇是否使用現有的Adobe Analytics結構描述，或是在您開始使用其他Platform服務時，更新為自己的XDM結構描述以更符合組織的需求。

+++將Adobe Analytics結構描述用於Adobe Analytics Web SDK實作

| 優勢 | 缺點 |
|----------|---------|
| <p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，將資料傳送至Adobe Experience Platform (之後可用於您的Customer Journey Analytics設定)。</p></li></ul> | <p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織不太可能使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul> |

+++

+++將您自己的XDM結構描述用於Adobe Analytics Web SDK實作

| 優勢 | 缺點 |
|----------|---------|
| <ul><p>更新至您自己的XDM結構描述的優點包括：</p><ul><li>根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化方案。</li><p>當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。</p></ul> | <p>更新至您自己的XDM結構的缺點包括：</p><ul><li>在開始將資料傳送至Platform之前，需要先更新您的結構描述，這是一個耗時的過程。</li></ul> |

+++

## 接著，將資料傳送至Adobe Experience Platform

使用上述資訊選擇升級路徑後，瞭解如何根據您選擇的升級路徑[傳送資料至Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)。
