---
title: 升級至Customer Journey Analytics時的替代方法
description: 瞭解升級至Customer Journey Analytics時的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 967d8a957e722a080cd712ea7cf77f26660289da
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 1%

---

# 升級替代方案：將AppMeasurement資料收集與Experience Platform Web SDK和Customer Journey Analytics搭配使用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="搭配使用AppMeasurement邏輯與Web SDK"
>abstract="請透過資料物件以AppMeasurement格式傳送所有變數，而不透過XDM物件傳送資料。<br><br>此選項可讓您將您的AppMeasurement邏輯對應至XDM，而不是從頭開始填入XDM物件，以節省實作時間。 不過，它會隨著時間增加額外的複雜性，因為您日後新增的任何欄位都必須對應至資料流中的XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="變更您的 AppMeasurement 邏輯以指向 Web SDK"
>abstract="此步驟之所以出現，是因為您選擇使用實作捷徑。 複製或變更AppMeasurement邏輯以填入資料物件，而非s物件。 例如，將s.eVar1的指派變更為資料。__adobe.analytics.eVar1並對所有Analytics變數重複。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

升級至Customer Journey Analytics時，Adobe [建議使用Experience Platform Web SDK的新實作](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。 不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。

您可以搭配Web SDK使用AppMeasurement或Analytics擴充功能資料收集邏輯，將資料傳送至Platform和Customer Journey Analytics，而非搭配XDM物件收集資料。 然而，這種替代方案會隨著時間推移而增加複雜性。

## 優點與缺點

此方法與[將整個資料層傳送至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因為兩種方法都完成相同的工作。 (此方法較適合將整個資料層傳送至Adobe。 Prop和eVar會處理資料，因此更加精確。__adobe.analytics._變數名稱_。)

請考量使用此升級替代方案的下列優缺點：

| 優勢 | 缺點 |
|----------|---------|
| 如果您的Adobe Analytics實作已使用Web SDK，此為首選升級路徑。<ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供使用XDM結構描述的選項**：您可以選擇使用現有的Adobe Analytics結構描述，或是建立XDM結構描述，並將資料物件中的欄位對應到您的XDM結構描述。 [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)是彈性的結構描述，可定義您需要的任何欄位，並且僅定義相關的欄位。 <p>請參閱下方的「使用您自己的XDM結構描述」，深入瞭解使用您自己的XDM結構描述的優點。</p></li><li>**保留規則和資料元素**：雖然它確實需要新的規則動作，但您可以重複使用現有的資料元素和規則條件，只需很少的變更。</li><li>**未來校訂**：如果您選擇使用自己的XDM結構描述，則未來的實作更新會比較容易。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**隨著時間增加額外的複雜性**：您日後新增的任何欄位都必須對應至資料流中的XDM。<p>只要將新欄位新增至您的實作，您就可以執行下列任一項作業：</p><ul><li>**選項1：**&#x200B;在資料物件中填入新的任意evar或新prop，然後將它對應到所要的XDM欄位。<p>此程式可促進使用者端實施的一致性，但需要對應功能。</p></li><li>**選項2：**&#x200B;將資料物件保留為舊版實作，並開始只為所有新欄位填入XDM物件。<p>此程式不需要進行對應，但這表示您的部分變數僅位在資料物件中，而其他變數僅位在XDM物件中。 每當需要對實施進行疑難排解時，您需要前往兩個位置。 請確定您的內部工作流程能因應這種情況。</p></li></ul> |

{style="table-layout:auto"}

## 基本步驟

移轉Adobe Analytics實施(AppMeasurement或Analytics擴充功能)以使用Web SDK將資料傳送至Customer Journey Analytics的基本步驟如下：

1. 移轉您的Adobe Analytics實作以使用Adobe Experience Platform Web SDK，並開始將資料傳送至Edge Network。

   此步驟可讓您移轉現有的Adobe Analytics實作，以使用網頁SDK。 您可以選擇將資料傳送至Adobe Analytics，在傳送資料至Adobe Analytics之前驗證一切都在Customer Journey Analytics中運作。 完成此設定且Adobe Analytics中的資料符合要求後，您就可以將資料從Edge Network傳送至Customer Journey Analytics。

   此彈性讓您可以更循序漸進、以更周到的方式升級至Customer Journey Analytics。

   如需如何執行此動作的詳細資訊，請參閱Adobe Analytics檔案中的下列文章：

   * [使用標籤移轉至網頁SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [使用JavaScript移轉至Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. 開始從Edge Network傳送資料至Platform。

   1. 透過資料物件，以AppMeasurement格式傳送所有變數。

      如需詳細資訊，請參閱[對應到Adobe Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/data-var-mapping)的資料物件變數。

   1. 選擇您的結構描述。

      您可以選擇是否使用現有的Adobe Analytics結構描述，或是在您開始使用其他Platform服務時，建立XDM結構描述以更符合組織的需求。

      Adobe建議建立XDM結構描述。 如需詳細資訊，請參閱[建立自訂結構描述以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

      +++使用Adobe Analytics結構描述

      | 優勢 | 缺點 |
      |----------|---------|
      | <p>使用Adobe Analytics結構描述的優點包括：</p><ul><li>容易升級<p>如果您已經透過Adobe Experience Platform Web SDK將資料傳送至Adobe Analytics，您可以新增其他服務至您的資料串流，將資料傳送至Adobe Experience Platform (之後可用於您的Customer Journey Analytics設定)。</p></li></ul> | <p>使用Adobe Analytics結構的缺點包括：</p><ul><li>雖然使用Adobe Analytics結構描述在其可搭配其他Platform應用程式使用方面不會限制您，但它的確會讓結構描述比其他應用程式更複雜。 這是因為Adobe Analytics結構描述包含許多專屬於Adobe Analytics的物件，您的組織不太可能使用。<p>當需要變更結構描述時，您必須篩選數千個未使用的欄位，以尋找需要更新的欄位。</p></li></ul> |

+++

      +++建立XDM結構描述

      | 優勢 | 缺點 |
      |----------|---------|
      | <ul><p>更新至您自己的XDM結構描述的優點包括：</p><ul><li>根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化方案。</li><p>當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。</p></ul> | <p>更新至您自己的XDM結構的缺點包括：</p><ul><li>在開始將資料傳送至Platform之前，需要先更新您的結構描述，這是一個耗時的過程。</li></ul> |

+++

   1. 使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。

      如需詳細資訊，請參閱Experience Platform檔案中[資料彙集的資料準備](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)中的[對應](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)。

   1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。




