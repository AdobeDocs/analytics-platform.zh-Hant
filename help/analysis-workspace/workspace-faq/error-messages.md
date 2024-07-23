---
description: 了解 Adobe Analysis Workspace 及其相關元件中的錯誤訊息
title: Analysis Workspace 的常見錯誤訊息
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
source-git-commit: fe089afb2022d8c4b50346bb81d6ba4ad6404014
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 66%

---

# 常見錯誤訊息

使用 Analysis Workspace 時，您可能會遇到也會影響效能的錯誤。下方列出最常見的錯誤類型、發生原因，以及可採取的最佳化措施。

| 錯誤訊息 | 為何發生這項錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 資料視圖出現了異常繁重的報告。請稍後再試。] | 您的組織針對特定資料檢視嘗試同時執行過多請求。 造成此錯誤的因素包括 API 請求、已排程專案、已排程報表、已排程警報，以及同時提出報表請求的用戶數量。 | 在一天中更平均地分佈資料檢視的請求和排程。<p>管理員可以使用[報告活動管理員來識別及取消消耗報告容量的要求](/help/reporting-activity-manager/reporting-activity-overview.md)。</p> |
| [!UICONTROL 這份報告過於複雜。請檢閱建置 Analysis Workspace 報告的最佳實務。] | 您的報表請求規模過大，無法執行。造成此錯誤的因素包括請求的複雜性導致的逾時。 | 縮短日期範圍、簡化篩選條件，或移除表格中的部分欄或列，藉此簡化您的請求。 或者，考慮將表格分割為個別請求。 |
| [!UICONTROL 資料檢視目前超出了其報告容量。請簡化要求或稍後重試。] | 您的組織針對特定資料檢視嘗試同時執行過多請求。 造成此錯誤的因素包括API請求、已排程專案，以及同時提出報表請求的使用者。 | 在一天中更平均地分佈資料檢視的請求和排程。 |
| [!UICONTROL 發生系統錯誤。請在「**[!UICONTROL 說明 > 提交支援票證]**」中提出客戶服務請求，並附上錯誤代碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 錯誤 500：無法載入頁面] | 您的本機網路問題 (例如公司[防火牆設定](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=zh-hant)) 是造成此錯誤的因素。此外，Adobe 可能遇到需要解決的問題。 | 請在幾分鐘後再次嘗試登入。如果問題持續發生，請將 EIM 例項 ID 代碼提交給客戶服務。 |
| [!UICONTROL 您的請求失敗，因為有太多欄或預先設定的列。] | 表格有太多自由形式儲存格 (列數 * 欄數)。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |
