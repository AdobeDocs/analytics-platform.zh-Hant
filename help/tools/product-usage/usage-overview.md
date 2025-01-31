---
title: 產品使用概述
description: 檢視有關貴組織如何使用Customer Journey Analytics的深入分析和報表。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: e7534a1943307f5bbc92a845ddffe0651794b854
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---

# 產品使用概述

產品使用情況讓貴組織能夠檢視有關貴組織如何使用Customer Journey Analytics的分析資料。 它適用於使用Customer Journey Analytics的所有組織。 下列Adobe Experience Platform元件啟用後，系統會自動為您建立和連結。 這些元件均為系統擁有、唯讀，且無法編輯。

* Adobe Experience Platform中的結構描述
* Adobe Experience Platform中的資料集
* Customer Journey Analytics中的連線
* Customer Journey Analytics中的資料檢視

啟用後，所有資料收集和設定都會自動為您設定。 每當使用者在Analysis Workspace中執行動作時，該動作就會受到追蹤並可用於報表。

>[!IMPORTANT]
>
>此功能會計入Adobe Experience Platform中的合約列限制。 在啟用此功能之前，請確定您的組織可以容納此功能產生的資料。

## 啟用產品使用情況

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 產品使用量]**

瀏覽至Customer Journey Analytics介面的這個區段，會帶您前往[資料設定](data-settings.md)，您可以在其中啟用此功能。

## 可用維度

當您啟用產品使用時，可使用下列維度。 如果您想要變更任何維度設定，請建立系統擁有的資料檢視的復本，並在Analysis Workspace中使用複製的資料檢視。

* **[!UICONTROL 動作名稱]**：使用者採取的動作型別。 您可以在資料檢視設定中建立副本，將此維度作為任何需要的量度使用。 Dimension專案包括：
   * [!UICONTROL 新增歸因]
   * [!UICONTROL 新增元件]
   * [!UICONTROL 新增面板]
   * [!UICONTROL 新增視覺效果]
   * [!UICONTROL 建立新的引導分析]
   * [!UICONTROL 建立新專案]
   * [!UICONTROL 組織元件]
   * [!UICONTROL 下載 CSV]
   * [!UICONTROL 下載 PDF]
   * [!UICONTROL 載入引導分析]
   * [!UICONTROL 載入專案]
   * [!UICONTROL 新計分卡已載入]
   * [!UICONTROL 開啟資料字典]
   * [!UICONTROL 開啟智慧型字幕]
   * [!UICONTROL 專案共用]
   * [!UICONTROL 執行實驗面板]
   * [!UICONTROL 儲存專案]
   * [!UICONTROL 已儲存計分卡]
   * [!UICONTROL 傳送檔案]
   * [!UICONTROL 依排程傳送檔案]
   * [!UICONTROL 與任何人共用專案]
   * [!UICONTROL 與Workspace使用者共用專案]
* **[!UICONTROL 使用的歸因模型]**：元件使用的歸因模型型別。 Dimension專案包括：
   * [!UICONTROL 上次接觸]
   * [!UICONTROL 首次接觸]
   * [!UICONTROL 線性]
   * [!UICONTROL 參與率]
   * [!UICONTROL 同一次接觸]
   * [!UICONTROL U形]
   * [!UICONTROL J曲線]
   * [!UICONTROL 反向J]
   * [!UICONTROL 時間耗損]
   * [!UICONTROL 自訂]
   * [!UICONTROL 演算法]
* **[!UICONTROL 元件名稱]**：新增、移除或修改的元件名稱。
* **[!UICONTROL 元件型別]**：新增、移除或修改的元件型別。 Dimension專案包括：
   * [!UICONTROL 維度]
   * [!UICONTROL 量度]
   * [!UICONTROL 篩選]
   * [!UICONTROL 計算量度]
   * [!UICONTROL 日期範圍]
   * [!UICONTROL 註解]
   * [!UICONTROL 警報]
* **[!UICONTROL 登入使用者]**：執行此動作的使用者。
* **[!UICONTROL 使用的面板]**：新增、移除或修改元件的面板。 Dimension專案包括：
   * [!UICONTROL 歸因]
   * [!UICONTROL 空白面板]
   * [!UICONTROL 實驗]
   * [!UICONTROL 自由格式]
   * [!UICONTROL 下一個或上一個項目]
   * [!UICONTROL 快速深入分析]
   * [!UICONTROL 趨勢]
   * [!UICONTROL 漏斗]
   * [!UICONTROL 使用者增長]
   * [!UICONTROL 影響]
   * [!UICONTROL 使用者串流]
   * [!UICONTROL 保留]
   * [!UICONTROL 功能矩陣]
* **[!UICONTROL 專案名稱]**：專案的好記名稱。
* **[!UICONTROL 專案型別]**：專案型別。 Dimension專案包括：
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 使用的視覺效果]**：新增、移除或修改的視覺效果。 Dimension專案包括：
   * [!UICONTROL 自由格式表格]
   * [!UICONTROL 同類群組表格]
   * [!UICONTROL 流失]
   * [!UICONTROL 流程]
   * [!UICONTROL 歷程畫布小報告]
   * [!UICONTROL 區域]
   * [!UICONTROL 堆疊區域圖]
   * [!UICONTROL 條狀圖]
   * [!UICONTROL 棧疊長條圖]
   * [!UICONTROL 項目符號]
   * [!UICONTROL 組合]
   * [!UICONTROL 環形圖]
   * [!UICONTROL 直方圖]
   * [!UICONTROL 橫條圖]
   * [!UICONTROL 棧疊的水準橫條圖]
   * [!UICONTROL 關鍵量度摘要]
   * [!UICONTROL Line]
   * [!UICONTROL 地圖]
   * [!UICONTROL 散佈圖]
   * [!UICONTROL 區段標題]
   * [!UICONTROL 摘要變更]
   * [!UICONTROL 摘要數字]
   * [!UICONTROL Text]
   * [!UICONTROL 樹狀圖]
   * [!UICONTROL 文氏圖表]

僅開啟或檢視專案時，產品使用情況不會追蹤個別專案元件。 但是，將會追蹤開啟專案的使用者動作。
