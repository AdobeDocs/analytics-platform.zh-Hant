---
description: 說明哪些因素影響 Real-time Customer Data Platform (Real-time CDP) 與 CJA 之間的量度一致性及受眾會籍數。
title: Real-time CDP 與 CJA 之間的量度一致性及受眾會籍數
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 94%

---


# Real-time CDP 與 CJA 之間的量度一致性及受眾會籍數

在真實世界的情境中，無法保證 Real-time Customer Data Platform (Real-time CDP) 與 Customer Journey Analytics (CJA) 之間的量度一致性及受眾會籍數。 本文件將說明原因。

在比較 Real-time CDP 與 CJA 之間的受眾會籍數時，一定要牢記這兩個工具有不同的用途。 Real-time CDP 會使用客戶個人檔案資料來針對個別消費者提供數位體驗，而 CJA 的設計目的則是為了幫助使用者了解關鍵商業量度和區段的模式。 雖然從 CJA 到 Real-time CDP 的受眾發佈可讓這些工具的使用者利用在 CJA 中獲得的知識，以原生方式輕鬆地「啟用」深入分析，但這些工具還是有截然不同的用途。

## 身分設定的差異

Real-time CDP 和 CJA 目前對個人的定義不同。 Real-time CDP 完全仰賴[身分圖表](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=zh-Hant)中的資訊來建立合併的個人檔案。

CJA 可設定為使用[跨管道分析](/help/cca/overview.md)，以便從資料湖中的資料集擷取識別碼，並套用自訂邏輯來一起連結它們。

在未來，CJA 將能夠使用身分圖表。

## 資料集設定的差異

您可以選擇將某些資料放入 Real-time CDP 中，並將某些資料放入 CJA 中；通常客戶選擇放入 CJA 中的歷史資料會多於放入 Real-time CDP 中的資料。 其他資料集與 Real-time CDP 的相關性可能會高於 CJA。

## 處理設定的差異

CJA 允許在查詢時進行廣泛的資料修改，例如合併欄位、分割欄位，以及其他像是包含/排除、子字串、重複值刪除、工作階段化及資料列層級篩選等操作。

Real-time CDP 提供一組不同的資料操作工具。 它會套用[合併原則](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=zh-Hant)以判斷哪些資料將會被優先處理，以及將合併哪些資料以建立個人的統一檢視。

## TTL (存留時間) 與資料擷取的差異

即便 Real-time CDP 和 CJA 中的資料集是相同的，Real-time CDP 可能只會保留非常有限的歷史時段。 相較之下，CJA 可能會保留多年的資料。 除此之外：

* CJA 和 Real-time CDP 客戶可以設定資料的自訂保留時段，且彼此獨立。

* Real-time CDP 和 CJA 有不同的資料擷取邏輯。 CJA 會忽略沒有個人 ID 或時間戳記的記錄，而且對於單一個人檔案/個人可能擁有的記錄數量有嚴格的限制。

* Real-time CDP 客戶可在 7 天內存取資料湖中的資料，主要是為了協助資料上線到個人檔案中及進行臨時查詢。

* 對 CJA 客戶而言，資料湖中的資料沒有 TTL。 不過，在建立連線時，CJA 使用者可以自行在 CJA 中設定自訂保留時段。

* Real-time CDP 中的個人檔案存放區允許使用可供客戶設定的 TTL。 客戶可以將此 TTL 變更為他們保留在授權範圍內所需的任何時間。

## 資料擷取延遲的差異

CJA尚未提供即時CDP的即時功能，因此CJA報表會在資料可供報表或建立受眾之前，先出現一些延遲。 Real-time CDP 會經由具有不同延遲的不同系統來處理資料。
