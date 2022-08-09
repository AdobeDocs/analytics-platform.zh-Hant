---
title: CJA支援Adobe Experience Platform資料治理
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# CJA支援Adobe Experience Platform資料治理

CJA與CJA的整合 [Adobe Experience Platform資料治理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 允許對敏感CJA資料進行標籤並強制實施隱私策略。

可以在CJA資料視圖工作流中顯示在Experience Platform使用的資料集上建立的隱私標籤和策略。 這些標籤會停止或警告從敏感欄位建立度量和/或維的用戶。

此外，當從CJA（通過報告、導出、API等）導出資料時，會添加警告或標籤以通知用戶報告包含需要以特定方式處理的敏感資訊。

此整合使您能夠更輕鬆地管理法規遵從性。 組織中的資料管理員可以設定策略以限制使用。 因此，您的CJA用戶可以更自信地使用資料，因為它遵守了由資料管理員定義的策略。

## Adobe Experience Platform標籤和政策

在Experience Platform中建立資料集時，可以建立 [資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 資料集中的某些或所有元素。 到目前為止，這些標籤在CJA中還未公開。 在此版本中，您可以在CJA中查看這些標籤。 CJA特別感興趣的是C8標籤，該標籤上寫著「資料不能用於測量貴組織的網站或應用」。

標籤本身並不意味著強制執行這些資料使用標籤。 這就是政策的用途。 通過 [策略服務API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform。

策略有兩個元件：資料標籤和營銷操作，資料消費者可以在受限資料使用策略的上下文中採取該操作。 在CJA中，兩個Adobe定義 [營銷活動](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) 很重要：

* 分析 — 將資料用於分析目的，例如測量、分析和報告您組織的站點或應用的用戶使用情況。

* 將此資料導出到Adobe環境，例如將資料導出到第三方。

將標籤和市場營銷操作與策略綁定在一起，然後開啟策略。 該策略將標籤和營銷操作標為：強制實施此限制。 CJA中出現了兩個Adobe定義的策略：

* 分析策略
* 下載策略

## 在CJA資料視圖中查看資料標籤

在Experience Platform中建立的資料標籤在資料視圖用戶介面的三個位置中顯示：

| 位置 | 說明 |
| --- | --- |
| 架構欄位上的「資訊」按鈕 | 按一下此按鈕可指示當前應用於欄位的資料使用標籤：<p>![](assets/data-label-left.png) |
| 右滑軌下方 [元件設定](/help/data-views/component-settings/overview.md) | 此處列出了任何資料使用標籤：<p>![](assets/data-label-right.png) |
| 將資料標籤添加為列 | 可以將資料標籤作為列添加到資料視圖的「包括的元件」列中。 只需按一下列選擇器表徵圖並選擇資料使用標籤：<p>![](assets/data-label-column.png) |

### CJA中資料治理標籤的篩選

在資料視圖編輯器中，按一下左側路徑中的「篩選器」表徵圖，然後按資料治理標籤篩選資料視圖元件：

![](assets/filter-labels.png)

### CJA中的資料治理策略篩選

您可以檢查是否開啟了阻止某些CJA資料視圖元素用於分析或導出目的的策略。

再次，按一下左欄中的「Filter（篩選器）」表徵圖，在「Data Governance（資料治理）」下按一下「Policies（策略）」：

![](assets/filter-policies.png)

如果開啟策略，則與其關聯的某些資料標籤（如C8）的那些架構欄位不能用於CJA Workspace中的分析或下載（如電子郵件或共用pdf）目的。

請注意

* 不允許將它們添加到資料視圖。 這些欄位將在左欄「架構」欄位清單中灰顯。
* 無法保存已阻止其中欄位的資料視圖。


