---
title: 建立受眾並將其發佈到即時客戶配置檔案
description: 瞭解如何從Customer Journey Analytics發佈觀眾
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 0108b07fd4fac33d026b8832931ffa3018b298e0
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 6%

---

# 建立和發佈受眾

>[!NOTE]
>
>此功能當前位於 [有限測試](/help/release-notes/releases.md)。

本主題討論如何建立和發佈Customer Journey Analytics(CJA)中標識的受眾 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=tw) 在Adobe Experience Platform的客戶定位和個性化。

閱讀 [概述](/help/components/audiences/audiences-overview.md) 熟悉CJA觀眾的概念。

## 建立對象

1. 要建立受眾，您有三種入門方法：

   | 建立方法 | 詳細資料 |
   | --- | --- |
   | 從主 **[!UICONTROL 元件] > [!UICONTROL 觀眾]** 菜單 | 將開啟「受眾管理器」頁。 按一下 **[!UICONTROL 建立受眾]** 和 [!UICONTROL 受眾構建器] 的上界。 |
   | 從自由形式表內 | 按一下右鍵「自由形式」(Freeform)表格中的項，然後選擇 **[!UICONTROL 從所選內容建立受眾]**。 使用此方法使用在表中選擇的維或維項預先填充篩選器。 |
   | 從篩選器建立/編輯UI | 選中顯示 **[!UICONTROL 通過此篩選器建立受眾]**。 使用此方法預填充篩選器。 |

   {style=&quot;table-layout:auto&quot;}

1. 構建受眾。

   在發佈受眾之前配置這些設定。

   ![](assets/create-audience.png)

   | 設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 名稱] | 受眾的名稱。 |
   | [!UICONTROL 標記] | 為組織目的而分配給受眾的任何標籤。 可以使用預先存在的標籤或輸入新標籤。 |
   | [!UICONTROL 說明] | 添加對受眾的良好描述，以區別於其他受眾。 |
   | [!UICONTROL 重新整理頻率] | 要刷新觀眾的頻率。<ul><li>您可以選擇建立不需要刷新的一次性訪問群體（預設）。 例如，這對特定的一次性市場活動可能有所幫助。</li><li>可以選擇其他刷新間隔。 4小時頻率限制為75或150個觀眾，具體取決於您的CJA權利。 對於其他時間間隔，沒有最大數量的受眾。</li></ul> |
   | 到期日期 | 觀眾何時停止刷新。 預設值為自建立日期起1年。 即將過期的受眾會被視為與過期的計畫報告類似 — 管理員在受眾過期前一個月收到一封電子郵件。 |
   | 重新整理回溯窗口 | 指定在建立此受眾時要在資料窗口中返回的距離。 最大為90天。 |
   | [!UICONTROL 一次性日期範圍] | 希望發佈一次性受眾的日期範圍。 |
   | [!UICONTROL 篩選器] | 過濾器是對受眾的主要輸入。 最多可以添加20個篩選器。 這些篩選器可與 `And` 或 `Or` 運算子。 |
   | [!UICONTROL 檢視範例 ID] | 此受眾中的ID示例。 使用搜索欄搜索示例ID。 |

   {style=&quot;table-layout:auto&quot;&quot;

1. 解釋資料預覽。

   觀眾預覽顯示在右欄中。 它允許對您建立的受眾進行匯總分析。

   ![](assets/data-preview.png)

   | 預覽設定 | 說明 |
   | --- | --- |
   | [!UICONTROL 資料預覽] 窗口 | 受眾的日期範圍。 |
   | [!UICONTROL 總人數] | 此受眾中總人數的匯總數。 它可以容納1億人。 如果您的受眾超過1億人，則必須先縮小受眾規模，然後才能發佈。 |
   | [!UICONTROL 對象人數限制] | 顯示這個觀眾的1億限制有多遠。 |
   | [!UICONTROL 預估的對象回訪] | 此設定對於重新瞄準此訪問群體中返回您的站點的客戶非常有用。 （換句話說，在此資料集中再次出現。） <p>在此，您可以為估計可返回的客戶數選擇時間範圍（下7天、下2週、下月）。 |
   | [!UICONTROL 預估的回訪] | 此數字為您提供了在從下拉清單中選擇的時間範圍內的估計數量的返回客戶。 我們觀察了這些觀眾的歷史流失率來預測這個數字。 |
   | [!UICONTROL 預覽量度] | 此設定允許您查看特定指標，以查看此受眾是否對此指標貢獻了不成比例的金額，如「 」[!UICONTROL 收入]或[!UICONTROL 現場平均時間]「 」。 它為您提供度量的聚合計數以及它所代表的總百分比。 您可以選擇資料視圖中可用的任何度量。 |
   | [!UICONTROL 包含的命名空間] | 與受眾中的人關聯的特定命名空間。 示例包括ECID、CRM ID、電子郵件地址等。 |
   | [!UICONTROL 沙箱] | 的 [Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant) 此受眾所在的位置。 將此訪問群體發佈到平台時，您只能在此沙箱的範圍內使用它。 |

   {style=&quot;table-layout:auto&quot;&quot;

1. 按兩下您的受眾配置 **[!UICONTROL 發佈]**。

   如果一切順利，您將收到一條確認消息，告知觀眾已經發佈。 這個觀眾只需一兩分鐘就能出現在Experience Platform。 （即使是擁有數百萬成員的觀眾，也需要不到5分鐘。）

1. 按一下 **[!UICONTROL 查看AEP中的受眾]** 在同一條消息中，您將被 [段UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=en) 在Adobe Experience Platform。 請參閱參下方瞭解詳情。

## 在Experience Platform中使用CJA觀眾


CJA現在將從發佈的受眾獲取所有命名空間和ID組合，並將它們流式傳輸到即時客戶配置檔案(RTCP)中。 然後，RTCP檢查每個命名空間/ID組合，並查找它可能屬於的配置檔案。 配置檔案基本上是連結的命名空間、 ID和設備的群集。 如果找到配置檔案，它將將命名空間和ID作為段成員屬性添加到此配置檔案中的其他ID中。 現在，例如，「user@adobe.com」可以跨所有設備和通道成為目標。 如果找不到配置檔案，則會建立新配置檔案。

通過轉到 **[!UICONTROL 段]** > **[!UICONTROL 建立段]** > **[!UICONTROL 觀眾]** 頁籤 **[!UICONTROL CJA觀眾]**。

可將CJA受眾拖入AEP段的段定義中。

![](assets/audiences-aep.png)

## 後續步驟

* 要管理此受眾，請轉到 [管理UI](/help/components/audiences/manage.md)。
