---
description: 瞭解AEP客戶AI如何與CJA中的Workspace整合。
title: 將客戶AI與CJA整合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 23c257c6b00b919b8e70b4cef58b5187227ec2a6
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 0%

---

# 將客戶AI與CJA整合

[客戶AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)作為Adobe Experience Platform智慧服務的一部分，向營銷人員提供在個人層面生成客戶預測的能力。

在影響因素的幫助下，客戶AI可以告訴您客戶可能做什麼以及為什麼。 此外，營銷人員可以從客戶人工智慧預測和洞察中獲益，通過提供最合適的優惠和資訊來個性化客戶體驗。

客戶AI依靠個人行為資料和個人資料資料進行傾向評分。 客戶AI具有靈活性，它可以接收多個資料源，包括Adobe Analytics、Adobe Audience Manager、消費者體驗事件資料和體驗事件資料。 如果使用Experience Platform源連接器輸入Adobe Audience Manager和Adobe Analytics資料，則模型會自動選取標準事件類型來訓練和計分模型。 如果導入自己的「體驗事件」資料集而不使用標準事件類型，則任何相關欄位都需要映射為自定義事件或配置檔案屬性（如果要在模型中使用）。 這可以在Experience Platform中的「客戶AI」配置步驟中完成。&#x200B;

客戶AI與Customer Journey Analytics(CJA)整合，以便客戶AI支援的資料集可以在CJA中的資料視圖和報告中得到利用。 通過此整合，您可以

* **跟蹤一段時間內用戶的傾向分數**。 示例用例：酒店客戶在酒店的音樂會場地購買展示票的可能性有多大？
* **分析哪些成功事件或屬性與傾向得分相關**。&#x200B;示例用例：我想瞭解與傾向得分相關的屬性或成功事件。
* **跟蹤客戶傾向在不同評分運行期間的錄入流**。 示例用例：我想瞭解一些最初傾向低的人，隨著時間推移，他們變成了傾向高的人&#x200B;。
* **看傾向的分佈**。 用例：我想瞭解我的傾向分數的分佈，可以更精確地分析我的部分。&#x200B;示例：零售商想以50美元的價格進行特定促銷。 由於預算等原因，他們可能只想進行非常有限的促銷。 他們分析資料，並決定只針對80%以&#x200B;上的客戶。
* **看看特定群體在一段時間內完成某項行動的傾向**。 用例：我想跟蹤一個特定群體。 這和第一個相似，但你可以追蹤一個特定的群體&#x200B;。 酒店示例：營銷人員可以跟蹤他們的銅製和銀制，銀制和金制。 然後，他們可以看到，每個群體都傾向於隨時間預訂酒店。&#x200B;

## 工作流程

在CJA中的輸出工作之前，在Adobe Experience Platform執行某些步驟。

### 步驟1:配置客戶AI實例

準備好資料並準備好所有憑據和架構後，請按照 [配置客戶AI實例](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) 在Adobe Experience Platform。

### 步驟2:設定到客戶AI資料集的CJA連接

在CJA，你現在可以 [建立一個或多個連接](/help/connections/create-connection.md) Experience Platform為客戶AI檢測的資料集。 每種預測（如「升級帳戶的可能性」）都相當於一個資料集。 這些資料集以「客戶AI Scores in EE Format - name_of_application」前置詞顯示。

>[!IMPORTANT]
>
>如果在步驟1中的配置期間啟用切換以啟用CJA的分數，則每個客戶AI實例具有兩個輸出資料集。 一個輸出資料集以配置檔案XDM格式顯示，一個以體驗事件XDM格式顯示。

![CAI得分](assets/cai-scores.png)

![建立連線](assets/create-conn.png)

以下是CJA作為現有或新資料集的一部分引入的XDM架構的示例：

![CAI模式](assets/cai-schema.png)

(請注意，此示例是配置檔案資料集；同一組架構對象將是CJA將獲取的「體驗事件」資料集的一部分。 「體驗事件」資料集將包含時間戳作為分數日期。) 此模型中的每個客戶都會有得分、得分日期等。 關聯。

### 第3步：基於這些連接建立資料視圖

在CJA中，您現在可以 [建立資料視圖](/help/data-views/create-dataview.md) 與作為您建立的連接的一部分引入的維（如分數、分數日期、概率等）和度量。

![建立資料視圖](assets/create-dataview.png)

### 第4步：Workspace中CAI成績的報告

在CJA Workspace中，現在可以建立新項目並拉入可視化效果。

下面是一個包含CAI資料的Workspace項目的示例，該項目在一段時間內將用戶的傾向分數&#x200B;趨勢化，如堆積條形圖：

![記分時段](assets/workspace-scores.png)

下表顯示了段具有高傾向或低傾向的原因代碼&#x200B;:

![原因代碼](assets/reason-codes.png)

此流程圖顯示了客戶傾向在不同評分運行期間的錄入流&#x200B;:

![入口流](assets/flow.png)

此條形圖顯示傾向得分的分佈&#x200B;:

![分佈](assets/distribution.png)

此Venn圖顯示了不同計分運行的傾向重疊：

![傾向重疊](assets/venn.png)
