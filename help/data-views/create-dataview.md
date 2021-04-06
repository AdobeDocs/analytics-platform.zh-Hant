---
title: 建立資料檢視
description: 說明如何在 Customer Journey Analytics (CJA) 中為 Platform 資料集建立資料檢視。
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 97%

---

# 建立資料檢視

資料檢視類似於 Analytics 中的虛擬報表套裝，其概念為資料的「經篩選」檢視。您可以為相同的連線建立不同的資料檢視，並針對造訪逾時、歸因等項目使用不同設定。您可以為單一資料集建立多個資料檢視。例如，您可以有一個資料檢視的所有維度都設為「上次接觸」，同時有另一個資料檢視 (以同一個資料集為基礎) 的所有維度都設為「首次接觸」。

Customer Journey Analytics 中的 Analysis Workspace 專案是以資料檢視為基礎。

按一下[這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html)，觀看概述影片。

## 先決條件

建立資料檢視之前，您需要先[設定一或多個 Experience Platform 資料集的連線](/help/connections/create-connection.md)。

## 設定設定

1. 在 Customer Journey Analytics 中，前往&#x200B;**[!UICONTROL 「資料檢視」]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 「新增」]**，新增資料檢視並設定其設定。

   | 工作階段設定 | 定義 |
   |---|---|
   | 連線 | 此欄位會將資料檢視連結至您先前建立的連線，其中包含 [!UICONTROL Experience Platform] 資料集。 |
   | 名稱 | 必須為資料檢視命名。 |
   | 說明 | 詳細說明非必填，但建議使用。 |
   | 新增標記 | 標記可用來將資料檢視整理到不同類別中。 |
   | 時區 | 選擇資料檢視的時區。 |
   | 工作階段逾時 | 選取「工作階段」的定義。工作階段逾時設定用於定義自動開始新工作階段之前，獨特訪客必須達到的閒置時間。已預設為 30 分鐘。例如，若您將工作階段逾時設為 45 分鐘，系統便會針對收集到的各點擊順序建立新的工作階段分組，並按照 45 分鐘閒置時間加以區隔。<!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 開始事件的新工作階段 | 不論作業階段是否已逾期，事件觸發時就會開始新的工作階段。新建立的工作階段將會包含啟動的事件。此外，您可以使用多個事件來啟動工作階段，如果資料中觀察到其中一個事件，就會觸發新的工作階段。此設定將會影響您的造訪計數、「工作階段」 (先前稱為「造訪」) 區段容器以及維度的造訪過期邏輯。 |
   | 新增篩選器 | 「篩選器」是 Customer Journey Analytics 中代表「區段」的詞彙。如果您希望篩選資料，請從左側邊欄拖曳適當的篩選器。如果沒有選取篩選器，資料檢視將會包含您的所有資料。 |

1. 按一下&#x200B;**[!UICONTROL 「繼續」]**。

## 新增元件

1. 現在是時候將元件（維度、量度）新增至資料檢視了。 請注意，資料集中的每個欄位現在都會轉換為維度或量度。將維度和量度拖曳至面板，或按一下&#x200B;**[!UICONTROL 「全部選取」]**&#x200B;以新增所有元件。

   ![](assets/add-all-components.png)

1. 按一下&#x200B;**[!UICONTROL 「新增元件」]**&#x200B;標籤，將維度和量度新增至資料檢視。

   ![](assets/add-all-components2.png)

1. (可選) 您可以將元件重新命名為好記的名稱，或選取元件並編輯其設定來變更其歸因設定。請注意，基礎名稱會保留。如需詳細資訊，請參閱[設定資料檢視和歸因](/help/data-views/configure-dataviews.md)。

1. 接下來的步驟是[指定元件和歸因設定](/help/data-views/configure-dataviews.md)。

## 刪除資料檢視

如果您刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視，畫面會顯示錯誤訊息，指出任何仰賴這個已刪除資料檢視的 Analysis Workspace 專案都會停止運作。
