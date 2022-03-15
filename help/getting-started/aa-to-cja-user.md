---
title: CJAAdobe Analytics使用手冊
description: 當您的公司將資料從Adobe Analytics移動到Customer Journey Analytics時，從用戶的角度考慮什麼
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 40%

---


# CJAAdobe Analytics使用手冊

恭喜，您的公司至少已將其部分資料移至Customer Journey Analytics! 在開始與Customer Journey Analytics合作時，你會注意到一些巨大的差異和一些相似之處。 本頁旨在解釋那些沒有改變的事以及一些主要差異。

我們還將告訴您，您如何獲得有關新概念的更多資訊，以及進一步的步驟，使您的客戶之旅更輕鬆、更成功。

## 未更改的內容

在報告方面，您熟悉的許多內容沒有改變。 您仍然可以利用Analysis Workspace的力量來分析您的資料，以及Adobe Analytics的儀表板和新版本的Report Builder。 工作區和儀表板的工作方式與傳統Adobe Analytics的工作方式基本相同。 Report Builder有一個新的介面，現在可以在PC、Mac電腦和Excel的Web版本上運行。 在報告方面，不同之處在於您能夠訪問更多要分析的跨渠道資料。 以下是工作區示例

## 新架構

從體系結構上講，Customer Journey Analytics從Adobe Experience Platform獲取資料。 Experience Platform使您能夠集中並標準化來自任何系統或渠道的客戶資料和內容，並應用資料科學和機器學習來改進個性化體驗的設計和交付。

Platform 中的客戶資料以資料集形式儲存，而資料集是由結構和資料批次組成。如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理員將建立與平台中資料的連接，並在這些連接中建立資料視圖。 將資料視圖視為類似於虛擬報告套件。 資料視圖是Customer Journey Analytics報告的基礎。

## 新概念和術語

與傳統的Adobe Analytics相比，CJA中的幾項功能已經更名並重新設計，以符合行業標準。 某些更新的術語包括段、虛擬報表套件、分類、客戶屬性和容器名稱。 耳熟能詳的概念，如電子貨幣和道具，以及它們施加的限制，已不復存在。

### 段現在是「篩選器」


### 虛擬報告套件現在是「資料視圖」


### 分類現在是「查找資料集」

### 客戶屬性現在是「配置式資料集」


### 命中容器現在是「事件」容器

### 訪問容器現在是「會話」容器

### 訪問者容器現在是「人」容器

## 有關Adobe Analytics元件的常見問題

| 問題 | 回答 |
| --- | --- |
| 我可以將 [!DNL Customer Journey Analytics] 中的[!UICONTROL 篩選器] ([!UICONTROL 區段]) 共用/發佈到 Experience Platform Unified Profile 或其他 Experience Cloud 應用程式嗎？ | 還不行，我們正在積極努力地提供這項功能。 |
| 我的舊 [!UICONTROL eVar] 設定發生了什麼事？ | [!UICONTROL Customer Journey Analytics] 中不再使用 Adobe Analytics 舊版本的 [!UICONTROL eVar]、[!UICONTROL prop] 和 [!UICONTROL event]。您有不限數量的結構元素 (維度、量度、清單欄位)。因此，您曾在資料收集程序期間套用的所有歸因設定，現在都會在查詢時套用。 |
| 我所有的工作階段和變數持續性設定現在位於何處？ | [!UICONTROL Customer Journey Analytics 會在報告時套用這些設定，而這些設定現在會顯示於「資料檢視」。]這些設定的變更現在可回溯，使用多個「資料檢視」即可擁有多個版本！ |
| 我們現有的區段/計算量度有何改變？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用 AEP 結構。]換句話說，現有的區段或計算量度都會與 [!UICONTROL Customer Journey Analytics] 不相容。 |
| [!UICONTROL Customer Journey Analytics] 如何處理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 沒有唯一值的限制，因此無需擔心這些限制！] |
| 如果我是現有 [!DNL Data Workbench] 客戶，現在是否可以改用 Customer Journey Analytics？ | 這取決於您的使用案例 - 請與您的 Adobe 帳戶團隊合作。 您目前的使用案例可能已經很適合使用 Customer Journey Analytics！ |
