---
title: 設定現有的 Adobe Analytics Web SDK 實作以傳送資料至平台
description: 瞭解如何設定您現有的Adobe Analytics Web SDK實作
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 8%

---

# 設定現有的 Adobe Analytics Web SDK 實作以傳送資料至平台 {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="將 Adobe Analytics 作為服務從資料流中移除"
>abstract="Web SDK 資料完全可使用後，請與平台管理員合作，將 Adobe Analytics 作為服務從資料流中移除。執行此動作之前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

如果您的Adobe Analytics實作已使用Adobe Experience Platform Web SDK，您可以設定資料串流，開始將資料傳送至Platform。 或者，如果您已將資料傳送至Platform，只需在Platform資料集和Customer Journey Analytics之間建立連線即可。


## 優點與缺點

請考量下列優缺點，設定您現有的Adobe Analytics Web SDK實作以傳送資料至Platform：

| 優勢 | 缺點 |
|----------|---------|
| 如果您的Adobe Analytics實作已使用Web SDK，此為首選升級路徑。<ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更，而不會影響現有的Adobe Analytics報表。</li><li>**提供使用XDM結構描述的選項**：您可以選擇使用現有的Adobe Analytics結構描述，或是建立XDM結構描述，並將資料物件中的欄位對應到您的XDM結構描述。 [XDM結構描述](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas)是彈性的結構描述，可定義您需要的任何欄位，並且僅定義相關的欄位。 <p>請參閱下方的「使用您自己的XDM結構描述」，深入瞭解使用您自己的XDM結構描述的優點。</p></li><li>**保留規則和資料元素**：雖然它確實需要新的規則動作，但您可以重複使用現有的資料元素和規則條件，只需很少的變更。</li><li>**未來校訂**：如果您選擇使用自己的XDM結構描述，則未來的實作更新會比較容易。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**隨著時間增加額外的複雜性**：您日後新增的任何欄位都必須對應至資料流中的XDM。<p>只要將新欄位新增至您的實作，您就可以執行下列任一項作業：</p><ul><li>**選項1：**&#x200B;在資料物件中填入新的任意evar或新prop，然後將它對應到所要的XDM欄位。<p>此程式可促進使用者端實施的一致性，但需要對應功能。</p></li><li>**選項2：**&#x200B;將資料物件保留為舊版實作，並開始只為所有新欄位填入XDM物件。<p>此程式不需要進行對應，但這表示您的部分變數僅位在資料物件中，而其他變數僅位在XDM物件中。 每當需要對實施進行疑難排解時，您需要前往兩個位置。 請確定您的內部工作流程能因應這種情況。</p></li></ul> |

{style="table-layout:auto"}

## 實作步驟

1. 開始從Edge Network傳送資料至Platform。 透過資料物件，以AppMeasurement格式傳送所有變數。

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

{{upgrade-final-step}}
