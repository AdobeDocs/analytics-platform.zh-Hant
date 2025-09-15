---
description: 瞭解如何使用智慧型字幕來產生自然語言的深入分析，以呈現視覺效果中的趨勢。
title: 智慧型註解
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 98%

---

# 智慧型註解 {#intelligent-captions}

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="智慧型註解"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"


智慧型註解功能是使用先進的生成式 AI，為自然語言中最常用的 Workspace 視覺效果提供關鍵分析。

智慧型註解適用於：

* 分析師，需要供其他使用者分享的敘述。分析師需要這些分析才能提供內容給使用者。
* 希望很快發現高層級要點的商業使用者。

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [智慧型註解](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


## 啟動智慧型註解 {#launch}

若要啟動為視覺效果自動產生的智慧型標題，請在視覺效果右上角選取「![智慧型註解](/help/assets/icons/AI.svg)」。這項選取會產生自然語言分析。

![啟動分析視窗顯示產品瀏覽量趨勢的智慧型註解。](assets/intelligent-captions.gif)


請記住以下事項：

* 您至少需要 3 個資料點才能成功產生註解。否則，你可能會收到如「**[!UICONTROL 資料不足而無法分析]**」的錯誤。

* 在支持視覺效果的表格中，若相關已選取的資料發生變化時，每次都會產生註解。

* 如果在關聯的自由格式表中有多個量度，則只會為第一個量度或使用者目前選取的量度產生註解。但是，可以為折線圖和區域圖視覺效果的多個量度產生註解。

* 如果您將專案儲存在特定點，並稍後重新加載，則註解將自動使用新資料來進行更新。這同樣適用於排程的專案和從項目匯出的 PDF 檔案。


## 視覺效果 {#visualizations}

以下視覺效果支援智慧型註解：

* [折線圖](line.md) (包括多個折線)
* [長條圖](bar.md)
* [橫條圖](horizontal-bar.md)
* [區域圖](area.md) (包括多條區域圖線)
* [環形圖](donut.md)
* [流失](fallout/fallout-flow.md)
* [流量](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 動作

您可以對智慧型註解執行以下操作：

### 複製到剪貼簿 {#copy}

您可以將註解複製到剪貼簿，然後將其貼到 PowerPoint 或其他工具中。您可以在逐一視圖中複製個別註解，也可以在擴大的註解視圖中一次複製所有註解。

* 若要複製註解，請在註解對話框右上角選取「![將註解複製到剪貼簿](/help/assets/icons/Copy.svg)」。

### 顯示全部或個別智慧型註解  {#show-all-or-individual}

您可以在展開視圖中一次顯示所有智慧型註解，也可以在逐一視圖中顯示單一智慧型註解。

* 若要顯示所有智慧型註解，請選取「![顯示所有智慧型註解](/help/assets/icons/Maximize.svg)」。
* 若要逐一顯示單一智慧型註解，請選取「![顯示個別的智慧型註解](/help/assets/icons/Minimize.svg)」。

### 編輯顯示區 {#edit}

您可以編輯註解的顯示，例如隱藏或取消隱藏特定類別的註解。

1. 在智慧型註解對話框中，選取「![編輯智慧型註解的可見度](/help/assets/icons/EditInLight.svg)」。

1. 在 ![切換可見度](/help/assets/icons/Visibility.svg) 顯示特定分析 (例如&#x200B;**[!UICONTROL 最小]**) 之間切換，或 ![切換可見度](/help/assets/icons/VisibilityOff.svg) 隱藏特定分析 (例如&#x200B;**[!UICONTROL 尖峰]**)。

   ![編輯智慧型註解](assets/edit-intelligent-captions.png)

1. 選取&#x200B;**[!UICONTROL 「套用」]**。


### 提供意見反應

您可以對生成的智慧型註解提供意見回饋 (僅可在擴充功能的註解檢視中提供意見回饋)。

1. 在智慧型註解對話框中，選取「![更多操作](/help/assets/icons/More.svg)」。

1. 選取「![反應良好](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 反應良好]**」、「![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 反應不佳]**」，「或者![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL 報告]**」。

1. 在「**[!UICONTROL 感謝您的意見回饋]**」對話框中，提供您的意見回饋並選取「**[!UICONTROL 提交]**」以提交意見回饋。

### 匯出 {#export}

您可以將智慧型註解作為 PDF 的一部分匯出，只要將附生成式智慧型註解的專案儲存即可。

### 關閉 {#toggle}

如果您不想顯示智慧型註解，您可以關閉該功能。

1. 前往[視覺效果偏好設定](/help/analysis-workspace/user-preferences.md#visualizations-preferences)。
1. 取消勾選「**[!UICONTROL 顯示智慧型註解]**」。

   ![折線圖視覺效果選項，顯示取消勾選「顯示智慧型解」的選項。](assets/toggle-captions.png)

1. 選取「**[!UICONTROL 儲存]**」以儲存偏好設定。


## Mobile 計分卡中智慧型註解

Customer Journey Analytics [行動記分卡](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)中也提供智慧型註解。

## 功能存取

以下參數控制對智慧型註解的存取：

* **解決方案存取**：智慧型註解功能適用於 Customer Journey Analytics，但不適用於 Adob&#x200B;&#x200B;e Analytics。

* **合約存取**：如果您無法使用智慧型註解，請聯絡您組織的管理員或 Adob&#x200B;&#x200B;e 客戶代表 (管理員)。在您的組織中使用智慧型註解之前，您必須同意某些與生成式 AI 相關的法律條款。

* **權限**：在 [!UICONTROL Adobe Admin Console] 中，[!UICONTROL 報告工具] **[!UICONTROL 智慧型註解]**&#x200B;權限會決定存取權。 [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要遵守 [!UICONTROL Admin Console]中的以下步驟：
   1. 導覽至「**[!UICONTROL Admin Console]** > **[!UICONTROL 產品與服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**」。
   1. 選取您想要提供智慧型註解存取權的產品設定檔標題。
   1. 在特定的產品設定檔中，選取「**[!UICONTROL 權限]**」。
   1. 選取「![編輯](/help/assets/icons/Edit.svg)」，可編輯「**[!UICONTROL 報告工具]**」。
   1. 選取 ![AddCircle](/help/assets/icons/AddCircle.svg)，可新增&#x200B;**智慧型註解**&#x200B;至&#x200B;**[!UICONTROL 包含的權限項目]**。

      ![新增權限](./assets/intelligent-captions-permissions.png)

   1. 選取「**[!UICONTROL 儲存]**」以儲存權限。

請參閱[存取控制概觀](/help/technotes/access-control.md#access-control)，了解更多資訊。
