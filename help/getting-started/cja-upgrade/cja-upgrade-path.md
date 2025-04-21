---
title: 選擇您的 Customer Journey Analytics 升級路徑
description: 了解升級到 Customer Journey Analytics 時可能使用的升級路徑優缺點
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 9559ba10-cbaf-4243-9c85-a0a5f6e3bbff
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '2981'
ht-degree: 97%

---

# 步驟 2：選擇您的升級路徑

+++ 展開此部分，查看此頁面資訊在更大規模升級程序中的位置。確保所有先前的升級步驟都已完成。

在繼續此部分之前，請先確保您已完成所有先前的升級工作。

本頁資訊涵蓋升級流程的步驟 2，重點如下表所示：

| 升級工作 | 詳細資料 |
|---------|----------|
| **步驟 1： [開始升級](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | 了解升級到 Customer Journey Analytics 的好處和基本升級流程。 |
| <span class="preview">**步驟 2：選擇升級路徑**</span> | <span class="preview">有多種方法可以升級到 Customer Journey Analytics。根據您組織目前的 Adob&#x200B;&#x200B;e Analytics 環境和長期目標，選擇最適合您組織的方法。</span> |
| **步驟 3： [將資料發送至 Adob&#x200B;&#x200B;e Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | 將資料發送送至 Adob&#x200B;&#x200B;e Experience Platform 的流程會因您在步驟 2 選擇的升級路徑而不同。 |
| **步驟 4：[保留歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 大多數組織需要保留其歷史 Adob&#x200B;&#x200B;e Analytics 資料達一段時間。有多種選項可以達到此目的。 |
| **步驟 5： [執行額外的實施工作](/help/getting-started/cja-getting-started.md)** | 在升級流程的這個階段中，您需要執行各類工作後，您的 Customer Journey Analytics 環境才可供使用。<p>這些額外工作適用於 Adob&#x200B;&#x200B;e Analytics 的升級以及新的 Customer Journey Analytics 實施。</p><p>這些工作包括：</p><ul><li>將其他資料引入 Experience Platform</li><li>建立 Platform 資料集和 Customer Journey Analytics 之間的連線</li><li>建立資料檢視</li><li>轉移報告 API 用法</li><li>考量資料摘要和 Data Warehouse</li><li>移轉專案和元件</li><li>規劃使用者上線</li></ul> <p>如需更多資訊，請參閱「[Customer Journey Analytics 快速入門手冊](/help/getting-started/cja-getting-started.md)」。 |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>本頁資訊已取代為下列更完整的升級資訊： <ul><li>**建議的升級步驟**<p>如需詳細資訊，請參閱[從Adobe Analytics升級為Customer Journey Analytics時的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。</p></li><li>**Customer Journey Analytics升級指南**<p>有新的升級指南可供使用，動態產生針對貴組織和獨特環境量身打造的升級步驟。</p><p>若要從Customer Journey Analytics存取指南，請選取&#x200B;**[!UICONTROL Workspace]**&#x200B;標籤，然後在左側面板中選取&#x200B;**[!UICONTROL 升級至Customer Journey Analytics]**。 請依照熒幕上的指示操作。</p></li></ul>


在您決定升級到 Customer Journey Analytics 後，您需要確定適合您組織的最佳升級路徑。

您選擇從 Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics 的路徑取決於以下因素：

* 您現有的 Adobe Analytics 實施。

* 你未來的目標

使用此頁面資訊來確定哪種 Customer Journey Analytics 升級路徑最符合您組織的目前實施和未來目標。

為了確定適合您組織的最佳升級路徑，應按順序閱讀以下部分：

1. 首先，[了解適用的升級路徑](#understand-upgrade-paths)。

1. 然後，[評估哪些升級路徑可供您選擇](#assess-the-upgrade-paths-available-to-you-based-on-your-current-adobe-analytics-implementation)。

1. 最後，[衡量每種升級路徑的優點和缺點](#weigh-the-advantages-and-disadvantages-of-the-upgrade-paths-available-to-you)。

## 了解升級路徑

從 Adobe Analytics 升級至 Customer Journey Analytics 時，有許多不同的可用路徑。

一般來說，每種升級路徑在執行升級需進行的作業程度，以及升級完成後達到的長期可行性有所不同。

下表列出有每種升級路徑、其作業程度以及長期可行性：

| 升級路徑 | 作業程度 | 長期可行性 |
|---------|----------|---------|
| **使用 Analytics 來源連接器的 Experience Platform Web SDK 全新實施**</br>&#x200B;您可以透過進行 Experience Platform Web SDK 的全新實施來開始使用 Customer Journey Analytics。這樣可讓您開始將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform Edge Network 和 Customer Journey Analytics。此外，您還可以使用 Analytics 來源連接器讓歷史資料進入 Customer Journey Analytics。<p>對於尚未使用 Web SDK 的組織，此升級路徑可能是將資料傳入 Edge Network 最直接的方式，因為這個方式需要的步驟最少；但是，由於所有工作都是提前完成 (例如建立 XDM 模式)，所以初步需要進行更多工作。</p><p>基本步驟如下：</p><ol><li>為您的組織建立 XDM 結構描述。</li><li>實施 Web SDK。</li><li>將資料傳送到 Platform。</li><li>設立 Analytics 來源連接器。</br>Analytics 來源連接器可用來讓歷史 Adob&#x200B;&#x200B;e Analytics 資料進入 Customer Journey Analytics。<!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--></li></ol><p><!-- **Note:** This is the recommended upgrade path when upgrading to Customer Journey Analytics. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). --></p> | 高 | 高 |
| **Experience Platform Web SDK 的全新實施**</br>&#x200B;您可以透過進行 Experience Platform Web SDK 全新實施來開始使用 Customer Journey Analytics。這樣可讓您開始將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform Edge Network 和 Customer Journey Analytics。 <p>對於尚未使用 Web SDK 的組織，此升級路徑可能是將資料傳入 Edge Network 最直接的方式，因為這個方式需要的步驟最少；但是，由於所有工作都是提前完成 (例如建立 XDM 模式)，所以初步需要進行更多工作。</p><p>基本步驟如下：</p><ol><li>為您的組織建立 XDM 結構描述。</li><li>實施 Web SDK。</li><li>將資料傳送到 Platform。</li></ol> | 高 | 高 |
| **移轉您的 Adob&#x200B;&#x200B;e Analytics 實施以使用 Web SDK**</br>&#x200B;如果您的 Adob&#x200B;&#x200B;e Analytics 實施是 AppMeasurement 或 Analytics 擴充功能，則您可以將其移轉以使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK，以便開始將資料傳送至 Edge Network 和 Adob&#x200B;&#x200B;e Analytics，然後再將其傳送至 Customer Analytics。<p>對於尚未使用 Web SDK 的組織，這是將資料傳入 Edge Network 的最簡單、最順暢方式；這方式需要更多步驟，但可讓 Adob&#x200B;&#x200B;e Analytics 轉換至 Customer Journey Analytics 更有條理，並提供更明確的里程碑。</p><p>基本步驟如下：</p><ol><li>將現有的 Adob&#x200B;&#x200B;e Analytics 實施移動至 Web SDK，並驗證 Ad&#x200B;&#x200B;ob&#x200B;&#x200B;e Analytics 中的一切是否正常運作。</li><li>當您有時間時，可為您的組織建立 XDM 結構描述。</li><li>使用資料流對應，將資料物件中的所有欄位對應到您的 XDM 結構描述。</li><li>將資料傳送到 Platform。</li></ol> | 中 | 高 |
| **設定您現有的 Adob&#x200B;&#x200B;e Analytics Web SDK 實施**</br>&#x200B;如果您的 Adob&#x200B;&#x200B;e Analytics 實施已經在使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK，則您可以透過設定資料流開始將資料傳送到 Platform。或者，如果您已經將資料傳送到 Platform，則只需在 Platform 資料集和 Customer Journey Analytics 之間建立連結。<p>在您將資料傳送到 Platform 以便在 Customer Journey Analytics 使用之前，請考慮根據組織的特定需求以及您使用的任何其他 Platform 應用程式來更新 Adob&#x200B;&#x200B;e Analytics 結構描述。</p><p>基本步驟如下：</p><ol><li>開始傳送資料至 Platform。<p>如果您已經使用 Adobe Analytics 實施將資料傳送到 Platform，則不需要此步驟。您只需要在 Platform 資料集和 Customer Journey Analytics 之間建立連線，如本過程後面所述。</p></li><li>(選用) 當您有時間時，可為您的組織建立 XDM 結構描述。</li><li>(選用) 如果您建立了 XDM 結構描述，請使用資料流對應將資料物件中的所有欄位對應到您的 XDM 結構描述。</li></ol> | 低 | 高 |
| **使用 Analytics 來源連接器**</br>&#x200B;如果您的 Adob&#x200B;&#x200B;e Analytics 實施是 AppMeasurement 或 Analytics 擴充功能，則您可以開始將資料傳送到 Customer Journey Analytics 中的資料檢視。<p>這是將資料傳送至 Customer Journey Analytics 的最簡單方法，但就長期來說並非最可行的方法。</p> <p>**注意：** 此升級路徑可個別使用。但為達到最佳成效，我們建議將此升級路徑與 Experience Platform WebSDK 的全新實施結合使用。 <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).--> </p> | 低 | 低 |

{style="table-layout:auto"}

使用下圖以視覺效果來幫助了解每種升級路徑的作業程度和長期可行性狀況：

![cja 升級路徑](assets/cja-upgrade-path-chart.png)

## 根據您目前的 Adob&#x200B;&#x200B;e Analytics 實施情況評估可用的升級路徑

並非所有升級路徑都適用於每種類型的 Adob&#x200B;&#x200B;e Analytics 實施。

使用以下資訊幫助您了解哪種升級路徑最適合您的組織。

如果您需要更具體的建議、指導或支援，請聯絡您的 Adob&#x200B;&#x200B;e 代表。

| 現有的 Adobe Analytics 實施 | 適用升級路徑 |
|---------|----------|
| AppMeasurement | <ul><li>Experience Platform Web SDK 全新實施</li><li>將 Adob&#x200B;&#x200B;e Analytics 移轉至 Web SDK</li><li>Analytics 來源連接器</li><li>(建議) 使用 Analytics 來源連接器的 Experience Platform Web SDK 全新實施</li></ul> |
| Adobe Analytics 擴充功能 | <ul><li>Experience Platform Web SDK 全新實施</li><li>將 Adob&#x200B;&#x200B;e Analytics 移轉至 Web SDK</li><li>Analytics 來源連接器</li><li>(建議) 使用 Analytics 來源連接器的 Experience Platform Web SDK 全新實施</li></ul> |
| Web SDK | <ul><li>設定 AdobeAnalyticsWebSDK 實施，以便將資料傳送到 Platform</li><li>(建議) 使用 Analytics 來源連接器的 Experience Platform Web SDK 全新實施</li></ul> |

{style="table-layout:auto"}

## 衡量適用升級路徑的優缺點

特定升級路徑的優缺點會因您現有的 Adob&#x200B;&#x200B;e Analytics 實施而異。

在使用以下資訊確定哪種升級路徑適合您之前，請先查看「[了解升級路徑](#understand-migration-methods)」中的資訊 (如果您還未查看)。

>[!NOTE]
>
>雖然以下各節說明的每種升級途徑均可個別使用，但無論您目前的 Adob&#x200B;&#x200B;e Analytics 實施情況如何，Adob&#x200B;&#x200B;e 建議您從 Adob&#x200B;&#x200B;e Analytics 升級到 Customer Journey Analytics 時要採用雙管齊下的升級方法： **Adobe 來源連接器**&#x200B;和 **Experience Platform WebSDK 全新實施**。
><!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) -->

### 對於使用以下方式的 Adob&#x200B;&#x200B;e Analytics 實施：AppMeasurement 和 Adob&#x200B;&#x200B;e Analytics 擴充功能

以下是已透過 AppMeasurement 或 Adob&#x200B;&#x200B;e Analytics 擴充功能實施 Adob&#x200B;&#x200B;e Analytics 的組織適用的升級路徑。展開每個部分可以查看每種升級路徑的優缺點。

#### 升級路徑

+++Experience Platform Web SDK 全新實施

| 優點 | 缺點 |
|----------|---------|
| <ul><li>**提供在 Experience Edge Network**&#x200B;中託管資料的所有優點： <p>這些優點包括：</p><ul><li>Adobe Experience Platform 是為支援 [即時個人化使用案例而建立，因此具有高效能報告和資料可用性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施</li><li>不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul></li><li>**具前瞻性**：未來實施的更新較容易。</li></ul> | <ul><li>**需要從頭開始的全新實施**：需要從頭開始進行全新實施表示有以下缺點： </li><ul><li>**耗時**：這是最耗時且要求最高的升級路徑，因為此方法會要求您從頭開始進行全新實作。</li><li>**必須在 XDM 中重新建立完整的結構描述**：在開始實施 Web SDK 之前，您必須在 XDM 中重新建立完整的結構描述。</li><li>**必須重新建立規則和資料元素**：在開始實施 Web SDK 之前，您必須從 Adob&#x200B;&#x200B;e Analytics 實施中重新建立所有規則條件和資料元素。</li></ul><li>**不考慮保留歷史資料：**  Adobe 建議將 Analytics 來源連接器與 Experience Platform Web SDK 的全新實施結合使用，以便在升級至 Customer Journey Analytics 後保留歷史資料。 <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li><li>**不考慮將原始實施的資料與全新實施的資料比較：** Adobe 建議將 Analytics 來源連接器與 Experience Platform Web SDK 的全新實施結合使用，以便在升級至 Customer Journey Analytics 後比較資料。 <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></li></ul> |

{style="table-layout:auto"}

+++

+++將 Adob&#x200B;&#x200B;e Analytics 移轉至 Experience Platform Web SDK

| 優點 | 缺點 |
|----------|---------|
| <ul><li>**提供在 Experience Edge Network**&#x200B;中託管資料的所有優點： <p>這些優點包括：</p><ul><li>Adobe Experience Platform 是為支援 [即時個人化使用案例而建立，因此具有高效能報告和資料可用性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施</li><li>不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**使用您現有的實施**：雖然這種方法需要進行一些實施變更，但這並不需要從頭開始進行全新實施。您可以使用現有的資料層和程式碼，對實施邏輯進行最少變更，而不會影響現有的 Adob&#x200B;&#x200B;e Analytics 報告。</li><li>**為您的組織以後建立 XDM 結構描述提供靈活性**：您可以移轉現有的 Adob&#x200B;&#x200B;e Analytics 實施至使用 Web SDK，並驗證 Ad&#x200B;&#x200B;ob&#x200B;&#x200B;e Analytics 一切正常運行，然後建立 XDM 結構描述。這種靈活性允許以更條理和週到方式升級至 Customer Journey Analytics。</li></ul> | <ul><li>**需要對應才能將資料傳送到 Platform**：當您的組織準備好使用 Customer Journey Analytics 時，您必須將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform 中的資料集。此操作要求資料物件中每個欄位都是資料流對應工具中的一個項目，可將其指派給 XDM 結構描述欄位。此工作流程僅需進行一次對應，且不涉及進行實施變更。但是，這是額外進行的步驟，在 XDM 物件中傳送資料時不需要進行。</li><li>**技術債**：由於這種方法是使用修改形式的現有實施，因此將來需要時要追蹤實施邏輯和執行變更可能會更困難。 </li></ul> |

{style="table-layout:auto"}

+++

+++使用 Analytics 來源連接器

| 優點 | 缺點 |
|----------|---------|
| <ul><li>最省時、最省力的升級路徑。 <p>只需最少投資即可快速將資料移轉至 Customer Journey Analytics</p></li></ul> | <ul><li>**資料未傳送至 Edge Network**： <p>這樣會導致以下缺點：</p><ul><li>在所有升級路徑的報告中hapi 最高級別[延遲](/help/technotes/guardrails.md#latencies)；未針對即時個人化使用案例進行最佳化。</li><li>資料不能與其他 Adob&#x200B;&#x200B;e Experience Platform 應用程式共用；此資料僅限於 Customer Journey Analytics 使用</li><li>依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**未來很難移轉至 Web SDK**：最後，您可能希望獲得 Experience Platform Web SDK 提供的優勢。為了開始使用 Experience Platform Web SDK，您必須進行全新實施。</li><li>**使用結構描述中的 Analytics Experience Event 欄位群組**：此欄位群組新增許多您 Customer Journey Analytics 結構描述中不需要的 Adob&#x200B;&#x200B;e Analytics 事件。這可能會導致比 Customer Journey Analytics 所需的更混亂、更複雜的結構描述。</li></ul><p>由於有這些缺點，Adobe 建議將 Analytics 來源連接器與 Experience Platform Web SDK 的全新實施結合使用。 <!-- For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md) --></p> |

{style="table-layout:auto"}

+++

### 使用 Web SDK 的 Adobe Analytics 實施

以下升級路徑適用於已使用 Experience Platform Web SDK 實施 Adob&#x200B;&#x200B;e Analytics 的組織。

當選擇此升級路徑時，您還需要選擇您的結構描述。

#### 升級路徑

+++設定 AdobeAnalyticsWebSDK 實施，以便將資料傳送到 Platform

| 優點 | 缺點 |
|----------|---------|
| 如果您的 Adob&#x200B;&#x200B;e Analytics 實施已經在使用 Web SDK，則這是首選的升級路徑。<ul><li>**提供在 Experience Edge Network**&#x200B;中託管資料的所有優點： <p>這些優點包括：</p><ul><li>Adobe Experience Platform 是為支援 [即時個人化使用案例而建立，因此具有高效能報告和資料可用性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施</li><li>不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**使用您現有的實施**：雖然這種方法需要進行一些實施變更，但這並不需要從頭開始進行全新實施。您可以使用現有的資料層和程式碼，對實施邏輯進行最少變更，而不會影響現有的 Adob&#x200B;&#x200B;e Analytics 報告。</li><li>**提供使用 XDM 結構描述的選項**：您可以選擇使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述或建立 XDM 結構描述，並將資料物件中的欄位對應到 XDM 結構描述。[XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home#xdm-schemas)是一種靈活的結構描述，可以定義您需要的任何欄位，並且只定義相關的欄位。 <p>若要了解更多使用您自己 XDM 結構描述的優勢，請參閱下面的「使用您自己的 XDM 結構描述」。</p></li><li>**保留規則和資料元素**：雖然這需要新的規則操作，但您可以在最少的變更下重複使用現有的資料元素和規則條件。</li><li>**面向未來**：如果您選擇使用自己的 XDM 結構描述，那麼未來的實施更新將會更容易。</li></ul> | 無 |

{style="table-layout:auto"}

+++

#### 選擇您的結構描述

如果您選擇允許您設定 Adobe Analytics Web SDK 實施以傳送資料到 Platform 的升級路徑，則您可以選擇要使用的結構描述。

您可以選擇使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述，也可以更新至您自己的 XDM 結構描述，以便在開始使用其他 Platform 服務時更能滿足組織的需求。

+++將 Adob&#x200B;&#x200B;e Analytics 結構描述與 Adob&#x200B;&#x200B;e Analytics Web SDK 實施結合使用

| 優點 | 缺點 |
|----------|---------|
| <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 將資料傳送至 Adob&#x200B;&#x200B;e Analytics，則您可以向資料流新增附加服務以將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform (然後可在您的 Customer Journey Analytics 設定中使用)。</p></li></ul> | <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的缺點包括：</p><ul><li>雖然使用 Adob&#x200B;&#x200B;e Analytics 結構描述不會限制您如何與其他 Platform 應用程式結合使用，但會導致比使用其他結構描述更複雜的結構描述。這是因為 Adobe Analytics 結構描述包含許多 Adob&#x200B;&#x200B;e Analytics 專屬的物件，而您的組織不太可能使用這些物件。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位來找到需要更新的欄位。</p></li></ul> |

+++

+++將您自己的 XDM 結構描述與 Adob&#x200B;&#x200B;e Analytics Web SDK 實施結合使用

| 優點 | 缺點 |
|----------|---------|
| <ul><p>更新到您自己的 XDM 結構描述的優點包括：</p><ul><li>根據您的組織需求和您使用的特定 Platform 應用程式量身定制的簡化結構描述。</li><p>當需要變更結構描述時，您不必篩選數千個未使用的欄位來找到需要更新的欄位。</p></ul> | <p>更新到您自己的 XDM 結構描述的缺點包括：</p><ul><li>更新結構描述相當耗費時間，這是開始將資料傳送到 Platform 之前必需進行的程序。</li></ul> |

+++

## 接下來，將資料發送至 Adob&#x200B;&#x200B;e Experience Platform

使用上述資訊選擇升級路徑後，了解如何根據所選的升級路徑[將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md) 。
