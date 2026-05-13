---
title: 管理您的Customer Journey Analytics使用情況
description: 說明如何管理您的Customer Journey Analytics使用情況。
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
TQID: https://experienceleague.adobe.com/LbcO4spfU9qS4AT-cV2-Jec3dJnfAZXiBXRA-grdUSg
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 37%

---

# 管理您的Customer Journey Analytics使用情況

>[!TIP]
>
>使用[**[!UICONTROL 使用狀況&#x200B;]**介面](/help/connections/manage-connections.md#usage)來**&#x200B;檢視&#x200B;**Customer Journey Analytics中所有連線之已擷取及可報告資料列的使用狀況。



您可以在[**[!UICONTROL 連線&#x200B;]**介面](/help/connections/create-connection.md)中管理您的Customer Journey Analytics使用情形。 在此介面中，您可以在連線層級將Customer Journey Analytics資料保留定義為單位為月數的滾動時段（1個月、3個月、6個月等）。

主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。 這有助於您未超過合約限制，並減少超額使用費用的風險。

如果您保留預設值 (未勾選)，保留期間將由 Adobe Experience Platform 資料保留設定取代。 如果您在Experience Platform中有25個月的資料，Customer Journey Analytics將透過回填取得25個月的資料。 如果您在 Platform 中刪除其中 10 個月的資料，Customer Journey Analytics 則會保留剩餘 15 個月的資料。

資料保留是以時間戳記為基礎，僅適用於事件資料集和摘要資料集。 由於無適用的時間戳記，因此輪廓或查詢資料集不存在滾動資料時間窗口設定。 如果您的連線包含任何設定檔或查詢資料集，由於它們與事件資料集連結，因此會根據事件資料集時間戳記上的資料保留設定，將資料保留在Customer Journey Analytics中。


>[!MORELIKETHIS]
>
>[檢視您的Customer Journey Analytics使用情形](/help/connections/manage-connections.md#usage)

