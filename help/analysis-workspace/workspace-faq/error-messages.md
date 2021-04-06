---
description: Adobe Analysis Workspace 及其相關元件的錯誤訊息清單
title: Analysis Workspace 的常見錯誤訊息
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 82%

---

# 常見錯誤訊息

使用 Analysis Workspace 時，您可能會遇到也會影響效能的錯誤。下方列出最常見的錯誤類型、發生原因，以及可採取的最佳化措施。

| 錯誤訊息 | 為何發生這項錯誤？ | 最佳化 |
| --- | --- | --- |
| [!UICONTROL 發生系統錯誤。請在&#x200B;**[!UICONTROL 「說明 > 提交支援票證」]**&#x200B;中提出客戶服務請求，並附上錯誤代碼。] | Adobe 遇到需要解決的問題。 | 將錯誤代碼提交給客戶服務。 |
| [!UICONTROL 錯誤 500：無法載入頁面] | 您的本機網路問題 (例如公司[防火牆設定](https://docs.adobe.com/content/help/zh-Hant/analytics/technotes/ip-addresses.html)) 是造成此錯誤的因素。此外，Adobe 可能遇到需要解決的問題。 | 請在幾分鐘後再次嘗試登入。如果問題持續發生，請將 EIM 例項 ID 代碼提交給客戶服務。 |
| [!UICONTROL 此視覺化中的其中一個篩選或搜尋包含傳回太多結果的文字搜尋。] | 您的篩選條件或報表篩選條件太廣泛。 | 請縮小搜尋文字條件，然後再次嘗試傳送請求。 |
| [!UICONTROL 請求太複雜。] | 您的報表請求規模過大，無法執行。此錯誤的成因是請求大小導致逾時、篩選或搜尋篩選器中匹配項目太多、包含量度太多、維度和量度組合不相容等。 | 移除表格中的部分欄或列，或考慮將表格分割為個別請求，藉此簡化您的請求。 |
| [!UICONTROL 此維度目前不支援非預設的歸因模型。] | 您使用的維度不支援非預設歸因。 | 使用與[「歸因 IQ」](/help/analysis-workspace/attribution/overview.md)相容的維度來取代表格中的維度。 |
| [!UICONTROL 您的請求失敗，因為有太多欄或預先設定的列。] | 表格有太多自由格式儲存格 (列數 * 欄數)。 | 移除表格中的欄或列，或考慮將表格分割為個別請求。 |
