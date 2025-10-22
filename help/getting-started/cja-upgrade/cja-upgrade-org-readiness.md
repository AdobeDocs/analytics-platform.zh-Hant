---
title: 從 Adobe Analytics 升級至 Customer Journey Analytics
description: 了解關於從 Adobe Analytics 升級至 Customer Journey Analytics 的建議步驟
role: Admin
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 7c0342a68f75774fd7b29979d3ce610f22d047ae
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 8%

---

# 準備您的組織以升級至Customer Journey Analytics

成功升級的一部分(如[從Adobe Analytics升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)中所述)是專注在特定營運考量上準備您的組織。 若要準備您的組織，建議您：

* 獲得主要利害關係人的認同和認同

* 定義並記錄您的目標

* 設定現實且深思熟慮的時間表

* 定義貢獻者的明確責任

## 利害關係人的認同和協調

您組織中的關鍵利害關係人和決策者需要調整以符合Customer Journey Analytics的升級。

以下各節將說明您獲得利害關係人一致性的方式。

### 關注價值

專注於Customer Journey Analytics可為貴組織帶來的價值，以及如何加速達成您的業務目標。

下表涵蓋您想要強調的一些主要功能。

| 功能 | 優點 | 範例 |
|---------|----------|---------|
| **[各種資料的容納](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home)** | Customer Journey Analytics結合Experience Platform掌握各種資料結構和型別的能力。 | 零售組織可透過將下列型別的資料整合至單一檢視，提供完整客戶歷程的可見度： <ul><li>網路點按資料流交易</li><li>行動應用程式交易</li><li>店內交易</li><li>CRM和忠誠度資料</li></ul> |
| **[跨管道分析](/help/use-cases/cross-channel/cross-channel.md)** | 透過統一來自各種網路、行動和離線屬性的資料，啟用跨各種管道的客戶行為的單一整合檢視。 | 從多個管道收集資料的零售組織可以執行以下型別的分析：<p>購物者按一下付費搜尋廣告、線上上瀏覽牛仔褲、收到推播通知，然後兩天後在店內購買。 此統一的觀點可啟用精確的跨管道歸因，顯示數位接觸點對店內銷售的貢獻度。 此外，也支援更精確的細分，例如以「線上瀏覽、店內購買」的客製化優惠方案來鎖定客戶。 此外，它在一個儀表板中提供清晰、全管道的收入報告，以全面瞭解客戶行為來取代分散的、孤立的深入分析。 |
| **[報告時間處理](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | 套用可追溯的設定，並建立多個版本的變數持續性，而無需變更基礎資料的收集方式。 | 由於Customer Journey Analytics可讓您即時建立及調整量度、維度和歸因模型，而不需重新擷取或重新處理資料，因此零售組織可瞭解最近的社交活動如何影響線上和店內銷售，而無須要求工程部門重建資料集。 他們可以立即將歸因模式從上次接觸變更為首次接觸或自訂規則型歸因。 |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | 協助行銷人員瞭解內容如何影響企業已定義的關鍵績效指標。 除了行為資料之外，Content Analytics 還會收集關於內容使用方式和內容產生影響的資料。 | 透過整合網頁、應用程式、電子郵件，甚至店內資料，零售組織就能確切瞭解他們建立的每一項數位內容對客戶歷程和轉換的貢獻。 <p>零售組織可發現，熱門社群媒體平台上的「夏季牛仔布風格指南」可促進忠誠會員的高度參與，且這些會員在一週內店內購買牛仔布的可能性增加40%。</p> |

### 指定高階主管支援人

尋找並指派組織內的高階主管支援人。 此高階主管支援人需要瞭解Customer Journey Analytics將如何加速達成您的業務目標。

高階主管支援人至關重要，因為他們：

* 組織中的Customer Journey Analytics達人

* 移除障礙

* 核准資源

### 確保整個組織的主要領導提供安全支援

在高階主管支持者的協助下，確保整個組織的其他重要領導提供支援。 貴組織下列領域的主管人員瞭解Customer Journey Analytics的好處，並願意為成功的實施作出貢獻，這點極為重要：

* Analytics

* 行銷

* IT

* 法律與法規遵循

* 個別業務單位

## 開發升級與通訊計畫

### 開發升級計畫並分發給利害關係人

升級計畫可能包含下列資訊：

* 清楚說明進行升級的原因。 例如，說明使用者以及組織或企業整體的優點。 如需有關權益的詳細資訊，請參閱[專注於值](#focus-on-value)。

* 一般時間表，例如計劃開始升級的時間、關鍵里程碑的概要，以及計畫升級完成時間的預估值。

* 表示使用者何時可以開始接受正式培訓以學習如何使用Customer Journey Analytics。 如需詳細資訊，請參閱[訓練整個組織的一般使用者](#train-end-users-throughout-your-organization)。

* 關於誰是升級的負責人，以及人們如何或何時可以提出問題的資訊。

### 建立通訊計畫

通訊計畫可能包含下列考量事項：

* 將通訊傳送給利害關係人和使用者的定義步調

* 將傳送的資訊型別的大綱

* 誰將傳送通訊的計畫

* 定義意見回圈，讓利害關係人和使用者可以提出問題或提供意見回饋

## 評估並稽核Adobe Analytics實作

對您的Adobe Analytics實作執行徹底的評估和稽核，重點放在下列關鍵領域：

* 目前使用者

* 使用者存取權

* 專案

* 業務流程

* 自訂元件

請參閱下列資源，以協助收集此資訊：

* [Analytics 庫存](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/analytics-inventory)

  提供組織內專案、區段、計算量度、報表套裝和使用者數量的相關資訊。

* [準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](https://experienceleague.adobe.com/zh-hant/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  提供有關如何準備移轉元件、專案和使用者的資訊。

## 識別擁護者和率先採用者

識別整個組織中的Champions。 這些冠軍應該是：

* Adobe Analytics進階使用者

* 可快速掌握Customer Journey Analytics

* 隨著Customer Journey Analytics更廣泛地推出，可供其他人提供協助和指導

## 訓練整個組織的一般使用者

* 提供實作訓練，著重於Customer Journey Analytics中資料模型、報表範例和新功能的差異。

* 提供即時課程（研討會或營業時間）和隨選資源（教學課程影片、動態Wiki頁面及內部檔案）。

* 將使用者引導至Experience League的相關培訓、教學課程和檔案。

  以下資源可幫助您快速入門：

   * [Customer Journey Analytics教學課程](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/overview)

   * [什麼是 Customer Journey Analytics？](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

   * [Customer Journey Analytics簡介](https://experienceleague.adobe.com/zh-hant/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

   * [Customer Journey Analytics 功能支援](/help/getting-started/aa-vs-cja/cja-aa.md)

## 遵循建議的升級步驟

當您準備好要開始升級程式時，請依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或《Customer Journey Analytics升級指南》中動態產生的升級步驟操作。 若要自 Customer Journey Analytics 存取指南，請選取「**[!UICONTROL 工作區]**」索引標籤，然後在左側面板中選取「**[!UICONTROL 升級至 Customer Journey Analytics]**」。接著按照畫面上的指示進行操作。

