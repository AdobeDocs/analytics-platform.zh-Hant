---
title: CJA 對象發佈總覽
description: 了解 Customer Journey Analytics 中發佈對象的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 100%

---

# CJA 對象發佈總覽

>[!NOTE]
>
>此功能目前在[有限測試](/help/release-notes/releases.md)中。

您現在可以將 Customer Journey Analytics (CJA) 中發現的對象建立並發佈到 Adobe Experience Platform 中的[即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant) (RTCP)，以用於客戶目標定位和個人化。 

發佈對象有助於理解情況，來啟用從 CJA 中獲得的分析並據以採取行動。 這些動作可能包括：

* 將對象用在 Adobe Journey Optimizer 中的歷程。
* 透過 Experience Platform 目的地功能，將對象匯出給第三方。
* 使用衍生自 CJA 中事件型資料的有用屬性，來擴充即時客戶個人檔案。
* 在發佈對象後以最小的延遲完成所有這些動作 (幾分鐘)
* 發佈單次對象或重複對象

## 重要術語

**對象**：一個身分識別組合或清單，其中包含命名空間和與命名空間有關的特定 ID。 對象可以從 Adobe Experience Platform 或位於其上層的應用程式 (例如 CJA) 中進行傳輸。 對象可包含混合的命名空間。

**篩選器**：一組規則，用來評估一段時間的資料組合時會產生資料子集。 搭配其他支援服務時，篩選器可用於建立對象流量。 篩選器是在 CJA 中定義和維護。

**篩選器**&#x200B;與&#x200B;**區段**：CJA 並未使用「區段」的概念，而是採用「篩選器」。 雖然兩者都是包含相似邏輯的一組規則，但產生的輸出內容有所不同。 篩選器是用來縮小資料集的範圍，以做為分析用途。 區段是用來產生身分識別清單，然後可用來進行啟動。 區段會在即時客戶個人檔案中產生對象，而篩選器 (單獨使用) 則不會。 CJA 對象發佈是指一種流量，其中使用 CJA 篩選器建立對象，該對象可提供即時客戶個人檔案使用。

## 權限

系統會自動授予管理員在 Adobe Admin Console 中的[!UICONTROL 對象發佈]權限。 管理員可為個別使用者授予此權限授。

## 後續步驟

* [建立及發佈對象](/help/components/audiences/publish.md)
* [管理對象](/help/components/audiences/manage.md)
