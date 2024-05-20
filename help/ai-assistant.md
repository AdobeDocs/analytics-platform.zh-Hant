---
description: 如何向Customer Journey Analytics檔案提出問題
title: Adobe Customer Journey Analytics的AI助理
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: d993f46821e6236f4536fea953585219ec8096b5
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---


# Adobe Customer Journey Analytics的AI助理

>[!NOTE]
>
>適用於Customer Journey Analytics的AI助理目前仍在測試階段。 功能及其檔案可能會有所變更。

AI助理是UI功能，可用來導覽及瞭解Adobe Customer Journey Analytics概念和術語。 Customer Journey Analytics中的AI助理已接受其Adobe Experience League檔案的培訓。 被問到問題時，AI Assistant會提供有助於快速學習的答案。

身為新手使用者，您可以使用AI Assistant來瞭解Customer Journey Analytics概念，並且將自己帶入你不熟悉的產品和功能。 身為經驗豐富的使用者，您可以使用AI助理呈現更進階的使用案例或提示與秘訣。

概念問題的一些範例包括：

* 批次和串流擷取之間有何差異？
* Customer Journey Analytics的最佳用途為何？
* 如何設定資料檢視？

說明檔案擷取模型是以Customer Journey Analytics為訓練基礎。 Customer Journey Analytics範圍以外的問題，例如Adobe Target和Adobe Creative Cloud Suite等其他Adobe產品的相關問題，則無法回答。

適用於Customer Journey Analytics的AI助理可用於所有產品層。

>[!IMPORTANT]
>
>目前，用於Customer Journey Analytics的AI助理無法回答有關您組織內資料物件的使用問題。

## 功能存取

在這個第一版中，對AI助理功能的存取受下列引數控制：

* **解決方案存取權**： AI助理可在Customer Journey Analytics中使用，但無法在Adobe Analytics中使用。 Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform應用程式也提供此功能。

* **合約存取**：您的Adobe銷售合約必須包含條款6.2，以允許Adobe在AI/ML模型開發中使用您的資料。

* **許可權**：此 [!UICONTROL Adobe Admin Console] [!UICONTROL 報告工具] 「AI助理檔案」許可權決定此工具的存取權。 此許可權將於5月中旬新增至「報表工具」區段。 您必須確保建立 [產品設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html) 以授予此許可權的Admin Console使用，並手動將使用者新增至此設定檔。

## 在Customer Journey AnalyticsUI中存取AI助理

1. 若要啟動AI助理，請從Customer Journey AnalyticsUI中任何頁面的頂端標題選取AI助理圖示。

   ![AI助理圖示](assets/ai-asst1.png)

   第一次使用AI Assistant時，會出現免責宣告，其中包含使用「Assistant」的一些條款與條件。

1. 在提供的方塊中，詢問AI Assistant的特定自然語言問題。

   ![問題方塊](assets/ai-asst2.png)

1. （可選）若要顯示來源，請按一下 **[!UICONTROL 顯示來源]**，並顯示通知答案的檔案來源。

1. （選擇性）您也可以對任何特定答案的效用提供豎起大拇指或豎起大拇指的投票選項。
