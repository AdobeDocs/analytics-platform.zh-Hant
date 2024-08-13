---
title: 建立客群並將客群發佈到即時客戶輪廓
description: 了解如何從 Customer Journey Analytics 發佈客群
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: c384c4cdd1a63fd26e6eff0ff3394a089105275c
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 53%

---

# 建立及發佈客群

此主題討論如何將在Customer Journey Analytics中識別的對象建立並發佈到Adobe Experience Platform中的[即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant)，以用於客戶目標定位和個人化。

請閱讀此[總覽](/help/components/audiences/audiences-overview.md)，熟悉Customer Journey Analytics對象的概念。

## 建立及發佈對象 {#create}

1. 若要開始建立和發佈對象，請執行下列任一項作業：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從主要&#x200B;**[!UICONTROL 「元件] > [!UICONTROL 客群」]**&#x200B;選單 | 系統會開啟 Audience Manager 頁面。按一下「**[!UICONTROL 建立客群]**」，[!UICONTROL 客群產生器]隨即開啟。 |
   | 從自由格式表格 | 右鍵按一下自由格式表格中的項目，然後選擇「**[!UICONTROL 從選取項目建立客群]**」。此方法會使用您在表格中選擇的維度或維度項目預先填入篩選器。 |
   | 從篩選器建立/編輯 UI | 勾選顯示「**[!UICONTROL 通過此篩選建立客群]**」的方塊。使用此方法預先填入篩選器。 |

   {style="table-layout:auto"}

1. 建置客群。

   請先配置設定，然後才能發佈客群。

   ![建立下一節所述對象傾斜設定的熒幕擷圖。](assets/create-audience.png)

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 客群名稱。 |
   | [!UICONTROL 標記] | 任何您針對組織目的想要套用到客群的標籤。您可以使用現有的標籤或輸入新的標籤。 |
   | [!UICONTROL 說明] | 新增客群的優質說明，以與其他客群區分開來。 |
   | [!UICONTROL 重新整理頻率] | 您想要重新整理客群的頻率。<ul><li>您可以選擇建立一次性的、不需更新的客群 (預設)。例如，這可能適合用於特定單次行銷活動。</li><li>您也可以選擇其他重新整理間隔。在4小時的重新整理頻率中，有75到150個對象重新整理的限制，具體取決於您的Customer Journey Analytics權益。</li></ul> |
   | 到期日 | 客群停止更新的時間。預設到期日是從建立日期算起的 1 年後。系統處理即將到期客群的方法與即將到期的排程報告相似，管理員會在客群到期前的一個月收到通知電子郵件。 |
   | 重新整理回顧期間 | 在建立此客群時，指定資料回溯期間的長度。最長 90 天。 |
   | [!UICONTROL 一次性日期範圍] | 您想要發佈一次性客群的日期範圍。 |
   | [!UICONTROL 篩選器] | 篩選條件是客群的主要輸入項目。可最多新增 20 個篩選器。這些篩選器可以加入 `And`或 `Or` 運算子。 |
   | [!UICONTROL 檢視範例 ID] | 此客群中的範例 ID。使用搜尋列來搜尋範例 ID。 |

   {style="table-layout:auto"}

1. 解讀資料預覽。

   客群預覽會顯示在右側邊欄中。它允許對您建立的客群進行摘要分析。

   ![顯示對象摘要分析的資料預覽熒幕擷圖。](assets/data-preview.png)

   | 預覽設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 資料預覽]視窗 | 客群的日期範圍。 |
   | [!UICONTROL 總人數] | 此客群中總人數的摘要數字。最多可以高達 2 千萬人。如果您的客群超過 2 千萬人，您必須先減少客群規模，才能發佈。 |
   | [!UICONTROL 客群規模限制] | 顯示此客群規模距離 2 千萬人限制還差多少。 |
   | [!UICONTROL 預估的客群回訪] | 此設定對於將此對象中回訪您網站、行動應用程式或其他管道（換言之，又會在此資料集中看到）的客戶做為目標很有用。 <p>在這裡，您可以選取可能回訪的估計客戶數量的時間範圍 (接下來 7 天、接下來 2 週、下個月)。 |
   | [!UICONTROL 預估回訪] | 此數字可提供從下拉式清單中所選時間範圍內的回訪客戶估計數量。我們查看該客群的歷史流失率來預測這個數字。 |
   | [!UICONTROL 預覽量度] | 此設定可讓您查看特定量度，以了解此客群是否對此量度貢獻了不成比例的數量，例如「[!UICONTROL 收入]」或「[!UICONTROL 網站平均逗留時間]」。它為您提供量度的彙總計數，以及它所代表的總數的百分比。您可以選取資料檢視中可用的任何量度。 |
   | [!UICONTROL 包含的命名空間] | 與客群中的人員相關聯的特定命名空間。範例包括 ECID、CRM ID、電子郵件地址等。 |
   | [!UICONTROL 沙箱] | 此客群所在的 [Experience Platform 沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)。當您將此客群發佈到 Platform 時，您只能在此沙箱的範圍內使用它。 |

   {style="table-layout:auto"}

1. 仔細檢查您的客群組態，然後按一下&#x200B;**[!UICONTROL 「發佈」]**。

   如果一切順利，您會收到一則客群已發佈的確認訊息。只需一兩分鐘，此客群就會出現在 Experience Platform 中。(即使是擁有數百萬成員的客群，應該也不超過 5 分鐘。)

1. 按一下同一則訊息中的&#x200B;**[!UICONTROL 「在 AEP 中檢視客群」]**，您將被帶到 Adobe Experience Platform 中的[「細分群體 UI」](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=zh-Hant)。請參閱下方以了解更多資訊。

## 建立及發佈對象後會發生什麼事？ {#after-audience-created}

在Customer Journey Analytics中建立並發佈對象後，您就能在Experience Platform中使用該對象。 只有貴組織設為串流區隔時，才會建立Adobe Experience Platform串流區隔。

* Platform中的對象會與Customer Journey Analytics對象共用相同的名稱/說明，但名稱會附加Customer Journey Analytics對象ID，以確保其是唯一的。
* 在Customer Journey Analytics中對對象名稱或說明所做的任何變更都會反映在Platform中。
* 若對象已在Customer Journey Analytics中刪除，對象仍可在Platform中使用。

## 延遲的注意事項 {#latency}

在對象發佈之前、期間和之後的數個時間點，可能會發生延遲。 以下是可能的延遲的概觀。

![此章節中所述的對象發佈延遲。](assets/latency-diagram.svg)

| # | 延遲點 | 延遲期間 |
| --- | --- | --- |
| 未顯示 | Adobe Analytics至Analytics來源聯結器(A4T) | 最多需 30 分鐘 |
| 1 | 將資料擷取至Data Lake （從Analytics來源聯結器或其他來源） | 最多需 90 分鐘 |
| 2 | 從Experience Platform Data Lake將資料擷取至Customer Journey Analytics | 最多需 90 分鐘 |
| 3 | 客群發佈至即時客戶輪廓，包括自動建立串流細分群體並允許該細分群體準備接收資料。 | 幾秒鐘 |
| 4 | 客群的更新頻率 | <ul><li>一次性重新整理 (延遲時間小於 5 分鐘)</li><li>每 4 小時、每天、每週、每月重新整理一次 (延遲與重新整理頻率息息相關) |
| 5 | 在Adobe Experience Platform中建立目的地：啟用新區段 | 1-2 小時 |

{style="table-layout:auto"}

## 在Experience Platform中使用Customer Journey Analytics對象 {#audiences-aep}

Customer Journey Analytics會從您發佈的對象中取得所有名稱空間和ID組合，並將它們串流傳送到即時客戶個人檔案(RTCP)。 根據設定連線時選取作為[!UICONTROL 人員ID]的專案，Customer Journey Analytics會將對象傳送至已設定主要身分的Experience Platform。

接著 RTCP 會檢查每個命名空間/ID 組合，並尋找它可能屬於的個人檔案。個人檔案基本上是一組連結的命名空間、ID 和裝置。如果找到設定檔，則會將名稱空間和ID新增到此設定檔中的其他ID，做為區段會籍屬性。 例如，<user@adobe.com>可以跨其所有裝置和管道進行定位。 如果找不到個人檔案，則會建立一個新的。

若要在Platform中檢視Customer Journey Analytics對象：

>[!AVAILABILITY]
>
>下列步驟中說明的功能處於發行的有限測試階段，可能尚未在您的環境中提供。 如果這些步驟與您在環境中看到的不相符，請改用以下步驟：移至&#x200B;[!UICONTROL **區段**] > [!UICONTROL **建立區段**] > [!UICONTROL **對象**]&#x200B;索引標籤> [!UICONTROL **CJA對象**]。
>
>當該功能供一般用途時，此備註將被刪除。如需Customer Journey Analytics發行程式的相關資訊，請參閱[Customer Journey Analytics功能發行](/help/release-notes/releases.md)。

1. 展開左側邊欄中的&#x200B;[!UICONTROL **客戶**]，然後選取&#x200B;[!UICONTROL **對象**]。<!-- is there a folder called "Customer Journey Analytics? -->

1. 選取&#x200B;[!UICONTROL **瀏覽**]&#x200B;標籤。

   左側面板中的![對象選項](assets/audiences-aep.png)

1. 若要找出您從Customer Journey Analytics發佈的對象，請執行下列任一項作業：

   * 依&#x200B;[!UICONTROL **Origin**]&#x200B;資料行排序資料表，以檢視將&#x200B;[!UICONTROL **Customer Journey Analytics**]&#x200B;顯示為來源的受眾。

   * 選取篩選器圖示。

   * 使用搜尋欄位。

如需在Platform中使用對象的詳細資訊，請參閱Experience Platform檔案之[區段產生器UI指南](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html)中的[對象](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#audiences)區段。


## 常見問題 {#faq}

客群發佈的常見問題。

+++**如果使用者不再是Customer Journey Analytics中的對象成員，會發生什麼情況？**

在這種情況下，系統會從Customer Journey Analytics傳送退出事件給Experience Platform。

+++

+++**如果您刪除Customer Journey Analytics中的對象，會發生什麼事？**

刪除Customer Journey Analytics對象時，該對象不會在Experience PlatformUI中顯示。 然而，實際上不會刪除在 Platform 中與該客群相關聯的輪廓。

+++

+++**如果 RTCDP 中沒有對應的設定檔，是否會建立新的設定檔？**

是，會建立。

+++

+++**Customer Journey Analytics是以管線事件還是同樣會傳送至資料湖的平面檔案的形式傳送對象資料？**

Customer Journey Analytics會透過管道將資料串流到RTCP中，而且這些資料也會收集到資料湖的系統資料集中。

+++

+++**Customer Journey Analytics傳送哪些身分？**

在[連線設定](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)中指定的任何識別/名稱空間配對。 具體而言，就是使用者選取要作為其「人員 ID」之欄位時的步驟。

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

* 若要管理此客群，請前往[「管理 UI」](/help/components/audiences/manage.md)。
