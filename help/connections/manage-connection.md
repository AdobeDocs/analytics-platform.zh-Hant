---
title: 管理連線
description: 說明如何管理與 Platform 資料集的連線。
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# 管理連線

建立一或多個連線後，您就可以在[!UICONTROL 「連線」]管理器中管理這些連線。您可以

* 刪除連線。
* 為連線重新命名。
* 從連線建立資料檢視。
* 開始和停止資料串流。

![連線管理器](assets/connections-manager.png)

1. 按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

2. 選取要編輯或管理的連線。

3. 完成下列其中一個動作：

   | 動作 | 說明 |
   |---|---|
   | [!UICONTROL 刪除] | 刪除連線不會刪除資料集，資料仍會保留於 [!DNL Adobe Experience Platform]。請參閱下列的「刪除連線」。 |
   | [!UICONTROL 重新命名] | 您可以使用更具體的名稱來為連線重新命名。 |
   | [!UICONTROL 建立資料檢視] | 此連結會帶您前往[資料檢視產生器](/help/data-views/create-dataview.md)。 |
   | [!UICONTROL 開始或停止資料串流] | 「串流」意指如果連線中的任何資料集新增大批資料，系統會將這些新資料匯入 [!UICONTROL Customer Journey Analytics] 製成報表。 |

## 刪除連線

| 如果我… | 就會發生下列情形 |
| --- | --- |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的連線？ | 錯誤訊息會指出：<ul><li>針對已刪除連線所建立的任何資料檢視都將停止運作。</li><li> 同樣地，如果有任何 Analysis Workspace 專案需仰賴所刪除連線中的資料檢視，也將停止運作。</li></ul> |
| 刪除 [!UICONTROL Adobe Experience Platform] 中的資料集？ | 如果刪除 AEP 中的資料集，該資料集的資料將不再傳輸至包含該資料集的任何連線。該資料集中的任何資料不會從關聯的 CJA 連線中自動刪除。 |
| 刪除 [!UICONTROL Customer Journey Analytics] 中的資料集？ | 目前您無法刪除連線中所儲存的資料集。您必須刪除整個連線，然後重新開始(不過您可以刪除 [!UICONTROL Adobe Experience Platform] 中的資料集)。 |
| (在 [!UICONTROL Adobe Experience Platform] 中) 從資料集刪除批次資料？ | 如果從 [!UICONTROL Adobe Experience Platform] 資料集中刪除批次資料，該批次資料會從包含該特定批次資料的所有 [!UICONTROL Customer Journey Analytics] 連線中移除。[!UICONTROL Customer Journey Analytics] 會收到批次資料已從 [!UICONTROL Adobe Experience Platform] 中刪除的通知。 |
| 將&#x200B;**匯入** [!UICONTROL Customer Journey Analytics] 的批次資料刪除？ | 如果資料集中只有一筆批次資料，該批次資料中的所有或部分資料都不會顯示於 [!UICONTROL Customer Journey Analytics]。系統會復原匯入作業。舉例來說，如果資料集含有 5 筆批次資料，其中 3 筆在資料集遭刪除前就已匯入完成，則該 3 筆批次資料的資料就會顯示於 [!UICONTROL Customer Journey Analytics]。 |
