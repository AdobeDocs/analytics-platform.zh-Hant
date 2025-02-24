---
title: 升級至Customer Journey Analytics時的替代方法
description: 瞭解升級至Customer Journey Analytics時的替代方法
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 0%

---

# 升級替代方案：將AppMeasurement資料收集與Experience Platform Web SDK和Customer Journey Analytics搭配使用 {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="搭配使用AppMeasurement邏輯與Web SDK"
>abstract="請透過資料物件以AppMeasurement格式傳送所有變數，而不透過XDM物件傳送資料。<br><br>此選項可讓您將您的AppMeasurement邏輯對應至XDM，而不是從頭開始填入XDM物件，以節省實作時間。 不過，它會隨著時間增加額外的複雜性，因為您日後新增的任何欄位都必須對應至資料流中的XDM。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>在回答[Customer Journey Analytics升級檢查清單](https://gigazelle.github.io/cja-ttv/)中的問題時，使用此頁面上的資訊。

升級至Customer Journey Analytics時，Adobe [建議使用Experience Platform Web SDK的新實作](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。 不過，根據數個因素（例如時間表和資源限制），建議的升級步驟可能對您的組織而言不實用。

您可以搭配Web SDK使用AppMeasurement或Analytics擴充功能資料收集邏輯，將資料傳送至Platform和Customer Journey Analytics，而非搭配XDM物件收集資料。 然而，這種替代方案會隨著時間推移而增加複雜性。

## 優點與缺點

此方法與[將整個資料層傳送至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md)互斥，因為兩種方法都完成相同的工作。 (此方法較適合將整個資料層傳送至Adobe。 Prop和eVar會處理資料，因此更加精確。__adobe.analytics._變數名稱_。)

請考量使用此升級替代方案的下列優缺點：

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>**提供在Experience Edge Network中託管資料的所有優點**： <p>這些優點包括：</p><ul><li>高效能的報告與資料可用性，因為Adobe Experience Platform是專為支援[即時個人化使用案例](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)而建置</li><li>在其他Adobe Experience Cloud產品(AJO、RTCDP等)之間整合Experience Cloud資料收集實作</li><li>不僅限於Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 它可讓您將您的AppMeasurement邏輯對應至XDM，而不是從頭開始填入XDM物件。</li></ul> | <ul><li>**需要對應才能將資料傳送至Platform**：當您的組織準備好使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求資料物件中的每個欄位都必須是資料流對應工具中的專案，才能將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li><li>**隨著時間增加額外的複雜性**：您日後新增的任何欄位都必須對應至資料流中的XDM。<p>只要將新欄位新增至您的實作，您就可以執行下列任一項作業：</p><ul><li>**選項1：**&#x200B;在資料物件中填入新的任意evar或新prop，然後將它對應到所要的XDM欄位。<p>此程式可促進使用者端實施的一致性，但需要對應功能。</p></li><li>**選項2：**&#x200B;將資料物件保留為舊版實作，並開始只為所有新欄位填入XDM物件。<p>此程式不需要進行對應，但這表示您的部分變數僅位在資料物件中，而其他變數僅位在XDM物件中。 每當需要對實施進行疑難排解時，您需要前往兩個位置。 請確定您的內部工作流程能因應這種情況。</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## 基本步驟

移轉Adobe Analytics實施(AppMeasurement或Analytics擴充功能)以使用Web SDK將資料傳送至Customer Journey Analytics的基本步驟如下：

1. （選用）移轉Adobe Analytics實作以使用Adobe Experience Platform Web SDK，並開始將資料傳送至Edge Network。

   此為選用步驟，可讓您移轉現有的Adobe Analytics實作以使用網頁SDK，並驗證在Adobe Analytics中一切都正常運作。 完成此設定且Adobe Analytics中的資料符合要求後，您就可以將資料從Edge Network傳送至Customer Journey Analytics。

   此彈性讓您可以更循序漸進、以更周到的方式升級至Customer Journey Analytics。

   如需如何執行此動作的詳細資訊，請參閱Adobe Analytics檔案中的下列文章：

   * [使用標籤移轉至網頁SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [使用JavaScript移轉至Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. 將資料從Edge Network傳送至Customer Journey Analytics。

   1. 透過資料物件，以AppMeasurement格式傳送所有變數。

      如需詳細資訊，請參閱[對應到Adobe Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/data-var-mapping)的資料物件變數。

   1. 如果您尚未建立XDM結構描述，請為您的組織建立。

      如需詳細資訊，請參閱[建立自訂結構描述以搭配您的Customer Journey Analytics Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。

   1. 使用資料流對應將資料物件中的所有欄位對應到您的XDM結構描述。

      如需詳細資訊，請參閱Experience Platform檔案中[資料彙集的資料準備](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)中的[對應](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping)。

