---
title: 將全域查閱新增至資料集
description: 使用全域查閱功能，在客戶歷程分析中使用有用的維度來增強報告。
translation-type: tm+mt
source-git-commit: b3c9757421537d2d84a78a4d37e9bfc362438d40
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# 將全域查閱新增至資料集

全域查閱可增強「客戶歷程分析」報告某些維度／屬性的能力，這些維度／屬性本身並無用處，但在與其他資料結合時非常有用。 範例包括行動裝置的屬性，以及作業系統和瀏覽器維度的屬性，例如瀏覽器版本號碼。 「全域查閱」與查閱資料集（在傳統Adobe Analytics中稱為分類）非常類似。 不過，全域查閱適用於Experience Cloud組織。 全局查找會自動應用於包含某些XDM架構欄位的所有事件資料集（有關特定欄位，請參見下面）。
對於Adobe正在分類的每個結構位置，都存在全域查閱資料集。 您可以搭配Analytics來源連接器或其他可接受的自訂資料集使用全域查閱資料集。

在傳統的Adobe Analytics中，這些維度會自行顯示，而在CJA中，您必須在建立資料檢視時主動加入這些維度。 當使用者在「連線」工作流程中，選擇以索引鍵標示為資料集的資料集時，資料檢視UI會知道包含所有可用於報告的全域查閱維度。 資料檢視工作流程知道會納入這些資料檢視可用的全域查閱維度。 查閱檔案會自動保持在最新狀態，而且可供所有地區和所有帳戶使用。 它們儲存在與客戶相關的地區特定組織中。

## 將全域查詢與Adobe Data Connector資料集搭配使用

全域查閱資料集會在報告時自動套用。 如果您使用[Analytics資料連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en#connectors)，而您引入Adobe提供全域查閱的維度，我們會自動套用此全域查閱。 如果事件資料集包含[XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en)欄位，我們可以套用全域查詢。

## 使用自訂資料集的全域查閱

事件資料集中必須有與全域查閱資料集相容的索引鍵。 只要您新增部分標準[Adobe Experience Platform架構mixins](https://experienceleague.adobe.com/docs/experience-platform/xdm/mixins/event/environment-details.html?lang=en#mixins)，以填入正確的XDM欄位，您就可以讓自訂資料集搭配全域查閱運作。

## 可用的全域查閱欄位

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`,  `group_id`  `id`
* `os_group`
   * `os_group`的  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## 全域查閱維度報告

若要報告全域查閱維度，您必須在「客戶歷程分析」中建立資料檢視時新增這些維度：

![](assets/global-lookup.png)

然後，您就可以在工作區中看到查閱資料：

![](assets/gl-reporting.png)

