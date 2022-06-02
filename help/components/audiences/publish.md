---
title: 建立受眾並將其發佈到即時客戶配置檔案
description: 瞭解如何從Customer Journey Analytics發佈觀眾
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# 建立和發佈受眾

本主題討論如何將在Customer Journey Analytics(CJA)中發現的受眾發佈到 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=tw) 在Adobe Experience Platform的客戶定位和個性化。

## 建立對象

1. 要建立受眾，您有三種入門方法：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從 **[!UICONTROL 元件] > [!UICONTROL 觀眾]** | 將開啟「受眾管理器」頁。 按一下 **[!UICONTROL 建立受眾]** 和 [!UICONTROL 受眾構建器] 的上界。 |
   | 從自由形式表內 | 按一下右鍵「自由形式」(Freeform)表格中的項，然後選擇 **[!UICONTROL 從所選內容建立受眾]**。 使用此方法使用在表中選擇的維或維項預先填充篩選器。 |
   | 從篩選器編輯UI | 選中顯示 **[!UICONTROL 通過此篩選器建立受眾]**。 使用此方法預填充篩選器。 |

   {style=&quot;table-layout:auto&quot;}

1. 配置訪問群體。

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 受眾的名稱。 |
   | [!UICONTROL 標記] | 為組織目的而分配給受眾的任何標籤。 可以使用預先存在的標籤或輸入新標籤。 |
   | [!UICONTROL 說明] | 添加對受眾的良好描述，以區別於其他受眾。 |
   | [!UICONTROL 重新整理頻率] | 要刷新觀眾的頻率。<ul><li>您可以選擇建立一次性受眾（預設），無需刷新，這對特定的一次性市場活動（例如）很有幫助。</li><li>可以選擇其他刷新間隔。 對於4小時頻率，受眾數量限制為150個，因為此刷新率非常需要處理。 對於其他中間人，沒有最多的觀眾數。</li></ul> |
   | 到期日期 | 觀眾何時停止刷新。 預設值為自建立日期起1年。 |
   | 重新整理回溯窗口 | 指定在建立此受眾時要在資料窗口中返回的距離。 最大。 90天。 過期的受眾會像過期的計畫報告一樣 — 管理員在計畫過期前一個月收到一封電子郵件。 |
   | [!UICONTROL 一次性日期範圍] | 希望發佈一次性受眾的日期範圍。 |
   | [!UICONTROL 篩選器] | 過濾器是對受眾的主要輸入。 最多可以添加20個篩選器。 這些篩選器可與 `And` 或 `Or` 運算子。 |

   {style=&quot;table-layout:auto&quot;&quot;

1. 解釋資料預覽。

   觀眾預覽顯示在右欄中。

   | 預覽設定 | 說明 |
   | --- | --- |
   | 資料預覽窗口 | 受眾的日期範圍。 |
   | 觀眾總人數 | 一個總數可以高達1億。 |
   | 對象人數限制 | 顯示這個觀眾的1億限制有多遠。 |
   | 預估的對象回訪 |  |
   | 預估的回訪 | 摘要編號…… |
   | 預覽量度 |  |

   {style=&quot;table-layout:auto&quot;&quot;


