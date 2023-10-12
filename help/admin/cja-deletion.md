---
title: 刪除關聯
description: 當您刪除 Customer Journey Analytics 或 Adobe Experience Platform 中的連線、資料集或批次時，會發生什麼事？
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 34b19024769f94c01c8655d80445fac836ec20f9
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 75%

---

# 刪除關聯

刪除 Customer Journey Analytics 或 Adobe Experience Platform 中的連線、資料集或批次之前，請考慮以下因素：

| 當您... | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何「工作區」專案與所刪除連線中的資料檢視相依，也將停止運作。</li></ul>請注意，您無法刪除繫結至您沒有許可權的Adobe Experience Platform沙箱的Customer Journey Analytics連線。 即使您擁有這些連線所建置之資料檢視的許可權，必須先取得基礎Adobe Experience Platform沙箱的許可權，才能刪除連線。 |
| 刪除中的資料集 [!UICONTROL Adobe Experience Platform] | 如果刪除 AEP 中的資料集，該資料集的資料將不再傳輸至包含該資料集的任何連線。系統會從關聯的 Customer Journey Analytics 連線中自動刪除該資料集中的任何資料。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 當您從Customer Journey Analytics中的連線中刪除資料集時，任何依賴該資料集的資料檢視和專案都將不再運作。 |
| 從資料集中刪除批次 (在 [!UICONTROL Adobe Experience Platform] 中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 [!UICONTROL Customer Journey Analytics] 連線中移除。[!UICONTROL Customer Journey Analytics] 會收到批次資料已從 [!UICONTROL Adobe Experience Platform] 中刪除的通知。 |
| 當批次&#x200B;**正要擷取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中時將它刪除 | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除中的查閱資料集 [!UICONTROL Adobe Experience Platform] | 雖然對其他來源連接器而言，刪除資料集是可行的，但是目前 [Analytics 分類來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html)不支援此作業。 如果您誤刪了資料集，請聯絡 Adobe 客戶服務。 |
