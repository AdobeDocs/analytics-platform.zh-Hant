---
title: 跨管道歷程分析
description: 從整個客戶歷程的客戶互動中，分析及擷取見解。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 61%

---

# 跨頻道分析

跨管道分析可透過統一來自各種網路、行動和離線屬性的資料，啟用跨不同管道的客戶行為單一整合檢視。 例如，您可以使用此整合檢視來分析跨桌面和行動裝置的客戶互動，以了解客戶行為並提取洞察以最佳化數位客戶體驗。您還可以分析跨管道的客戶互動，包括數位和離線管道，例如支援互動和店內購買，以更好地了解和最佳化客戶旅程。

## 實施步驟

![實作步驟的流程，如本節所述。](../assets/cca-architecture.png)

1. 為要擷取的資料[建立結構描述](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)。
1. 為要擷取的資料[建立資料集](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html)。
1. [將資料內嵌至Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html)：
   1. 透過Edge Network或Analytics來源聯結器，從網站或行動應用程式取得事件型資料![事件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg)。
   2. 設定檔資料![設定檔](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) （例如，來自CRM系統、客服中心應用程式、忠誠度應用程式）。
   3. 查詢資料![查詢](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) （例如產品名稱、產品資訊系統中的類別）。

1. 跨資料集使用通用名稱空間ID。 使用[拼接](../../stitching/overview.md)提升任何事件型資料集![資料重新整理](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg)，以便在每一列提供通用ID。 請注意，Customer Journey Analytics 目前不使用 Experience Platform 設定檔或身份識別服務進行拼接。
1. 執行任何自訂資料準備，以確保跨時間序列資料集的公用鍵被引入 Customer Journey Analytics。
1. 為查閱資料提供一個可以連結到事件資料中欄位的主要 ID。計為授權中的列。
1. 將設定檔資料的主要 ID 設定為事件資料的主要 ID。
1. [建立連線](../../connections/overview.md)以將相關的資料集從Experience Platform擷取到Customer Journey Analytics。
1. 在連線上[建立資料檢視](/help/data-views/create-dataview.md)以選擇要包含在檢視中的特定維度和量度。歸因和配置設定也在資料檢視中設定。這些設定是在報告時計算的。
1. [建立專案](/help/analysis-workspace/home.md)以在Analysis Workspace中設定儀表板和報表。

## 考量事項

建立此工作流程時，請務必考慮以下幾點。

* 跨通道分析資料要求每個記錄具有相同的 ID 命名空間。
* 統一不同資料集的聯合過程需要跨資料集的共同主要人員/實體鍵。
* 目前不支援根據次要鍵的聯合。
* 拼接過程允許根據共用相同永久ID的記錄中的暫時ID （例如驗證ID）資訊，重新輸入列中的身分。這允許將不同的記錄解析為單一拼接ID，以便在人員層級，而不是裝置或Cookie層級進行分析。
* 同一 XDM 欄位的物件和屬性合併為 Customer Journey Analytics 中的一個維度。要將來自不同資料集的多個屬性合併到同一個 Customer Journey Analytics 維度中，資料集應該引用相同的 XDM 欄位或結構描述。

