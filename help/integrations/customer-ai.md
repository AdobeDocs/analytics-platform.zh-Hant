---
description: 瞭解Adobe Experience Platform Customer AI資料如何在Customer Journey Analytics中與工作區整合。
title: 將Customer AI資料與Customer Journey Analytics整合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 49%

---

# 將Customer AI資料與Adobe Customer Journey Analytics整合

{{release-limited-testing}}

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=zh-Hant) 是 Adobe Experience Platform Intelligent Services 的一部分，它讓行銷人員能夠產生個人層面的客戶預測。

在影響因子的協助下，Customer AI 可告知您客戶可能會有什麼行為以及原因何在。 此外，行銷人員可受益於 Customer AI 預測和洞見，藉由提供最適合的方案和訊息來打造個人化客戶體驗。

Customer AI 需要使用個別行為資料和個人資料來處理傾向分數。 Customer AI 具有靈活彈性，可接收多個資料來源，包括 Adobe Analytics、Adobe Audience Manager、取用者體驗事件資料和體驗事件資料。 如果您使用 Experience Platform 來源連接器引進 Adobe Audience Manager 和 Adobe Analytics 資料，模型會自動挑選標準事件類型來訓練及評分模型。 如果您引進自己的體驗事件資料集，但不包含標準事件類型，如果您想在模型中使用任何相關欄位，則需要將其對應為自訂事件或個人資料屬性。 這可以在Experience Platform的Customer AI設定步驟中完成。

Customer AI可與Customer Journey Analytics整合，以便在Customer Journey Analytics的資料檢視和報告中運用具有Customer AI功能的資料集。 您可以：

* **追蹤使用者區段不同時期的傾向分數**。 
   * 使用案例：瞭解特定區段中的客戶轉換的可能性。
   * 範例：連鎖飯店的行銷人員想要瞭解飯店客戶在飯店音樂會場地購買演出門票的可能性。
* **分析哪些成功事件或屬性與傾向分數相關**.
   * 使用案例：瞭解與傾向分數相關的屬性或成功事件。
   * 範例：連鎖飯店的行銷人員想要瞭解在飯店音樂會場地購買演出門票與傾向分數有何關聯。
* **經過不同評分執行下來，追蹤客戶傾向的變化過程**。 
   * 使用案例：瞭解起初傾向性偏低，但隨著時間轉為傾向性偏高的使用者。
   * 範例：連鎖飯店的行銷人員想要瞭解哪些飯店客戶最初被認定為低購買演出門票傾向的客戶，但隨著時間推移，這些客戶變成高購買演出門票傾向的客戶。
* **檢視傾向性的分佈**。 
   * 使用案例：瞭解傾向分數的分佈，以在定義區段時更精確。
   * 範例：零售商想要以$50的產品折扣進行特定促銷。 由於預算等因素，他們只能進行有限度的促銷活動。 他們分析資料，並決定只將目標鎖定在前80%以上的客戶。
* **檢視特定同類群組在不同時期完成某項動作的傾向性**。 
   * 使用案例：追蹤特定同類群組在不同時期的情況。
   * 範例：某連鎖飯店的行銷人員想要追蹤觀察銅級與銀級客群，或銀級與金級客群在不同時期的情況。 他們可以檢視每個同類群組在不同時期訂房的傾向。

若要將Customer AI資料與Customer Journey Analytics實際整合，請遵循下列步驟：

>[!NOTE]
>
>在使用Customer Journey Analytics中的輸出之前，必須在Adobe Experience Platform中執行某些步驟。


## 步驟 1：設定 Customer AI 執行個體

當您準備好資料及所有認證和結構描述後，請依照 Adobe Experience Platform 中的[設定 Customer AI 執行個體](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=zh-Hant)指南中的指示開始進行。

## 步驟2：設定與Customer AI資料集的Customer Journey Analytics連線

在Customer Journey Analytics中，您現在可以 [建立一或多個連線](/help/connections/create-connection.md) Experience Platform已針對Customer AI檢測的資料集。 每項預測 (例如升級帳戶的可能性) 等於一個資料集。 這些資料集出現時會有「EE 格式的 Customer AI 分數 – 應用程式名稱」前置詞。

>[!IMPORTANT]
>
>如果在步驟1的設定中開啟切換以啟用Customer Journey Analytics分數，則每個Customer AI執行個體都有兩個輸出資料集。 其中一個輸出資料集為個人資料 XDM 格式，另一個為體驗事件 XDM 格式。

![CAI 分數](assets/cai-scores.png)

![建立連線](assets/create-conn.png)

以下是Customer Journey Analytics將會當作現有或新資料集的一部分引進的XDM結構描述範例：

![CAI 結構描述](assets/cai-schema.png)

(請注意，此範例是設定檔資料集；同一組結構描述物件將成為Customer Journey Analytics捕捉的體驗事件資料集的一部分。 體驗事件資料集會包含時間戳記當作評分日期。) 在此模型中被評分的每個客戶都會有與其相關的分數、評分日期等。

## 步驟 3：根據這些連線建立資料檢視

在Customer Journey Analytics中，您現在可以繼續進行 [建立資料檢視](/help/data-views/create-dataview.md) 以及您在建立的連線中引進的維度（例如分數、評分日期、機率等）和量度。

![建立資料檢視](assets/create-dataview.png)

## 步驟 4：在工作區中報告 CAI 分數

在Customer Journey Analytics工作區中，建立新專案並提取視覺效果。

### 趨勢傾向分數

以下是工作區專案的範例，專案中包含的 CAI 資料會在堆疊長條圖中顯示使用者區段在不同時期的傾向分數：

![分數貯體](assets/workspace-scores.png)

### 原因代碼表格

這裡的表格列出原因代碼，說明區段傾向性偏高或低的原因&#x200B;：

![原因代碼](assets/reason-codes.png)

### 客戶傾向性的變化過程

此流程圖顯示經過不同評分執行下來，客戶傾向的變化過程&#x200B;：

![變化過程](assets/flow.png)

### 傾向分數的分佈

此長條圖顯示傾向分數的分佈情形&#x200B;：

![分佈](assets/distribution.png)

### 傾向性重疊

此文氏圖表顯示經過不同評分執行下來，傾向性的重疊情形：

![傾向性重疊](assets/venn.png)
