---
title: CJA支援Adobe Experience Platform資料治理
description: 瞭解AEP中定義的資料標籤和策略如何影響CJA中的報告。
mini-toc-levels: 3
source-git-commit: 82060862c64aae10ea6dd375a8cd65d67ee21704
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---


# CJA支援Adobe Experience Platform資料治理

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

CJA與CJA的整合 [Adobe Experience Platform資料治理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) 允許對敏感CJA資料進行標籤並強制實施隱私策略。

可以在CJA資料視圖工作流中顯示在Experience Platform使用的資料集上建立的隱私標籤和策略。 這些標籤會停止或警告從敏感欄位建立度量和/或維的用戶。

此外，當從CJA（通過報告、導出、API等）導出資料時，會添加警告或標籤以通知用戶報告包含需要以特定方式處理的敏感資訊。

此整合使您能夠更輕鬆地管理法規遵從性。 組織中的資料管理員可以設定策略以限制使用。 因此，您的CJA用戶可以更自信地使用資料，因為它遵守了由資料管理員定義的策略。

## Adobe Experience Platform標籤和政策

在Experience Platform中建立資料集時，可以建立 [資料使用標籤](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) 資料集中的某些或所有元素。 到目前為止，這些標籤在CJA中還未公開。 在此版本中，您可以在CJA中查看這些標籤。 CJA特別感興趣的是以下標籤：

* 的 `C8` 標籤 —  **[!UICONTROL 無測量]**。 此標籤表示無法將資料用於組織網站或應用上的分析。

* 的 `C12` 標籤 —  **[!UICONTROL 無常規資料導出]**。 無法從CJA（通過報告、導出、API等）導出或下載標有此方式的架構欄位

標籤本身並不意味著強制執行這些資料使用標籤。 這就是政策的用途。 通過 [策略服務API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform。

策略有兩個元件：資料標籤和營銷操作，資料消費者可以在受限資料使用策略的上下文中採取該操作。 在CJA中，兩個Adobe定義 [營銷活動](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) 很重要：

* 分析 — 將資料用於分析目的，例如測量、分析和報告您組織的站點或應用的用戶使用情況。

* 將資料導出到第三方 — 即從Adobe環境導出。

將標籤和市場營銷操作與策略綁定在一起，然後開啟策略。 該策略將標籤和營銷操作標為：強制實施此限制。 CJA中出現了兩個Adobe定義的策略並影響報告和下載/共用：

* 強制分析策略
* 強制下載策略


### 在CJA資料視圖中查看資料標籤

在Experience Platform中建立的資料標籤顯示在資料視圖用戶介面的三個位置：

| 位置 | 說明 |
| --- | --- |
| 架構欄位上的「資訊」按鈕 | 按一下此按鈕可指示當前應用於欄位的資料使用標籤：<p>![](assets/data-label-left.png) |
| 右滑軌下方 [元件設定](/help/data-views/component-settings/overview.md) | 此處列出了任何資料使用標籤：<p>![](assets/data-label-right.png) |
| 將資料標籤添加為列 | 可以將資料標籤作為列添加到資料視圖的「包括的元件」列中。 只需按一下列選擇器表徵圖並選擇資料使用標籤：<p>![](assets/data-label-column.png) |

### 篩選資料視圖中的資料治理標籤

在資料視圖編輯器中，按一下左側路徑中的「篩選器」表徵圖，然後按資料治理標籤/s篩選資料視圖元件：

![](assets/filter-labels.png)

按一下 **[!UICONTROL 應用]** 查看哪些元件具有附加標籤。

### 在資料視圖中篩選資料治理策略

您可以檢查是否開啟了阻止某些CJA資料視圖元素用於分析或導出目的的策略。

再次，按一下左欄中的「Filter（篩選器）」表徵圖，在「Data Governance（資料治理）」下按一下「Policies（策略）」：

![](assets/filter-policies.png)

按一下 **[!UICONTROL 應用]** 查看啟用的策略 _?_

### 如何 [!UICONTROL 強制分析] 策略影響工作區項目

如果開啟此策略，則與其關聯的某些資料標籤（如C8）的架構欄位不能用於CJA Workspace中的分析目的。

對於報告，這意味著

* 不能將這些欄位添加到資料視圖中，它們在左欄中呈灰色顯示 [!UICONTROL 架構欄位] 清單框。
* 無法保存已阻止其中欄位的資料視圖。

如果嘗試對包含禁止分析的項的資料視圖執行工作區分析，則會收到類似以下內容的通知：

![](assets/policy-enforce.png)

在單個元件上，消息將類似於以下內容：

![](assets/policy-enforce2.png)

### 如何 [!UICONTROL 強制下載] 策略影響工作區項目

如果開啟此策略，則Workspace項目的任何下載（如電子郵件或共用pdf）都將對敏感欄位進行散列。 您仍然可以在Workspace中對這些欄位進行分析，但是，如果您嘗試通過電子郵件或以其他方式共用項目，則被阻止的欄位將作為散列項出現在.pdf檔案中。

在此處添加螢幕截圖。

### 查看Report Builder中的標籤

請參閱 _此部分_ 的子菜單。 （克莉絲汀醫生的連結）
