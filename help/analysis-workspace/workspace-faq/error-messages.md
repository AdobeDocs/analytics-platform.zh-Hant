---
description: 瞭解錯誤訊息，以及如何在AdobeAnalysis Workspace中疑難排解
title: Analysis Workspace中的常見錯誤及疑難排解
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: ec32b7bca6fd4fc4b2652d1265048ec788f19718
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 74%

---

# 錯誤與疑難排解

在與Analysis Workspace互動時，您可能會遇到會影響其功能或效能的錯誤。 下方列出最常見的錯誤類型、發生原因，以及可採取的最佳化措施。

## 錯誤訊息

您在使用Analysis Workspace時可能會看到的一些常見錯誤訊息：

| 錯誤訊息 | 為何發生錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 資料視圖出現了異常繁重的報告。請稍後再試。] | 您的組織針對特定資料視圖同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案、已排程報告、已排程警報，以及同時提出報告請求的用戶數量。 | 在一天中更平均地分佈資料視圖的請求和排程。<p>管理員可以使用[報告活動管理程式來識別和取消](/help/reporting-activity-manager/reporting-activity-overview.md)正在消耗報告產能的請求。</p> |
| [!UICONTROL 這份報告過於複雜。請檢閱建置 Analysis Workspace 報告的最佳實務。] | 您的報告請求規模過大，無法執行。造成此錯誤的原因是由於請求的複雜性而導致的逾時。 | 簡化您的要求。 例如，縮短日期範圍、簡化篩選條件，或移除表格中的部分欄或列。 您也可以考慮將表格分割為個別請求。 |
| [!UICONTROL 資料檢視目前超出了其報告容量。請簡化要求或稍後重試。] | 您的組織針對特定資料視圖同時執行過多請求。造成此錯誤的因素包括 API 請求、已排程專案，以及同時提出報告請求的用戶數量。 | 在一天中更平均地分佈資料視圖的請求和排程。 |
| [!UICONTROL 發生系統錯誤。請在「**[!UICONTROL 說明 > 提交支援票證]**」中提出客戶服務請求，並附上錯誤代碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 錯誤 500：無法載入頁面] | 您的本機網路問題 (例如公司[防火牆設定](https://experienceleague.adobe.com/en/docs/analytics/technotes/ip-addresses)) 是造成此錯誤的因素。此外，Adobe 可能遇到需要解決的問題。 | 請在幾分鐘後再次嘗試登入。如果問題持續發生，請將 EIM 例項 ID 代碼提交給客戶服務。 |
| [!UICONTROL 您的請求失敗，因為有太多欄或預先設定的列。] | 表格有太多自由形式儲存格 (列數 * 欄數)。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |


## 疑難排解

使用Analysis Workspace時，您可以使用下列資訊來疑難排解一些常見問題。

| 問題 | 疑難排解 |
|---|---|
| 我將量度拖曳到專案後，顯示&#x200B;*資料無效*。 | 資料無效代表 Adobe 無法運用報表中使用的維度和量度組合傳回資料。舉例來說，將兩個量度彼此堆疊在一起就無法傳回資料，因為系統無法以這種方式顯示兩個量度。因此，請改為並排放置量度。 |
| 我將量度拖曳到專案後，系統並未顯示任何實際資料，只顯示零。 | 如果您成功建立了 Workspace 報表，但當中沒有任何資料，建議您檢查以下幾個事項：<ul><li>如果您在報表中套用了篩選器，則可能是篩選器標準與任何資料皆不符。 請嘗試移除篩選器或調整篩選器定義。</li><li>檢查右上角的日期範圍，確認已設為您預期的值。</li><li>導覽至您的網站，使用[除錯工具](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)驗證資料正在收集中。</li></ul> |
