---
title: 產品使用情況概觀
description: 檢視有關您的組織如何使用 Customer Journey Analytics 的深入分析和報告。
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 22f3059ffef5df76028f36ffa00da8f98956dee1
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 91%

---

# 產品使用情況概觀

產品使用情況會為您的組織提供檢視分析資料的能力，分析您的組織如何使用 Customer Journey Analytics。這適用於所有使用 Customer Journey Analytics 的組織。一旦啟用，以下 Adob&#x200B;&#x200B;e Experience Platform 元件會為您自動建立並連接。這些元件全部都是系統擁有、唯讀並且不能被編輯。

* 在 Adobe Experience Platform 中的結構描述
* 在 Adobe Experience Platform 中的資料集
* 在 Customer Journey Analytics 中的連線
* 在 Customer Journey Analytics 中的資料檢視

一旦啟用，所有資料收集和設定都會自動進行。每當使用者在 Analysis Workspace 中執行動作時，該動作都會被追蹤並可供報告。

>[!IMPORTANT]
>
>啟用產品使用情況後，使用情況資料會儲存在Adobe Experience Platform資料湖中。 請確定貴組織的資料湖儲存配置可容納啟用此功能所產生的其他資料集。
>
>此功能不會計入您的授權Customer Journey Analytics報告列限制或事件資料權益中。

## 啟用產品使用情況

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 工具]** > **[!UICONTROL 產品使用情況]**

導覽至 Customer Journey Analytics 介面的此部分，您將看到可啟用此功能的[資料設定](data-settings.md)。

## 適用的維度

當您啟用「產品使用情況」時，有以下維度可使用。如果您要變更任何維度設定，請建立系統擁有的資料檢視副本，並在 Analysis Workspace 中使用複製的資料檢視。

* **[!UICONTROL 動作名稱]**：使用者採取的動作類型。您可以透過在資料來視設定中建立副本，將此維度用作任何所需的量度。維度項目包含：
   * [!UICONTROL 新增歸因]
   * [!UICONTROL 新增元件]
   * [!UICONTROL 新增面板]
   * [!UICONTROL 新增視覺效果]
   * [!UICONTROL 建立新的引導式分析]
   * [!UICONTROL 建立新專案]
   * [!UICONTROL 組織元件]
   * [!UICONTROL 下載 CSV]
   * [!UICONTROL 下載 PDF]
   * [!UICONTROL 載入引導式分析]
   * [!UICONTROL 載入專案]
   * [!UICONTROL 已載入新計分卡]
   * [!UICONTROL 開啟資料字典]
   * [!UICONTROL 開啟智慧型註解]
   * [!UICONTROL 專案共用]
   * [!UICONTROL 執行實驗面板]
   * [!UICONTROL 儲存專案]
   * [!UICONTROL 計分卡已儲存]
   * [!UICONTROL 傳送檔案]
   * [!UICONTROL 依排程傳送檔案]
   * [!UICONTROL 與任何人共用專案]
   * [!UICONTROL 與 Workspace 使用者共用專案]
   * [!UICONTROL 切換資料釋圖]
* **[!UICONTROL 所使用的歸因模型]**：元件使用的歸因模型類型。維度項目包含：
   * [!UICONTROL 上次接觸]
   * [!UICONTROL 首次接觸]
   * [!UICONTROL 線性]
   * [!UICONTROL 參與率]
   * [!UICONTROL 同一次接觸]
   * [!UICONTROL U 形]
   * [!UICONTROL J 曲線]
   * [!UICONTROL 反向 J]
   * [!UICONTROL 時間耗損]
   * [!UICONTROL 自訂]
   * [!UICONTROL 演算法]
* **[!UICONTROL 元件 ID]**：已新增、移除或修改的元件 ID。
* **[!UICONTROL 元件名稱]**：已新增、移除或修改的元件易記名稱。
* **[!UICONTROL 元件類型]**：已新增、刪除或修改的元件類型。維度項目包含：
   * [!UICONTROL 維度]
   * [!UICONTROL 量度]
   * [!UICONTROL 區段]
   * [!UICONTROL 計算量度]
   * [!UICONTROL 日期範圍]
   * [!UICONTROL 註解]
   * [!UICONTROL 警報]
* **[!UICONTROL 資料釋圖 ID]**：資料釋圖的 ID。
* **[!UICONTROL 資料釋圖名稱]**：資料釋圖的易記名稱。
* **[!UICONTROL 登入使用者]**：採取動作的使用者。
* **[!UICONTROL 使用的面板]**：已新增、移除或修改的面板。維度項目包含：
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
* **[!UICONTROL 專案 ID]**：專案的 ID。
* **[!UICONTROL 專案名稱]**：專案易記的名稱。
* **[!UICONTROL 專案類型]**：專案類型。維度項目包含：
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 使用的視覺效果]**：已新增、刪除或修改的視覺效果。維度項目包含：
   * [!UICONTROL 自由格式表格]
   * [!UICONTROL 同類群組表格]
   * [!UICONTROL 流失]
   * [!UICONTROL 流量]
   * [!UICONTROL 歷程畫布小報告]
   * [!UICONTROL 區域]
   * [!UICONTROL 堆疊區域圖]
   * [!UICONTROL 條狀圖]
   * [!UICONTROL 堆疊長條圖]
   * [!UICONTROL 項目符號]
   * [!UICONTROL 組合]
   * [!UICONTROL 環形圖]
   * [!UICONTROL 直方圖]
   * [!UICONTROL 橫條圖]
   * [!UICONTROL 堆疊橫條圖]
   * [!UICONTROL 關鍵量度摘要]
   * [!UICONTROL 折線圖]
   * [!UICONTROL 地圖]
   * [!UICONTROL 散佈圖]
   * [!UICONTROL 區段標題]
   * [!UICONTROL 摘要變更]
   * [!UICONTROL 摘要數字]
   * [!UICONTROL Text]
   * [!UICONTROL 樹狀圖]
   * [!UICONTROL 文氏圖表]

當僅開啟或檢視專案時，產品使用情況不會追蹤個別專案元件。但是，開啟專案的使用者動作會被追蹤。

## 可用的範本

系統提供一個 [Adobe 範本](/help/analysis-workspace/templates/use-templates.md)，此範本使用透過此功能自動產生的元件。

「**[!UICONTROL Adobe 範本]** > **[!UICONTROL 其他]** > **[!UICONTROL 產品使用概觀]**」

在資料視圖選擇器中，選取產品使用情況自動建立的資料視圖，然後選擇「**[!UICONTROL 產品使用情況概觀]**」範本。選取「**[!UICONTROL 預覽]**」即可查看範本使用的面板並了解最佳使用案例，或選擇「**[!UICONTROL 使用範本]**」在 Analysis Workspace 中開啟它。
