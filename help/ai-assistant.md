---
description: 如何詢問 Customer Journey Analytics 文件的問題
title: 適用於 Adobe Customer Journey Analytics 的 AI 助理
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 82b36895fe5186f0133c128d434470ea7f875677
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 96%

---


# 適用於 Adobe Customer Journey Analytics 的 AI 助理

AI 助理是一種對話式體驗，可讓從業人員迅速地執行任務。無論該任務是了解概念、問題的疑難排解或搜尋資訊。AI 助理也可讓非專家執行專家任務，並提高整體工作品質。

Customer Journey Analytics 中的 AI 助理是根據 Adobe Experience League 文件進行訓練。在收到所提出的問題時，AI 助理會提供有助於快速學習的回覆。

身為新手使用者，您可以使用 AI 助理學習 Customer Journey Analytics 概念，並了解您還不熟悉的產品和功能。身為經驗豐富的使用者，您可以使用 AI 助理呈現更進階的使用案例或提示與秘訣。

概念問題的一些範例包括：

* 批次攝取和串流攝取之間有何區別？
* Customer Journey Analytics 最適合的用途是什麼？
* 如何設定資料檢視?

無法回答超出 Customer Journey Analytics 範圍的問題，例如有關 Adobe Target 和 Adobe Creative Cloud Suite 等其他 Adobe 產品的問題。

Customer Journey Analytics 的 AI 助理可用於所有的產品層級。

## 產品知識 {#knowledge}

| 產品知識 | 範例 |
| --- | --- |
| 針對性的學習 | <ul><li>Adobe Analytics 和 Customer Journey Analytics 之間有何差異？</li><li>如何建置計算量度？</li></ul> |
| 開放式探索 | <ul><li>如何匯出 Workspace 專案？</li><li>如何找到重複的 Workspace 元件？</li></ul> |
| 疑難排解 | <ul><li>資料進入 CJA 需要多久的時間？</li><li>Customer Journey Analytics 連線中可以有多少個衍生欄位？</li></ul> |

## 資料分析

Data Insights 代理可以透過 Customer Journey Analytics 中的 AI 助理進行存取，是一個生成式 AI 對話代理程式，能迅速有效地回答您的資料相關問題。此代理會使用來自資料視圖的元件以及您的實際資料，在 Analysis Workspace 建置相關的視覺內容。

如需在AI助理中使用Data Insights Agent的詳細資訊，請參閱[使用Data Insights Agent視覺化資料](/help/data-analysis-ai.md)。

## 功能存取

以下參數控制對 AI 助手功能的存取：

* **解決方案存取**：AI 助理可用於 Customer Journey Analytics，但無法在 Adobe Analytics 中使用。也可以用於 Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP 和其他 Experience Platform 應用程式。

* **合約存取權**：如果您無法使用 AI 助理，請聯絡貴組織的管理員或 Adobe 客戶代表。在貴組織可以使用 AI 助理之前，您必須同意關於生成式 AI 的一些法律條款。

* **權限**：在 [!UICONTROL Adobe Admin Console] 中，[!UICONTROL 報告工具]&#x200B;**[!UICONTROL AI 助理：產品知識]**&#x200B;權限決定此工具的存取權。[產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要遵守 [!UICONTROL Admin Console] 中的以下步驟：
   1. 請前往「**[!UICONTROL Admin Console]** > **[!UICONTROL 產品與服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**」。
   1. 選取您想要提供 [!UICONTROL AI 助理：產品知識]存取權的產品設定檔標題。
   1. 在特定的產品設定檔中，選取「**[!UICONTROL 權限]**」。
   1. 選取「![編輯](/help/assets/icons/Edit.svg)」，可編輯「**[!UICONTROL 報告工具]**」。
   1. 選取 ![AddCircle](/help/assets/icons/AddCircle.svg) 以新增「**AI 助理：產品知識**」到「**[!UICONTROL 已包含的權限項目]**」。

      ![新增權限](assets/ai-assistant-permissions.png)。

   1. 選取「**[!UICONTROL 儲存]**」，儲存權限。

請參閱[存取控制概觀](/help/technotes/access-control.md#access-control)，了解更多資訊。

## 存取 Customer Journey Analytics UI 中的 AI 助理

1. 若要啟動 AI 助理，請從 Customer Journey Analytics UI 中任一頁面的頂端標題中選取 AI 助理圖示。

   ![AI 助理圖示](assets/ai-asst1.png)

   第一次使用 AI 助理時，會出現一個包含一些助理使用條款和條件的免責聲明。

1. 在所提供的方塊中，以自然語言向 AI 助理詢問特定的問題。

   ![問題方塊](assets/ai-asst2.png)

1. (可選) 若要顯示來源，請按一下「**[!UICONTROL 顯示來源]**」，然後就會顯示告知答案的文件來源。

1. (可選) 您也可以對任何給定答案的實用程度進行肯定或否定投票。

1. (可選) 您可以標幟不適當或有害內容的答案。
