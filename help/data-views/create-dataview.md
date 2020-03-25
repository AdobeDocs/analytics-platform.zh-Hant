---
title: 建立資料檢視
description: 說明如何在客戶歷程分析(CJA)中建立平台資料集的資料檢視。
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# 建立資料檢視

資料檢視類似於Analytics中的虛擬報表套裝，因為它是資料的「篩選」檢視。 您可以針對相同的連線建立不同的資料檢視，並針對瀏覽逾時、歸因等設定不同。 您可以為單一資料集建立多個資料檢視。 例如，您可以有一個資料檢視，其中所有維度都設為「上次接觸」，而同時有另一個資料檢視（以相同資料集為基礎），所有維度都設為「首次接觸」。

「客戶歷程分析」中的工作區專案是以資料檢視為基礎。

按一 [下這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) ，即可檢視影片總覽。

## 先決條件

在建立資料檢視之前，您需 [要設定一或多個Adobe Experience Platform資料集的連線](/help/connections/create-connection.md)。

## 設定設定

1. 在「客戶歷程分析」中，前往標 **[!UICONTROL Data Views]** 簽。

1. 按一 **[!UICONTROL Add]** 下以新增資料檢視並設定其設定。

   | 會話設定 | 定義 |
   |---|---|
   | 連線 | 此欄位會將資料檢視連結至您先前建立的連線，其中包含平台資料集。 |
   | 名稱 | 必須為資料檢視指定名稱。 |
   | 說明 | 詳細說明並非必要，但建議使用。 |
   | 新增標籤 | 標籤可讓您將資料檢視組織成類別。 |
   | 時區 | 選擇資料檢視的時區。 |
   | 工作階段逾時 | 選擇「會話」的定義。 作業逾時設定會定義獨特訪客在自動啟動新作業前必須閒置的量。 預設為30分鐘。 例如，如果您將作業逾時設為45分鐘，則會針對收集的每個點擊序列建立新的作業群組，並以45分鐘的閒置分隔。 <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | 開始新的活動階段作業 | 無論作業是否逾時，新作業會在引發事件時啟動。 新建立的會話包含啟動該會話的事件。 此外，您可以使用多個事件來啟動作業，而如果資料中觀察到任何這些事件，則會觸發新作業。 此設定會影響您的瀏覽計數、作業階段（先前稱為瀏覽）區段容器，以及維度上的瀏覽過期邏輯。 |
   | 新增篩選 | 「篩選」是「客戶歷程分析」中「區段」的詞語。 如果您想要篩選資料，請從左側導軌拖曳適當的篩選。 如果您未選取篩選，資料檢視將包含您的所有資料。 |

1. 按一下 **[!UICONTROL Continue]**.

## 新增元件

1. 現在是時候將元件（維度、量度）新增至資料檢視（類似於虛擬報表套裝中的組織體驗）了。請注意，資料集中的每個欄位現在都會轉換為維度或量度。 將維度和量度拖曳至面板或 **[!UICONTROL選擇全部** ，以新增所有元件。

   ![](assets/add-all-components.png)

1. 按一下 **[!UICONTROL Add Components]** 標籤，將維度和量度新增至資料檢視。

   ![](assets/add-all-components2.png)

1. （可選）您可以將元件重新命名為好記名稱，或透過選取元件並編輯其設定來變更其歸因設定。 請注意，基礎名稱會保留。 如需詳細資訊，請參 [閱設定資料檢視和歸因](/help/data-views/configure-dataviews.md)。

1. 接下來的步驟是指 [定元件和歸因設定](/help/data-views/configure-dataviews.md)。