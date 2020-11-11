---
title: 管理連線
description: 說明如何管理與 Platform 資料集的連線。
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 23%

---


# 管理連線

建立一個或多個連接後，可以在[!UICONTROL 連接]管理器中管理這些連接。 您可以

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
   | [!UICONTROL 刪除] | 刪除連線並不會刪除資料集，因為資料仍在 [!DNL Adobe Experience Platform] 中。請參閱下面的「刪除連接」。 |
   | [!UICONTROL 重新命名] | 您可以使用更具說明性的名稱來為連線重新命名。 |
   | [!UICONTROL 建立資料檢視] | 此連結會帶您前往[資料檢視產生器](/help/data-views/create-dataview.md)。 |
   | [!UICONTROL 啟動或停止資料串流] | 「串流」意指如果有任何新批次新增至連線中的任何資料集，此新資料將會匯入[!UICONTROL 客戶歷程分析]以進行報告。 |

## 刪除連接

| 如果我…… | 這可能發生在下列情形 |
| --- | --- |
| 刪除[!UICONTROL 客戶歷程分析]中的連線？ | 錯誤訊息會指出：<ul><li>為已刪除的連接建立的任何資料視圖將不再工作。</li><li> 同樣地，任何依賴已刪除連線中資料檢視的工作區專案都將停止運作。</li></ul> |
| 刪除[!UICONTROL Adobe Experience Platform]中的資料集？ | 在AEP中刪除資料集會停止資料從該資料集流向包含該資料集的任何連線。 該資料集中的任何資料不會自動從關聯的CJA連線中刪除。 |
| 刪除[!UICONTROL 客戶歷程分析]中的資料集？ | 目前，您無法刪除已儲存連線中的資料集。 您必須刪除整個連接，然後重頭開始。 （但是，您可以刪除[!UICONTROL Adobe Experience Platform]中的資料集。） |
| 從資料集刪除批次（在[!UICONTROL Adobe Experience Platform]中）? | 如果從[!UICONTROL Adobe Experience Platform]資料集刪除批次，則會從包含該特定批次的任何[!UICONTROL 客戶歷程分析]連線移除相同批次。 [!UICONTROL 客戶歷程] 分析會通知在 [!UICONTROL Adobe Experience Platform中刪除的批次]。 |
| 在將批&#x200B;**收錄到[!UICONTROL 客戶歷程分析]時刪除批&lt;a0/>?** | 如果資料集中只有一個批次，則該批次的資料或部分資料不會出現在[!UICONTROL 客戶歷程分析]中。 將回退攝取。 例如，如果資料集中有5個批次，且刪除資料集時已收錄了其中3個批次，則這3個批次的資料會出現在[!UICONTROL 客戶歷程分析]中。 |
