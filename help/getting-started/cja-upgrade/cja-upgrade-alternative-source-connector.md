---
title: 僅使用 Analytics 來源連接器以升級至 Customer Journey Analytics
description: 瞭解如何建立Analytics來源聯結器和對應欄位
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 19%

---

# 更新替代方案：僅使用 Analytics 來源連接器以升級至 Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="僅使用 Analytics 來源連接器"
>abstract="(不建議) 您可以使用 Analytics 來源連接器作為 Customer Journey Analytics 的唯一實作路徑。<br><br>此選項透過快速將資料傳送至 Customer Journey Analytics 以省下實作時間。然而，這種作法有一些缺點，例如較高的延遲和未來難以脫離 Adobe Analytics。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

雖然不建議使用，但您可以使用Analytics來源聯結器作為Customer Journey Analytics的唯一實作路徑。 不過，由於這類升級有其固有的缺點，Adobe建議將Analytics來源聯結器與Experience Platform Web SDK的新實作搭配使用。 如需此建議升級路徑的詳細資訊，請參閱[從Adobe Analytics升級至Customer Journey Analytics時的建議路徑](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)。

## 優點與缺點

使用下表中的資訊來瞭解在升級至Customer Journey Analytics時僅使用來源聯結器的優缺點。

| 優勢 | 缺點 |
|----------|---------|
| <ul><li>最省時又省力的升級路徑。 <p>資料可快速輕鬆地移轉至Customer Journey Analytics。</p></li></ul> | <ul><li>**資料未傳送至Edge Network**： <p>這會導致下列缺點：</p><ul><li>所有升級路徑的報告中[延遲](/help/technotes/guardrails.md#latencies)的最高層級；未針對即時個人化使用案例進行最佳化。</li><li>資料無法與其他Adobe Experience Platform應用程式共用；僅限於Customer Journey Analytics</li><li>依賴Adobe Analytics命名法(屬性、eVar、事件等)</li></ul><li>**日後很難改用Web SDK**：最終，您可能會想要使用Experience Platform Web SDK所提供的優點。 若要開始使用Experience Platform Web SDK，您必須執行新的實作。</li><li>**在您的結構描述中使用Analytics體驗事件欄位群組**：此欄位群組新增許多Customer Journey Analytics結構描述中不需要的Adobe Analytics事件。  這可能會導致Customer Journey Analytics的結構描述更雜亂、更複雜。</li><li>**需要Adobe Analytics和Customer Journey Analytics的授權**：使用Analytics來源聯結器需要您同時為Adobe Analytics和Customer Journey Analytics付費。</li></ul> |

{style="table-layout:auto"}

## 基本步驟

如果您決定使用Analytics來源聯結器作為Customer Journey Analytics的唯一實作路徑，請依照[使用來源聯結器擷取及使用資料中所述的實作步驟操作](/help/data-ingestion/sources.md)。

