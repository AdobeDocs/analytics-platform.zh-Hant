---
title: 資料檢視概觀
description: 資料檢視指定您想要如何解釋 Customer Journey Analytics 連線中的資料元素，例如量度、維度、工作階段等。
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 100%

---

# 資料檢視概觀

資料檢視是特定於 Customer Journey Analytics 的容器，可讓您決定如何解釋來自[連線](/help/connections/create-connection.md)的資料。它指定 Analysis Workspace 中可用的所有維度和量度，以及這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

>[!NOTE]
>
>您在資料檢視中選取或變更的任何設定都是可回溯且不具破壞性的。換言之，這些並不會永久變更您的基礎資料。 

您可以針對相同的連線建立不同的資料檢視，並使用非常不同的元件集 (維度/量度)。或者，使用造訪逾時、歸因等的不同設定來建立資料檢視。例如，您可以有一個資料檢視，其中所有維度皆設為「[!UICONTROL 上次接觸]」，同時，另一個資料檢視 (以相同資料集為基礎) 則設為「[!UICONTROL 首次接觸]」。

Customer Journey Analytics 中的 Analysis Workspace 專案是以資料檢視為基礎。

>[!IMPORTANT]
>
>單一資料檢視中最多可新增 5,000 個量度和 5,000 個維度。

## 資料檢視功能 {#capabilities}

資料檢視可讓您自發地變更「資料檢視」中的「綱要」元素設定，而不需變更 Adobe Experience Platform 的綱要或重新實作 Customer Journey Analytics 環境。

* **您可以將元件從「量度」變更為「維度」，反之亦然**。您可以從字串欄位建立量度，或從數值欄位建立維度。這可讓您的生活更輕鬆，因為您不需要在 XDM 結構中為每個所需的量度建立數值欄位。您只需在資料檢視對話方塊中自發建立它。以下是一些範例：
   * **從單一結構欄位建立一或多個和/或一個維度**。這是一對多的關係。例如，您可以從單一結構欄位建立一或多個「收入」量度及/或一或多個「收入」維度。
   * **使用字串欄位做為量度**：當您在 Experience Platform 中填入資料集的結構時，您可能不知道您需要什麼結構元素。例如，您可能沒有意識到您需要「頁面上的錯誤」量度。因此，您並未就此建立數值結構元素。現在，只要使用字串元素做為量度，您就可以使用資料檢視設定來指定只要字串包含「error」這個字，就可以將它當做量度。
   * **使用數值欄位做為維度**：例如，如果您想從「收入」維度提取「收入」量度，「收入」維度會將每個值顯示為維度項目 ($100、$175、$1,000等) 以及每個維度項目的例項數。收入做為量度的行為會與以往一樣。

* **您可以使用不同的歸因模型或不同的回顧視窗，**&#x200B;從相同的結構欄位建立多個量度。

* **您可以編輯元件的 ID**，此 ID 用於跨資料檢視的相容性。報告 API 使用元件 ID 來識別特定量度或維度。由於您可以任意從一個 XDM 欄位建立許多量度或維度，因此我們將提供您定義您自己的元件 ID 的選項。因此，您在一個 Workspace 專案中使用的量度可以跨資料檢視 (和 API) 相容，即使這些量度是根據不同連線、資料檢視或 XDM 中不同結構的完全不同欄位。

* **您可以指定將在 Analysis Workspace 中顯示的友好元件名稱**。根據預設，此名稱繼承自結構顯示名稱，但您現在可以覆蓋該特定資料檢視的名稱。

* **您可以檢視有關元件的更多結構相關資訊**，例如：它來自的資料集類型 (事件、設定檔、查詢)、結構類型 (字串、整數等)，以及結構路徑 (它基於的 XDM 欄位)。

* **您可以標記元件**，更輕鬆地在 Workspace 中搜尋它。

* **您可以在報告中隱藏元件**。有些量度和維度設定需要第二個量度或維度才能進行設定 (例如，量度重複化或購買重複化)。這可讓您定義可用於其他量度或維度設定的量度或維度，而不會直接在報告中公開 (例如購買 ID)。

* **您可以套用格式至量度**，例如顯示小數、時間、百分比或貨幣；指定小數位；呈綠色或紅色上升趨勢；以及指定貨幣選項。

* 您&#x200B;**只能根據結構欄位&#x200B;中的某些值來建立量度或維度**。例如，如果您想要「errors」量度，則可從頁面名稱欄位建立量度，但僅包括任何包含單字「error」的頁面。依此建立的「error」量度可進行篩選、可插入至計算量度，並可與歸因、流量、流失等搭配使用。

* 對於維度，您可以&#x200B;**在特定欄位&#x200B;中自動包含或排除特定值**。例如，如果開發人員將 `dev mistake` 錯誤值傳送至欄位，您可以使用排除規則在報告中輕鬆排除它，且其行為就像它從未在資料中存在過一樣。

* 您可以在資料檢視中&#x200B;**重新命名容器**，並使這些容器在任何以此資料檢視為基礎的 Workspace 專案中顯示。

## 資料檢視先決條件 {#prerequisites}

* 建立資料檢視之前，您需要先[設定一或多個 Experience Platform 資料集連線](/help/connections/create-connection.md)。
* 若要建立或管理資料檢視，您需要在 [Adobe Admin Console 中設定一組權限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#admin-access-permissions)。
* 如果您有使用 [Adobe Analytics 來源連接器](/help/data-ingestion/analytics.md)或確實具備 Adobe Analytics 背景知識，您可能會想了解綱要和資料集中的欄位 (連線的一部分) 如何與其 Adobe Analytics 對應項相關聯。如需更多資訊，請參閱 [Analytics 欄位對應](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html)。

## 您可以在 Workspace 中覆寫資料檢視設定 {#settings-override}

有些資料檢視設定可在 Analysis Workspace 的專案層級覆寫，有些則無法覆寫。

* [!UICONTROL 回顧視窗]
* 量度歸因
* 使用者是否在報表中看到[!UICONTROL 無值]條列項目

## 您無法在 Workspace 中覆寫資料檢視設定 {#settings-no-override}

* [!UICONTROL 元件類型]
* 量度格式 
* 資料檢視名稱
* 維度分配

## 刪除資料檢視 {#delete}

如果刪除 [!UICONTROL Customer Journey Analytics] 中的資料檢視，則會出現錯誤訊息，指出任何與這個被刪除的資料檢視相依的 [!UICONTROL Workspace] 專案都將不再運作。

## 後續步驟

* [建立資料檢視](/help/data-views/create-dataview.md)
* [資料檢視使用案例](/help/use-cases/data-views/data-views-usecases.md)
