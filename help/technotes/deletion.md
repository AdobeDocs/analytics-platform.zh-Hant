---
title: 刪除關聯
description: 瞭解刪除或重設Customer Journey Analytics或Experience Platform物件的含意。
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: 6c53e0cd13bd08a874a160851f925e7acc99bcd2
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 9%

---

# 刪除和重設的關聯

刪除或重設Customer Journey Analytics或Experience Platform物件確實有影響。 本文會概述這些含意。

## Customer Journey Analytics

刪除Customer Journey Analytics中的連線、資料檢視或資料集之前，請先考慮下列含意：

| 動作 | 影響 |
| --- | --- |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線 | 錯誤訊息指出：<ul><li>為已刪除的連線所建立的任何資料檢視都不再有效。</li><li> 同樣地，如果有任何Workspace專案與所刪除連線中的資料檢視相依，也將停止運作。</li></ul><p>請注意，您無法刪除符合以下條件的Customer Journey Analytics連線：</p><ul><li>繫結至您沒有許可權的Adobe Experience Platform沙箱。 即使您擁有這些連線所建置之資料檢視的許可權，必須先取得基礎Adobe Experience Platform沙箱的許可權，才能刪除連線。</li><li>為與連線關聯的資料檢視選取下列相容性選項： **[!UICONTROL 在Adobe Journey Optimizer中設定為預設資料檢視]**<p>如需此組態選項的詳細資訊，請參閱[建立或編輯資料檢視](/help/data-views/create-dataview.md#compatibility)中的[相容性](/help/data-views/create-dataview.md)。</p></li><li>用於下列任何服務的設定：<ul><li>[對象分析](/help/connections/audience-analysis/audience-analysis-overview.md)：將對象資料提供給Customer Journey Analytics以進行深入分析</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md)：提供有關內容使用量及對Customer Journey Analytics影響的資料</li></ul><p>您必須先刪除或編輯使用此連線的設定，才能刪除連線。</p></li></ul> |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集 | 當您從Customer Journey Analytics中的連線中刪除資料集時，任何依賴該資料集的資料檢視和專案都不再運作。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視 | 當您刪除Customer Journey Analytics中的資料檢視時，Workspace專案中依賴資料檢視的任何面板都不再正常運作。<p>請注意，您無法刪除在下列任何服務的設定中使用的Customer Journey Analytics資料檢視：</p><ul><li>[對象分析](/help/connections/audience-analysis/audience-analysis-overview.md)：將對象資料提供給Customer Journey Analytics以進行深入分析</li><li>[Adobe Content Analytics](/help/content-analytics/content-analytics.md)：提供有關內容使用量及對Customer Journey Analytics影響的資料</li></ul><p>您必須先刪除或編輯使用此資料檢視的設定，才能刪除資料檢視。</p></li></ul> |



## Experience Platform

在刪除資料集或批次之前，或在Experience Platform中重設或刪除沙箱時，請考慮以下問題：

| 動作 | 影響 |
| --- | --- |
| 刪除[!UICONTROL Experience Platform]中的資料集 | 在Experience Platform中，來自該資料集的資料流會停止到包含該資料集的任何連線。 系統會從相關聯的 Customer Journey Analytics 連線自動刪除該資料集中的任何資料。 |
| 從[!UICONTROL Experience Platform]的資料集中刪除批次 | 如果從[!UICONTROL Adobe Experience Platform]資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有[!UICONTROL Customer Journey Analytics]連線中移除。 [!UICONTROL Customer Journey Analytics] 會收到批次資料已從 [!UICONTROL Adobe Experience Platform] 中刪除的通知。 |
| 將批次擷取[!UICONTROL 到]Customer Journey Analytics **時，從** Experience Platform刪除批次 | 如果資料集中只有一個批次，則該批次中的所有或部分資料都不會顯示在 [!UICONTROL Customer Journey Analytics] 中。擷取會收回。舉例來說，如果資料集中有5筆批次資料，其中3筆在第四筆批次資料遭刪除時就已匯入完成，則該3筆批次資料的資料就會顯示於[!UICONTROL Customer Journey Analytics]。 |
| 刪除[!UICONTROL Experience Platform]中的查閱資料集 | 雖然對其他來源聯結器而言，刪除資料集是可行的，但是不支援刪除[Analytics Classifications Source Connector](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications)資料集。 如果您誤刪了這類資料集，請聯絡客戶服務。 |
| 刪除或重設Experience Platform中的沙箱 | 當您[刪除Experience Platform沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/ui/user-guide#delete-a-sandbox)時，也會刪除該沙箱中的所有結構描述、資料集、批次、原則等。 沙箱已不存在，以及沙箱識別碼和沙箱名稱。<br/>當您[重設Experience Platform沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/ui/user-guide#reset-a-sandbox)時，將會刪除該沙箱中的所有結構描述、資料集、批次、原則等。 雖然沙箱名稱和許可權保持不變，但在重設完成後沙箱識別碼會變更。<br/><br/>Customer Journey Analytics使用沙箱識別碼和沙箱名稱來關聯與沙箱的連線。 因此： <ul><li>與已刪除或重設沙箱關聯的連線已刪除。</li><li>以已刪除的連線為基礎的資料檢視（以及資料檢視內的所有元件定義，例如衍生欄位）都會被刪除。</li><li>依賴已刪除資料檢視的元件會遭刪除。 例如區段、計算量度、註解、警報、已發佈對象和匯出。</li><li>Workspace專案中參照已刪除資料檢視的面板變得無法使用。 這些面板顯示&#x200B;**[!UICONTROL 未知的資料檢視]**&#x200B;錯誤。 移除這些面板，或可能的話，將這些面板與現有資料檢視建立關聯。</li><li>您不應再使用查詢服務或依賴BI擴充功能的工具，從Customer Journey Analytics中已可用的已刪除連線中查詢（歷史）資料。 最終Adobe支援或工程人員會從Customer Journey Analytics中刪除此資料。</li></ul>由於Experience Platform中重設或刪除沙箱會有很重大的影響，在重設或刪除沙箱前，請先考慮下列事項：<ul><li>列出您的連線，以瞭解哪些連線屬於哪些沙箱。</li><li>列出資料檢視，以瞭解哪些資料檢視與哪些連線相關聯。</li><li>識別重要的Workspace專案，並瞭解這些專案在其面板中參照的資料檢視。</li><li>識別與使用BI擴充功能之工具的整合，並瞭解這些整合所依賴的資料檢視。</li></ul> |
