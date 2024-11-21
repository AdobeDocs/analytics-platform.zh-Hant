---
description: 如何向Customer Journey Analytics檔案提出問題
title: 適用於 Adobe Customer Journey Analytics 的 AI 助理
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# 適用於 Adobe Customer Journey Analytics 的 AI 助理

AI Assistant是一種對話式體驗，可讓從業人員快速執行工作。 工作內容是瞭解概念、疑難排解問題或搜尋資訊。 AI Assistant也可讓非專家執行專家任務，並提高整體工作品質。

Customer Journey Analytics中的AI助理已接受其Adobe Experience League檔案的培訓。 被問到問題時，AI Assistant會提供有助於快速學習的答案。

身為新手使用者，您可以使用AI Assistant來瞭解Customer Journey Analytics概念，並且將自己帶入你不熟悉的產品和功能。 身為經驗豐富的使用者，您可以使用AI助理呈現更進階的使用案例或提示與秘訣。

概念問題的一些範例包括：

* 批次和串流擷取之間有何差異？
* Customer Journey Analytics的最佳用途為何？
* 如何設定資料檢視？

Customer Journey Analytics範圍以外的問題，例如Adobe Target和Adobe Creative Cloud Suite等其他Adobe產品的相關問題，則無法回答。

適用於Customer Journey Analytics的AI助理可用於所有產品層。

## 產品知識 {#knowledge}

產品知識擷取模型是針對Customer Journey Analytics進行訓練。 其他功能（例如資料分析）將於稍後推出。

| 產品知識 | 範例 |
| --- | --- |
| 點式學習 | <ul><li>Adobe Analytics和Customer Journey Analytics之間有何差異？</li><li>如何建立計算量度？</li></ul> |
| 開啟探索 | <ul><li>如何匯出Workspace專案？</li><li>如何找到重複的Workspace元件？</li></ul> |
| 疑難排解 | <ul><li>資料需要多久才能進入CJA？</li><li>Customer Journey Analytics連線中可以有幾個衍生欄位？</li></ul> |

## 功能存取

下列引數可控制對AI助理功能的存取：

* **解決方案存取**： AI小幫手可在Customer Journey Analytics中使用，但無法在Adobe Analytics中使用。 Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform應用程式也提供此功能。

* **合約存取**：如果您無法使用AI小幫手，請連絡您組織的管理員或Adobe帳戶代表。 貴組織必須同意特定的GenAI相關法律條款，才能使用AI Assistant。

* **許可權**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 報告工具] **[!UICONTROL AI小幫手：產品知識]**&#x200B;許可權決定此工具的存取權。 [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中遵循下列步驟：
   1. 導覽至&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 產品及服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**
   1. 選取您要為其提供[!UICONTROL AI助理存取權的產品設定檔標題：產品知識]。
   1. 在特定產品設定檔中，選取&#x200B;**[!UICONTROL 許可權]**。
   1. 選取![編輯](/help/assets/icons/Edit.svg)以編輯&#x200B;**[!UICONTROL 報告工具]**。
   1. 選取![AddCircle](/help/assets/icons/AddCircle.svg)以將&#x200B;**AI助理：產品知識**&#x200B;新增至&#x200B;**[!UICONTROL 包含的許可權專案]**。

      ![新增許可權](assets/ai-assistant-permissions.png)。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存許可權。

如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md#access-control)。

## 在Customer Journey AnalyticsUI中存取AI助理

1. 若要啟動AI助理，請從Customer Journey AnalyticsUI中任何頁面的頂端標題選取AI助理圖示。

   ![AI助理圖示](assets/ai-asst1.png)

   第一次使用AI Assistant時，會出現免責宣告，其中包含使用「Assistant」的一些條款與條件。

1. 在提供的方塊中，詢問AI Assistant的特定自然語言問題。

   ![問題方塊](assets/ai-asst2.png)

1. （選擇性）若要顯示來源，請按一下[顯示來源] ****，就會顯示通知答案的檔案來源。

1. （選擇性）您也可以對任何特定答案的效用提供豎起大拇指或豎起大拇指的投票選項。

1. （選擇性）您可以針對不適當或有害的內容標示答案。
