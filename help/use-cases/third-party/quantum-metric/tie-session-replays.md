---
title: 繫結量子量度工作階段重播至Customer Journey Analytics中的資料
description: 連結量度工作階段會重播CJA資料，以便更清楚瞭解「內容」背後的「原因」。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---

# 繫結量子量度工作階段重播至Customer Journey Analytics中的資料

連結Quantum量度工作階段重播與CJA資料，可讓客戶更瞭解「內容」背後的「原因」。  Workspace可用來探索摩擦的工作階段，然後您可以按一下超連結的工作階段ID，以探索「量度」中的工作階段重播。  此資料可讓您檢視工作階段中的行為，並更瞭解促使消費者發生摩擦的因素。  透過與CJA繫結的工作階段重播，您可以擷取有關您體驗中客戶行為的關鍵內容。

## 先決條件

這些步驟假設您使用Adobe Experience Platform資料彙集中的標籤。 如果您的組織未使用標籤，您可以將這些資料收集方法調整為手動Web SDK實施。

如需詳細資訊，請參閱[Quantum量度標籤延伸功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/catalog/analytics/quantum-metric)檔案。

## 步驟1：建立結構欄位以容納量度工作階段ID

此使用案例需要專用的結構描述欄位才能傳送資料。 您可以在結構描述中的任何所需位置建立此欄位，並隨意命名。 如果您的組織對名稱或地點沒有偏好設定，則會提供範例值。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 結構描述]**。
1. 從清單中選取所需的結構描述。
1. 選取所要物件旁的![新增欄點陣圖示](/help/assets/icons/AddCircle.svg)圖示。 例如，`Implementation Details`旁。
1. 在右側，輸入所需的[!UICONTROL 名稱]。 例如，`qmSessionId`。
1. 輸入所需的[!UICONTROL 顯示名稱]。 例如，`Quantum Metric session ID`。
1. 選取[!UICONTROL Type]作為&#x200B;**[!UICONTROL String]**。
1. 選取「**[!UICONTROL 儲存]**」。

## 步驟2：使用量度標籤擴充功能擷取Quantum量度工作階段ID

請依照下列步驟，將Quantum量度工作階段ID附加至您傳送至Adobe Experience Platform的資料。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。
1. 選取所需的標籤屬性。
1. 選取&#x200B;**[!UICONTROL 資料元素]**，然後選取&#x200B;**[!UICONTROL 新增資料元素]**。
1. 設定下列設定：
   * **[!UICONTROL 名稱]**： `Quantum Metric session ID`
   * **[!UICONTROL 延伸模組]**： [!UICONTROL 核心]
   * **[!UICONTROL 資料元素型別]**： [!UICONTROL 自訂程式碼]
1. 選取&#x200B;**[!UICONTROL 開啟編輯器]**&#x200B;按鈕，然後貼入下列程式碼：

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. 選取「**[!UICONTROL 儲存]**」。

## 步驟3：將資料元素對應至所需的XDM結構描述欄位

資料元素現在擁有取得所需值的邏輯，請將資料元素對應至XDM物件。

1. 在標籤屬性中，選取&#x200B;**[!UICONTROL 資料元素]**，然後選取用來容納XDM物件的資料元素。
1. 在此資料元素的右欄，導覽至建立結構欄位時建立的路徑。
1. 將值設為百分比符號包住的資料元素名稱。 例如，`%Quantum Metric session ID%`。
1. 選取「**[!UICONTROL 儲存]**」。
1. 新增程式庫，然後將變更發佈至生產環境。

如果您的XDM物件已包含在傳送事件動作設定中，則會在變更發佈後開始看到資料。

>[!NOTE]
>
>有時Web SDK的執行速度會比Quantum Metric程式碼更快。 在這些情況下，工作階段ID會在後續點選時傳送。 如果訪客跳出，則系統不會收集這些例項的工作階段ID。

## 步驟3：將Quantum量度工作階段ID新增為可用維度

您的實作發佈上述變更後，請編輯現有的資料檢視，將工作階段ID新增為Customer Journey Analytics中的可用維度。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL 資料檢視]**。
1. 選取所需的現有資料檢視。
1. 在左側找到「量度工作階段ID」欄位，並將其拖曳至中央的維度區域。
1. 在右窗格中，將[持續性](/help/data-views/component-settings/persistence.md)設定設為`Session`。
1. 選取「**[!UICONTROL 儲存]**」。

## 步驟4：設定Analysis Workspace以容納工作階段ID維度

在Workspace中建立自由表格，並進行設定，以便工作階段ID值直接連結至Quantum量度。

1. 登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至Customer Journey Analytics，然後在頂端功能表中選取&#x200B;**[!UICONTROL Workspace]**。
1. 選取現有專案，或建立專案。
1. 建立[自由格式表格](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
1. 將「工作階段ID」維度拖曳至Workspace畫布。
1. 以滑鼠右鍵按一下維度資料行標題，然後選取&#x200B;**[!UICONTROL 為所有維度專案建立超連結]**。
1. 選取&#x200B;**[!UICONTROL 建立自訂URL]**。
1. 貼上下列URL結構：

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 按一下「**[!UICONTROL 建立]**」。

每個工作階段ID現在都是可點按的連結。 如需新增超連結至Analysis Workspace維度專案的詳細資訊，請參閱[在自由格式表格中建立超連結](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。

![工作階段重播](assets/session-replay.png)

## 步驟5：從Customer Journey Analytics檢視工作階段

在您找到想要探索工作階段重播的有趣區段後，可將其套用至包含工作階段ID連結的面板。 此表格會傳回該區段中的所有工作階段，您可以按一下任一工作階段，進一步探索Quantum量度。

如需詳細資訊，請參閱[Quantum量度上的工作階段重播企業指南](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay)。 您也可以連絡您的Quantum Metric客戶支援代表，或透過[Quantum Metric客戶請求入口網站](https://community.quantummetric.com/s/public-support-page)提交請求。
