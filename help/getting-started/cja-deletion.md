---
title: 刪除意涵
description: 刪除Customer Journey Analytics或Adobe Experience Platform中的連線、資料集或批次時，會發生什麼事。
source-git-commit: 3fa2c562abaf4aa1f18baa5de5ee66c7ad828f52
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 60%

---

# 刪除意涵

刪除連線、資料集或Customer Journey Analytics或Adobe Experience Platform中的批次資料之前，請先考量一下這點：

| 當您... | 就會發生下列情形... |
| --- | --- |
| 刪除[!UICONTROL Customer Journey Analytics]中的連接 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何 Analysis Workspace 專案需仰賴所刪除連線中的資料檢視，也將停止運作。</li></ul> |
| 刪除[!UICONTROL Adobe Experience Platform](AEP)中的資料集 | 如果刪除 AEP 中的資料集，該資料集的資料將不再傳輸至包含該資料集的任何連線。該資料集中的任何資料不會從關聯的 CJA 連線中自動刪除。 |
| 刪除[!UICONTROL Customer Journey Analytics]中的資料集 | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(不過您可以刪除 [!UICONTROL Adobe Experience Platform] 中的資料集)。 |
| 從資料集刪除批次資料(在[!UICONTROL Adobe Experience Platform]中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 [!UICONTROL Customer Journey Analytics] 連線中移除。[!UICONTROL Customer Journey Analytics] 會收到批次資料已從 [!UICONTROL Adobe Experience Platform] 中刪除的通知。 |
| 將批&#x200B;**導入[!UICONTROL Customer Journey Analytics]時刪除該批** | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除[!UICONTROL Adobe Experience Platform]中的查閱資料集 | 雖然其他來源連接器可以刪除資料集，但[Analytics分類資料連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=en)目前不支援。 如果您誤刪了資料集，請聯絡Adobe客戶服務。 |