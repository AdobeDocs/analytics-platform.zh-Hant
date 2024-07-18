---
title: Customer Journey Analytics 連線概觀
description: 了解 Customer Journey Analytics 中的連線。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 7a5fa07e3bafa3da5b044ce37299196a006f1d64
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# 連線概觀

連線可讓 Customer Journey Analytics 產品管理員與其他 [!DNL Adobe Experience Platform] 資料來源 (例如事件、查詢和設定檔資料集) 建立連線。這些連線可以將連線中的資料整合到衍生資料視圖中。連線是 CJA 的基礎，是根據 [!DNL Experience Platform] 來源資料集建立的。存取連線也可讓您檢視連線管理器，您可在其中檢視構成連線的基礎資料集，以及進行關鍵編輯和設定的選項。

建議將連線管理的存取權限制為核心管理群組。連線層級的設定對於導入 Customer Journey Analytics 的資料量分配具有合約影響。

以下是影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 必要權限

若要建立 Customer Journey Analytics 連線，您需要在 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 中設定以下權限：

Adobe Experience Platform：

* 資料模型製作：檢視綱要、管理綱要
* 資料管理：檢視資料集、管理資料集
* 資料擷取：管理來源
* 檢視身分命名空間

Customer Journey Analytics

* 產品管理員存取權

>[!IMPORTANT]
>
>您可以將多個 [!DNL Experience Platform] 資料集合併到單一連線中。
