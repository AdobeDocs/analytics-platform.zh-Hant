---
title: 將全域查詢新增至資料集
description: 在 Customer Journey Analytics 中使用全域查詢功能，透過實用維度來增強報表。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---

# 將全域查詢新增至資料集

全域查詢可增強 Customer Journey Analytics 針對部分維度/屬性建立報表的能力，這些維度/屬性本身雖不實用，但與其他資料結合後效用甚大，像是結合行動裝置和作業系統的屬性以及瀏覽器維度 (例如瀏覽器版本編號)，便是很實用的應用方式。「全域查詢」類似於查詢資料集。 全域查詢適用於採用 Experience Cloud 的所有組織。 內含特定 XDM 結構描述欄位的所有事件資料集都會自動套用全域查詢 (請參閱底下的特定欄位說明)。 Adobe 正在分類的每個結構描述位置會有全域查詢資料集存在。

在傳統 Adobe Analytics 中，這些維度會自行顯示，但在 CJA 中，您必須在建立資料檢視時主動納入這些維度。 在連線工作流程中，您會選取被標記為有包含全域查詢索引鍵的資料集。 資料檢視 UI 自動知道要納入可用於報告的所有全域查詢維度。 所有區域和帳戶的查詢檔案都會自動保持在最新狀態。這些檔案會儲存在與客戶相關聯區域的組織中。

## 搭配使用全域查詢與 Adobe Data Connector 資料集

全域查詢資料集會在報表時間自動套用。如果您使用 Analytics 資料連接器，並引進 Adobe 為其提供全域查詢的維度，我們就會自動套用此全域查詢。 如果事件資料集包含 XDM 欄位，我們就能為該資料集套用全域查詢。

## 可用的全域查詢欄位

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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
