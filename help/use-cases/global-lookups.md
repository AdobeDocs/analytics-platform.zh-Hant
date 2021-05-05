---
title: 將全域查詢新增至資料集
description: 在 Customer Journey Analytics 中使用全域查詢功能，透過實用維度來增強報表。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: tm+mt
source-git-commit: 26ee2b61fb80b55a7982d90941ec121547423cfc
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 63%

---

# 將全域查詢新增至資料集

全域查詢可增強 Customer Journey Analytics 針對部分維度/屬性建立報表的能力，這些維度/屬性本身雖不實用，但與其他資料結合後效用甚大，像是結合行動裝置和作業系統的屬性以及瀏覽器維度 (例如瀏覽器版本編號)，便是很實用的應用方式。「全域查閱」類似於查閱資料集。 全域代碼適用於所有Experience Cloud組織。 它們會自動套用至包含特定XDM架構欄位的所有事件資料集（請參閱以下特定欄位）。 對於Adobe正在分類的每個模式位置，都存在全局查找資料集。

舊版 Adobe Analytics 中，這些維度會自行顯示，但在 CJA 中，您必須在建立資料檢視時主動加入這些維度。在「連線」工作流程中，您會選取以索引鍵標示為資料集的資料集。 「資料檢視」UI會自動知道包含所有可用於報告的全域查閱維度。 所有區域和帳戶的查詢檔案都會自動保持在最新狀態。這些檔案會儲存在與客戶相關聯區域的組織中。

## 搭配使用全域查詢與 Adobe Data Connector 資料集

全域查詢資料集會在報表時間自動套用。如果您使用Analytics資料連接器，並引入Adobe提供全域查閱的維度，我們會自動套用此全域查閱。 如果事件資料集包含 XDM 欄位，系統就能為資料集套用全域查詢。

## 可用的全域查詢欄位

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

## 全域查詢維度報表

若要使用全域查詢維度來建立報表，請在 Customer Journey Analytics 中建立資料檢視時將其加入：

![](assets/global-lookup.png)

接著，您就能在 Analysis Workspace 中看見查詢資料：

![](assets/gl-reporting.png)
