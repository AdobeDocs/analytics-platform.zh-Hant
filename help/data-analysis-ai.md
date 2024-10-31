---
description: 如何向Customer Journey Analytics檔案提出資料分析問題
title: Customer Journey Analytics中的Data Analysis AI助理
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e723339831bf835b43096affd4e0f15f41462f54
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 4%

---


# Customer Journey Analytics中的Data Analysis AI助理 — Alpha

Data Analysis AI Assistant是智慧型內容感知交談代理程式，可協助您更快速、有效率地回答有關Customer Journey Analytics中Analysis Workspace資料的問題。

「小幫手」會檢視資料檢視中的所有資料，包括不同型別的量度和元件，並將您的提示翻譯為此分析的正確維度、量度和日期範圍。 您不必熟悉資料檢視元件，並以最佳組合拖放這些元件來回答您的問題，只要在AI Assistant中輸入問題即可。

## Alpha版本的範圍內與範圍外功能

範圍內功能：

| 支援的功能 | 說明 |
| --- | --- |
| 建立和更新視覺效果 | 產生自由表格和相關聯的視覺效果（例如線條、長條圖、環形圖等）。<p>範例： *從2月到5月，SKU的利潤是多少？* |
| 支援的視覺效果型別 | 折線、多行、自由格式、長條圖、環圈圖、摘要數字視覺效果 |
| 超出範圍提示偵測 | 如果您提交超出範圍的提示（例如「匯出此專案」），「助理員」會通知您問題超出範圍。 |
| 澄清問題 | 如果您要問的問題沒有足夠內容可供AI助理回答或過於寬泛，則AI助理會以澄清問題和/或建議的選項回應。 範例： <p>**元件**<ul><li>量度： *您指的是哪個「收入」量度？*</li><li>Dimension： *您想要著重下列哪個「地區」？*</li><li>篩選器： *您要套用哪個「帳戶」篩選器？*</li><li>日期範圍： *以「上個月」表示，您是指「上個月」還是「過去30天」？*</li></ul>**Dimension專案**：您指的是哪個「商店名稱」？ (例如，商店#5274、商店#2949等) |
| 多圈 | AI助理員會使用先前提示的內容來回應提示，讓使用者可以更新視覺效果和提出後續問題。 範例： *改為顯示三月到四月的資料。* |
| 意見反應 | <ul><li>豎起大拇指</li><li>向下拇指</li><li>標幟</li></ul> |

範圍外功能：

| 不支援的功能 | 說明 |
| --- | --- |
| 內嵌摘要或回應 | AI助理無法在聊天邊欄中以使用者提示的摘要回答內聯回應。範圍外提示範例：<ul><li>*提供上次提示的見解摘要。*</li><li>*從線條視覺效果摘要醒目提示。*</li></ul> |
| 澄清問題 | 澄清的問題僅限於元件和維度專案。 AI Assistant無法釐清資料檢視、視覺效果、資料精細度、比較、範圍等。 如果沒有澄清問題，「助理」會預設為您最可能要求的內容。 如果它傳回非預期的視覺效果或資料詳細程度，您就可以使用多圈/更新功能來調整視覺效果和資料。 |
| Workspace動作/功能 | 除了建置和更新視覺效果以外，AI助理無法在Workspace中為使用者執行動作。 例如，它無法執行下列任何動作：<ul><li>內容動作UI按鈕（新增至圖表、新面板、新表格）</li><li>共用</li><li>匯出</li><li>下載</li><li>管理使用者偏好設定</li><li>組織</li><li>管理資料檢視</li><li>Analytics儀表板應用程式</li><li>歸因</li></ul> |
| 不支援的視覺效果型別 | <ul><li>流量</li><li>流失</li><li>同類群組表格</li><li>區域圖、棧疊區域圖</li><li>堆疊長條圖</li><li>項目符號</li><li>組合</li><li>長條圖</li><li>橫條圖、棧疊橫條圖</li><li>關鍵量度摘要</li><li>散佈圖</li><li>摘要變更</li><li>文字</li><li>樹狀圖</li><li>文氏圖表</li></ul> |
| 可解釋性和可驗證性 | AI助理產生回應的方式透明描述或引文，並提供您確認答案正確的方法。 |

## Customer Journey Analytics UI中的功能存取

[Alpha是否需要此節？]

下列引數可控制對「資料分析AI助理」功能的存取：

* **解決方案存取**： Data Analysis AI Assistant可供Analysis Prime和Ultimate客戶Customer Journey Analytics。 在Adobe Analytics中無法使用。

Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDP及其他Experience Platform應用程式也提供此功能。

* **合約存取**：如果您無法使用AI小幫手，請連絡您組織的管理員或Adobe帳戶代表。 貴組織必須同意特定GenAI相關法律條款，才能使用Data Analysis AI Assistant。

* **許可權**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 報告工具] **[!UICONTROL AI小幫手：資料分析]**&#x200B;許可權決定此工具的存取權。 [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中遵循下列步驟：
   1. 導覽至&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 產品及服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**
   1. 選取您要為其提供[!UICONTROL AI助理存取權的產品設定檔標題：產品知識]。
   1. 在特定產品設定檔中，選取&#x200B;**[!UICONTROL 許可權]**。
   1. 選取![編輯](/help/assets/icons/Edit.svg)以編輯&#x200B;**[!UICONTROL 報告工具]**。
   1. 選取![AddCircle](/help/assets/icons/AddCircle.svg)以新增&#x200B;**AI助理：資料分析**&#x200B;至&#x200B;**[!UICONTROL 包含的許可權專案]**。

      ![新增許可權](assets/ai-assistant-permissions.png)。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存許可權。

如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md#access-control)。

## 存取及使用資料分析AI助理

1. 請移至此連結，在Labs IMS組織（階段中）中開啟Workspace，然後使用您的Adobe ID登入。

1. 按一下專案頁面頂端橫幅中的&#x200B;**[!UICONTROL 空白專案]**，開啟新的空白專案。

1. 按一下右上角的AI助理聊天圖示。

   ![AI助理圖示](/help/assets/ai-asst-icon.png)

1. 在底部的&#x200B;**[!UICONTROL 詢問Customer Journey Analytics]**&#x200B;對話方塊中，在AI助理中詢問您的第一個資料分析問題。

   例如，假設您對您的企業在7月收到的訂單感興趣。 所以您可以輸入「七月顯示訂單」。

   ![AI提示](/help/assets/ai-asst-prompt1.png)


## 範例資料分析提示

以下是AI助理如何回應提示和預期視覺效果的一些範例：

| 範例提示 | 預期的視覺效果 |
| --- | --- |
| 顯示[個月]的利潤 | 折線圖<p>依預設，在特定時間範圍要求趨勢或量度將會傳回線條視覺效果。 |
| [個月]的趨勢訂單 | 折線圖 |
| 在[個月]內依地區顯示收入 | 長條圖 |
| 依產品類別劃分的收入份額 | 環形圖 |
| 按周從1月到5月的訂單 | 長條圖 |
| 依性別顯示三月至六月的訂單 | 長條圖 |
| 從2月到5月，SKU利潤如何 | 長條圖 |
| [個月]內依商店名稱區分的收入 | 長條圖 |
| 我的[月]利潤前10名SKU為何？ | 長條圖 |
| 按月份和年份的購買比例 | 環形圖 |
| [個月]的總利潤 | 摘要數字<p>在特定時間範圍內詢問量度的「總計」時，應該會傳回「摘要數字」視覺效果。 |


## 提示最佳實務

待定

## Alpha測試期望和要求的意見回饋

待定

## 問題與連絡人

電子郵件`taylorb@adobe.com` （下午）
在AlphaSlack頻道中傳送問題和意見回饋




