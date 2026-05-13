---
title: Customer Journey Analytics搶鮮版發行說明
description: 檢視最新Customer Journey Analytics發行前注意事項
feature: Release Notes
hide: true
exl-id: 61982e38-b43a-41b5-85e0-59ed374463a9
TQID: https://experienceleague.adobe.com/V4jdf363mA1GmsYjZ7yv3MiAMc7sJ7U3s7kXeY47Uyo
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: f2ef16dc-055a-4bb7-baa5-7039653f3966
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 662
ht-degree: 81%

---

# Adobe Customer Journey Analytics搶鮮版發行說明

>[!IMPORTANT]
>
>本檔案旨在當月發行說明的&#x200B;**預覽**。 發行專案可能會有所變更，且可能會在最終發行中新增或移除。

這些發行說明涵蓋 2025 年 6 月 2 日至 7 月 15 日的發行期間。 Adobe Customer Journey Analytics 版本會在[持續傳遞模式](releases.md)上運作，允許以擴充性更高且可分階段進行的方式進行功能部署。

如需Adobe Experience Platform及其應用程式發行說明，請參閱下列檔案：

* [Adobe Experience Platform](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [聯合客群構成](https://experienceleague.adobe.com/en/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/en/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 新功能或更新功能

| 功能 | 說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **當游標停留時，Analysis Workspace 的左側面板不再開啟和關閉** | 您可以使用 Analysis Workspace 中的左側面板，將元件、面板和視覺效果等內容新增至專案。 將游標停留在最左側的其中一個圖示來暫時開啟左側面板的選項不再適用。 現在改為按一下其中一個圖示可保持面板開啟，再按一下相同的圖示可將面板關閉。 |  | 2025 年 6 月 2 日 <p>(原計劃於 2025 年 5 月 29 日發行)</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition 透過提供可操作的客戶洞察來推動收入成長，幫助 B2B 公司協調其行銷、銷售和產品團隊。 由於客戶是資料模型的中心，因此所有分析都集中在客戶歷程上。 在人員和時間型事件上新增實體層 (客戶、銷售機會和購買群組)，即可建立完整的 B2B 行銷和收入生命週期的完整樣貌。 [了解更多](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025 年 6 月 18 日 |
| **在 Report Builder 中支援安全目標** | 新的匯出目標已新增至 Report Builder 增益集。 支援以下雲端儲存空間目標： <ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 2025 年 6 月 18 日 |
| **全新預覽體驗** | 用於預覽區段、計算量度和其他內容的預覽面板，現已改用橫條圖視覺效果來取代原本的環形圖視覺效果。 |  | 2025 年 6 月 18 日 |
| **已修改歸因模型對話框** | 您現在可以在歸因模型對話框中分別定義容器及時段。 |  | 2025 年 6 月 18 日 |
| **連線圖** | 新的[連線圖介面](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection#connection-map)可用來視覺化顯示您的連線設定。 |  | 2025 年 6 月 18 日 |
| **在 Analysis Workspace 專案中新增和檢視註解** | Analysis Workspace 中的新[註解功能](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)，讓您可以在 Analysis Workspace 專案的內容中共用洞察及提出問題。 這樣可以簡化關於資料的討論過程，讓對話聚焦於所討論的資料範圍內。 您可以 <ul><li>對任何您有權存取的 Analysis Workspace 專案留下註解</li><li>針對視覺內容中的特定點留下註解，或對專案留下一般註解</li><li>標記其他使用者，通知他們您有留下註解</li><li>管理現有註解 (編輯、釘選、解決等)</li></ul>Customer Journey Analytics 管理員可以[於組織層級停用註解](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)。 專案所有者可以[在專案層級停用註解](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)。 |  | 2025 年 6 月 25 日 <p>(原計劃於 2025 年 5 月 29 日發行)</p> |
