---
description: 解釋影響Real-time Customer Data Platform（即時CDP）和CJA之間度量一致性的因素。
title: 即時CDP和CJA之間度量的一致性
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# 即時CDP和CJA之間度量的一致性

在現實場景中，無法保證跨Real-time Customer Data Platform（即時CDP）和Customer Journey Analytics(CJA)的指標的一致性。 本文檔解釋了原因。

## CJA尚未使用標識圖

CDP和CJA目前對個人的定義不同。 CJA尚未使用 [標識圖](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant) 告知對人的定義。 即時CDP完全依賴身份圖中的資訊來構建合併的配置檔案。

CJA使用名為 [基於欄位的縫合](/help/connections/cca/overview.md) 它從資料湖中的資料集中提取標識符，並應用自定義邏輯將它們連結在一起。 預計中期後，CJA將開始利用 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) 導出到資料湖，允許跨即時CDP和CJA共用身份概念。

>[!IMPORTANT]
>
>使Adobe Experience Platform身份服務成為所有Adobe Experience Platform應用程式的真實身份來源並不會自動使各應用程式的指標保持一致。 閱讀瞭解原因。

## 應用程式資料靈活性

Experience Platform不會實施嚴格的強制措施來保持即時客戶配置檔案和資料湖之間的資料相同。 某些使用案例在 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) （激活），而其他人則 [資料湖](https://business.adobe.com/blog/basics/data-lake) （報告和查詢服務）。

即時CDP客戶通常沒有100%的Adobe Experience Platform資料池資料進入配置檔案。 這是按設計進行的 — 客戶應專門為Profile啟用湖中的資料。 CJA允許資料分析員自由選擇要從資料庫中引入哪些資料進行分析，而與為即時CDP啟用的資料無關。

## 應用程式特定的修飾符

CJA允許在查詢時進行大量資料修改，如組合欄位、拆分欄位以及其他操作（如貨幣兌換、值消除、會話化和行級篩選）。 這些功能對CDP不可用。

同樣，即時CDP也適用 [合併策略](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) 確定哪些資料將按優先順序排列，哪些資料將合併，以建立一個人的統一視圖。 這些配置牢牢地存在於每個應用程式的邏輯中，不會共用。

## 讀時間與寫時間行為

即時CDP需要使用最新的ID圖形進行時間點配置檔案拼接。

* 即時CDP旨在即時裝配配置檔案資訊以進行激活。

* 它可即時地容納給定用戶對所設定標識符的所有更改。

* 回望窗口由段定義控制。

CJA要求使用ID圖導出在寫入時縫合資料。

* CJA在資料準備好進行分析之前應用複雜的預處理步驟，如索引、共用和分組。

* 給定用戶的身份標識是預處理階段的關鍵輸入；後續更換人員識別符，具有較大的後處理成本。

* 在應用程式級別控制回望窗口。

## TTL（生存時間）和資料接收的差異

即使即時CDP和CJA中的資料集是相同的，即時CDP也只能保留非常有限的歷史窗口。 相比之下，CJA可能擁有多年的資料。 除此之外:

* CJA和即時CDP客戶可以為資料設定自定義的保留窗口，這兩個窗口彼此獨立。

* 即時CDP和CJA在接收資料時有不同的邏輯。 CJA忽略沒有人員ID或時間戳的記錄，對單個配置檔案/人員可能擁有的記錄數有嚴格限制。

* 即時CDP客戶可以在7天內訪問湖中的資料，這主要是為了方便資料登入配置檔案和即席查詢。

* CJA客戶在湖中沒有資料的TTL。 但是，CJA用戶在建立連接時可以在CJA中設定自定義保留窗口。

* Profile Store in Real-time CDP允許客戶可配置的TTL。 客戶可以將此TTL更改為任何他們需要保留在其許可證權限內的內容。

## GDPR（一般資料保護法規）處理的差異

跨即時CDP和資料湖的GDPR和資料衛生的資料處理邏輯大不相同。 我們正在努力採取單一的辦法。

## 資料接收延遲方面的差異

CJA報告包括在資料可用於報告或訪問群體建立之前的某些延遲。 即時CDP通過具有不同延遲的不同系統處理資料。