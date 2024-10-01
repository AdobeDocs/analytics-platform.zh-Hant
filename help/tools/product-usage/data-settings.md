---
title: 產品使用資料設定
description: 啟用、停用或設定產品使用設定。
hide: true
hidefromtoc: true
source-git-commit: 5c18fd78a71ddffef62dc3ac69f1abc3b42bddda
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---

# 產品使用資料設定 {#product-usage-data-settings}

_資料設定_&#x200B;頁面會處理您的產品使用設定。 您可以使用此頁面來啟用或停用貴組織的產品使用情形。 您也可以設定要在哪個Adobe Experience Platform沙箱下建立資料集，並視需要覆寫資料保留視窗。 只有產品管理員能看見。

**Customer Journey Analytics** > **工具** > **產品使用量** > **資料設定**

>[!IMPORTANT]
>
>啟用此功能時，您必須先接受條款與條件，才能加以使用。 接受這些條款與條件時，代表整個組織進行。

此頁面提供下列設定：

* **啟用產品使用狀況**：切換產品使用狀況資料收集的可用性。 如果您啟用產品使用，並在日後停用，則不會刪除資料集、連線和資料檢視。 您的組織在切換為關閉時，會全域停用追蹤。
* **沙箱**：決定要在其下建立結構描述和資料集的Adobe Experience Platform沙箱。 您選擇的沙箱不會影響產品使用資料收集。 如果您變更此沙箱設定，則會建立個別的資料集、連線和資料檢視。 歷史資料會保留在先前的沙箱中。
* **覆寫資料保留期間**：每個資料集都有預設的資料保留期間。 如果停用此設定，則產品使用會依循預設時段。 若要縮短資料保留時間，可啟用此設定。 資料保留期間無法超出資料集的預設資料保留期間。

>[!CONTEXTUALHELP]
>id="cja_product_usage_sandbox"
>title="Adobe Experience Platform沙箱"
>abstract="決定要在其下建立結構描述和資料集的Adobe Experience Platform沙箱。"

>[!CONTEXTUALHELP]
>id="cja_product_usage_data_retention"
>title="覆寫資料保留期間"
>abstract="縮短產品使用資料的可用性，協助降低成本。"
