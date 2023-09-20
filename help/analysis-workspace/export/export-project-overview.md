---
description: 瞭解可從Analysis Workspace匯出的各種方法。
keywords: Analysis Workspace
title: 匯出專案資料概觀
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# 匯出概觀

您可以從Analysis Workspace匯出Customer Journey Analytics資料。 您可能會基於多種原因想要匯出Customer Journey Analytics資料，例如儲存大量歷史資料或在協力廠商工具中分析原始資料。

以下各節說明支援的檔案型別、可用於匯出的各種方法以及每種方法的優點。

## 支援的檔案型別

您可以將Customer Journey Analytics資料匯出為PDF或CSV檔案。

* **PDF：** 提供與利害關係人共用視覺資料的簡單方法。 PDF檔案包含專案中所有顯示的（可見）表格和視覺效果。

* **CSV：** 可讓您檢視試算表應用程式（例如Excel）中的原始資料。 CSV檔案包含純文字資料。

## 匯出方法

從Analysis Workspace匯出時，有多種方法可供使用。 選擇匯出方法時，請考量您要匯出哪些專案，以及哪些人需要存取它。

| 匯出方法 | 優勢 |
|---------|----------|
| [下載至您的工作站](/help/analysis-workspace/export/download-send.md) | 如果您想要： <ul><li>將專案下載至您的個人工作站。</li><li>下載僅供臨機操作（無法排程）。</li> <li>總共下載50,000列。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [傳送給其他使用者](/help/analysis-workspace/export/t-schedule-report.md) | 如果您想要： <ul><li>透過電子郵件將匯出的Customer Journey Analytics資料傳送給組織中的其他使用者。</li><li>可以是臨時或依排程。</li> <li>總共包含50,000列。</li> <!--true?--> |
| [傳送至雲端應用程式](/help/analysis-workspace/export/export-cloud.md) | 如果您想要： <ul><li>匯出至共用位置，例如Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflake或Adobe Experience Platform。</li><li>可以是臨時或依排程。</li><li>儲存大量歷史Customer Journey Analytics資料。</br>這類資料可用於偵測長期趨勢，以獲得商業智慧，最終做出更好的商業決策。</li><li>匯出包含數千或數百萬列的完整表格。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

