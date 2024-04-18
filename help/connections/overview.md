---
title: Customer Journey Analytics 連線概觀
description: 了解 Customer Journey Analytics 中的連線。
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 55%

---

# 連線概觀

連線可讓Customer Journey Analytics產品管理員與其他人建立連線 [!DNL Adobe Experience Platform] 資料來源，例如事件、查詢和設定檔資料集。 這些連線可以將連線中的資料整合到衍生資料視圖中。連線是CJA的基礎，建立來源為 [!DNL Experience Platform] 來源資料集。 存取連線也可讓您檢視連線管理員，您可以在其中檢視組成連線的基礎資料集，以及進行重要的編輯和組態選擇。

建議將連線管理的存取權限制為核心管理群組。「連線」層級的設定對於引入Customer Journey Analytics之資料的磁碟區配置具有合約意涵。

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
