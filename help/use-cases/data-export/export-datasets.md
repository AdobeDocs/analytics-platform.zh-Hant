---
title: Customer Journey Analytics匯出資料集
description: 說明如何使用匯出資料集來備份您的資料。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 19018e31bb2a46e88a27643fe10c388b40de243e
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 1%

---


# 匯出資料集

本文概述了 [!DNL Customer Journey Analytics Export datasets] 可用來實作下列專案 [資料匯出使用案例](overview.md)：

- 資料備份

## 簡介

匯出資料，使用 [!DNL Experience Platform Export datasets] 可讓您將資料從Customer Journey Analytics資料檢視匯出至任何雲端儲存空間目的地。

![BI副檔名](../assets/export-datasets.svg)

## 詳細資訊

您可以從Experience Platform中的資料湖將原始資料集匯出至雲端儲存目標。 此匯出位於「Experience Platform目的地」術語中，稱為「資料集匯出目的地」。 另請參閱 [將資料集匯出至雲端儲存空間目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) 以取得概覽。

支援下列雲端儲存空間目的地：

- [Azure Data Lake Storage Gen2](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/adls-gen2)
- [資料登陸區域](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/data-landing-zone)
- [Google雲端儲存空間](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/google-cloud-storage)
- [Amazon S3](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/amazon-s3#changelog)
- [Azure Blob](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/azure-blob#changelog)
- [SFTP](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/cloud-storage/sftp#changelog)


### EXPERIENCE PLATFORMUI

您可以透過Experience Platform UI匯出及排程資料集的匯出。 本節將說明相關步驟。

#### 選取目的地

當您決定要將資料集匯出到的雲端儲存空間目的地時， [選取目的地](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-destination). 如果您尚未設定偏好雲端儲存空間的目的地，您必須 [建立新的目的地連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination).

在設定目的地時，您可以定義：

- 檔案型別（JSON或Parquet）、
- 產生的檔案是否應該壓縮，以及
- 是否應該包含資訊清單檔案。


#### 選取資料集

當您選取目的地時，在下一個 **[!UICONTROL 選取資料集]** 您必須從資料集清單中選取資料集的步驟。 如果您已建立多個排程查詢，且希望資料集傳送至相同的雲端儲存空間目的地，則可選取對應的資料集。 另請參閱 [選取您的資料集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#select-datasets) 以取得詳細資訊。

#### 排程資料集匯出

最後，您想要將資料集匯出排程為 **[!UICONTROL 正在排程]** 步驟。 在該步驟中，您可以定義排程，以及資料集匯出是否應為增量式的。 另請參閱 [排程資料集匯出](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#scheduling) 以取得詳細資訊。


#### 最後步驟

[檢閱](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#review) 您的選取範圍並在正確後，開始將資料集匯出至雲端儲存空間目的地。

首先，您必須 [驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 資料匯出成功。 匯出資料集時，Experience Platform會建立一或多個 `.json` 或 `.parquet` 存放位置中定義的檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。

### 流程服務API

或者，您可以使用API匯出及排程資料集的匯出。 相關步驟的記錄於 [使用流量服務API匯出資料集](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets).

#### 開始使用

若要匯出資料集，請確定您已 [必要許可權](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#permissions). 同時確認您要傳送資料集的目的地支援匯出資料集。 然後，您必須 [收集必要和選用標題的值](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-values-headers) 用於API呼叫的內容。 您也需要 [識別目的地的連線規格和流程規格ID](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#gather-connection-spec-flow-spec) 您打算將資料集匯出至。

#### 擷取合格的資料集

您可以 [擷取合格資料集的清單](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#retrieve-list-of-available-datasets) 使用，驗證您的資料集是否屬於該清單 [`GET /connectionSpecs/{id}/configs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Configurations/operation/getDatasets) API。


#### 建立來源連線

接下來，您必須 [建立來源連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-source-connection) 針對您要匯出至雲端儲存空間目的地的資料集（使用其唯一ID）。 您使用 [`POST /sourceConnections`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Source-connections/operation/postSourceConnection) API。

#### 驗證到目的地（建立基礎連線）

您現在必須 [建立基礎連線](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-base-connection) 使用驗證並安全地儲存認證至您的雲端儲存空間目的地 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。


#### 提供匯出引數

接下來，您必須 [建立其他目標連線來儲存匯出引數](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-target-connection) 針對您的資料集，再次使用 [`POST /targetConection`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Target-connections/operation/postTargetConnection) API。 這些匯出引數包括位置、檔案格式、壓縮等等。

#### 設定資料流

最後，您 [設定資料流](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#create-dataflow) 以確保您的資料集已使用，匯出至雲端儲存空間目的地 [`POST /flows`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflows/operation/postFlow) API。 在此步驟中，您可以使用來定義匯出排程 `scheduleParams` 引數。

#### 驗證資料流

至 [檢查資料流的成功執行](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/api/export-datasets#get-dataflow-runs)，使用 [`GET /runs`](https://developer.adobe.com/experience-platform-apis/references/destinations/#tag/Dataflow-runs/operation/getFlowRuns) API，將資料流ID指定為查詢引數。 此資料流ID是您設定資料流時傳回的識別碼。

[驗證](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets#verify) 資料匯出成功。 匯出資料集時，Experience Platform會建立一或多個 `.json` 或 `.parquet` 存放位置中定義的檔案。 預期會根據您設定的匯出排程，將新檔案儲存在您的儲存位置。 Experience Platform會在您指定為所選目的地一部分的儲存位置中建立資料夾結構，並存放匯出的檔案。 每次匯出時都會建立一個新資料夾，其模式如下： `folder-name-you-provided/datasetID/exportTime=YYYYMMDDHHMM`. 預設檔案名稱是隨機產生的，並確保匯出的檔案名稱是唯一的。
