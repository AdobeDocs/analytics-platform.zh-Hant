---
description: 如何設定使用Adobe Analytics儀表板行動應用程式的使用者
title: 設定使用儀表板的主管
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/78Bp5YSZg7Qs-qBnCfIoS6mjxda7CAglDG19Qq07Fw4
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b743a5d9-dc51-41ed-8b2f-86a1f8de430fid: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b21c7889-c659-4a99-a779-de1bae57e47eid: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 720
ht-degree: 65%

---

# 設定使用控制面板的高階主管使用者

某些情況下，高階主管使用者可能需要額外的協助，才能存取及使用應用程式。 本節提供可幫助組織者提供這類協助的資訊。

## 確認應用程式使用者有 Adobe Analytics 存取權

1. 在[CX Enterprise Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)中設定新使用者。

1. 為了能共用計分卡，您必須授予應用程式使用者許可權，使其能存取Analysis Workspace之類的計分卡元件、計分卡根據的資料檢視以及區段、量度和維度。

## 應用程式使用者系統的先決條件

為確保高階主管使用者能存取您在應用程式上的計分卡，請確定：

* 其裝置的最低行動作業系統需求為 iOS 10 (含) 以上版本，或 Android 4.4 (KitKat) (含) 以上版本
* 使用者處於Customer Journey Analytics的有效登入狀態。
* 您已為使用者正確建立行動計分卡，並和他們共用這些計分卡。
* 使用者可存取計分卡中的元件。 請注意，您可在共用計分卡時選取&#x200B;**[!UICONTROL 共用嵌入元件]**&#x200B;的選項。

## 協助高階主管下載和安裝應用程式

>[!NOTE]
>
>雖然行動應用程式在應用程式商店中的名稱為Adobe Analytics儀表板，但該應用程式可與Customer Journey Analytics行動計分卡同等使用。

**若高階主管使用者使用 iOS：**

按一下以下連結(也可從Customer Journey Analytics的&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Analytics儀表板（行動應用程式）]**&#x200B;底下存取)，然後依照提示下載、安裝和開啟應用程式：

`[iOS link](https://apple.co/2zXq0aN)`

**若高階主管使用者使用 Android：**

按一下以下連結(也可從Customer Journey Analytics中的&#x200B;**[!UICONTROL 工具]** > **[!UICONTROL Analytics儀表板（行動應用程式）]**&#x200B;底下存取)，然後依照提示下載、安裝和開啟應用程式：

`[Android link](https://bit.ly/2LM38Oo)`

下載並安裝完畢後，主管使用者就可使用現有的Customer Journey Analytics憑證登入應用程式；系統可支援Adobe和Enterprise/Federated ID。

![Adobe Analytics儀表板歡迎畫面](assets/welcome.png)

## 協助高階主管存取您的計分卡

1. 要求高階主管使用者登入應用程式。

   「**[!UICONTROL 選擇公司]**」畫面隨即顯示。 此畫面會列出高階主管使用者所屬的登入公司。

1. 要求他們點選套用至您共用計分卡的登入公司或CX Enterprise組織的名稱。

   該計分卡清單接著就會顯示該登入公司和高階主管共用的所有計分卡。

1. 若情況適用，要求他們依「**[!UICONTROL 最近修改項目]**」將清單排序。

1. 要求他們點選計分卡的名稱來加以檢視。

   ![選擇公司](assets/accesscard.png)


### 說明計分卡 UI

向高階主管使用者說明圖磚在您所共用的計分卡中顯示的方式。

![說明圖磚，包括選取的日期範圍、區段以及量度和維度](assets/newexplain.png)

![計分卡範例](assets/intro_scorecard.png)

圖磚的其他資訊：

* 走勢圖的顆粒度取決於日期範圍的長度：
* 若長度為一天，圖表會顯示每小時趨勢
   * 若長度為一天以上、一年以下，則會顯示每日趨勢
   * 若長度為一年 (含) 以上，圖表會顯示每週趨勢
   * 百分比值變更公式為量度合計 (目前日期範圍) - 量度合計 (比較日期範圍) / 量度合計 (比較日期範圍)。
   * 下拉畫面即可重新整理計分卡。


1. 點選圖磚，即可顯示圖磚劃分的詳細運作資訊。

   ![劃分檢視](assets/sparkline.png)

   * 點選走勢圖上的任一點，可查看與線上該點相關聯的資料。

   * 其中包含一個表格，會顯示新增至圖磚的維度資料。 點選向下箭頭可選取維度。 如果未將任何維度新增至圖磚，表格將會顯示圖表資料。

1. 若要變更計分卡的日期範圍，點選日期標題並選取想要檢視的主要和比較日期範圍組合。

   ![變更日期](assets/changedate.png)

## 變更應用程式偏好設定

若要變更偏好設定，請點選上方顯示的&#x200B;**[!UICONTROL 偏好設定]**&#x200B;選項。 在偏好設定中，您可以開啟生物特徵辨識登入，或是將應用程式設定為深色模式，如下所示：

![深色模式](assets/darkmode.png)

## 疑難排解

如果高階主管使用者登入後看到無共用項目的訊息:

![無共用項目](assets/nothing.png)

* 高階主管使用者可能選取了錯誤的Customer Journey Analytics沙箱，或者
* 可能尚未和該高階主管使用者共用任何計分卡。

確認執行使用者可登入正確的Customer Journey Analytics沙箱，且有與其共用的計分卡。
