---
description: 了解從 Analysis Workspace 匯出資料可使用的方法。
keywords: Analysis Workspace
title: 如何匯出專案資料
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 100%

---

# 匯出概觀

您可以從 Analysis Workspace 匯出 Customer Journey Analytics 專案 (的一部分)。您可能基於多種原因想要匯出 Customer Journey Analytics 報告，例如在第三方工具中使用或與外部資料合併。

以下多個部分將說明支援的文件類型、可用&#x200B;來匯出的各種方法，以及每種方法的優點。

## 支援的檔案類型

您可以將 Customer Journey Analytics 報告匯出為 PDF、CSV 或 JSON 檔案。

* **PDF：** 為您與利害關係人共用視覺效果資料提供的一種簡單方法。PDF 檔案包含專案中顯示的所有 (可見) 表格和視覺效果。

* **CSV：** 允許您在試算表應用程式 (例如 Excel) 中查看原始資料。CSV 檔案包含純文字資料。

* **JSON：** 提供可共用資料的開放式標準文件格式。

## 匯出方法

您要從 Analysis Workspace 匯出資料可以使用多種方法。選擇匯出方法時，請考慮您要匯出哪些資料，以及哪些人需要存取這些資料。

| 匯出方法 | 如果您想要執行以下操作，請使用此方法： |
|---------|----------|
| [下載至您的工作站](/help/analysis-workspace/export/download-send.md) | <li>下載專案至您的個人工作站。</li><li>僅下載臨時資料 (未排程)。</li> <li>最多下載 50,000 列。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [傳送給其他使用者](/help/analysis-workspace/export/t-schedule-report.md) | <li>透過電子郵件將匯出的 Customer Journey Analytics 資料傳送給組織中的其他使用者。</li><li>臨時或按排程傳送電子郵件。</li> <li>此電子郵件中最多包含 50,000 列。</li> <!--true?--> |
| [匯出至雲端位置](/help/analysis-workspace/export/export-cloud.md) | <li>匯出至雲端位置，例如 <ul><li>Adobe Experience Platform 資料登錄區</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>臨時或按排程匯出資料。</li><li>儲存更大量 Customer Journey Analytics 資料。</li><li>匯出包含數千或數百萬列的完整表格。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
