---
description: 解釋哪些因素會影響Real-time Customer Data Platform（即時CDP）和CJA之間的指標一致性和受眾成員數量。
title: 在即時CDP和CJA之間度量和受眾成員數量的一致性
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# 在即時CDP和CJA之間度量和受眾成員數量的一致性

在現實世界情形中，無法保證跨Real-time Customer Data Platform（即時CDP）和Customer Journey Analytics(CJA)的指標和受眾成員數量的一致性。 本文檔解釋了原因。

在比較即時CDP和CJA之間的受眾成員數時，必須記住這兩種工具的不同用途。 即時CDP使用客戶配置檔案資料將數字型驗瞄準個體消費者，而CJA旨在幫助用戶瞭解關鍵業務指標和細分領域的模式。 雖然從CJA到即時CDP的受眾發佈使這些工具的用戶能夠輕鬆、本地地「激活」洞察力，同時利用CJA中獲得的學習知識，但這些工具的用途卻截然不同。

## 標識配置的差異

即時CDP和CJA目前對於一個人的定義不同。 即時CDP完全依賴於 [標識圖](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) 建立合併的配置檔案。

CJA可配置為使用 [跨渠道分析](/help/connections/cca/overview.md) 它從資料湖中的資料集中提取標識符，並應用自定義邏輯將它們連結在一起。

未來，CJA將能夠使用身份圖。

## 資料集配置中的差異

您可以選擇將一些資料放入即時CDP中，而將一些資料放入CJA中；通常，客戶選擇在CJA中放置比與即時CDP相關的更多歷史資料。 其他資料集對於即時CDP可能比CJA更相關。

## 處理配置的差異

CJA允許在查詢時進行大量資料修改，如組合欄位、拆分欄位以及包括/排除、子字串、值消除、會話化和行級篩選等其他操作。

即時CDP提供了一組不同的資料操作工具。 它適用 [合併策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 確定哪些資料將按優先順序排列，哪些資料將合併，以建立一個人的統一視圖。

## TTL（生存時間）和資料接收的差異

即使即時CDP和CJA中的資料集是相同的，即時CDP也只能保留非常有限的歷史窗口。 相比之下，CJA可能擁有多年的資料。 除此之外:

* CJA和即時CDP客戶可以為資料設定自定義的保留窗口，這兩個窗口彼此獨立。

* 即時CDP和CJA在接收資料時有不同的邏輯。 CJA忽略沒有人員ID或時間戳的記錄，對單個配置檔案/人員可能擁有的記錄數有嚴格限制。

* 即時CDP客戶可以在7天內訪問湖中的資料，這主要是為了方便資料登入配置檔案和即席查詢。

* CJA客戶在湖中沒有資料的TTL。 但是，CJA用戶在建立連接時可以在CJA中設定自定義保留窗口。

* Profile Store in Real-time CDP允許客戶可配置的TTL。 客戶可以將此TTL更改為任何他們需要保留在其許可證權限內的內容。

## 資料接收延遲方面的差異

CJa尚不具備即時CDP的即時功能，因此，CJA報告在資料可用於報告或建立受眾之前會包含一些延遲。 即時CDP通過具有不同延遲的不同系統處理資料。
