---
description: 如何設定使用 Analytics 行動應用程式的使用者
title: 設定使用控制面板的高階主管
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '668'
ht-degree: 100%

---

# 設定使用控制面板的高階主管使用者

某些情況下，高階主管使用者可能需要額外的協助，才能存取及使用應用程式。本節提供可幫助組織者提供這類協助的資訊。

## 確認應用程式使用者有 Adobe Analytics 存取權

1. 在 [Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hant) 中設定新使用者。

1. 為了能共用計分卡，您必須授予應用程式使用者權限，使其能存取 Analysis Workspace 之類的計分卡元件、計分卡根據的資料檢視以及篩選器、量度和維度。

## 應用程式使用者系統的先決條件

為確保高階主管使用者能存取您在應用程式上的計分卡，請確定：

* 使用者裝置的行動作業系統需為 iOS 10 (含) 以上版本或 Android 4.4 (KitKat) (含) 以上版本
* 使用者處於 Adobe Analytics 的有效登入狀態。
* 您已為使用者正確建立行動計分卡，並和他們共用這些計分卡。
* 使用者可存取計分卡中的元件。請注意，您可在共用計分卡時選取&#x200B;**[!UICONTROL 共用內嵌元件]**&#x200B;的選項。

## 協助高階主管下載和安裝應用程式

**若高階主管使用者使用 iOS：**

按一下以下連結 (也可從 Analytics 中的&#x200B;**[!UICONTROL 「工具]** > **[!UICONTROL Analytics 儀表板 (行動應用程式)」]**&#x200B;底下存取)，然後依照提示下載、安裝和開啟應用程式：

`[iOS link](https://apple.co/2zXq0aN)`

**若高階主管使用者使用 Android：**

按一下以下連結 (也可從 Analytics 中的&#x200B;**[!UICONTROL 「工具]** > **[!UICONTROL Analytics 儀表板 (行動應用程式)」]**&#x200B;底下存取)，然後依照提示下載、安裝和開啟應用程式：

`[Android link](https://bit.ly/2LM38Oo)`

下載並安裝完畢後，高階主管使用者就可使用現有的 Adobe Analytics 憑證登入應用程式；系統可支援 Adobe 和 Enterprise/Federated ID。

![應用程式歡迎畫面](assets/welcome.png)

## 協助高階主管存取您的計分卡

1. 要求高階主管使用者登入應用程式。

   「**[!UICONTROL 選擇公司]**」畫面隨即顯示。此畫面會列出高階主管使用者所屬的登入公司。

1. 要求他們點選適用於您所共用的計分卡的登入公司或 Experience Cloud 組織名稱。

   該計分卡清單接著就會顯示該登入公司和高階主管共用的所有計分卡。

1. 若情況適用，要求他們依「**[!UICONTROL 最近修改項目]**」將清單排序。

1. 要求他們點選計分卡的名稱來加以檢視。

   ![選擇公司](assets/accesscard.png)


### 說明計分卡 UI

向高階主管使用者說明圖磚在您所共用的計分卡中顯示的方式。

![說明圖磚](assets/newexplain.png)

![計分卡範例](assets/intro_scorecard.png)

圖磚的其他資訊：

* 走勢圖的粒度取決於日期範圍的長度：
* 若長度為一天，圖表會顯示每小時趨勢
   * 若長度為一天以上、一年以下，則會顯示每日趨勢
   * 若長度為一年 (含) 以上，圖表會顯示每週趨勢
   * 百分比值變更公式為量度合計 (目前日期範圍) - 量度合計 (比較日期範圍) / 量度合計 (比較日期範圍)。
   * 下拉畫面即可重新整理計分卡。


1. 點選圖磚，即可顯示圖磚劃分的詳細運作資訊。

   ![劃分檢視](assets/sparkline.png)

   * 點選走勢圖上的任一點，可查看與線上該點相關聯的資料。

   * 其中包含一個表格，會顯示新增至圖磚的維度資料。點選向下箭頭可選取維度。如果未將任何維度新增至圖磚，表格將會顯示圖表資料。

1. 若要變更計分卡的日期範圍，點選日期標題並選取想要檢視的主要和比較日期範圍組合。

   ![變更日期](assets/changedate.png)

## 變更應用程式偏好設定

若要變更偏好設定，請點選上方顯示的&#x200B;**[!UICONTROL 偏好設定]**&#x200B;選項。在偏好設定中，您可以開啟生物特徵辨識登入，或是將應用程式設定為深色模式，如下所示：

![深色模式](assets/darkmode.png)

## 疑難排解

如果高階主管使用者登入後看到無共用項目的訊息:

![無共用項目](assets/nothing.png)

* 高階主管使用者可能選取了錯誤的 Analytics 實例，或者
* 可能尚未和該高階主管使用者共用任何計分卡。

請確認高階主管使用者可登入正確的 Adobe Analytics 實例，且有與其共用的計分卡。
