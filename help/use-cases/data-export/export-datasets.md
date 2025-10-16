---
title: Customer Journey Analytics匯出資料集
description: 說明如何使用匯出資料集來備份您的資料。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: b861f765-b18d-4be2-b4c7-c66186d37d99
source-git-commit: 9fef1fddbb4b51efb9282e3ef13501bd498a4546
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 2%

---

# 匯出資料集

本文概述如何使用[!DNL Customer Journey Analytics Export datasets]實作下列[資料匯出使用案例](overview.md)：

- 資料備份

## 簡介

使用[!DNL Experience Platform Export datasets]匯出資料可讓您將資料從Customer Journey Analytics資料檢視匯出至任何雲端儲存體目的地。

![BI延伸模組](../assets/export-datasets.svg)

## 詳細資訊

您可以從Experience Platform中的資料湖將原始資料集匯出至雲端儲存目標。 此匯出位於Experience Platform目的地術語中，稱為資料集匯出目的地。 請參閱[將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/ui/activate/export-datasets)以取得概觀。

支援以下雲端儲存空間目標：

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [資料登陸區域](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google雲端儲存空間](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORM UI

您可以透過Experience Platform UI匯出及排程資料集的匯出。 本節將說明相關步驟。

#### 選取目的地

當您決定要將資料集匯出到的雲端儲存空間目的地時，[請選取目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination)。 當您尚未設定慣用雲端儲存空間的目的地時，您必須[建立新的目的地連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination)。

在設定目的地時，您可以定義：

- 檔案型別（JSON或Parquet）、
- 產生的檔案是否應該壓縮，以及
- 是否應該包含資訊清單檔案。


#### 選取資料集

當您選取目的地後，在下一個&#x200B;**[!UICONTROL 選取資料集]**&#x200B;步驟中，您必須從資料集清單中選取您的資料集。 如果您已建立多個排程查詢，且希望資料集傳送至相同的雲端儲存空間目的地，則可選取對應的資料集。 如需詳細資訊，請參閱[選取您的資料集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets)。

#### 排程資料集匯出

最後，您想要排程資料集匯出，作為&#x200B;**[!UICONTROL 排程]**&#x200B;步驟的一部分。 在該步驟中，您可以定義排程，以及資料集匯出是否應為增量式的。 如需詳細資訊，請參閱[排程資料集匯出](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling)。


#### 最後步驟

[檢閱](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review)您的選取專案，並在正確後，開始將資料集匯出至雲端儲存空間目的地。

首先，您必須[驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)資料匯出成功。 匯出資料集時，Experience Platform會在目的地中定義的儲存位置中建立一或多個`.json`或`.parquet`檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立檔案夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

### 流程服務API

或者，您可以使用API匯出及排程資料集的匯出。 有關步驟已記錄在[使用流程服務API](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets)匯出資料集內。

#### 開始使用

若要匯出資料集，請確定您具有[必要的許可權](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions)。 同時確認您要傳送資料集的目的地支援匯出資料集。 然後，您必須[收集您在API呼叫中使用的必要和選用標頭](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers)的值。 您也需要[識別您要將資料集匯出至的目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec)的連線規格和流量規格ID。

#### 擷取合格的資料集

您可以[擷取符合匯出條件的資料集清單](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets)，並使用[`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API來驗證您的資料集是否屬於該清單。


#### 建立來源連線

接下來，您必須使用資料集的唯一ID，為要匯出至雲端儲存空間目的地的資料集[建立來源連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection)。 您使用[`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 驗證到目的地（建立基礎連線）

您現在必須[建立基礎連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection)，以使用[`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API驗證並安全地儲存認證至您的雲端儲存空間目的地。


#### 提供匯出引數

接下來，您必須[建立其他目標連線，再次使用](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) [`POST /targetConection` API為您的資料集儲存匯出引數](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection)。 這些匯出引數包括位置、檔案格式、壓縮等等。

#### 設定資料流

最後，您[設定資料流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow)，以確保您的資料集已使用[`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API匯出至雲端儲存空間目的地。 在此步驟中，您可以使用`scheduleParams`引數定義匯出排程。

#### 驗證資料流

若要[檢查資料流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)的成功執行，請使用[`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，將資料流ID指定為查詢引數。 此資料流ID是您設定資料流時傳回的識別碼。

[驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify)資料匯出成功。 匯出資料集時，Experience Platform會在目的地中定義的儲存位置中建立一或多個`.json`或`.parquet`檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立檔案夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`。 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。
