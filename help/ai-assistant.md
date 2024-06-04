---
description: 如何向Customer Journey Analytics檔案提出問題
title: Adobe Customer Journey Analytics的AI助理
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: f73e7e9be8593c3bbcad02925ab8b525694a4a15
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---


# Adobe Customer Journey Analytics的AI助理

>[!NOTE]
>
>適用於Customer Journey Analytics的AI助理目前仍在測試階段。 功能及其檔案可能會有所變更。

AI Assistant是一種對話式體驗，可讓從業人員快速執行工作，無論是瞭解概念、疑難排解問題或搜尋資訊。 它也能讓非專家執行專家任務，並提高整體工作品質。

Customer Journey Analytics中的AI助理已接受其Adobe Experience League檔案的培訓。 被問到問題時，AI Assistant會提供有助於快速學習的答案。

身為新手使用者，您可以使用AI Assistant來瞭解Customer Journey Analytics概念，並且將自己帶入你不熟悉的產品和功能。 身為經驗豐富的使用者，您可以使用AI助理呈現更進階的使用案例或提示與秘訣。

概念問題的一些範例包括：

* 批次和串流擷取之間有何差異？
* Customer Journey Analytics的最佳用途為何？
* 如何設定資料檢視？

Customer Journey Analytics範圍以外的問題，例如Adobe Target和Adobe Creative Cloud Suite等其他Adobe產品的相關問題，則無法回答。

適用於Customer Journey Analytics的AI助理可用於所有產品層。

## 產品知識 {#knowledge}

產品知識擷取模型是針對Customer Journey Analytics進行訓練。 其他功能（例如資料分析）將在日後推出。

| 產品知識 | 範例 |
| --- | --- |
| 點式學習 | <ul><li>Adobe Analytics和Customer Journey Analytics之間有何差異？</li><li>如何建立計算量度？</li></ul> |
| 開啟探索 | <ul><li>如何匯出Workspace專案？</li><li>如何找到重複的工作區元件？</li></ul> |
| 疑難排解 | <ul><li>資料需要多久才能進入CJA？</li><li>Customer Journey Analytics連線中可以有幾個衍生欄位？</li></ul> |

## 功能存取

在這個第一版中，對AI助理功能的存取受下列引數控制：

* **解決方案存取權**： AI助理可在Customer Journey Analytics中使用，但無法在Adobe Analytics中使用。 Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform應用程式也提供此功能。

* **合約存取**：如果您無法使用AI助理，請聯絡您組織的管理員或Adobe客戶代表。 貴公司必須同意特定的GenAI相關法律條款，組織才能使用AI Assistant。

* **許可權**：在 [!UICONTROL Adobe Admin Console]，則 [!UICONTROL 報告工具] 「AI助理：產品知識」許可權決定了此工具的存取權。
A [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html) 需要在Admin Console中遵循下列步驟：
   1. 瀏覽至 [!UICONTROL Admin Console] > [!UICONTROL 產品和服務] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL 產品設定檔] > [!UICONTROL 許可權] > [!UICONTROL 編輯報告工具].
   1. 新增「AI助理：產品知識」。
      ![新增許可權](assets/image.png)

## 在Customer Journey AnalyticsUI中存取AI助理

1. 若要啟動AI助理，請從Customer Journey AnalyticsUI中任何頁面的頂端標題選取AI助理圖示。

   ![AI助理圖示](assets/ai-asst1.png)

   第一次使用AI Assistant時，會出現免責宣告，其中包含使用「Assistant」的一些條款與條件。

1. 在提供的方塊中，詢問AI Assistant的特定自然語言問題。

   ![問題方塊](assets/ai-asst2.png)

1. （可選）若要顯示來源，請按一下 **[!UICONTROL 顯示來源]**，並顯示通知答案的檔案來源或來源。

1. （選擇性）您也可以對任何特定答案的效用提供豎起大拇指或豎起大拇指的投票選項。
