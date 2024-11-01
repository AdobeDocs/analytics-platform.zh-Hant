---
title: 瞭解Customer Journey Analytics對象發佈概觀
description: 了解 Customer Journey Analytics 中發佈客群的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 42%

---

# 對象發佈概觀

您現在可以在Adobe Experience Platform中建立並在Customer Journey Analytics中發現的對象，並發佈到[即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)，以用於客戶目標定位和個人化。

發佈對象有助於理解情況，並據以啟用Customer Journey Analytics中的見解並據以採取行動。 這些動作可能包括：

* 將客群用在 Adobe Journey Optimizer 中的歷程。
* 透過 Experience Platform 目的地功能，將客群匯出給第三方。
* 使用衍生自Customer Journey Analytics中事件型資料的有用屬性，來擴充即時客戶個人檔案。
* 在發佈客群後以最小的延遲完成所有這些動作。[了解更多](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* 發佈一次性對象或循環對象。

您在Customer Journey Analytics中建立的對象不必以為設定檔啟用的資料集為基礎。 您可以將歷史資料擷取至Experience Platform，無需為設定檔啟用關聯的資料集和結構描述。 然後，使用這些資料集探索Customer Journey Analytics中的相關受眾，並將這些受眾發佈到Experience Platform中的即時客戶個人檔案以進行啟用。

## 重要術語

**客群**：一個身分識別組合或清單，其中包含命名空間和與命名空間有關的特定 ID。 對象可以從Adobe Experience Platform和位於其上層的應用程式(例如Customer Journey Analytics)中進行傳輸。 客群可包含混合的命名空間。

**篩選器**：一組規則，用來評估一段時間的資料組合時會產生資料子集。 搭配其他支援服務時，篩選條件可用於建立客群。 篩選器是以Customer Journey Analytics來定義和維護。

**篩選器**&#x200B;與&#x200B;**區段**：Customer Journey Analytics不使用&#x200B;*區段*&#x200B;的概念，而是使用&#x200B;*篩選器*。 雖然兩者都是包含相似邏輯的一組規則，但產生的輸出內容有所不同。 篩選器是用來縮小資料集的範圍，以做為分析用途。 區段是用來產生身分識別清單，然後可用來進行啟動。 細分群體會在即時客戶輪廓中產生客群，而篩選條件 (單獨使用) 則不會。 Customer Journey Analytics對象發佈是指一種流程，其中使用Customer Journey Analytics篩選器建立對象，該對象可提供即時客戶個人檔案使用。

## 權限

* 系統會自動授予管理員在Adobe Admin Console中的&#x200B;**[!UICONTROL 對象發佈]**&#x200B;許可權。

* 管理員和產品設定檔管理員可以授與個別使用者的&#x200B;**[!UICONTROL 對象建立]**&#x200B;和&#x200B;**[!UICONTROL 對象檢視]**&#x200B;許可權。 如需詳細資訊，請參閱[使用者層級存取控制](/help/technotes/access-control.md#user-level-access)。

* 管理員也需要Adobe Experience Platform中的&#x200B;**[!UICONTROL 管理設定檔]**&#x200B;許可權。

## 資料控管和同意

當您在Customer Journey Analytics中發佈對象時，將會記錄附加到對象中使用之欄位的資料控管標籤和原則。  在任何 Adobe Experience 應用程式中啟用客群後，所有相關的資料控管標籤和策略都可供該客群使用，並且可套用適當的強制執行。[進一步瞭解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy)。

## 後續步驟

* [建立及發佈客群](/help/components/audiences/publish.md)
* [管理客群](/help/components/audiences/manage.md)
