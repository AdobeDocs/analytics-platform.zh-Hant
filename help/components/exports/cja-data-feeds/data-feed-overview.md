---
description: 瞭解如何使用資料摘要從Customer Journey Analytics中取得原始資料。 了解使用資料摘要的先決條件以及接下來該做的步驟。
keywords: 點按資料流;資料摘要;資料摘要;資料摘要
title: Analytics 資料摘要概觀
feature: Components
hide: true
hidefromtoc: true
source-git-commit: b0b86424399ea79deca8f1d522d52354dfaaa8c7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 40%

---

# 資料摘要概觀

資料摘要是從Customer Journey Analytics中取得原始資料的有力方式。 這類原始資料可用於 Adobe 以外的其他平台，供組織任意使用。資料會在每小時結束時以小時的批次傳送，或在每天結束時以當天的批次傳送。

## 先決條件

在使用資料摘要之前，請確認您符合下列所有需求。

* 具有擷取至Adobe Customer Journey Analytics之資料的有效實作。<!-- For more information, see Data ingestion overview - add link -->
* 您的帳戶為Analytics產品管理員，或屬於可存取資料摘要的產品設定檔。<!--???-->
* 在Amazon S3、Google Cloud Platform、Azure RBAC或Azure SAS上設定的貯體。<!--Which cloud providers do we support??-->
* （舊版：只有舊版FTP和SFTP目的地型別才需要）有可用的FTP站台和認證（您的組織提供的FTP認證）。<!--Delete???-->

## 比較Customer Journey Analytics和Adobe Analytics中的資料摘要

Customer Journey Analytics中的資料摘要功能與Adobe Analytics不同。 如需詳細資訊，請參閱[比較Customer Journey Analytics和Adobe Analytics中的資料摘要](/help/components/exports/cja-data-feeds/df-comparison.md)。


## 後續步驟

以下資源可幫助您了解取得資料摘要的基本工作流程。了解基本工作流程之後，您就可以與組織內的團隊合作，將原始資料儲存或收錄至資料庫。

* 資料摘要最佳實務<!--add link-->：建立和管理資料摘要的最佳實務。
* 建立資料摘要<!--add link-->：建立資料摘要的技術詳細資訊，詳細說明個別欄位
* 管理資料摘要<!--add link-->：進一步瞭解如何導覽資料摘要介面
* 資料摘要內容<!--add link-->：了解壓縮檔案<!-- Is this still the output users can download from the destination? I aske Jun. -->中的內容
* 資料欄定義<!--add link-->：所有可用欄的完整清單。

>[!BEGINSHADEBOX]

請參閱![影片簽出](/help/assets/icons/VideoCheckedOut.svg) [導覽至資料摘要介面](https://video.tv.adobe.com/v/3428570?captions=chi_hant&quality=12&learn=on){target="_blank"}，以觀看示範影片。

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

請參閱![影片簽出](/help/assets/icons/VideoCheckedOut.svg) [尋找您的資料摘要 ID](https://video.tv.adobe.com/v/3480890?captions=chi_hant&quality=12&learn=on){target="_blank"}，以觀看示範影片。

>[!ENDSHADEBOX]
