---
title: 刪除關聯
description: 當您刪除 Customer Journey Analytics 或 Adobe Experience Platform 中的連線、資料集或批次時，會發生什麼事？
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '339'
ht-degree: 100%

---

# 刪除關聯

刪除 Customer Journey Analytics 或 Adobe Experience Platform 中的連線、資料集或批次之前，請考慮以下因素：

| 當您... | 就會發生下列情形... |
| --- | --- |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何 Workspace 專案與所刪除連線中的資料檢視相依，也將停止運作。</li></ul> |
| 刪除 [!UICONTROL Adobe Experience Platform] (AEP) 中的資料集 | 如果刪除 AEP 中的資料集，該資料集的資料將不再傳輸至包含該資料集的任何連線。系統不會從關聯的 CJA 連線中自動刪除該資料集中的任何資料。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(不過您可以刪除 [!UICONTROL Adobe Experience Platform] 中的資料集)。 |
| 從資料集中刪除批次 (在 [!UICONTROL Adobe Experience Platform] 中) | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 [!UICONTROL Customer Journey Analytics] 連線中移除。[!UICONTROL Customer Journey Analytics] 會收到批次資料已從 [!UICONTROL Adobe Experience Platform] 中刪除的通知。 |
| 當批次&#x200B;**正要擷取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中時將它刪除 | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的查閱資料集 | 雖然對其他來源連接器而言，刪除資料集是可行的，但是目前 [Analytics Classifications 資料連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=zh-Hant)不支援此作業。 如果您誤刪了資料集，請聯絡 Adobe 客戶服務。 |
