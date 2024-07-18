---
description: 使用智慧型字幕來產生自然語言的深入分析，以便快速呈現視覺效果中的趨勢。
title: 智慧型註解
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# 智慧型註解

智慧型註解使用進階的機器學習和生成式 AI，為 Workspace 視覺效果提供有價值的自然語言深入解析。初始發行提供自動產生的[線條](line.md)視覺化前瞻分析。 （隨後將提供其他視覺效果。）

智慧型字幕的目標為：

* 需要與其他使用者分享敘述的分析師。 分析師需要這些見解才能為其使用者提供內容。
* 想要快速探索高階料理的商業使用者。

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

您可以將註解複製到剪貼簿，然後貼到Powerpoint或其他工具中。 在註解對話方塊右上角找到&#x200B;**[!UICONTROL 將註解複製到剪貼簿]**&#x200B;圖示。

## 編輯註解 {#edit}

您可以編輯註解，例如隱藏或取消隱藏特定類別的深入分析。 例如，如果您不想要瞭解最小訂購，您可以直接隱藏它，然後按一下「套用」，它就不會再顯示。

1. 按一下剪貼簿圖示旁的&#x200B;**[!UICONTROL 編輯智慧型註解顯示]**&#x200B;圖示。

1. 在編輯對話方塊中，按一下您要隱藏之分析旁的眼睛圖示。

1. 按一下&#x200B;**[!UICONTROL 套用]**。

使用相同的程式來取消隱藏字幕。

## 匯出註解 {#export}

您可以透過PDF **匯出**&#x200B;註解，只要專案儲存時已產生註解即可。

## 關閉註解 {#toggle}

如果您不想產生智慧型字幕，您可以移至視覺效果偏好設定並取消勾選&#x200B;**[!UICONTROL 顯示智慧型字幕]**，以關閉此功能。

![顯示取消勾選「顯示智慧型字幕」選項的線條視覺效果選項。](assets/toggle-captions.png)

## 行動計分卡上的智慧型字幕

智慧型字幕也適用於Customer Journey Analytics[行動計分卡](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)。