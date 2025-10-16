---
description: 了解 Adobe Experience Platform Customer AI 資料如何與 Customer Journey Analytics 中的 Workspace 整合。
title: 整合 Customer AI 資料
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
source-git-commit: ed7e9a6c34c5f8ba9ba4f75be05768409cbc158d
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 97%

---

# 整合 Customer AI 資料

{{release-limited-testing}}

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html) 是 Adobe Experience Platform Intelligent Services 的一部分，它讓行銷人員能夠產生個人層面的客戶預測。

在影響因子的協助下，Customer AI 可告知您客戶可能會有什麼行為以及原因何在。 此外，行銷人員可受益於 Customer AI 預測和洞見，藉由提供最適合的方案和訊息來打造個人化客戶體驗。

Customer AI 需要使用個別行為資料和輪廓來處理傾向分數。 Customer AI 具有靈活彈性，可接收多個資料來源，包括 Adobe Analytics、Adobe Audience Manager、取用者體驗事件資料和體驗事件資料。 如果您使用 Experience Platform 來源連接器引進 Adobe Audience Manager 和 Adobe Analytics 資料，模型會自動挑選標準事件類型來訓練及評分模型。 如果您引進自己的體驗事件資料集，但不包含標準事件類型，如果您想在模型中使用任何相關欄位，則需要將其對應為自訂事件或輪廓屬性。 此動作可以在 Experience Platform 中的 Customer AI 設定步驟中完成。

Customer AI 可以與 Customer Journey Analytics 整合到一定的程度，以便具備 Customer AI 功能的資料集能夠在 Customer Journey Analytics 的資料視圖和報告中運用。您可以：

* **追蹤使用者區段不同時期的傾向分數**。
   * 使用案例：了解特定區段中客戶轉換的可能性。
   * 例如：連鎖旅館的行銷人員想要了解，旅館顧客在旅館音樂會場地購買演出門票的可能性。
* **分析哪些成功事件或屬性與傾向分數相關**。
   * 使用案例：了解與傾向分數相關的屬性或成功事件。
   * 例如：連鎖旅館的行銷人員想要了解，在旅館音樂會場地購買演出門票與傾向分數之間的關係。
* **經過不同評分回合後，追蹤客戶傾向的變化過程**。
   * 使用案例：了解起初傾向性偏低，但過一段時間後變成傾向性偏高的使用者。
   * 例如：連鎖旅館的行銷人員想要了解，哪些旅館客戶最初被認定為購買演出門票傾向性較低的客戶，但一段時間後變成購買演出門票傾向性較高的客戶。
* **檢視傾向性的分佈**。
   * 使用案例：了解傾向分數的分佈，以便更精準地定義區段。
   * 範例：零售商想要以 50 美元的產品折扣進行特定促銷活動。由於預算等因素，他們只能進行非常有限的促銷活動。分析資料之後，他們決定只將目標鎖定在前 80% 以上的客戶。
* **檢視特定同類群組在不同時期完成某項動作的傾向性**。
   * 使用案例：追蹤特定同類群組在不同時期的情況。
   * 範例：連鎖旅館的行銷人員想要追蹤銅級與銀級客群，或銀級與金級客群在不同時期的情況。他們就能掌握各同類群組在不同時期訂房的傾向性。

若要實際整合 Customer AI 資料與 Customer Journey Analytics，請遵循以下步驟：

>[!NOTE]
>
>部分步驟是在使用 Customer Journey Analytics 輸出之前在 Adobe Experience Platform 中執行。


## 步驟 1：設定 Customer AI 執行個體

當您準備好資料及所有認證和結構描述後，請依照 Adobe Experience Platform 中的[設定 Customer AI 執行個體](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html)指南中的指示開始進行。

## 步驟 2：設定與 Customer AI 資料集的 Customer Journey Analytics 連線

現在，您可以在 Customer Journey Analytics 中，[建立一或多個連線](/help/connections/create-connection.md)來連結已針對 Customer AI 檢測的 Experience Platform 資料集。每項預測 (例如升級帳戶的可能性) 等於一個資料集。 這些資料集出現時會有「EE 格式的 Customer AI 分數 – 應用程式名稱」前置詞。

>[!IMPORTANT]
>
>如果在步驟 1 的設定期間對 Customer Journey Analytics 開啟了分數功能，則每個 Customer AI 執行個體都會有兩個輸出資料集。其中一個輸出資料集為輪廓 XDM 格式，另一個為體驗事件 XDM 格式。

![CAI 分數](assets/cai-scores.png)

![建立連線](assets/create-conn.png)

以下是 Customer Journey Analytics 會當作現有或新資料集之一部分導入的 XDM 結構描述範例：

![CAI 結構描述](assets/cai-schema.png)

(請注意，此範例為輪廓資料集；相同一組結構描述物件將成為 Customer Journey Analytics 擷取之 Experience Event 資料集的一部分。體驗事件資料集將包含時間戳記作為評分日期。) 在此模型中得分的每個客戶都會有分數、scoreDate等 評分日期等。

## 步驟 3：根據這些連線建立資料檢視

現在，您可以在 Customer Journey Analytics 中繼續使用維度 (例如分數、評分日期、可能性等) 以及您在建立之連線中導入的量度來[建立資料視圖](/help/data-views/create-dataview.md)。

![建立資料檢視視窗](assets/create-dataview.png)

## 步驟 4：在 Workspace 中報告 CAI 分數

在 Customer Journey Analytics Workspace 中，建立一個新專案並提取視覺效果。

### 趨勢傾向分數

以下是 Workspace 專案的範例，專案中包含的 CAI 資料會在堆疊長條圖中顯示使用者區段在不同時期的傾向分數：

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
