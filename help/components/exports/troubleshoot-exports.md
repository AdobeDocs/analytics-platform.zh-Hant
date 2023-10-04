---
description: 管理現有匯出的記錄
keywords: Analysis Workspace
title: 疑難排解失敗的匯出
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---

# 疑難排解失敗的匯出

{{release-limited-testing}}

當您 [將完整表格從Analysis Workspace匯出至雲端目的地](/help/analysis-workspace/export/export-cloud.md)，您可從以下位置檢視這些匯出的狀態： [匯出索引標籤](/help/components/exports/manage-exports.md) 和從 [記錄檔索引標籤](/help/components/exports/manage-export-logs.md). 失敗的匯出會顯示狀態 [!UICONTROL **已失敗**].

## 常見失敗與動作

匯出可能會因為各種原因而失敗。 下表說明一些最常見的原因，以及您可以採取哪些動作來解決失敗：

| 失敗原因 | 建議的動作 | 詳細資訊 |
|---------|----------|---------|
| 無效的位置或帳戶資訊 | 請確定您的憑證和其他資訊對於您要匯出的雲端帳戶和位置而言是正確的。 | [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md) 和 [設定雲端匯出位置](/help/components/exports/cloud-export-locations.md). |
| 報表中的維度或量度已從資料檢視中移除 | 請聯絡您的系統管理員，檢視已從資料檢視中移除哪些元件。 您可能需要在匯出中使用不同的資料檢視，或從表格中移除不再可用的元件。 | [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md) |
| 貴組織強制執行的資料治理原則會限制表格中的元件不可匯出 | 請連絡您的系統管理員，檢視哪些元件限制匯出。 匯出前先移除受限制的元件。 | *篩選資料檢視中的資料控管原則* 中的區段 [標籤和原則](/help/data-views/data-governance.md) |

## 連絡 Adobe 客戶服務

如果您持續遇到問題，請聯絡Adobe客戶服務。 就匯出失敗連絡客戶服務時，請確定您有以下可用的資訊：

* 匯出名稱

* 匯出 ID

* 實例 ID

* 資料檢視名稱

* 位置

* 帳戶

* 連線

* 公司名稱
