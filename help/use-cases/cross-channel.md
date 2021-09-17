---
title: 跨管道歷程分析
description: 從整個客戶歷程的客戶互動中，分析及擷取見解。
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# 跨管道歷程分析

透過統一各種網路、行動裝置和離線屬性的資料，以單一的整合檢視不同管道的客戶行為。 例如，您可以使用此整合檢視來分析案頭和行動裝置間的客戶互動，以了解客戶行為並擷取深入分析，以最佳化數位客戶體驗。 您也可以分析各管道的客戶互動，包括數位和離線管道，例如支援互動和店內購買，以便更清楚了解並最佳化客戶歷程。

## 架構

![跨通道架構](assets/cross-channel-architecture.svg)

## 實施步驟

1. [建立](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant) 要擷取資料的架構。
1. [為要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) 擷取的資料建立資料集。
1. [將資料內嵌至 Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. 跨資料集使用通用的命名空間ID，或使用[跨管道分析](/help/connections/cca/overview.md)將人員連結在一起。 請注意，Customer Journey Analytics目前不使用Experience Platform設定檔或Identity服務來匯整。
1. 執行任何自訂資料準備，以確保將時間序列資料集的共同索引鍵內嵌至Customer Journey Analytics。
1. 為查詢資料指定可連結至事件資料欄位的主要ID。 在授權中計為列。
1. 設定設定檔資料的主要ID與事件資料的主要ID相同。
1. 設定資料連線，將資料從Experience Platform內嵌至Customer Journey Analytics。
1. [建立連線](/help/data-views/create-dataview.md) 上的資料檢視，以選取要納入檢視中的特定維度和量度。歸因和配置設定也可在資料檢視中設定。 這些設定會在報告時計算。
1. 建立專案以在Analysis Workspace中設定控制面板和報表。

## 考量事項

建立此工作流程時，請務必考量下列幾點。

* 跨管道分析資料時，每個記錄都需要相同的ID命名空間。
* 統一不同資料集的聯合程式需要資料集中有共同的主要人員/實體索引鍵。
* 目前不支援次要密鑰型聯合。
* 依欄位的身分拼接程式允許根據後續的暫時ID記錄（例如驗證ID），對列中的身分重設金鑰。 這可將不同的記錄解析為單一ID，以便在人員層級（而非裝置或Cookie層級）進行分析。
* 相同XDM欄位的物件和屬性會合併為一個Customer Journey Analytics中的維度。 若要將多個資料集的多個屬性合併至相同的Customer Journey Analytics維度，資料集應參考相同的XDM欄位或結構。
