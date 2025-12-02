---
title: 僅使用 Analytics 來源連接器以升級至 Customer Journey Analytics
description: 了解如何建立 Analytics 來源連接器和對應欄位
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 94%

---

# 更新替代方案：僅使用 Analytics 來源連接器以升級至 Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="僅使用 Analytics 來源連接器"
>abstract="(不建議) 您可以使用 Analytics 來源連接器作為 Customer Journey Analytics 的唯一實作路徑。<br><br>此選項透過快速將資料傳送至 Customer Journey Analytics 以省下實作時間。然而，這種做法有一些缺點，例如較大的延遲幅度，以及未來難以脫離 Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

雖然不建議這麼做，但您可以使用 Analytics 來源連接器作為 Customer Journey Analytics 的唯一實施路徑。但是，由於原本就有與這類升級有關聯的缺點，Adobe 建議將 Analytics 來源連接器與 Experience Platform Web SDK 的新實施結合使用。若要了解更多關於此建議的升級路徑，請參閱[從 Adobe Analytics 升級至 Customer Journey Analytics 的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。

## 優點和缺點

使用下表中的資訊來瞭解在升級至Customer Journey Analytics時僅使用來源聯結器的優缺點。

| 優點 | 缺點 |
|----------|---------|
| <ul><li>最省時、最省力的升級路徑。 <p>資料可以快速輕鬆地移轉至 Customer Journey Analytics。</p></li></ul> | <ul><li>**資料未傳送至 Edge Network**： <p>這樣會導致以下缺點：</p><ul><li>在所有升級路徑的報告中hapi 最高級別[延遲](/help/technotes/guardrails.md#latencies)；未針對即時個人化使用案例進行最佳化。</li><li>資料不能與其他 Adob&#x200B;&#x200B;e Experience Platform 應用程式共用；此資料僅限於 Customer Journey Analytics 使用</li><li>依賴 Adobe Analytics 命名法 (prop、eVar 和 event 等)</li></ul><li>**未來很難移轉至 Web SDK**：最後，您可能希望獲得 Experience Platform Web SDK 提供的優勢。為了開始使用 Experience Platform Web SDK，您必須進行全新實施。</li><li>**使用結構描述中的 Analytics Experience Event 欄位群組**：此欄位群組新增許多您 Customer Journey Analytics 結構描述中不需要的 Adob&#x200B;&#x200B;e Analytics 事件。這可能會導致比 Customer Journey Analytics 所需的更混亂、更複雜的結構描述。</li><li>**需要 Adob&#x200B;&#x200B;e Analytics 和 Customer Journey Analytics 的授權**：使用 Analytics 來源連接器時，您必須同時支付 Adob&#x200B;&#x200B;e Analytics 和 Customer Journey Analytics 的費用。</li></ul> |

{style="table-layout:auto"}

## 基本步驟

如果您決定使用 Analytics 來源連接器作為 Customer Journey Analytics 的唯一實施路徑，請依照「[使用來源連接器攝取和使用資料](/help/data-ingestion/sources.md)」中所述的實施步驟進行操作。

