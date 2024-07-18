---
title: 建立對象並將對象發佈到即時客戶個人檔案
description: 了解如何從 Customer Journey Analytics 發佈對象
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 91ab1d3160db83979e1550f8f1b5135065cc6707
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 57%

---

# 建立及發佈對象

此主題討論如何將在Customer Journey Analytics中識別的對象建立並發佈到Adobe Experience Platform中的[即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)，以用於客戶目標定位和個人化。

請閱讀此[總覽](/help/components/audiences/audiences-overview.md)，熟悉Customer Journey Analytics對象的概念。

## 建立對象 {#create}

1. 您可以透過三種方法建立對象：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從主要&#x200B;**[!UICONTROL 「元件] > [!UICONTROL 對象」]**&#x200B;選單 | 系統會開啟 Audience Manager 頁面。按一下「**[!UICONTROL 建立對象]**」，[!UICONTROL 對象產生器]隨即開啟。 |
   | 從自由格式表格 | 以右鍵按一下自由格式表格中的項目，然後選擇「**[!UICONTROL 從選取項目建立對象]**」。此方法會使用您在表格中選擇的維度或維度項目預先填入篩選器。 |
   | 從篩選器建立/編輯 UI | 勾選顯示「**[!UICONTROL 從這個篩選器建立對象]**」的方塊。使用此方法預先填入篩選器。 |

   {style="table-layout:auto"}

1. 建置對象。

   請先配置設定，然後才能發佈對象。

   ![建立下一節所述對象傾斜設定的熒幕擷圖。](assets/create-audience.png)

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 對象名稱。 |
   | [!UICONTROL 標記] | 任何您針對組織目的想要套用到對象的標籤。您可以使用現有的標籤或輸入新的標籤。 |
   | [!UICONTROL 說明] | 新增對象的優質說明，以與其他對象區分開來。 |
   | [!UICONTROL 重新整理頻率] | 您想要重新整理對象的頻率。<ul><li>您可以選擇建立單次、不需重新整理的對象 (預設)。例如，這可能適合用於特定單次行銷活動。</li><li>您也可以選擇其他重新整理間隔。在4小時的重新整理頻率中，有75到150個對象重新整理的限制，具體取決於您的Customer Journey Analytics權益。</li></ul> |
   | 到期日 | 對象停止重新整理的時間。預設到期日是從建立日期算起的 1 年後。系統處理即將到期對象的方法與即將到期的排程報告相似，管理員會在對象到期的一個月前收到通知電子郵件。 |
   | 重新整理回顧期間 | 在建立此對象時，指定資料回溯期間的長度。最長 90 天。 |
   | [!UICONTROL 一次性日期範圍] | 您想要發佈一次性對象的日期範圍。 |
   | [!UICONTROL 篩選器] | 篩選器是對象的主要輸入項目。可最多新增 20 個篩選器。這些篩選器可以加入 `And`或 `Or` 運算子。 |
   | [!UICONTROL 檢視範例 ID] | 此對象中的範例 ID。使用搜尋列來搜尋範例 ID。 |

   {style="table-layout:auto"}

1. 解讀資料預覽。

   對象預覽會顯示在右側邊欄中。它允許對您建立的對象進行摘要分析。

   ![顯示對象摘要分析的資料預覽熒幕擷圖。](assets/data-preview.png)

   | 預覽設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 資料預覽]視窗 | 對象的日期範圍。 |
   | [!UICONTROL 總人數] | 此對象中總人數的摘要數字。最多可以高達 2 千萬人。如果您的對象超過 2 千萬人，您必須先減少對象規模，才能發佈。 |
   | [!UICONTROL 對象規模限制] | 顯示此對象規模距離 2 千萬人限制還差多少。 |
   | [!UICONTROL 預估的對象回訪] | 此設定對於將此對象中回訪您網站、行動應用程式或其他管道（換言之，又會在此資料集中看到）的客戶做為目標很有用。 <p>在這裡，您可以選取可能回訪的估計客戶數量的時間範圍 (接下來 7 天、接下來 2 週、下個月)。 |
   | [!UICONTROL 預估回訪] | 此數字可提供從下拉式清單中所選時間範圍內的回訪客戶估計數量。我們查看該對象的歷史流失率來預測這個數字。 |
   | [!UICONTROL 預覽量度] | 此設定可讓您查看特定量度，以了解此對象是否對此量度貢獻了不成比例的數量，例如「[!UICONTROL 收入]」或「[!UICONTROL 網站平均逗留時間]」。它為您提供量度的彙總計數，以及它所代表的總數的百分比。您可以選取資料檢視中可用的任何量度。 |
   | [!UICONTROL 包含的命名空間] | 與對象中的人員相關聯的特定命名空間。範例包括 ECID、CRM ID、電子郵件地址等。 |
   | [!UICONTROL 沙箱] | 此對象所在的 [Experience Platform 沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。當您將此對象發佈到 Platform 時，您只能在此沙箱的範圍內使用它。 |

   {style="table-layout:auto"}

1. 仔細檢查您的對象組態，然後按一下&#x200B;**[!UICONTROL 「發佈」]**。

   如果一切順利，您會收到一則對象已發佈的確認訊息。只需一兩分鐘，此對象就會出現在 Experience Platform 中。(即使是擁有數百萬成員的對象，應該也不需要 5 分鐘。)

1. 按一下同一則訊息中的&#x200B;**[!UICONTROL 「在 AEP 中檢視對象」]**，您將被帶到 Adobe Experience Platform 中的[「區段 UI」](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hant)。請參閱下方以了解更多資訊。

## 建立對象後的情況? {#after-audience-created}

建立對象後，Adobe會為每個新Experience Platform對象建立Customer Journey Analytics串流區段。 只有貴組織設為串流區隔時，才會建立Adobe Experience Platform串流區隔。

* Adobe Experience Platform區段會與Customer Journey Analytics對象共用相同的名稱/說明，但名稱會附加Customer Journey Analytics對象ID，以確保其是唯一的。
* 如果Customer Journey Analytics對象名稱/說明有所變更，Adobe Experience Platform區段名稱/說明也會反映這項變更。
* 如果使用者刪除了Customer Journey Analytics對象，系統不會刪除Adobe Experience Platform區段。 原因在於Customer Journey Analytics對象稍後可能會遭到取消刪除。

## 延遲的注意事項 {#latency}

在對象發佈之前、期間和之後的數個時間點，可能會發生延遲。 以下是可能的延遲的概觀。

![此章節中所述的對象發佈延遲。](/help/components/audiences/assets/latency-diagram.png)

| # | 延遲點 | 延遲期間 |
| --- | --- | --- |
| 未顯示 | Adobe Analytics至Analytics來源聯結器(A4T) | 最多需 30 分鐘 |
| 1 | 將資料擷取至Data Lake （從Analytics來源聯結器或其他來源） | 最多需 90 分鐘 |
| 2 | 從Experience Platform Data Lake將資料擷取至Customer Journey Analytics | 最多需 90 分鐘 |
| 3 | 對象發佈至即時客戶設定檔，包括自動建立串流區段並允許該區段準備接收資料。<p>**注意**：對象會在1-2分鐘內以Experience Platform建立/定義。 不過，對象需要大約60分鐘才會開始根據相符條件收到ID，並準備好啟用。 | 約 60 分鐘 |
| 4 | 對象的重新整理頻率 | <ul><li>一次性重新整理 (延遲時間小於 5 分鐘)</li><li>每 4 小時、每天、每週、每月重新整理一次 (延遲與重新整理頻率息息相關) |
| 5 | 在Adobe Experience Platform中建立目的地：啟用新區段 | 1-2 小時 |

{style="table-layout:auto"}

## 在Experience Platform中使用Customer Journey Analytics對象 {#audiences-aep}

Customer Journey Analytics會從您發佈的對象中取得所有名稱空間和ID組合，並將它們串流傳送到即時客戶個人檔案(RTCP)。 根據設定連線時選取的[!UICONTROL 人員ID]，Customer Journey Analytics會將對象傳送至已設定主要身分的Experience Platform。

接著 RTCP 會檢查每個命名空間/ID 組合，並尋找它可能屬於的個人檔案。個人檔案基本上是一組連結的命名空間、ID 和裝置。如果找到個人檔案，則會將命名空間和 ID 新增到此個人檔案中的其他 ID，做為區段會籍屬性。例如，現在可以跨其所有裝置和管道以<user@adobe.com>為目標。 如果找不到個人檔案，則會建立一個新的。

您可以在Platform中檢視Customer Journey Analytics對象，方法是前往&#x200B;**[!UICONTROL 區段]** > **[!UICONTROL 建立區段]** > **[!UICONTROL 對象]**&#x200B;標籤> **[!UICONTROL CJA對象]**。

您可以將Customer Journey Analytics受眾拖曳至Adobe Experience Platform區段的區段定義。

![Adobe Experience Platform UI在左窗格中醒目提示區段，並在主面板中醒目提示CJA對象。](assets/audiences-aep.png)

## 常見問題 {#faq}

對象發佈的常見問題。

+++**如果使用者不再是Customer Journey Analytics中的對象成員，會發生什麼情況？**

在這種情況下，系統會從Customer Journey Analytics傳送退出事件給Experience Platform。

+++

+++**如果您刪除Customer Journey Analytics中的對象，會發生什麼事？**

刪除Customer Journey Analytics對象時，該對象不會在Experience PlatformUI中顯示。 然而，實際上不會刪除在 Platform 中與該對象相關聯的設定檔。

+++

+++**如果 RTCDP 中沒有對應的設定檔，是否會建立新的設定檔？**

是，會建立。

+++

+++**Customer Journey Analytics是以管線事件還是同樣會傳送至資料湖的平面檔案的形式傳送對象資料？**

Customer Journey Analytics會透過管道將資料串流到RTCP中，而且這些資料也會收集到資料湖的系統資料集中。

+++

+++**Customer Journey Analytics傳送哪些身分？**

在[連線設定](https://experienceleague.adobe.com/tw/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)中指定的任何識別/名稱空間配對。 具體而言，就是使用者選取要作為其「人員 ID」之欄位時的步驟。

+++

+++**選擇哪個 ID 作為主要身分？**

請參閱上述內容。我們只會針對每個Customer Journey Analytics「人員」傳送一個身分。

+++

+++**RTCP是否也會處理Customer Journey Analytics訊息？ Customer Journey Analytics是否可透過對象共用將身分新增至設定檔身分圖表？**

否。我們只會為每個「人員」發送一個身分，因此 RTCP 將沒有圖形邊可供使用。

+++

+++**一天中的哪個時間進行每日、每週和每月的重新整理？ 每週的哪一天會進行每週重新整理？**

重新整理的時間會根據原始對象的發佈時間以及當天時間的錨點（以及一週中的某天或一個月中的某天）來確定。

+++

+++**使用者是否可以設定每日、每週和每月的重新整理時間？**

不可以，使用者無法設定它們。

+++


## 後續步驟

* 若要管理此對象，請前往[「管理 UI」](/help/components/audiences/manage.md)。
