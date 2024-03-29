---
description: 說明哪些因素影響Real-time Customer Data Platform (Real-time CDP)與Customer Journey Analytics之間量度的一致性及受眾會籍數。
title: Real-time CDP與Customer Journey Analytics之間的量度一致性及受眾會籍數
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 23%

---


# Real-time CDP與Adobe Customer Journey Analytics之間的量度一致性及受眾會籍數

在真實世界的情境中，無法保證Real-time Customer Data Platform (Real-time CDP)與Customer Journey Analytics之間的量度一致性及受眾會籍數。 本文件將說明原因。

在比較Real-time CDP和Customer Journey Analytics之間的受眾會籍數時，請務必牢記這兩個工具的不同用途。 Real-time CDP會使用客戶個人檔案資料來針對個別消費者提供數位體驗，而Customer Journey Analytics的設計目的則是為了協助使用者瞭解關鍵業務量度和區段的模式。 雖然從Customer Journey Analytics到Real-time CDP的受眾發佈可讓這些工具的使用者利用在Customer Journey Analytics中獲得的知識，以原生方式輕鬆地「啟用」深入分析，但這些工具的用途完全不同。

## 身分設定的差異

Real-time CDP和Customer Journey Analytics目前對個人的定義不同。 Real-time CDP 完全仰賴[身分圖表](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html)中的資訊來建立合併的個人檔案。

Customer Journey Analytics可設定為使用 [拼接](../stitching/overview.md) 會從資料湖中的資料集擷取識別碼，並套用自訂邏輯來一起連結它們。

Customer Journey Analytics未來將能使用身分圖表。

## 資料集設定的差異

您可以選擇將某些資料放入Real-time CDP中，並將某些資料放入Customer Journey Analytics；通常，客戶選擇放入Customer Journey Analytics的歷史資料比Real-time CDP更多的資料。 其他資料集與Real-time CDP的相關性可能高於Customer Journey Analytics。

## 處理設定的差異

Customer Journey Analytics允許在查詢時進行廣泛的資料修改，例如合併欄位、分割欄位，以及其他像是包含/排除、子字串、重複值刪除、工作階段化及列層級篩選等操作。

Real-time CDP 提供一組不同的資料操作工具。它會套用[合併原則](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html)以判斷哪些資料將會被優先處理，以及將合併哪些資料以建立個人的統一檢視。

## TTL (存留時間) 與資料擷取的差異

即使Real-time CDP和Customer Journey Analytics中的資料集相同，Real-time CDP可能只會保留非常有限的歷史時段。 相較之下，Customer Journey Analytics則可能有多年的資料量。 除此之外：

* Customer Journey Analytics和Real-time CDP客戶可以設定資料的自訂保留時段，且彼此獨立。

* Real-time CDP和Customer Journey Analytics有不同的資料擷取邏輯。 Customer Journey Analytics會忽略沒有個人ID或時間戳記的記錄，而且對於單一設定檔/個人可能擁有的記錄數量有嚴格的限制。

* Real-time CDP 客戶可在 7 天內存取資料湖中的資料，主要是為了協助資料上線到個人檔案中及進行臨時查詢。

* 對Customer Journey Analytics客戶而言，資料湖中的資料沒有TTL。 不過，在建立連線時，Customer Journey Analytics使用者可以自行在Customer Journey Analytics中設定自訂保留期間。

* Real-time CDP 中的個人檔案存放區允許使用可供客戶設定的 TTL。客戶可以將此 TTL 變更為他們保留在授權範圍內所需的任何時間。

## 資料擷取延遲的差異

Customer Journey Analytics尚不具備Real-time CDP的即時功能，因此，在資料可用於報表或建立受眾之前，Customer Journey Analytics報表會包含一些延遲。 Real-time CDP 會經由具有不同延遲的不同系統來處理資料。
