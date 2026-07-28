---
title: 資料摘要中的細分
description: 瞭解如何將區段套用至Customer Journey Analytics資料摘要，並瞭解日期範圍區段如何與摘要的報表回溯期互動。
keywords: 點按資料流；資料摘要；資料摘要；分段；區段；日期範圍
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# 資料摘要中的細分

{{release-limited-testing}}

Customer Journey Analytics中的資料摘要支援分段，可讓您篩選每個摘要傳送中包含的列。 您可以在資料檢視層級、摘要層級或兩者套用區段。

## 區段的套用位置

您可以在兩個位置將區段套用至資料摘要：

- **資料檢視**：在資料檢視中設定的區段，適用於使用該資料檢視的所有摘要。
- **資料摘要**：除了任何資料檢視區段外，還直接套用至個別摘要的區段。

兩者皆已設定後，Customer Journey Analytics會將其合併，只有符合兩個區段的列才會納入摘要輸出中。

## 包含日期範圍的區段

您可以在資料摘要中使用包含日期範圍的區段。 不過，報表期間一律由摘要的排程傳送（每小時或每日）定義。 如果區段包含日期範圍，它會在資料摘要視窗中篩選列，而不會移動或展開視窗本身。

這與Analysis Workspace不同，套用包含日期範圍的區段會變更作用中報告期間，以符合區段的日期範圍。

## 區段資格和回顧日期範圍

對於使用人員或工作階段容器的區段，資格由&#x200B;**回顧日期範圍**&#x200B;設定決定，而不只是傳遞期間。 如果某個人符合回顧日期範圍內的資格，則包含該個人在傳遞期間內的所有事件。 容器設定會決定範圍：

- **事件容器**：僅包含符合傳遞期間內的區段條件的事件。
- **工作階段容器**：已包含傳遞期間中合格工作階段的所有事件，這些事件會在回顧日期範圍內評估工作階段資格。
- **人員容器**：在回顧日期範圍內符合資格的任何人員，都會包含傳遞期間內的所有事件。

如需有關回顧日期範圍以及它如何影響區段資格的詳細資訊，請參閱[建立資料摘要](/help/components/exports/cja-data-feeds/create-feed.md)。

