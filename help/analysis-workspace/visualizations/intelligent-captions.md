---
description: 使用智慧型字幕來產生自然語言的深入分析，以便快速呈現視覺效果中的趨勢。
title: 智慧型註解
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# 智慧型註解

智慧型字幕使用進階機器學習和創作AI，為Workspace視覺效果提供有價值的自然語言見解。 初始版本為「 」提供自動產生的分析 [折線圖](line.md) 視覺效果。 （隨後將提供其他視覺效果。）

智慧型字幕的目標為：

* 需要與其他使用者分享敘述的分析師。 分析師需要這些見解才能為其使用者提供內容。
* 想要快速探索高階料理的商業使用者。

註解可供所有Customer Journey Analytics使用者使用，且不需要特殊許可權。

## 啟動智慧型字幕 {#launch}

若要啟動自動產生的線條圖視覺效果註解，請按一下 **[!UICONTROL 智慧型字幕]** 圖示加以識別。

![啟動「分析」視窗，顯示「產品檢視趨勢」的智慧型註解。 ](assets/intell-caps-1.png)

自然語言見解正在產生中。

請記住：

* 您至少需要3個資料點才能成功產生註解。 否則，您可能會收到顯示「資料不足，無法分析」的錯誤。

* 每次在提供視覺效果之表格中的基礎選定資料變更時，都會產生字幕。

* 如果表格中有多個量度，系統只會針對第一個量度或使用者目前選取的量度產生標題。

* 如果此時儲存專案，稍後再重新載入，註解會自動以新資料更新。 這同樣適用於從此專案匯出的排程專案和PDF檔案。

## 檢視和解讀註解 {#view}

以下是註解的範例：

![折線圖視覺效果的智慧型字幕，包括季節性、最小值、最大值、尖峰和下降。](assets/captions.png)

## 複製到剪貼簿 {#copy}

您可以將註解複製到剪貼簿，然後貼到Powerpoint或其他工具中。 尋找 **[!UICONTROL 將註解複製到剪貼簿]** 圖示加以顯示。

## 編輯註解 {#edit}

您可以編輯註解，例如隱藏或取消隱藏特定類別的深入分析。 例如，如果您不想要瞭解最小訂購，您可以直接隱藏它，然後按一下「套用」，它就不會再顯示。

1. 按一下 **[!UICONTROL 編輯智慧型字幕顯示]** 圖示加以存取。

1. 在編輯對話方塊中，按一下您要隱藏之分析旁的眼睛圖示。

1. 按一下&#x200B;**[!UICONTROL 套用]**。

使用相同的程式來取消隱藏字幕。

## 匯出註解 {#export}

您可以 **透過PDF匯出註解**，只要專案儲存時產生註解。

## 關閉註解 {#toggle}

如果您不想產生智慧型字幕，您可以前往「視覺效果」偏好設定並取消勾選，將此功能切換為關閉 **[!UICONTROL 顯示智慧型字幕]**.

![線條視覺效果選項，顯示取消勾選「顯示智慧型字幕」的選項。](assets/toggle-captions.png)

## 行動計分卡上的智慧型字幕

Customer Journey Analytics中也提供智慧型字幕 [行動計分卡](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).