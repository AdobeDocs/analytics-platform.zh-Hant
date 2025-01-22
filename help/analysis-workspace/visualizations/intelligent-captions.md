---
description: 使用智慧型字幕來產生自然語言的深入分析，以顯示視覺效果中的趨勢。
title: 智慧型註解
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 7d103e9d709ec076519360a4b43af44f061171e9
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 19%

---

# 智慧型註解 {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="智慧型註解：區域圖"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="智慧型註解：長條圖"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="智慧型註解：環形圖"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="智慧型註解：長條圖"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="智慧型註解：折線圖"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="智慧型註解：流失"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="智慧型註解：流量"
>abstract="以自然語言形式產生深入分析，協助您更輕鬆地了解和解釋此視覺效果的資料。"

<!-- markdownlint-enable MD034 -->

智慧型字幕功能使用進階的產生AI，針對最常使用的自然語言Workspace視覺效果提供關鍵深入分析。

智慧型字幕的目標為：

* 需要與其他使用者分享敘述的分析師。 分析師需要這些見解才能為其使用者提供內容。
* 想要快速探索高階外賣產品的商務使用者。

## 啟動智慧型字幕 {#launch}

若要啟動視覺效果自動產生的智慧型字幕，請選取視覺效果右上角的![智慧型字幕](/help/assets/icons/AI.svg)。 此選取範圍會產生自然語言深入分析。

![啟動顯示產品檢視趨勢智慧型字幕的分析視窗。](assets/intelligent-captions.gif)


請記住以下事項：

* 您至少需要3個資料點才能成功產生註解。 否則，您可能會收到&#x200B;**[!UICONTROL 資料不足]**&#x200B;等錯誤訊息。

* 每次在提供視覺效果功能的表格中變更基礎選取資料時，都會產生註解。

* 如果相關的自由表格中有多個量度，系統只會針對第一個量度或使用者目前選取的量度產生註解。 不過，線條和區域的視覺效果中，有多個量度會產生註解。

* 如果您在特定點儲存專案，並在稍後重新載入，則註解會自動以新資料更新。 這同樣適用於從專案匯出的排程專案和PDF檔案。


## 視覺效果 {#visualizations}

下列視覺效果支援智慧型字幕：

* [行](line.md) （包括多行）
* [長條圖](bar.md)
* [橫條圖](horizontal-bar.md)
* [區域](area.md) （包含多個區域線）
* [環形圖](donut.md)
* [流失](fallout/fallout-flow.md)
* [流量](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 動作

您可以對智慧型字幕執行下列動作：

### 複製到剪貼簿 {#copy}

您可以將註解複製到剪貼簿，然後貼到PowerPoint或其他工具中。 您可以在逐一檢視中複製個別註解，也可以在展開的註解檢視中一次複製所有註解。

* 若要複製註解，請選取註解對話方塊右上角的![將註解複製到剪貼簿](/help/assets/icons/Copy.svg)。

### 顯示所有或個別智慧型字幕  {#show-all-or-individual}

您可以在展開檢視中一次顯示所有智慧型字幕，也可以依序在檢視中顯示個別智慧型字幕。

* 若要顯示所有智慧型字幕，請選取![顯示所有智慧型字幕](/help/assets/icons/Maximize.svg)。
* 若要逐一顯示個別智慧型字幕，請選取![顯示個別智慧型字幕](/help/assets/icons/Minimize.svg)。

### 編輯顯示區 {#edit}

您可以編輯註解的顯示，例如隱藏或取消隱藏特定類別的深入分析。

1. 在「智慧型字幕」對話方塊中選取![編輯智慧型字幕的可見度](/help/assets/icons/EditInLight.svg)。

1. 在![切換可見度](/help/assets/icons/Visibility.svg)之間切換以顯示特定分析（例如&#x200B;**[!UICONTROL 分鐘]**），或在![切換可見度](/help/assets/icons/VisibilityOff.svg)之間切換以隱藏特定分析（例如&#x200B;**[!UICONTROL 尖峰]**）。

   ![編輯智慧型字幕](assets/edit-intelligent-captions.png)

1. 選取&#x200B;**[!UICONTROL 「套用」]**。


### 提供意見反應

您可以針對產生的智慧型註解提供意見反應（意見反應只能在展開的註解檢視中提供）。

1. 在「智慧型字幕」對話方塊中選取![其他動作](/help/assets/icons/More.svg)。

1. 選取![好回應](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 好回應]**、![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 壞回應]**&#x200B;或![旗標](/help/assets/icons/Flag.svg) **[!UICONTROL 報告]**。

1. 在&#x200B;**[!UICONTROL 感謝您的意見反應]**&#x200B;對話方塊中，提供您的意見反應，並選取&#x200B;**[!UICONTROL 提交]**&#x200B;以提交意見反應。

### 匯出 {#export}

只要儲存專案並產生智慧型字幕，您就可以將智慧型字幕匯出為PDF的一部分。

### 切換關閉 {#toggle}

如果您不想顯示智慧型字幕，您可以關閉該功能。

1. 移至[視覺效果偏好設定](/help/analysis-workspace/user-preferences.md#visualizations-preferences)。
1. 取消勾選&#x200B;**[!UICONTROL 顯示智慧型字幕]**。

   ![顯示取消勾選「顯示智慧型字幕」選項的線條視覺效果選項。](assets/toggle-captions.png)

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存偏好設定。


## 行動計分卡上的智慧型字幕

智慧型字幕也適用於Customer Journey Analytics[行動計分卡](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)。

## 功能存取

下列引數可控制智慧型字幕的存取權：

* **解決方案存取**：智慧型字幕功能可在Customer Journey Analytics中使用，但不適用於Adobe Analytics。

* **合約存取**：如果您無法使用智慧型字幕，請聯絡貴組織的管理員或Adobe帳戶代表（管理員）。 您必須先同意特定的Generative AI相關法律條款，才能在組織中使用智慧型字幕。

* **許可權**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 報告工具] **[!UICONTROL 智慧型字幕]**&#x200B;許可權會決定存取權。 [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中遵循下列步驟：
   1. 導覽至&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 產品及服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**。
   1. 選取您要為其提供智慧型字幕存取許可權的產品設定檔標題。
   1. 在特定產品設定檔中，選取&#x200B;**[!UICONTROL 許可權]**。
   1. 選取![編輯](/help/assets/icons/Edit.svg)以編輯&#x200B;**[!UICONTROL 報告工具]**。
   1. 選取![AddCircle](/help/assets/icons/AddCircle.svg)以將&#x200B;**智慧型字幕**&#x200B;新增至&#x200B;**[!UICONTROL 包含的許可權專案]**。

      ![新增許可權](./assets/intelligent-captions-permissions.png)

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存許可權。

如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md#access-control)。
