---
title: 將全域查閱新增至資料集
description: 使用全域查閱功能，在客戶歷程分析中使用有用的維度來增強報告。
translation-type: tm+mt
source-git-commit: e57d92f702445d8caac25a7cc11a6aafe6c62262
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---


# 將全域查閱新增至資料集

全域查閱可增強「客戶歷程分析」報告某些維度／屬性的能力，這些維度／屬性本身並無用處，但在與其他資料結合時非常有用。 範例包括行動裝置的屬性，以及作業系統和瀏覽器維度的屬性，例如瀏覽器版本號碼。 「全域查閱」與查閱資料集（在傳統Adobe Analytics中稱為分類）非常類似。 不過，Experience Cloud組織間的服務是全球性的。 全局查找會自動應用於包含某些XDM架構欄位的所有事件資料集（有關特定欄位，請參見下面）。
對於Adobe正在分類的每個結構位置，都存在全域查閱資料集。 您可以搭配Analytics來源連接器或其他可接受的自訂資料集使用全域查閱資料集。

在傳統的Adobe Analytics中，這些維度會自行顯示，而在CJA中，您必須在建立資料檢視時主動加入這些維度。 當在CJA中選取要包含在連線中的資料集時，有些資料集會標幟為與全域查閱相容。 資料檢視工作流程知道會納入這些資料檢視可用的全域查閱維度。 查閱檔案會自動保持在最新狀態，而且可供所有地區和所有帳戶使用。 它們儲存在與客戶相關的地區特定組織中。
當使用者在「連線」工作流程中，選擇以索引鍵標示為資料集的資料集時，資料檢視UI會知道包含所有可用於報告的全域查閱維度。

## 將全域查詢與Adobe Data Connector資料集搭配使用

全局查找資料集在報告時自動應用。 如果您使用[分析資料連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors)，並且您引入了Adobe提供全局查找的維，則我們將自動應用此全局查找。 如果事件資料集包含[XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en)欄位，則我們可以對其應用全局查找。

## 對自定義資料集使用全局查找

事件資料集中需要與全局查找資料集相容的密鑰。 只要通過添加一些標準[Adobe體驗平台架構混合](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins)來填充正確的XDM欄位，您就可以使自定義資料集使用全局查找。

## 可用全局查找欄位

* 瀏覽器
*browser,group id, ID
* 瀏覽器組
*browser_group,ID
* os
   * os, groupid, ID
* os_group
   * os_group,ID
* mobile_audio_support — 多個
* mobile_color_depth
* mobile_cookie_support
* mobile_device_name
* mobile_device_number_transmit
* mobile_device_type
* mobile_drm — 多
* mobile_image_support — 多個
* mobile_information_services
* mobile_java_vm — 多個
* mobile_mail_centering
* mobile_manufacturer
* mobile_max_bookmark_url_length
* mobile_max_browser_url_length
* mobile_max_mail_url_length
* mobile_net_protocols — 多
* mobile_os
* mobile_push_to_talk
* mobile_screen_height
* mobile_screen_size
* mobile_screen_width
* mobile_video_support — 多個

## 全局查找維度報告

為了報告全局查找維，您必須在「客戶行程分析」中建立資料視圖時添加這些維：

![](assets/global-lookup.png)

然後，您可以在Workspace中查看查找資料：

![](assets/gl-reporting.png)

