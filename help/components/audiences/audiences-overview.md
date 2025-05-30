---
title: 了解 Customer Journey Analytics 客群發佈概觀
description: 了解 Customer Journey Analytics 中發佈客群的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: be062e350a8c1989be41aeb2774471a3fe1bf524
workflow-type: ht
source-wordcount: '435'
ht-degree: 100%

---

# 客群發佈概觀

您現在可以將 Customer Journey Analytics 中發現的客群建立並發佈到 Adobe Experience Platform 中的[即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)，以用於客戶目標選擇和個人化。 

發佈對象有助於理解情況，來啟用從 Customer Journey Analytics 中獲得的分析並據以採取行動。 這些動作可能包括：

* 將客群用於 Adobe Journey Optimizer 中的歷程。
如需關於使用發佈至 Experience Platform 之客群的更多資訊，請參閱 Journey Optimizer 文件中的[開始使用客群](https://experienceleague.adobe.com/zh-hant/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences)。
* 透過 Experience Platform 目的地，將客群匯出給第三方。
* 使用衍生自 Customer Journey Analytics 中事件型資料的有用屬性，來擴充即時客戶設定檔。
* 在發佈客群後以最小的延遲完成所有這些動作。
如需詳細資訊，請參閱[建立及發佈客群](/help/components/audiences/publish.md)中的[延遲考量](/help/components/audiences/publish.md#latency-considerations)。
* 發佈一次性客群或重複客群。

您在 Customer Journey Analytics 中建立的客群不一定要以個人資料啟用的資料集為主。您可以將歷史資料攝取至 Experience Platform，而無需啟用設定檔的關聯資料集和模式。然後使用這些資料集在 Customer Journey Analytics 中探索有關的客群，並將這些客群發佈到 Experience Platform 中的即時客戶設定檔以進行啟動。

## 重要術語

**客群**：一個身分識別組合或清單，其中包含命名空間和與命名空間有關的特定 ID。 對象可以從 Adobe Experience Platform 或位於其上層的應用程式 (例如 Customer Journey Analytics) 中進行傳輸。 客群可包含混合的命名空間。

**區段**：一組規則，用於評估一個時段內的資料集時會產生資料子集。搭配其他支援服務時，區段可用於建立客群。區段在 Customer Journey Analytics 中進行定義和維護。

## 權限

* 系統會自動授予管理員在 Adobe Admin Console 中的&#x200B;**[!UICONTROL 客群發佈]**&#x200B;權限。 

* 管理員和產品設定檔管理員可以授予個人使用者對&#x200B;**[!UICONTROL 客群建立]**&#x200B;和&#x200B;**[!UICONTROL 客群檢視]**&#x200B;的權限。請參閱[使用者層級存取控制](/help/technotes/access-control.md#user-level-access)，以了解更多資訊。

* 管理員也需要 Experience Platform 中的&#x200B;**[!UICONTROL 管理設定檔]**&#x200B;權限。

## 資料控管和同意

當您在 Customer Journey Analytics 中發佈對象時，將記錄附加到對象中使用之欄位的資料控管標籤和策略。在任何 Adobe Experience 應用程式中啟用客群後，所有相關的資料控管標籤和策略都可供該客群使用，並且可套用適當的強制執行。[進一步瞭解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=zh-Hant#consent-policy)。

## 後續步驟

* [建立及發佈客群](/help/components/audiences/publish.md)
* [管理客群](/help/components/audiences/manage.md)
