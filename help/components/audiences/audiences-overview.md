---
title: CJA觀眾發佈概述
description: 學習Customer Journey Analytics中的受眾出版概念
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 3%

---


# CJA觀眾發佈概述

現在，您可以將在Customer Journey Analytics(CJA)中發現的受眾發佈到 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=tw) 在Adobe Experience Platform的客戶定位和個性化。 使用即時客戶配置檔案，您可以通過組合來自多個渠道的資料（包括線上、離線、CRM和第三方）來查看每個客戶的整體視圖。 配置檔案允許您將客戶資料整合到一個統一視圖中，為每次客戶交互提供一個可操作且時間戳記的帳戶。

發佈受眾為對CJA中的洞見採取行動提供了明確的途徑。 這些操作可能包括：

* 向此受眾發送電子郵件。
* 正在向此受眾發送推送消息。
* 利用觀眾去Adobe Journey Optimizer。
* 通過Experience Platform目的地將觀眾導出到第三方。

## 重要術語

**觀眾**:具有與該命名空間相關的命名空間和特定ID的標識集或清單。 觀眾可從Adobe Experience Platform轉運，並可在其上放置應用程式（如CJA）。 受眾可以包含混合命名空間。

**篩選**:一組規則，當在一組資料上計算一個時間段時，生成資料子集。 當與其它支援服務結合時，可在建立受眾的過程中使用過濾器。 過濾器在CJA中定義和維護。

**篩選器** 與 **段**:CJA不使用「段」的概念，而是使用「過濾器」。 雖然這兩種規則都是一組可以包含相似邏輯的規則，但它們會產生不同的輸出。 過濾器用於縮小資料集以便進行分析。 段用於生成可用於激活的身份清單。 網段在即時客戶概要檔案中產生受眾，而篩選器（單獨）則不會。 「CJA受眾發佈」是我們使用CJA篩選器建立可由即時客戶配置檔案使用的受眾的過程。

## 權限

管理員將自動獲得 [!UICONTROL 受眾發佈] 在Adobe Admin Console。 他們可以將此權限授予單個用戶。

## 後續步驟

* [建立和發佈受眾](/help/components/audiences/publish.md)
* [管理受眾](/help/components/audiences/manage.md)

