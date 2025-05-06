---
description: 說明哪些因素影響 Real-time Customer Data Platform (Real-time CDP) 與 Customer Journey Analytics 之間的量度及客群會籍數的一致性。
title: 量度和客群會籍的一致性
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 7c906e30d54362713f5013c8661ee523938d4b0f
workflow-type: ht
source-wordcount: '625'
ht-degree: 100%

---


# 量度和客群會籍的一致性

在現實情境中，無法保證 Real-time Customer Data Platform (Real-time CDP) 與 Customer Journey Analytics 之間的量度及客群會籍數的一致性。本文件將說明原因。

在比較 Real-time CDP 與 Customer Journey Analytics 之間的客群會籍數時，一定要牢記這兩個工具有不同的用途。Real-time CDP 使用客戶輪廓資料來針對個別消費者提供數位體驗，而 Customer Journey Analytics 的設計目的則是幫助使用者了解關鍵商業量度和區段的模式。雖然從 Customer Journey Analytics 到 Real-time CDP 的客群發佈可讓這些工具的使用者利用在 Customer Journey Analytics 中獲得的知識，以原生方式輕鬆地「啟用」深入分析，但這些工具還是有截然不同的用途。

## 身分識別設定的差異

Real-time CDP 和 Customer Journey Analytics 目前對個人的定義不同。Real-time CDP 完全仰賴[身分識別圖](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=zh-Hant)中的資訊來建立合併的輪廓。

Customer Journey Analytics 可以設定為使用[拼接](../stitching/overview.md)。若您使用[欄位式拼接](/help/stitching/fbs.md)做為拼接機制，可以從資料湖中的資料集指定一個識別碼來拼接該資料集中的資料，目的是透過改進的合併輪廓來提升資料集。若您使用[圖表式拼接](/help/stitching/gbs.md)做為拼接機制，則類似的過程是使用根據指定命名空間的身分識別圖。


## 資料集設定的差異

您可以選擇將部分資料放入 Real-time CDP 中，而部分放入 Customer Journey Analytics 中；通常客戶選擇放入 Customer Journey Analytics 中的歷史資料會多於放入 Real-time CDP 中的資料。其他資料集與 Real-time CDP 的相關性可能會高於 Customer Journey Analytics。

## 處理設定的差異

Customer Journey Analytics 允許在查詢時進行廣泛的資料修改，例如合併欄位、分割欄位，以及其他像是包含/排除、子字串、重複值刪除、工作階段化及資料列層級篩選等操作。

Real-time CDP 提供一組不同的資料操作工具。它會套用[合併原則](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=zh-Hant)以判斷哪些資料將會被優先處理，以及將合併哪些資料以建立個人的統一檢視。

## TTL (存留時間) 與資料擷取的差異

即使 Real-time CDP 和 Customer Journey Analytics 中的資料集相同，Real-time CDP 可能只會保留非常有限的歷史記錄期間。相較之下，Customer Journey Analytics 可能擁有多年的資料價值。除此之外：

* Customer Journey Analytics 和 Real-time CDP 客戶可以設定資料的自訂保留期間，且彼此獨立。

* Real-time CDP 和 Customer Journey Analytics 具有不同的資料擷取邏輯。Customer Journey Analytics 會忽略沒有個人 ID 或時間戳記的記錄，而且對於單一輪廓/個人可能擁有的記錄數量有嚴格的限制。

* Real-time CDP 客戶可在 7 天內存取資料湖中的資料，主要是為了協助資料上線到輪廓中及進行臨時查詢。

* 對 Customer Journey Analytics 客戶而言，資料湖中的資料沒有 TTL。然而，Customer Journey Analytics 使用者可以在建立連線時，自行在 Customer Journey Analytics 中設定自訂保留期間。

* Real-time CDP 中的輪廓存放區允許使用可供客戶設定的 TTL。客戶可以將此 TTL 變更為他們保留在授權範圍內所需的任何時間。

## 資料擷取延遲的差異

Customer Journey Analytics 還沒有 Real-time CDP 的即時功能，因此在資料可用於報告或建立客群之前，Customer Journey Analytics 報告會包含一些延遲。Real-time CDP 會經由具有不同延遲的不同系統來處理資料。
