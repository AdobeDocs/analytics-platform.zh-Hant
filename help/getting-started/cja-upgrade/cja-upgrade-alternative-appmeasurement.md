---
title: 升級至Customer Journey Analytics時的替代方法
description: 瞭解升級至Customer Journey Analytics時的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 58%

---

# 升級替代方案：將 AppMeasurement 資料收集與 Experience Platform Web SDK 和 Customer Journey Analytics 併用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="將 AppMeasurement 邏輯與 Web SDK 併用"
>abstract="您可以透過資料物件以 AppMeasurement 格式傳送所有變數，而非透過 XDM 物件傳送資料。<br><br>此選項可讓您將 AppMeasurement 邏輯對應至 XDM，無須從頭開始填入 XDM 物件，進而省下實作時間。然而，這種做法會隨時間變得複雜，因為您將來新增的任何欄位都必須對應至資料流中的 XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="變更您的 AppMeasurement 邏輯以指向 Web SDK"
>abstract="因為您選取執行實作捷徑，故顯示此步驟。複製或變更 AppMeasurement 邏輯以填入資料物件，而非 s 物件。例如，將 s.eVar1 的指派變更為 data.__adobe.analytics.eVar1，並對所有 Analytics 變數重複此動作。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

升級到 Customer Journey Analytics 時，Adobe [建議對 Experience Platform Web SDK 進行新實施](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。但是，根據時間軸和資源限制等多種因素，建議的升級步驟可能不適合您組織。

您可以搭配Web SDK使用AppMeasurement或Analytics擴充功能資料收集邏輯，將資料傳送至Platform和Customer Journey Analytics，而非搭配XDM物件收集資料。 然而，這種替代方案會隨著時間推移而增加複雜性。

## 優點和缺點

此方法與[將整個資料層傳送至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因為兩種方法都完成相同的工作。 (此方法較適合將整個資料層傳送至Adobe。 Prop和eVar會處理資料，因此更加精確。__adobe.analytics._變數名稱_。)

請考量使用此升級替代方案的下列優缺點：

| 優點 | 缺點 |
|----------|---------|
| 如果您的 Adob&#x200B;&#x200B;e Analytics 實施已經在使用 Web SDK，則這是首選的升級路徑。<ul><li>**提供在 Experience Edge Network**&#x200B;中託管資料的所有優點： <p>這些優點包括：</p><ul><li>Adobe Experience Platform 是為支援 [即時個人化使用案例而建立，因此具有高效能報告和資料可用性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=zh-Hant)</li><li>在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施</li><li>不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**使用您現有的實施**：雖然這種方法需要進行一些實施變更，但這並不需要從頭開始進行全新實施。您可以使用現有的資料層和程式碼，對實施邏輯進行最少變更，而不會影響現有的 Adob&#x200B;&#x200B;e Analytics 報告。</li><li>**提供使用 XDM 結構描述的選項**：您可以選擇使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述或建立 XDM 結構描述，並將資料物件中的欄位對應到 XDM 結構描述。[XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home#xdm-schemas)是一種靈活的結構描述，可以定義您需要的任何欄位，並且只定義相關的欄位。 <p>若要了解更多使用您自己 XDM 結構描述的優勢，請參閱下面的「使用您自己的 XDM 結構描述」。</p></li><li>**保留規則和資料元素**：雖然這需要新的規則操作，但您可以在最少的變更下重複使用現有的資料元素和規則條件。</li><li>**面向未來**：如果您選擇使用自己的 XDM 結構描述，那麼未來的實施更新將會更容易。</li></ul> | <ul><li>**需要對應才能將資料傳送到 Platform**：當您的組織準備好使用 Customer Journey Analytics 時，您必須將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform 中的資料集。此操作要求資料物件中每個欄位都是資料流對應工具中的一個項目，可將其指派給 XDM 結構描述欄位。此工作流程僅需進行一次對應，且不涉及進行實施變更。但是，這是額外進行的步驟，在 XDM 物件中傳送資料時不需要進行。</li><li>**隨著時間增加額外的複雜性**：您日後新增的任何欄位都必須對應至資料流中的XDM。<p>只要將新欄位新增至您的實作，您就可以執行下列任一項作業：</p><ul><li>**選項1：**&#x200B;在資料物件中填入新的任意evar或新prop，然後將它對應到所要的XDM欄位。<p>此程式可促進使用者端實施的一致性，但需要對應功能。</p></li><li>**選項2：**&#x200B;將資料物件保留為舊版實作，並開始只為所有新欄位填入XDM物件。<p>此程式不需要進行對應，但這表示您的部分變數僅位在資料物件中，而其他變數僅位在XDM物件中。 每當需要對實施進行疑難排解時，您需要前往兩個位置。 請確定您的內部工作流程能因應這種情況。</p></li></ul> |

{style="table-layout:auto"}

## 基本步驟

移轉Adobe Analytics實施(AppMeasurement或Analytics擴充功能)以使用Web SDK將資料傳送至Customer Journey Analytics的基本步驟如下：

1. 移轉您的Adobe Analytics實作以使用Adobe Experience Platform Web SDK，並開始將資料傳送至Edge Network。

   此步驟可讓您移轉現有的Adobe Analytics實作，以使用網頁SDK。 您可以選擇將資料傳送至Adobe Analytics，在傳送資料至Adobe Analytics之前驗證一切都在Customer Journey Analytics中運作。 完成此設定且Adobe Analytics中的資料符合要求後，您就可以將資料從Edge Network傳送至Customer Journey Analytics。

   這種靈活性允許以更條理和週到方式升級至 Customer Journey Analytics。

   如需如何執行此動作的詳細資訊，請參閱Adobe Analytics檔案中的下列文章：

   * [使用標籤移轉至網頁SDK](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [使用JavaScript移轉至Web SDK](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. 開始從Edge Network傳送資料至Platform。

   1. 透過資料物件，以AppMeasurement格式傳送所有變數。

      如需詳細資訊，請參閱[對應到Adobe Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/data-var-mapping)的資料物件變數。

   1. 選擇您的結構描述。

      您可以選擇是否使用現有的Adobe Analytics結構描述，或是在您開始使用其他Platform服務時，建立XDM結構描述以更符合組織的需求。

      Adobe建議建立XDM結構描述。 如需詳細資訊，請參閱[建立自訂結構描述以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

      +++使用Adobe Analytics結構描述

      | 優點 | 缺點 |
      |----------|---------|
      | <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經使用 Adob&#x200B;&#x200B;e Experience Platform Web SDK 將資料傳送至 Adob&#x200B;&#x200B;e Analytics，則您可以向資料流新增附加服務以將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform (然後可在您的 Customer Journey Analytics 設定中使用)。</p></li></ul> | <p>使用 Adob&#x200B;&#x200B;e Analytics 結構描述的缺點包括：</p><ul><li>雖然使用 Adob&#x200B;&#x200B;e Analytics 結構描述不會限制您如何與其他 Platform 應用程式結合使用，但會導致比使用其他結構描述更複雜的結構描述。這是因為 Adobe Analytics 結構描述包含許多 Adob&#x200B;&#x200B;e Analytics 專屬的物件，而您的組織不太可能使用這些物件。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位來找到需要更新的欄位。</p></li></ul> |

      +++

      +++建立 XDM 結構描述

      | 優點 | 缺點 |
      |----------|---------|
      | <ul><p>更新到您自己的 XDM 結構描述的優點包括：</p><ul><li>根據您的組織需求和您使用的特定 Platform 應用程式量身定制的簡化結構描述。</li><p>當需要變更結構描述時，您不必篩選數千個未使用的欄位來找到需要更新的欄位。</p></ul> | <p>更新到您自己的 XDM 結構描述的缺點包括：</p><ul><li>更新結構描述相當耗費時間，這是開始將資料傳送到 Platform 之前必需進行的程序。</li></ul> |

      +++

   1. 使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。

      如需詳細資訊，請參閱Experience Platform檔案中[資料彙集的資料準備](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/data-prep?lang=en#mapping)中的[對應](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/data-prep)。

{{upgrade-final-step}}。




