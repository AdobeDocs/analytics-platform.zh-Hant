---
title: 將標準查詢新增至資料集
description: 在 Customer Journey Analytics 中使用標準查詢功能，透過實用維度來增強報表。
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 47%

---

# 將標準查詢新增至資料集

>[!IMPORTANT]
>
>標準查詢僅適用於Customer Journey Analytics中的Analytics來源聯結器資料來源。 您可以將其用於標準 Adobe Analytics 實施、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant) 或 Experience Platform 資料收集 API。
>

標準查詢 (也稱為 Adobe 提供的查詢) 可增強 Customer Journey Analytics 針對部分維度/屬性建立報表的能力，這些維度/屬性本身雖不實用，但與其他資料結合後效用甚大； 像是結合行動裝置和作業系統的屬性以及瀏覽器維度 (例如瀏覽器版本編號)，便是很實用的應用方式。「標準查詢」類似於查詢資料集。 標準查詢適用於採用 Experience Cloud 的所有組織。 內含特定XDM結構描述欄位的所有事件資料集（請參閱底下的特定欄位說明）都會自動套用全域查詢。 Adobe正在分類的每個結構描述位置會有標準查詢資料集。

在傳統Adobe Analytics中，這些維度會自行顯示，但在Customer Journey Analytics中，您必須在建立資料檢視時主動納入這些維度。 在連線工作流程中，您會選取被標記為有包含標準查詢索引鍵的資料集。 資料檢視 UI 會自動知道要納入可用於報告的所有標準查詢維度。 所有區域和帳戶的查詢檔案都會自動保持在最新狀態。這些檔案會儲存在與客戶相關聯區域的組織中。

## 搭配使用標準查詢與Analytics來源聯結器資料集

標準查詢資料集會在報表時間自動套用。 如果您使用Analytics來源聯結器，並引進Adobe為其提供標準查詢的維度，我們就會自動套用此標準查詢。 如果事件資料集包含 XDM 欄位，我們就能為該資料集套用標準查詢。

<!--
### Specific IDs that need to be populated

The following IDs need to be populated in the specific XDM mixins for this functionality to work:

* Environment Details Mixin – device/typeID value populated - Must match Device Atlas IDs and will populate device data.
* Adobe Analytics ExperienceEvent Template Mixin or Adobe Analytics ExperienceEvent Full Extension Mixin with analytics/environment/browserIDStr and analytics/environment/operatingSystemIDStr. Both must match the Adobe IDs and  populate browser and OS data, respectively.

You need these mixins with the three IDs populated (device/typeID, environment/browserIDStr, and environment/operatingSystemIDStr). The lookup dimensions will then be pulled automatically by Customer Journey Analytics and will be available in the Data View.

The catch here is that they can only populate those IDs today if they have a direct relationship with Device Atlas. They are Device Atlas IDs, and they provide an API to allow a customer to look them up. This is a significant hurdle, and we may just want to take the reference to this capability out of the product documentation until we have a productized way to expose the Device Atlas ID lookup functionality.
-->

### 可用的標準查詢欄位

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

## 標準查詢維度報表

若要針對Adobe標準查詢維度製作報表，當您在Customer Journey Analytics中建立[資料檢視](/help/data-views/data-views.md)時，必須新增一或多個這些維度。 在&#x200B;**[!UICONTROL 資料檢視]** > **[!UICONTROL 元件]**&#x200B;中：

1. 從左側邊欄的下拉式功能表中選取&#x200B;**[!UICONTROL 結構描述欄位]**。
1. 從結構描述欄位容器清單中選取&#x200B;**[!UICONTROL Adobe查詢]**。
1. 深入探討&#x200B;**[!UICONTROL 瀏覽器]**、**[!UICONTROL 行動裝置]**&#x200B;或&#x200B;**[!UICONTROL 作業系統]**，直到您找到要新增的維度。
1. 將維度拖曳至&#x200B;**[!UICONTROL 包含的元件]**&#x200B;內的&#x200B;**[!UICONTROL 量度]**&#x200B;或&#x200B;**[!UICONTROL 維度]**&#x200B;資料表。

   ![建立顯示[新增元件]清單的資料檢視](assets/add-standard-lookup-dimension.gif)

接著，您就可以在Workspace中使用查詢資料：

![顯示資料的自由格式表格](assets/gl-reporting.png)
