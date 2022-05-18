---
description: 瞭解AEP客戶AI如何與CJA中的Workspace整合。
title: 將客戶AI與CJA整合
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---


# 將客戶AI與CJA整合

>[!NOTE]
>
>此頁正在構建中。

[客戶AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)作為Adobe Experience Platform智慧服務的一部分，向營銷人員提供在個人層面生成客戶預測的能力。

在影響因素的幫助下，客戶AI可以告訴您客戶可能做什麼以及為什麼。 此外，營銷人員可以從客戶人工智慧預測和洞察中獲益，通過提供最合適的優惠和資訊來個性化客戶體驗。

客戶AI通過分析以下資料集之一來預測流失或轉換傾向得分：

* Adobe Analytics資料使用分析源連接器
* Adobe Audience Manager資料使用Audience Manager源連接器
* Experience Event (EE) dataset
* Consumer Experience Event (CEE) dataset

客戶AI與Customer Journey Analytics(CJA)整合，以便客戶AI支援的資料集可以在CJA中的資料視圖和報告中得到利用。

## 工作流程

在CJA中的輸出工作之前，在Adobe Experience Platform執行某些步驟。

### Step 1: Download Customer AI scores

Downloading Customer AI scores is done through a combination of Experience Platform API calls, as described [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### 步驟2:定義客戶AI輸入和輸出

此過程在 [客戶AI中的輸入和輸出](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) 文檔。

### 第3步：配置客戶AI實例

準備好資料並準備好所有憑據和架構後，請按照 [配置客戶AI實例](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) 的子菜單。

### 第4步：設定到客戶AI資料集的CJA連接

在CJA，你現在可以 [建立一個或多個連接](/help/connections/create-connection.md) Experience Platform為客戶AI檢測的資料集。 這些資料集以「客戶AI分數」前置詞顯示，如下所示：

![CAI得分](assets/cai-scores.png)

每種預測，如「升級帳戶的可能性」等於一個資料集。

以下是CJA作為現有或新資料集的一部分引入的XDM架構的示例：

![CAI模式](assets/cai-schema.png)

(請注意，此示例是配置檔案資料集；同一組架構對象將是CJA將獲取的「體驗事件」資料集的一部分。 「體驗事件」資料集將包含時間戳作為分數日期。) Every customer scored in this model would have a score, a scoreDate, etc. 關聯。

### 第5步：基於這些連接建立資料視圖

在CJA中，現在可以繼續建立資料視圖，其中包含作為所建立連接的一部分引入的維。