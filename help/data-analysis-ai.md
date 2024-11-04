---
description: 如何向Customer Journey Analytics檔案提出資料分析問題
title: Customer Journey Analytics中的Data Analysis AI助理
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: ab8a4c65de59e725d7d181ee699d7a196988bf98
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 4%

---


# Customer Journey Analytics中的Data Analysis AI助理 — Alpha

Data Analysis AI Assistant是智慧型內容感知交談代理程式，可協助您更快速、有效率地回答有關Customer Journey Analytics中Analysis Workspace資料的問題。

「小幫手」會檢視資料檢視中的所有資料，包括不同型別的量度和元件，並將您的提示翻譯為此分析的正確維度、量度和日期範圍。 您不必熟悉資料檢視元件，並以最佳組合拖放這些元件來回答您的問題，只要在AI Assistant中輸入問題即可。

## Alpha版本的範圍內與範圍外功能

### 範圍內功能

| 支援的功能 | 說明 |
| --- | --- |
| **建置和更新視覺效果** | 產生自由表格和相關聯的視覺效果（例如線條、長條圖、環形圖等）。<p>範例： *從2月到5月，SKU的利潤是多少？* |
| **支援的視覺效果型別** | <ul><li>折線圖</li><li>多行</li><li>自由格式</li><li>長條圖</li><li>環形圖</li><li>摘要數字</li></ul> |
| **範圍外提示偵測** | 如果您提交超出範圍的提示（例如「匯出此專案」），「助理員」會通知您問題超出範圍。 |
| **澄清問題** | 如果您要問的問題沒有足夠內容可供AI助理回答或過於寬泛，則AI助理會以澄清問題和/或建議的選項回應。 範例： <p>**元件**<ul><li>量度： *您指的是哪個「收入」量度？*</li><li>Dimension： *您想要著重下列哪個「地區」？*</li><li>篩選器： *您要套用哪個「帳戶」篩選器？*</li><li>日期範圍： *以「上個月」表示，您是指「上個月」還是「過去30天」？*</li></ul>**Dimension專案**：您指的是哪個「商店名稱」？ (例如，商店#5274、商店#2949等) |
| **多圈** | AI助理員會使用先前提示的內容來回應提示，讓使用者可以更新視覺效果和提出後續問題。 範例： *改為顯示三月到四月的資料。* |
| **意見反應** | <ul><li>豎起大拇指</li><li>向下拇指</li><li>標幟</li></ul> |

### 超出範圍的功能

| 不支援的功能 | 說明 |
| --- | --- |
| **內嵌摘要或回應** | AI助理無法在聊天邊欄中以使用者提示的摘要回答內聯回應。範圍外提示範例：<ul><li>*提供上次提示的見解摘要。*</li><li>*從線條視覺效果摘要醒目提示。*</li></ul> |
| **澄清問題** | 澄清的問題僅限於元件和維度專案。 AI Assistant無法釐清資料檢視、視覺效果、資料精細度、比較、範圍等。 如果沒有澄清問題，「助理」會預設為您最可能要求的內容。 如果它傳回非預期的視覺效果或資料詳細程度，您就可以使用多圈/更新功能來調整視覺效果和資料。 |
| **Workspace動作/功能** | 除了建置和更新視覺效果以外，AI助理無法在Workspace中為使用者執行動作。 例如，它無法執行下列任何動作：<ul><li>內容動作UI按鈕（新增至圖表、新面板、新表格）</li><li>共用</li><li>匯出</li><li>下載</li><li>管理使用者偏好設定</li><li>組織</li><li>管理資料檢視</li><li>Analytics儀表板應用程式</li><li>歸因</li></ul> |
| **不支援的視覺效果型別** | <ul><li>流量</li><li>流失</li><li>同類群組表格</li><li>區域圖、棧疊區域圖</li><li>堆疊長條圖</li><li>項目符號</li><li>組合</li><li>長條圖</li><li>橫條圖、棧疊橫條圖</li><li>關鍵量度摘要</li><li>散佈圖</li><li>摘要變更</li><li>文字</li><li>樹狀圖</li><li>文氏圖表</li></ul> |
| **可說明性和可驗證性** | AI助理產生回應的方式透明描述或引文，並提供您確認答案正確的方法。 |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## 存取及使用資料分析AI助理

1. 請移至此連結，在Labs IMS組織（階段中）中開啟Workspace，然後使用您的Adobe ID登入。

1. 按一下專案頁面頂端橫幅中的&#x200B;**[!UICONTROL 空白專案]**，開啟新的空白專案。

1. 按一下右上角的AI助理聊天圖示。

   ![AI助理圖示](/help/assets/ai-asst-icon.png)

1. 在底部的&#x200B;**[!UICONTROL 詢問Customer Journey Analytics]**&#x200B;對話方塊中，在AI助理中詢問資料分析問題。

### 範例 1

例如，假設您對您的企業在7月收到的訂單感興趣。

1. 輸入「七月顯示訂單」。

   ![AI提示](/help/assets/ai-asst-prompt1.png)

1. AI Assistant現在會透過檢視資料檢視中的資料（包括量度和元件）來收集深入見解。 這會將提示轉譯為正確的維度、量度和資料範圍。

   如您所見，它已自動產生線條圖和自由表格，顯示7月的訂單。

   ![提示的回答 — 折線圖和自由格式表格](/help/assets/ai-asst-result.png)

### 範例 2

接下來，您想要瞭解依地區比較收入的方式。

1. 在提示視窗中，輸入「依地區顯示收入」。

2. AI足夠聰明，因此可瞭解「地區」的意思是「客戶地區」。 這會產生一個長條圖，最能依地區顯示收入：

   ![長條圖](/help/assets/ai-asst-result2.png)

### 範例 3

現在來依照產品類別檢視收入。

1. 在提示視窗中，輸入「依產品類別顯示收入」。

2. 再次強調，Data Analysis AI Assistant會挑選最適合的視覺效果（在此案例中為&#x200B;**[!UICONTROL 環形圖]**&#x200B;視覺效果）來回答問題。

   ![環形圖](/help/assets/ai-asst-result3.png)

### 範例 4

最後，您想知道哪個SKU最有利可圖，以及您應該將行銷資源投資於何處。

1. 在提示視窗中，詢問「從2月到5月，SKU的利潤是多少？」

1. 簡單的&#x200B;**[!UICONTROL 橫條圖]**&#x200B;提供最簡明的答案：

   ![長條圖](/help/assets/ai-asst-result4.png)

## 範例資料分析提示

以下是常見提示的一些範例，以及AI協助用於回應這些提示的視覺效果。

| 範例提示 | 預期的視覺效果 |
| --- | --- |
| 顯示[個月]的利潤 | 折線圖<p>依預設，詢問特定時間範圍內的趨勢或量度會傳回線條視覺效果。 |
| [個月]的趨勢訂單 | 折線圖 |
| 在[個月]內依地區顯示收入 | 長條圖 |
| 依產品類別劃分的收入份額 | 環形圖 |
| 按周中某日（從1月到5月）的訂單 | 長條圖 |
| 依性別顯示從3月到6月的訂單 | 長條圖 |
| 從2月到5月，SKU利潤如何 | 長條圖 |
| [個月]內依商店名稱區分的收入 | 長條圖 |
| 在[月]中，依利潤排列的前10名SKU為何？ | 長條圖 |
| 按月份和年份的購買比例 | 環形圖 |
| [個月]的總利潤 | 摘要數字<p>在特定時間範圍內詢問量度的「總計」時，應該會傳回「摘要數字」視覺效果。 |


## 提示最佳實務

待定

## Alpha測試期望和要求的意見回饋

提出每個問題後，請仔細檢閱助理提供的答案。 提供意見回饋之前，請務必全面評估產生的視覺效果。

評估回應：提供的回應是否正確？

如果助理在聊天邊欄中回應：評估文字回應。

* 如果顯示了視覺效果/圖表：評估視覺效果。 這是您問題的適當/預期視覺效果嗎？

* 如果顯示自由表格：評估自由表格。 自由格式表格資料正確嗎？ 它是否在請求時劃分資料？ 套用的篩選器是您要求還是預期的篩選器？

* 如果提供了一般錯誤訊息指出問題超出範圍，請根據您的提示提供您認為超出範圍的訊息是否適當的回饋。 您的提示是否確實在範圍內？

對於每個回應，請根據回應向上或向下拇指

在按一下上/下縮圖選擇後，請選取相關的多選意見反應方塊。 如果您想提供其他意見反應，請在開啟的文字方塊中新增附註。

## 問題與連絡人

* 電子郵件`taylorb@adobe.com` （下午）
* 在AlphaSlack頻道中傳送問題和意見回饋： #aep-cja-ai-assistant-testers ???


