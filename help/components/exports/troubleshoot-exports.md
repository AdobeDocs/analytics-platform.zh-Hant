---
description: 管理現有匯出的記錄
keywords: Analysis Workspace
title: 疑難排解失敗的匯出
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# 疑難排解失敗的匯出

當您從Analysis Workspace [匯出完整資料表至雲端目的地](/help/analysis-workspace/export/export-cloud.md)時，您可以從[匯出標籤](/help/components/exports/manage-exports.md)和[記錄檔標籤](/help/components/exports/manage-export-logs.md)檢視這些匯出的狀態。 失敗的匯出顯示&#x200B;[!UICONTROL **失敗**]&#x200B;的狀態。

## 常見失敗與動作

匯出可能會因為各種原因而失敗。 下表說明一些最常見的原因，以及您可以採取哪些動作來解決失敗：

| 失敗原因 | 建議的動作 | 詳細資訊 |
|---------|----------|---------|
| 位置或帳戶資訊無效 | 請確定您的憑證和其他資訊對於您要匯出的雲端帳戶和位置而言是正確的。 | [設定雲端匯出帳戶](/help/components/exports/cloud-export-accounts.md)和[設定雲端匯出位置](/help/components/exports/cloud-export-locations.md)。 |
| 報表中的維度或量度已從資料檢視中移除 | 請聯絡您的系統管理員，檢視已從資料檢視中移除哪些元件。 您可能需要在匯出中使用不同的資料檢視，或從表格中移除不再可用的元件。 | [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md) |
| 超出列數限制 | 根據您的授權型別，您最多可以匯出300萬、3000萬、1.5億或3億列。 更新您正在匯出的表格以減少總列數。 | [將Customer Journey Analytics報表匯出至雲端](/help/analysis-workspace/export/export-cloud.md) |
| 排程的匯出到期日 | 您設定的排程匯出已過期。 更新匯出的到期日。 | [管理匯出](/help/components/exports/manage-exports.md) |
| 不支援Dimension | <p>「完整表格匯出」不支援符合下列所有條件的任何維度：</p> <ul><li>是從屬於物件陣列一部分的欄位建立的</li><li>已啟用持續性<li>未使用繫結維度</li> | <ul><li>[使用物件陣列](/help/use-cases/object-arrays.md)</li><li>[持續性元件設定](/help/data-views/component-settings/persistence.md)<li>[在Customer Journey Analytics中使用繫結維度和量度](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| 貴組織強制執行的資料治理原則會限制表格中的元件不可匯出 | 請連絡您的系統管理員，檢視哪些元件限制匯出。 匯出前先移除受限制的元件。 | *篩選*&#x200B;標籤和原則[中資料檢視表](/help/data-views/data-governance.md)區段的資料治理原則 |

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
