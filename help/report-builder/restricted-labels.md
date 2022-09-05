---
title: 什麼是 Report Builder 中受限制的標籤
description: 說明 Report Builder 中受限制的標籤
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# Report Builder 中受限制的標籤

一般 Customer Journey Analytics 中的任何資料控管相關設定是從 Adobe Experience Platform 繼承的。CJA 與 Adobe Experience Platform 資料控管之間的整合可讓您標示敏感的 CJA 資料強制執行隱私權原則。

在 Experience Platform 使用的資料集上建立的隱私權標籤和原則，可以在 CJA 資料檢視工作流程中出現。這些標籤會阻止或警告從敏感性欄位建立量度和/和維度的使用者。如需資料集的資訊，請參閱 [資料集總覽](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=zh-Hant)。

此外，從 CJA (透過報告、匯出、API 等) 匯出資料時，便會新增其他警告或標籤，以通知使用者報告包含需要以特定方式處理敏感性資訊。

此整合可讓您更輕鬆地管理合規性。在您組織中的資料監管員可以設定限制使用的原則。因此，您的 CJA 使用者可以更秘密地使用資料，了解資料符合資料監管員定義的原則。

如需更多資訊，請參閱 [Customer Journey Analytics 和資料控管](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## 查看 Report Builder 中受限制的資料

CJA 中出現兩個影響報告、下載和共用的 Adobe 定義原則：

* 強制執行 Analytics 原則
* 強制執行下載原則

受這些原則影響的元件會顯示為灰色。當您將滑鼠懸停在套用了原則的元件上時，會顯示一個包含以下內容的註解：**原則已套用於此欄位，禁止使用此資料。**&#x200B;如需詳細資訊，請參閱 [標籤與原則](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html)。

![](assets/rb-restricted-label.png)

## 更新報告包含受限制的資料

如果使用者建立的 Report Builder 報告包含後來受到限制的資料元素，則重新整理報告時會顯示錯誤訊息。

![](assets/error-restricted-data.png)
