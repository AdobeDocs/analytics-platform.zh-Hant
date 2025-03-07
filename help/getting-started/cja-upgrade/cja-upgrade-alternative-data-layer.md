---
title: 升級至Customer Journey Analytics時的替代方法
description: 瞭解升級至Customer Journey Analytics時的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 34%

---

# 升級替代方案：將資料層傳送至 Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="將資料層傳送至 Adobe"
>abstract="您可以透過資料物件將整個資料層傳送至 Adobe，而非透過 XDM 物件傳送資料。<br><br>此選項可讓您將資料層對應至 XDM，無須從頭開始填入 XDM 物件，進而省下實作時間。然而，這種對應會帶來繁重的工作量，因為其中有大量 Adobe 無法快速理解的資料。此一選項也會隨時間變得更加複雜，因為您將來新增到資料中的任何欄位都必須對應至資料流中的 XDM。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="將您的資料層傳送至 Adobe"
>abstract="設定您的實作，以在預計時間將資料傳送至 Adobe，並將 JSON 承載設定為您的完整資料層。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="將各個資料層元素指派給 XDM"
>abstract="將每個資料層元素對應至所需的 XDM 欄位。任何未對應至 XDM 欄位的資料層元素都將被永久刪除，因為 Adobe 無法確定該資料儲存的位置或方式。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

升級至Customer Journey Analytics時，Adobe [建議使用Experience Platform Web SDK的新實作](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。 不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。

您可以將整個資料層傳送至Customer Journey Analytics，而非使用XDM物件來收集資料。 然而，這種替代方案會隨著時間推移而增加複雜性。

## 優點與缺點

此方法與[使用您的AppMeasurement資料收集邏輯搭配Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因為兩種方法都完成相同的工作。

以下是使用此升級替代方案的優缺點：

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不依賴Adobe Analytics命名法(prop、eVar、event等)</li></ul><li>**使用您目前的資料層邏輯**：此方法會使用您目前的資料層邏輯，取代傳統的Web SDK實作。 雖然此方法需要一些設定，但並不需要從頭開始的全新實作，也不需要填入資料元素或標籤規則。 它可讓您將資料層中的資料對應至XDM，而不是從頭開始填入XDM物件。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 <p>因為此選項可讓您將整個使用者端資料層放入資料物件中，並將其傳送到Adobe，這會導致Adobe無法輕鬆解譯的大量資料。 若要允許Adobe解譯資料，您必須使用資料流對應將每個個別欄位對應到所需的XDM欄位。</p></li><li>**硬式實作**：實作受限於傳送點選時資料層提供的內容。 對於具有基本資料需求的組織而言，這可能是一種可接受的做法，但大多陣列織應避免這種僵化的實作，而採用更具彈性的實作，以便填入資料元素。</li><li>**未來的變更更難實作**：您日後新增至資料的任何欄位都必須對應至資料流中的XDM。</li></ul> |

{style="table-layout:auto"}

## 基本步驟

將整個資料層傳送至Customer Journey Analytics的基本步驟如下：

1. 設定您的實作，以在預計時間將資料傳送至 Adobe，並將 JSON 承載設定為您的完整資料層。

1. 將每個資料層元素對應至所需的XDM欄位。

   任何未對應至 XDM 欄位的資料層元素都將被永久刪除，因為 Adobe 無法確定該資料儲存的位置或方式。
