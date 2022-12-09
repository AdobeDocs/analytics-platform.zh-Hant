---
title: 跨管道歷程分析
description: 從整個客戶歷程的客戶互動中，分析及擷取見解。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---

# 跨管道歷程分析

透過統一來自各種網路、行動和離線資產的資料，跨各種管道獲得客戶行為的單一整合檢視。例如，您可以使用此整合檢視來分析跨桌面和行動裝置的客戶互動，以了解客戶行為並提取洞察以最佳化數位客戶體驗。您還可以分析跨管道的客戶互動，包括數位和離線管道，例如支援互動和店內購買，以更好地了解和最佳化客戶旅程。

## 架構

![跨管道架構](../assets/cross-channel-architecture.svg)

## 實施步驟

1. 為要擷取的資料[建立結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)。
1. 為要擷取的資料[建立資料集](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html)。
1. [將資料擷取至 Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html)。
1. 跨資料集使用通用命名空間 ID，或使用[跨管道分析](/help/connections/cca/overview.md)將人們連結在一起。請注意，Customer Journey Analytics 目前不使用 Experience Platform 設定檔或身份識別服務進行拼接。
1. 執行任何自訂資料準備，以確保跨時間序列資料集的公用鍵被引入 Customer Journey Analytics。
1. 為查閱資料提供一個可以連結到事件資料中欄位的主要 ID。計為授權中的列。
1. 將設定檔資料的主要 ID 設定為事件資料的主要 ID。
1. 設定資料連線以將資料從 Experience Platform 擷取到 Customer Journey Analytics。
1. 在連線上[建立資料檢視](/help/data-views/create-dataview.md)以選擇要包含在檢視中的特定維度和量度。歸因和配置設定也在資料檢視中設定。這些設定是在報告時計算的。
1. 建立專案，以在 Analysis Workspace 中設定儀表板和報告。

## 考量事項

建立此工作流程時，請務必考慮以下幾點。

* 跨通道分析資料要求每個記錄具有相同的 ID 命名空間。
* 統一不同資料集的聯合過程需要跨資料集的共同主要人員/實體鍵。
* 目前不支援根據次要鍵的聯合。
* 根據欄位的身份拼接過程允許根據後續臨時 ID 記錄（例如身份驗證 ID）重新鍵入列中的身份。這允許將不同的記錄解析為單個 ID，以便在人員層級而不是裝置或 cookie 層級進行分析。
* 同一 XDM 欄位的物件和屬性合併為 Customer Journey Analytics 中的一個維度。要將來自不同資料集的多個屬性合併到同一個 Customer Journey Analytics 維度中，資料集應該引用相同的 XDM 欄位或結構描述。
