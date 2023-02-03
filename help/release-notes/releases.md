---
description: 說明 Customer Journey Analytics 的持續功能發行策略
title: Customer Journey Analytics 功能發行
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 40f145d20125c41f3399ab0690a673f01c1817e3
workflow-type: ht
source-wordcount: '391'
ht-degree: 100%

---

# Customer Journey Analytics 功能發行

Customer Journey Analytics 的發行模式是持續傳遞，允許透過可調整、分階段的方法進行未來部署。

## 發行策略

[!UICONTROL Analysis Workspace] 使用功能旗標 (也稱為「切換」) 來控制新功能的可見性，以在完整版發行之前進行有限度的規模測試。此發行策略包含下列階段：

* **有限測試**：分階段的發佈，從內部 Adobe 使用者的測試開始。接著將開放少部分顧客帳戶進行測試，以確保功能符合顧客需求與期望。

* **開始推出**：分階段的發佈推出，從有限測試階段開始。在隨後的幾個月內，該版本對客戶的可用性會從 0% 擴充至 100%。分階段推出會在 Experience Cloud 組織層級進行，因此組織中所有已獲授權的使用者都會獲得相同的體驗。

* **正式發行 (GA)**：已獲授權的 Experience Cloud 組織可使用 100% 的功能，功能發行至此即告完成。

每個功能發行從 RTP 到 GA 的時程可能不盡相同。共同目標是要縮短發行時程，以期在開始發行 (RTP) 後的 2 個月內，就正式發行功能。

## 功能旗標

功能旗標可用於控制新功能在發行期間的可見度。Adobe 建議將 `app.launchdarkly.com` 新增到防火牆的[允許清單](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-Hant)中，以便在發行期間提供最佳體驗。 正式發行後不久，旗標將會移除。

您可以隨時在&#x200B;**「說明 > 關於 Workspace > 有效功能旗標」**&#x200B;檢視有效的功能旗標。

## 福利

分階段發行可讓 Adobe 更精確地調整軟體部署程序，並確保功能在正式發行之前已完整強化。此外，還可讓功能在可供使用時立即發行，而無須依循固定的每月發行時程。

## 常見問答

| 問題 | 回答 |
| --- | --- |
| 我是否可要求搶先使用功能？ | 否。 我們不授與搶先使用的權限。<br>如果您想要搶先體驗 Analytics 的概念，建議您嘗試透過 [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=zh-Hant) 對我們領先業界的創新能力提供意見反應。 |
| 此發行策略是否會影響我使用功能？ | 否。 功能一旦達到正式發行階段，只要功能包含在您的 Analytics 套件中，即可供您使用。 |
