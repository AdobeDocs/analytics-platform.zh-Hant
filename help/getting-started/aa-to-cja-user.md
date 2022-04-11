---
title: CJAAdobe Analytics使用手冊
description: 當您的公司將資料從Adobe Analytics移動到Customer Journey Analytics時，從用戶的角度考慮什麼
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 6981a7a68d8a517f6b842cb36382f543c80f4582
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 6%

---

# CJAAdobe Analytics使用手冊

如果您的組織開始使用Customer Journey Analytics(CJA)，您可能會注意到傳統分析和CJA之間的一些相似點和差異。 本頁旨在說明這些差異，以幫助您的組織適應新的實施和報告工作流。 本頁還提供了有關新概念的更多資源，以及進一步的步驟，讓您作為分析師的旅途更輕鬆、更成功。

CJA中的幾項功能都經過重新命名和重新設計，以符合行業標準。 某些更新的術語包括段、虛擬報表套件、分類、客戶屬性和容器名稱。 eVars和props的局限性已不復存在，而是支援靈活的自定義尺寸和度量。

## 未更改的內容

在報告方面，您熟悉的許多內容都沒有改變。

* 你仍然可以利用 [Analysis Workspace](/help/analysis-workspace/home.md) 分析資料。 工作區與傳統Adobe Analytics的工作區一樣。
* 同一版本 [Adobe Analytics儀表板](/help/mobile-app/home.md) 可用，並且在CJA和傳統分析之間同樣工作。
* [Report Builder](/help/report-builder/report-buider-overview.md) 具有新介面，並在MS Windows、iOS和Excel的Web版本上運行。 (在此版本的Report Builder之前，除非在VMware上運行，否則無法在Mac上使用。) 此版本尚不支援傳統AA資料請求。

## 報告更改

您可以訪問更多要分析的跨通道資料。 例如，您可以建立一個工作區項目來分析多個通道的效能，前提是這些資料集由您的組織攝取，並包含在CJA使用的資料視圖中（請參閱下面的「對資料體系結構所做的更改」）。

![多通道可視化](assets/cross-channel.png)

## 對資料體系結構的更改 {#architecture}

CJA從Adobe Experience Platform獲取資料。 Experience Platform使您能夠集中並標準化來自任何系統或渠道的客戶資料和內容，並應用資料科學和機器學習來改進個性化體驗的設計和交付。

Experience Platform中的客戶資料以資料集形式儲存，資料集由 [架構](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=zh-Hant) 和資料批。 如需有關 Platform 的詳細資訊，請參閱 [Adobe Experience Platform 架構概覽](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en)。

您的CJA管理員建立 [連接](/help/connections/create-connection.md) 到Experience Platform中的資料集。 然後他們建造 [資料視圖](/help/data-views/data-views.md) 利用這些連接。 資料視圖在概念上與虛擬報告套件相似，是CJA報告的基礎。 由於Experience Platform源是所有報告資料，因此報告套件不再作為資料容器存在。

通過連接，分析管理員可以將來自Adobe Experience Platform的資料集整合到CJA中，包括在以下視頻中：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe提供了多種將資料導入Adobe Experience Platform的方法，包括通過Adobe Analytics源連接器或Web SDK的報告套件資料。 來自多個報告套件的現有實現可以組合為Experience Platform。 基於這些資料集的連接和資料視圖可以合併先前存在於單獨報告套件中的資料。

## 對虛擬報告套件概念的更改 {#data-views}

[!UICONTROL 資料視圖] 將虛擬報表套件的概念應用到 [啟用對資料的其他控制項](/help/data-views/create-dataview.md) 連接可用。 這些更改使常規設定（如時區和會話超時間隔）可配置且具有追溯性。 也可以在報告或資料視圖級別上自定義個別變數設定，如屬性和到期。 這些設定是無損的和可追溯的。

請注意，右上方的報告套件選擇器現在允許您從可用資料視圖中進行選擇：

![資料視圖選擇器](assets/data-views.png)

請參閱 [圍繞資料視圖使用案例](/help/data-views/data-views-usecases.md) 的子菜單。

## eVars和道具概念的變化

C. [!UICONTROL 埃瓦爾]。 [!UICONTROL 道], [!UICONTROL 事件] 在傳統的Adobe Analytics [!UICONTROL Customer Journey Analytics]。 在Adobe Analytics,eVars和props儲存對內容、客戶、活動等的描述。 而事件會計收入、訂閱或生成的線索等。 Customer Journey Analytics保留了這兩種類型的資料，並且您可以以相同的方式訪問它們 — 分別從Analysis Workspace的左滑軌Dimension或度量下訪問。

在CJA中，有無限的架構元素，包括維、度量和清單欄位。 這些元素映射到無限方案元素，包括Experience Platform中的維、度量和清單欄位。 在Adobe Analytics處理規則後應用的所有訪問和屬性設定現在都在查詢時在Customer Journey Analytics中應用。

利用這種靈活性，您可能會遇到這樣的情況：單個架構欄位既可用作維又可用作度量，以支援不同的跟蹤需求。

## 對段概念的更改

Adobe已將&quot;段&quot;部分改為&quot;過濾器&quot;，以便更好地與行業標準保持一致，更好地區分Adobe Experience Platform的段。

[!UICONTROL Customer Journey Analytics] 不再使用eVars、props或事件，而是使用它們已映射到的Experience Platform架構欄位名稱。 這一變化意味著，Adobe Analytics現有的段均不與 [!UICONTROL Customer Journey Analytics]。 如果要將現有Adobe Analytics段移至Customer Journey Analytics，請參閱以下視頻：

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

雖然您尚不能共用或發佈 [!UICONTROL 篩選] ([!UICONTROL 段]從 [!DNL Customer Journey Analytics] 要Experience Platform統一配置檔案，此功能正在開發中。

除了段更改的概念外，段容器也會更新。

* **命中容器現在是「事件」容器**。 「[!UICONTROL 人員]」容器包含指定時間段內訪客的每個工作階段和事件。
* **訪問容器現在是「會話」容器**。 「[!UICONTROL 工作階段]」容器可讓您識別特定工作階段的頁面互動、促銷活動或轉換。
* **訪問者集裝箱現已 [!UICONTROL 人員] 容器**。 「[!UICONTROL 人員]」容器包含指定時間段內訪客的每個工作階段和事件。

## 對計算度量概念的更改

計算的度量在傳統分析和CJA之間的名稱類似。 但是， [!UICONTROL Customer Journey Analytics] 不再使用eVars、props或events，而是使用任何Experience Platform架構元素。 這一根本性變化意味著現有計算度量都與 [!UICONTROL Customer Journey Analytics]。 如果要將Adobe Analytics計算的度量移到Customer Journey Analytics，請參閱以下視頻：

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## 對變數屬性和過期設定的更改

[!UICONTROL Customer Journey Analytics] 在報告時應用所有變數設定，包括屬性和過期。 這些設定現在位於 [資料視圖](/help/data-views/component-settings/persistence.md)，並且某些變數設定（如屬性）可以在Workspace項目中更改。

在同一資料視圖中，可以有多個版本的同一變數。 例如，您可以有一個跟蹤代碼維，該維在30天後過期，另一個維在會話結束時過期。 這兩個跟蹤代碼維都使用相同的源資料，但使用不同的屬性設定。

您還可以基於同一連接具有多個資料視圖。 例如，您可以有一個會話超時為30分鐘的資料視圖，另一個會話超時為15分鐘的資料視圖。 兩個資料視圖都顯示在右上部選擇器中，因此您可以在它們之間無縫轉換。

## 對分類概念的更改

「分類」現在稱為「查找資料集」。 查找資料集用於查找在事件或配置檔案資料中找到的值或鍵。 例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。請參閱 [將帳戶級別資料添加為查找資料集](/help/use-cases/b2b.md) 例如用例。

## 對客戶屬性概念的更改

「客戶屬性」現在稱為「配置式資料集」。 配置檔案資料集包含應用於訪問者、用戶或客戶的資料 [!UICONTROL 事件] 資料。 例如，它允許您上傳有關客戶的CRM資料。 您可以挑選要包含的人員 ID。定義的每個資料集 [!DNL Experience Platform] 定義了自己的一個或多個人員ID集。

## 對Adobe識別訪問者方式的更改

CJA將標識的概念擴展到ECID之外，以包括要使用的任何ID，包括客戶ID、Cookie ID、縫合ID、用戶ID、跟蹤代碼等。 跨資料集使用公用命名空間ID，或使用 [跨渠道分析](/help/connections/cca/overview.md) 幫助將不同資料集的人聯繫在一起。 任何在CJA中設定Workspace項目的用戶都必須瞭解跨資料集使用的ID。 請參閱以下視頻，突出顯示CJA中標識的使用：

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## 對低流量維項概念的更改

在傳統Adobe Analytics中，接收太多唯一值的變數將在 [!UICONTROL 低流量]。 CJA對高基數欄位的限制較少。 對報告體系結構的更改使Analysis Workspace能夠報告許多更獨特的維項。 請參閱 [長尾](../analysis-workspace/workspace-faq/long-tail.md) 有關CJA如何為具有許多唯一值的維優化報告的詳細資訊，
