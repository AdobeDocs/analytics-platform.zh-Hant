---
description: 使用智慧型字幕來產生自然語言見解，以快速在視覺效果中呈現趨勢。
title: 智慧型註解
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: dae2282717d5d84862259d5b056fbfeb2d068cce
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 4%

---

# 智慧型註解

智慧型註解使用進階的機器學習和生成式 AI，為 Workspace 視覺效果提供有價值的自然語言深入解析。初始發行提供自動產生的[線條](line.md)視覺化前瞻分析。 隨後將提供其他視覺效果。

智慧型字幕的目標為：

* 需要與其他使用者分享敘述的分析師。 分析師需要這些見解才能為其使用者提供內容。
* 想要快速探索高階內容的企業使用者。

註解可供所有Customer Journey Analytics使用者使用，且不需要特殊許可權。

## 啟動智慧型字幕 {#launch}

若要為線條視覺效果啟動自動產生的註解，請按一下視覺效果右上角的&#x200B;**[!UICONTROL 智慧型註解]**&#x200B;圖示。

![啟動顯示產品檢視趨勢智慧型字幕的分析視窗。](assets/intell-caps-1.png)

自然語言見解正在產生中。

請記住：

* 您至少需要3個資料點才能成功產生註解。 否則，您可能會收到顯示「資料不足，無法分析」的錯誤。

* 每次在提供視覺效果之表格中的基礎選定資料變更時，都會產生字幕。

* 如果表格中有多個量度，系統只會針對第一個量度或使用者目前選取的量度產生標題。

* 如果此時儲存專案，稍後再重新載入，註解會自動以新資料更新。 這同樣適用於從此專案匯出的排程專案和PDF檔案。

## 檢視和解讀註解 {#view}

以下是註解的範例：

![線條視覺效果的智慧型字幕，包括季節性、最小值、最大值、尖峰與下降。](assets/captions.png)

## 複製到剪貼簿 {#copy}

您可以將註解複製到剪貼簿，然後貼到PowerPoint或其他工具中。 在註解對話方塊右上角選取![將註解複製到剪貼簿](/help/assets/icons/Copy.svg)。

## 編輯註解 {#edit}

您可以編輯註解，例如隱藏或取消隱藏特定類別的深入分析。 例如，如果您不想要最低訂購的相關分析，您可以隱藏該分析，然後按一下「套用」。 而且不會再顯示。

1. 選取「編輯智慧型字幕」對話方塊中的![智慧型字幕顯示](/help/assets/icons/EditInLight.svg)。

1. 在![可見度](/help/assets/icons/Visibility.svg)之間切換以顯示特定分析（如&#x200B;**[!UICONTROL 分鐘]**），或在![可見度關閉](/help/assets/icons/VisibilityOff.svg)之間切換以隱藏特定分析（如&#x200B;**[!UICONTROL 尖峰]**）。

   ![編輯智慧型字幕](assets/edit-intelligent-captions.png)

1. 選取&#x200B;**[!UICONTROL 「套用」]**。


## 提供意見反應

您可以對產生的智慧型字幕提供意見回饋。

1. 在「智慧型字幕」對話方塊中選取![其他動作](/help/assets/icons/More.svg)。

1. 選取![好回應](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 好回應]**、![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 壞回應]**&#x200B;或![旗標](/help/assets/icons/Flag.svg) **[!UICONTROL 報告]**。

1. 在&#x200B;**[!UICONTROL 感謝您的意見反應]**&#x200B;對話方塊中，提供您的意見反應，並選取&#x200B;**[!UICONTROL 提交]**&#x200B;以提交意見反應。

## 匯出註解 {#export}

您可以透過PDF **匯出**&#x200B;註解，只要專案儲存時已產生註解即可。

## 關閉註解 {#toggle}

如果您不想顯示智慧型字幕，可以關閉此功能。

1. 移至[視覺效果偏好設定](/help/analysis-workspace/user-preferences.md#visualizations-preferences)。
1. 取消勾選&#x200B;**[!UICONTROL 顯示智慧型字幕]**。

   ![顯示取消勾選「顯示智慧型字幕」選項的線條視覺效果選項。](assets/toggle-captions.png)

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存偏好設定。





## 行動計分卡上的智慧型字幕

智慧型字幕也適用於Customer Journey Analytics[行動計分卡](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)。

## 功能存取

下列引數可控制智慧型字幕的存取權：

* **解決方案存取**：智慧型字幕功能可在Customer Journey Analytics中使用，但不適用於Adobe Analytics。

* **合約存取**：如果您無法使用智慧型字幕，請連絡您組織的管理員或Adobe帳戶代表。 您必須同意特定的GenAI相關法律條款，才能在組織中使用Intelligent。

* **許可權**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 報告工具] **[!UICONTROL 智慧型字幕]**&#x200B;許可權會決定存取權。 [產品設定檔管理員](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中遵循下列步驟：
   1. 導覽至&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 產品及服務]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 產品設定檔]**。
   1. 選取您要為其提供智慧型字幕存取許可權的產品設定檔標題。
   1. 在特定產品設定檔中，選取&#x200B;**[!UICONTROL 許可權]**。
   1. 選取![編輯](/help/assets/icons/Edit.svg)以編輯&#x200B;**[!UICONTROL 報告工具]**。
   1. 選取![AddCircle](/help/assets/icons/AddCircle.svg)以將&#x200B;**智慧型字幕**&#x200B;新增至&#x200B;**[!UICONTROL 包含的許可權專案]**。

      ![新增許可權](./assets/intelligent-captions-permissions.png)

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存許可權。

如需詳細資訊，請參閱[存取控制](/help/technotes/access-control.md#access-control)。