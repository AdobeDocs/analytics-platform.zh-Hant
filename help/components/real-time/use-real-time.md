---
description: 瞭解如何在Analysis Workspace中使用即時報告。
title: 使用即時報表
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
TQID: https://experienceleague.adobe.com/tQgkfejYepjtgY4eN6cmT4K49I8VUb6les1abWXGGa0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 12%

---

# 使用即時報告 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="即時重新整理"
>abstract="啟用即可即時更新此面板的資料及視覺效果。"

若要使用即時報告，請在Workspace專案中啟用下列任何面板的&#x200B;**[!UICONTROL 即時重新整理]**&#x200B;切換功能：

* [空白面板](/help/analysis-workspace/c-panels/blank-panel.md)
* [自由格式](/help/analysis-workspace/c-panels/freeform-panel.md)
* [歸因](/help/analysis-workspace/c-panels/attribution.md)
* [下一個或上一個項目](/help/analysis-workspace/c-panels/next-previous.md)

您會看到包含資料最近一次重新整理時間戳記的訊息。 例如： [!UICONTROL  *上次重新整理時間： 07:55 pm*]。

從下拉式選單中選取您要報告的即時時段。 可選擇下列選項：

* [!UICONTROL 最近15分鐘]
* [!UICONTROL 最近30分鐘]
* [!UICONTROL 最後一小時]
* [!UICONTROL 最近8小時]
* [!UICONTROL 最近24小時]

現在面板中的所有視覺效果會每分鐘更新一次，最多更新30分鐘，同時啟用即時重新整理面板的瀏覽器標籤會啟用。

例如，檢視下方&#x200B;**[!UICONTROL 即時報表面板]**&#x200B;的快照，該快照會隨著時間從&#x200B;**[!UICONTROL *06:26pm*]**&#x200B;移至&#x200B;**[!UICONTROL *06:27下午&#x200B;*]**，重新整理**[!UICONTROL &#x200B;總收入/小時&#x200B;]**長條圖視覺效果和**[!UICONTROL &#x200B;總收入/小時&#x200B;]**自由格式表格。

![即時重新整理](assets/real-time-refresh.gif)

30分鐘後，或當瀏覽器標籤停用時，**[!UICONTROL 即時重新整理]**&#x200B;切換會自動停用，且即時更新會停止。

停用「即時重新整理」切換後，面板（及其中的所有視覺效果）就會傳回[使用Customer Journey Analytics](real-time.md#how-it-works)的標準報表資料和功能。
