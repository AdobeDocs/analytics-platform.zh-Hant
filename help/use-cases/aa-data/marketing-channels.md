---
title: 在 Adobe Experience Platform 中使用行銷管道維度
description: 使用 Analytics 來源連接器將行銷頻道處理規則匯入 Adobe Experience Platform。
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 74%

---

# 在 Adobe Experience Platform 中使用行銷頻道維度

如果您的組織使用 [Analytics來源聯結器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant) 若要將報表套裝資料帶入Customer Journey Analytics，您可以在Customer Journey Analytics中設定連線，製作行銷管道維度的相關報表。

## 先決條件

* 需先使用 [Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hant)將報告套裝資料匯入 Adobe Experience Platform。由於行銷管道需仰賴 Analytics 報告套裝中的處理規則來運作，因此不支援其他資料來源。
* 行銷管道處理規則須完成設定。另請參閱 [行銷管道的處理規則](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=zh-Hant) (在Adobe Analytics元件指南中)。

## 行銷管道結構元素

您在所需的報告套裝建立 Analytics 來源連接器後，系統隨即就會建立 XDM 結構描述。此結構包含所有 Analytics 維度和量度，這些原始資料都不具歸因或持續性，而是由系統使用各個行銷管道處理規則逐一檢驗每個事件，並記錄相符的第一個規則。在Customer Journey Analytics中建立資料檢視時，您可以指定歸因和持續性。

1. [建立連線](/help/connections/create-connection.md)，納入以 Analytics 來源連線器為基礎的資料集。
2. [建立資料檢視](/help/data-views/create-dataview.md)，其中包含下列維度：
   * **`channel.typeAtSource`**：相當於[行銷管道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=zh-Hant)維度。
   * **`channel._id`**：相當於[行銷管道詳細資訊](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=zh-Hant)。
3. 為各維度提供所需的歸因模型和持續性。若您要同時使用首次接觸和最近一次接觸等維度，請分次將各行銷管道維度拖曳至元件區域。為各維度提供所需的歸因模型和持續性。Adobe 也建議針對各維度指定顯示名稱，以便在 Analysis Workspace 中使用。
4. 建立資料檢視。

現在您可透過 Analysis Workspace 使用您的行銷管道維度。

>[!NOTE]
>
> 分析來源連接器要求填入 `channel.typeAtSource` (行銷頻道) 和 `channel._id` (行銷頻道詳細資料)，否則兩者都不會傳遞到 XDM ExperienceEvent。如果來源報告套裝中的行銷頻道詳細資料為空白，這將導致空白 `channel._id`，並且分析來源連接器也將使 `channel.typeAtSource` 空白。這可能會導致 Adobe Analytics 和 Customer Journey Analytics 之間的報告差異。

## 處理與架構差異

>[!IMPORTANT]
>
>報告套裝資料和 Platform 資料之間有些基礎上的資料差異。Adobe 強烈建議您調整報告套裝的行銷管道處理規則，以便在 Platform 收集正確的資料。

>[!NOTE]
>
>為了讓 Attribution IQ 和 Customer Journey Analytics 的行銷管道獲得最大成效，我們已發佈一些[修改過的最佳做法](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=zh-Hant)。

行銷管道設定對 Platform 資料和報告套裝資料的運作方式不同。設定Customer Journey Analytics的行銷管道時，請考量下列差異：

* **是瀏覽的第一個頁面**：此規則條件在多個行銷管道的預設定義中很常見。只要處理規則內含有此條件，Platform 就會加以忽略 (同一規則中的其他條件仍適用)。工作階段是由資料查詢時間 (而非資料收集時間) 所決定，因此 Platform 無法使用此特定規則條件。Adobe 建議重新評估任何包含「為造訪的第一頁」標準的行銷管道處理規則，選擇可實現目標的替代方法。

  ![瀏覽的第一個頁面](../assets/first-page-of-visit.png)

* **覆寫最近一次接觸管道**：這項設定位於「行銷管道管理員」，一旦啟用，通常某些管道就無法取得最近一次接觸管道的評分。Platform 會忽略這項設定，導致「直接」或「內部」等各種管道以您不樂見的方式歸因至量度。Adobe 建議您移除未勾選「覆寫最近一次接觸管道」的管道。
   * 您可以在「行銷管道管理員」中刪除「直接」行銷管道，然後仰賴Customer Journey Analytics的「無值」維度專案來建立該管道。 您也可以將此維度項目重新命名為「直接」，或在設定資料檢視時完全排除此維度項目。
   * 或者，您也可以建立行銷管道分類，除了您想在Customer Journey Analytics中排除的管道外，每個值都自行分類。 接著您就可以在建立資料檢視時使用此分類維度，而非使用 `channel.typeAtSource`。

  ![覆寫最近一次接觸管道](../assets/override-last-touch-channel.png)

* **行銷管道有效期**：此參與期間設定會決定使用者在報表套裝資料中取得首次接觸管道前的閒置時間。 Platform會使用自己的歸因設定，因此在Customer Journey Analytics中會完全忽略此設定。

  ![行銷管道有效期](../assets/marketing-channel-expiration.png)

## 比較Customer Journey Analytics和Adobe Analytics之間的資料

由於Adobe Experience Platform的架構與Adobe Analytics報表套裝不同，因此無法保證兩者產生的結果相符。 不過，您可以透過下列提示輕鬆比較：

* 確認上方列出的架構差異不會影響比較作業，包括移除不會覆寫最近一次接觸管道的管道，以及移除第一個瀏覽點擊 (工作階段) 的規則條件。
* 再次確認連線是否使用與Adobe Analytics相同的報表套裝。 如果您的Customer Journey Analytics連線包含多個報表套裝，且套裝具有專屬的行銷管道處理規則，便無法與Adobe Analytics輕鬆比較。 建議您為每個報告套裝建立個別連線，以便比較資料。
* 確認您所比較的資料出自相同的日期範圍，而且資料檢視與報告套裝的時區設定相同。
* 檢視報告套裝資料時，請使用自訂歸因模型，例如使用量度非預設歸因模型的[「行銷管道」](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=zh-Hant)維度。由於[「首次接觸管道」](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=zh-Hant)或[「最近一次接觸管道」](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=zh-Hant)皆仰賴報告套裝所收集的歸因，因此 Adobe 不建議比較這些預設維度。Customer Journey Analytics不仰賴報表套裝的歸因資料，而是在執行Customer Journey Analytics報表時計算。
* 基於報告套裝資料和 Platform 資料的架構有所差異，部分量度並不適合比較，範例包括造訪/工作階段、人員/人員以及發生次數/事件。
