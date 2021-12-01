---
title: 將標準查詢新增至資料集
description: 在Customer Journey Analytics中使用標準查詢功能，以實用維度來增強報表。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 6c5fb7b3964cbf2bb5158733a2ede9b54f9415a5
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 31%

---

# 將標準查詢新增至資料集

標準查閱(也稱為Adobe提供的查閱)可增強Customer Journey Analytics報告某些維度/屬性的能力，這些維度/屬性本身並不實用，但與其他資料結合時非常有用。 像是結合行動裝置和作業系統的屬性以及瀏覽器維度 (例如瀏覽器版本編號)，便是很實用的應用方式。「標準查詢」類似於查詢資料集。 標準查閱適用於所有Experience Cloud組織。 內含特定 XDM 結構描述欄位的所有事件資料集都會自動套用全域查詢 (請參閱底下的特定欄位說明)。 Adobe所分類的每個結構位置皆有標準查詢資料集。

在傳統 Adobe Analytics 中，這些維度會自行顯示，但在 CJA 中，您必須在建立資料檢視時主動納入這些維度。 在「連線」工作流程中，您可以選取以標籤鍵進行標準查詢的資料集。 資料檢視UI會自動知道納入所有可用於報表的標準查閱維度。 所有區域和帳戶的查詢檔案都會自動保持在最新狀態。這些檔案會儲存在與客戶相關聯區域的組織中。

## 搭配AdobeData Connector資料集使用標準查詢

報表時間會自動套用標準查詢資料集。 如果您使用Analytics Data Connector，並加入Adobe提供標準查閱的維度，系統就會自動套用此標準查閱。 如果事件資料集包含XDM欄位，系統就能為資料集套用標準查詢。

### 可用的標準查閱欄位

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

## 標準查閱維度報表

若要針對標準查閱維度製作報表，您必須在Customer Journey Analytics中建立資料檢視時新增這些維度：

![](assets/global-lookup.png)

接著，您就能在 Analysis Workspace 中看見查詢資料：

![](assets/gl-reporting.png)
