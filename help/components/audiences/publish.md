---
title: 建立對象並將對象發佈到即時客戶個人檔案
description: 了解如何從 Customer Journey Analytics 發佈對象
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 9ff64cb1b30fef5c475ecc6f7d19961144530095
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 36%

---

# 建立及發佈對象

本主題討論如何建立和發佈Customer Journey Analytics(CJA)中標識的受眾 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hant) 在Adobe Experience Platform的客戶定位和個性化。

閱讀 [概述](/help/components/audiences/audiences-overview.md) 熟悉CJA觀眾的概念。

## 建立對象

1. 您可以透過三種方法建立對象：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從主 **[!UICONTROL 元件] > [!UICONTROL 觀眾]** 菜單 | 系統會開啟 Audience Manager 頁面。 按一下「**[!UICONTROL 建立對象]**」，[!UICONTROL 對象產生器]隨即開啟。 |
   | 從自由格式表格 | 以右鍵按一下自由格式表格中的項目，然後選擇「**[!UICONTROL 從選取項目建立對象]**」。 此方法會使用您在表格中選擇的維度或維度項目預先填入篩選器。 |
   | 從篩選器建立/編輯UI | 勾選顯示「**[!UICONTROL 從這個篩選器建立對象]**」的方塊。 使用此方法預先填入篩選器。 |

   {style=&quot;table-layout:auto&quot;}

1. 構建受眾。

   在發佈受眾之前配置這些設定。

   ![](assets/create-audience.png)

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 對象名稱。 |
   | [!UICONTROL 標記] | 任何您針對組織目的想要套用到對象的標籤。 您可以使用現有的標籤或輸入新的標籤。 |
   | [!UICONTROL 說明] | 新增對象的優質說明，以與其他對象區分開來。 |
   | [!UICONTROL 重新整理頻率] | 您想要重新整理對象的頻率。<ul><li>您可以選擇建立不需要刷新的一次性訪問群體（預設）。 例如，這對特定的一次性市場活動可能有所幫助。</li><li>您也可以選擇其他重新整理間隔。 4小時頻率限制為75或150個觀眾，具體取決於您的CJA權利。 對於其他時間間隔，沒有最大數量的受眾。</li></ul> |
   | 到期日 | 對象停止重新整理的時間。 預設到期日是從建立日期算起的 1 年後。即將過期的受眾會被視為與過期的計畫報告類似 — 管理員在受眾過期前一個月收到一封電子郵件。 |
   | 重新整理回顧期間 | 在建立此對象時，指定資料回溯期間的長度。 最大為90天。 |
   | [!UICONTROL 一次性日期範圍] | 您想要發佈一次性對象的日期範圍。 |
   | [!UICONTROL 篩選器] | 篩選器是對象的主要輸入項目。 可最多新增 20 個篩選器。 這些篩選器可以加入 `And` 或 `Or` 運算子。 |
   | [!UICONTROL 檢視範例 ID] | 此受眾中的ID示例。 使用搜索欄搜索示例ID。 |

   {style=&quot;table-layout:auto&quot;&quot;

1. 解讀資料預覽。

   對象預覽會顯示在右側邊欄中。它允許對您建立的受眾進行匯總分析。

   ![](assets/data-preview.png)

   | 預覽設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 資料預覽視窗] | 對象的日期範圍。 |
   | [!UICONTROL 總人數] | 此受眾中總人數的匯總數。 它可以達到兩億人。 如果您的受眾超過2億，則必須先縮小受眾規模，然後才能發佈。 |
   | [!UICONTROL 對象規模限制] | 顯示此受眾的2億限制距離有多遠。 |
   | [!UICONTROL 預估的對象回訪] | 此設定對於重新瞄準此訪問群體中返回您的站點的客戶非常有用。 （換句話說，在此資料集中再次出現。） <p>在此，您可以為估計可返回的客戶數選擇時間範圍（下7天、下2週、下月）。 |
   | [!UICONTROL 預估回訪] | 此數字為您提供了在從下拉清單中選擇的時間範圍內的估計數量的返回客戶。 我們觀察了這些觀眾的歷史流失率來預測這個數字。 |
   | [!UICONTROL 預覽量度] | 此設定允許您查看特定指標，以查看此受眾是否對此指標貢獻了不成比例的金額，如「 」[!UICONTROL 收入]或[!UICONTROL 現場平均時間]「 」。 它為您提供度量的聚合計數以及它所代表的總百分比。 您可以選擇資料視圖中可用的任何度量。 |
   | [!UICONTROL 包含的命名空間] | 與受眾中的人關聯的特定命名空間。 示例包括ECID、CRM ID、電子郵件地址等。 |
   | [!UICONTROL 沙箱] | 的 [Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant) 此受眾所在的位置。 將此訪問群體發佈到平台時，您只能在此沙箱的範圍內使用它。 |

   {style=&quot;table-layout:auto&quot;&quot;

1. 按兩下您的受眾配置 **[!UICONTROL 發佈]**。

   如果一切順利，您將收到一條確認消息，告知觀眾已經發佈。 這個觀眾只需一兩分鐘就能出現在Experience Platform。 （即使是擁有數百萬成員的觀眾，也需要不到5分鐘。）

1. 按一下 **[!UICONTROL 查看AEP中的受眾]** 在同一條消息中，您將被 [段UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=en) 在Adobe Experience Platform。 請參閱參下方瞭解詳情。

## 在Experience Platform中使用CJA觀眾


CJA現在將從發佈的受眾獲取所有命名空間和ID組合，並將它們流式傳輸到即時客戶配置檔案(RTCP)中。 然後，RTCP檢查每個命名空間/ID組合，並查找它可能屬於的配置檔案。 配置檔案基本上是連結的命名空間、 ID和設備的群集。 如果找到配置檔案，它將將命名空間和ID作為段成員屬性添加到此配置檔案中的其他ID中。 現在，例如，「user@adobe.com」可以跨所有設備和通道成為目標。 如果找不到配置檔案，則會建立新配置檔案。

您可以在 Platform 中檢視 CJA 對象，方法是前往「**[!UICONTROL 區段]** > **[!UICONTROL 建立區段]** > **[!UICONTROL 對象]**&#x200B;標籤 > **[!UICONTROL CJA 對象]**」。

您可以將 CJA 對象拖到 AEP 區段的區段定義。

![](assets/audiences-aep.png)

## 後續步驟

* 要管理此受眾，請轉到 [管理UI](/help/components/audiences/manage.md)。
