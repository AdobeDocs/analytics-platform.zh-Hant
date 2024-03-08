---
title: 瞭解Customer Journey Analytics對象發佈概觀
description: 了解 Customer Journey Analytics 中發佈對象的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 50%

---

# Customer Journey Analytics對象發佈概觀

您現在可以建立在Customer Journey Analytics中發現的對象，並將其發佈到 [即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant) Adobe Experience Platform中用於客戶目標定位和個人化。

發佈對象有助於理解情況，並據以啟用Customer Journey Analytics中的見解並據以採取行動。 這些動作可能包括：

* 將對象用在 Adobe Journey Optimizer 中的歷程。
* 透過 Experience Platform 目的地功能，將對象匯出給第三方。
* 使用衍生自Customer Journey Analytics中事件型資料的有用屬性，來擴充即時客戶個人檔案。
* 在發佈對象後以最小的延遲完成所有這些動作。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* 發佈一次性對象或循環對象。

您在Customer Journey Analytics中建立的對象不必以為設定檔啟用的資料集為基礎。 您可以將歷史資料擷取至Experience Platform，無需為設定檔啟用關聯的資料集和結構描述。 然後，使用這些資料集探索Customer Journey Analytics中的相關受眾，並將這些受眾發佈到Experience Platform中的即時客戶個人檔案以進行啟用。

## 重要術語

**對象**：一個身分識別組合或清單，其中包含命名空間和與命名空間有關的特定 ID。 對象可以從Adobe Experience Platform和位於其上層的應用程式(例如Customer Journey Analytics)中進行傳輸。 對象可包含混合的命名空間。

**篩選器**：一組規則，用來評估一段時間的資料組合時會產生資料子集。 搭配其他支援服務時，篩選器可用於建立對象流量。 篩選器是以Customer Journey Analytics來定義和維護。

**篩選器** 與 **區段**：Customer Journey Analytics並未使用「區段」的概念，而是採用「篩選器」。 雖然兩者都是包含相似邏輯的一組規則，但產生的輸出內容有所不同。 篩選器是用來縮小資料集的範圍，以做為分析用途。 區段是用來產生身分識別清單，然後可用來進行啟動。 區段會在即時客戶個人檔案中產生對象，而篩選器 (單獨使用) 則不會。 Customer Journey Analytics對象發佈是指一種流程，其中使用Customer Journey Analytics篩選器建立對象，該對象可提供即時客戶個人檔案使用。

## 權限

* 系統會自動授予管理員在 Adobe Admin Console 中的&#x200B;**[!UICONTROL 對象發佈]**&#x200B;權限。 

* 管理員可以將此權限授予給個別使用者。

* 管理員也需要 Experience Platform 中的&#x200B;**[!UICONTROL 管理設定檔]**。

## 資料控管和同意

當您在Customer Journey Analytics中發佈對象時，將會記錄附加到對象中使用之欄位的資料控管標籤和原則。  在任何 Adobe Experience 應用程式中啟用對象後，所有相關的資料控管標籤和策略都可供該對象使用，並且可套用適當的強制執行。[進一步瞭解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=zh-Hant#consent-policy)。

## 後續步驟

* [建立及發佈對象](/help/components/audiences/publish.md)
* [管理對象](/help/components/audiences/manage.md)
