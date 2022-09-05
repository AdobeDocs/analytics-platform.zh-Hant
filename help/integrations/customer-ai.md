---
description: 了解 AEP Customer AI 如何在 CJA 中與工作區整合。
title: 將 Customer AI 與 CJA 整合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 75e72f94b90ad67a3f8e9506abb09b96a59383d8
workflow-type: ht
source-wordcount: '888'
ht-degree: 100%

---

# 將 Customer AI 與 CJA 整合

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=zh-Hant) 是 Adobe Experience Platform Intelligent Services 的一部分，它讓行銷人員能夠產生個人層面的客戶預測。

在影響因子的協助下，Customer AI 可告知您客戶可能會有什麼行為以及原因何在。 此外，行銷人員可受益於 Customer AI 預測和洞見，藉由提供最適合的方案和訊息來打造個人化客戶體驗。

Customer AI 需要使用個別行為資料和個人資料來處理傾向分數。 Customer AI 具有靈活彈性，可接收多個資料來源，包括 Adobe Analytics、Adobe Audience Manager、取用者體驗事件資料和體驗事件資料。 如果您使用 Experience Platform 來源連接器引進 Adobe Audience Manager 和 Adobe Analytics 資料，模型會自動挑選標準事件類型來訓練及評分模型。 如果您引進自己的體驗事件資料集，但不包含標準事件類型，如果您想在模型中使用任何相關欄位，則需要將其對應為自訂事件或個人資料屬性。 這可以在 Experience Platform 的 Customer AI 設定步驟中完成。 &#x200B;

Customer AI 與 Customer Journey Analytics (CJA) 整合到一定的程度，以便可以在 CJA 的資料檢視和報告中利用具有 Customer AI 功能的資料集。 透過這項整合，您可以

* **追蹤使用者區段不同時期的傾向分數**。 使用案例範例：飯店客戶在飯店音樂會場地購買節目門票的可能性有多高？
* **分析哪些成功事件或屬性與傾向分數相關**。 &#x200B;使用案例範例：我想了解與傾向分數相關的屬性或成功事件。
* **經過不同評分執行下來，追蹤客戶傾向的變化過程**。 使用案例範例：我想了解起初傾向性偏低，但隨著時間轉為傾向性偏高的使用者。&#x200B;
* **檢視傾向性的分佈**。 使用案例：我想了解傾向分數的分佈，以針對我的區段做出更準確的處置。 &#x200B;範例：零售商想要以 $50 的產品折扣展開特定促銷活動。 由於預算等因素，他們只能進行有限度的促銷活動。 經過資料分析，他們決定只將目標鎖定在前 80% 以上的客戶。
* **檢視特定同類群組在不同時期完成某項動作的傾向性**。 使用案例：我想追蹤觀察特定同類群組在不同時期的情況。 這與第一個項目類似，但您可以追蹤特定同類群組在不同時期的情況。&#x200B; 旅館業範例：行銷人員可以追蹤觀察銅級與銀級客群，或銀級與金級客群在不同時期的情況。 接著，他們就能掌握各同類群組在不同時期訂房的傾向性。 &#x200B;

## 工作流程

在 CJA 中使用輸出之前會在 Adobe Experience Platform 中執行某些步驟。

### 步驟 1：設定 Customer AI 執行個體

當您準備好資料及所有認證和結構描述後，請依照 Adobe Experience Platform 中的[設定 Customer AI 執行個體](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=zh-Hant)指南中的指示開始進行。

### 步驟 2：設定 CJA 與 Customer AI 資料集的連線

現在在 CJA 中，您可以[建立一個或多個連線](/help/connections/create-connection.md)來連接已針對 Customer AI 檢測的 Experience Platform 資料集。 每項預測 (例如升級帳戶的可能性) 等於一個資料集。 這些資料集出現時會有「EE 格式的 Customer AI 分數 – 應用程式名稱」前置詞。

>[!IMPORTANT]
>
>如果在步驟 1 的設定中開啟 CJA 分數設定，則每個 Customer AI 執行個體會有兩個輸出資料集。 其中一個輸出資料集為個人資料 XDM 格式，另一個為體驗事件 XDM 格式。

![CAI 分數](assets/cai-scores.png)

![建立連線](assets/create-conn.png)

以下是 CJA 將會當作現有或新資料集的一部分引進的 XDM 結構描述範例：

![CAI 結構描述](assets/cai-schema.png)

(請注意，此範例為個人基本資料集；相同一組結構描述物件將成為 CJA 捕捉的 Experience Event 資料集的一部分。 體驗事件資料集會包含時間戳記當作評分日期。) 在此模型中被評分的每個客戶都會有與其相關的分數、評分日期等。

### 步驟 3：根據這些連線建立資料檢視

現在在 CJA 中，您可以繼續使用維度 (例如分數、評分日期、可能性等) 以及您在建立的連線中引進的量度來[建立資料檢視](/help/data-views/create-dataview.md)。

![建立資料檢視](assets/create-dataview.png)

### 步驟 4：在工作區中報告 CAI 分數

在 CJA Workspace 中，建立新專案並提取視覺效果。

**趨勢傾向分數**

以下是工作區專案的範例，專案中包含的 CAI 資料會在堆疊長條圖中顯示使用者區段在不同時期的傾向分數：

![分數貯體](assets/workspace-scores.png)

**原因代碼表格**

這裡的表格列出原因代碼，說明區段傾向性偏高或低的原因&#x200B;：

![原因代碼](assets/reason-codes.png)

**客戶傾向性的變化過程**

此流程圖顯示經過不同評分執行下來，客戶傾向的變化過程&#x200B;：

![變化過程](assets/flow.png)

**傾向分數的分佈**

此長條圖顯示傾向分數的分佈情形&#x200B;：

![分佈](assets/distribution.png)

**傾向性重疊**

此文氏圖表顯示經過不同評分執行下來，傾向性的重疊情形：

![傾向性重疊](assets/venn.png)
