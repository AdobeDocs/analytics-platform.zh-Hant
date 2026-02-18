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
ht-degree: 66%

---

# 設定現有的 Adobe Analytics Web SDK 實作以傳送資料至平台 {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="將 Adobe Analytics 作為服務從資料流中移除"
>abstract="Web SDK 資料完全可使用後，請與平台管理員合作，將 Adobe Analytics 作為服務從資料流中移除。執行此動作之前，請確保您的使用者已從使用 Adobe Analytics 轉換為 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

如果您的Adobe Analytics實作已使用Adobe Experience Platform Web SDK，您可以設定資料串流，開始將資料傳送至Platform。 或者，如果您已經將資料傳送到 Platform，則只需在 Platform 資料集和 Customer Journey Analytics 之間建立連結。


## 優點和缺點

請考量下列優缺點，設定您現有的Adobe Analytics Web SDK實作以傳送資料至Platform：

| 優點 | 缺點 |
|----------|---------|
| 如果您的 Adob&#x200B;&#x200B;e Analytics 實施已經在使用 Web SDK，則這是首選的升級路徑。<ul><li>**提供在 Experience Edge Network**&#x200B;中託管資料的所有優點： <p>這些優點包括：</p><ul><li>Adobe Experience Platform 是為支援 [即時個人化使用案例而建立，因此具有高效能報告和資料可用性](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>在其他 Experience Cloud 產品 (AJO、RTCDP 等) 之間整合 Adob&#x200B;&#x200B;e Experience Cloud 資料收集的實施</li><li>不依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**使用您現有的實施**：雖然這種方法需要進行一些實施變更，但這並不需要從頭開始進行全新實施。您可以使用現有的資料層和程式碼，對實施邏輯進行最少變更，而不會影響現有的 Adob&#x200B;&#x200B;e Analytics 報告。</li><li>**提供使用 XDM 結構描述的選項**：您可以選擇使用現有的 Adob&#x200B;&#x200B;e Analytics 結構描述或建立 XDM 結構描述，並將資料物件中的欄位對應到 XDM 結構描述。[XDM 結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home#xdm-schemas)是一種靈活的結構描述，可以定義您需要的任何欄位，並且只定義相關的欄位。 <p>若要了解更多使用您自己 XDM 結構描述的優勢，請參閱下面的「使用您自己的 XDM 結構描述」。</p></li><li>**保留規則和資料元素**：雖然這需要新的規則操作，但您可以在最少的變更下重複使用現有的資料元素和規則條件。</li><li>**面向未來**：如果您選擇使用自己的 XDM 結構描述，那麼未來的實施更新將會更容易。</li></ul> | <ul><li>**需要對應才能將資料傳送到 Platform**：當您的組織準備好使用 Customer Journey Analytics 時，您必須將資料傳送至 Adob&#x200B;&#x200B;e Experience Platform 中的資料集。此操作要求資料物件中每個欄位都是資料流對應工具中的一個項目，可將其指派給 XDM 結構描述欄位。此工作流程僅需進行一次對應，且不涉及進行實施變更。但是，這是額外進行的步驟，在 XDM 物件中傳送資料時不需要進行。</li><li>**隨著時間增加額外的複雜性**：您日後新增的任何欄位都必須對應至資料流中的XDM。<p>只要將新欄位新增至您的實作，您就可以執行下列任一項作業：</p><ul><li>**選項1：**&#x200B;在資料物件中填入新的任意evar或新prop，然後將它對應到所要的XDM欄位。<p>此程式可促進使用者端實施的一致性，但需要對應功能。</p></li><li>**選項2：**&#x200B;將資料物件保留為舊版實作，並開始只為所有新欄位填入XDM物件。<p>此程式不需要進行對應，但這表示您的部分變數僅位在資料物件中，而其他變數僅位在XDM物件中。 每當需要對實施進行疑難排解時，您需要前往兩個位置。 請確定您的內部工作流程能因應這種情況。</p></li></ul> |

{style="table-layout:auto"}

## 實作步驟

1. 開始從Edge Network傳送資料至Platform。 透過資料物件，以AppMeasurement格式傳送所有變數。

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

   如需詳細資訊，請參閱Experience Platform檔案中[資料彙集的資料準備](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)中的[對應](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)。

{{upgrade-final-step}}
