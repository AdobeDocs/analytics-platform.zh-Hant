---
title: 使用標籤來實作用於Customer Journey Analytics的Web SDK
description: 瞭解如何使用標籤來實作用於Customer Journey Analytics的Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 76%

---

# 使用標籤來實作用於Customer Journey Analytics的Web SDK

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

您可以使用Adobe Experience Platform中的標籤功能，在您的網站上實作程式碼以收集資料。 此標記管理解決方案可讓您部署程式碼以及其他標記需求。 標籤可使用 Adobe Experience Platform Web SDK 擴充功能與 Adobe Experience Platform 緊密整合。

## 建立標籤

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取[!UICONTROL 「資料收集」]中的&#x200B;**[!UICONTROL 「標籤」]**。

2. 選取&#x200B;**[!UICONTROL 「新屬性」]**。

   為標籤命名，選取 **[!UICONTROL Web]** 並輸入域名。選取&#x200B;**[!UICONTROL 「儲存」]**&#x200B;以繼續。

   ![建立屬性](assets/create-property.png)

## 設定您的標籤

建立標籤後，您必須使用正確的擴充功能加以設定，並根據您要追蹤網站及傳送資料至Adobe Experience Platform的方式，設定資料元素和規則。

從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。


### **擴充功能**

為確保您能傳送資料至Adobe Experience Platform （透過資料流），請將Adobe Platform Web SDK擴充功能新增至您的標籤。

若要建立及設定 Adobe Experience Platform Web SDK 擴充功能：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「擴充功能」]**。

1. 在頂端列中選取 **[!UICONTROL 「目錄」]**。

1. 搜尋或捲動至 Adobe Experience Platform Web SDK 擴充功能，然後選取&#x200B;**[!UICONTROL 「安裝」]**&#x200B;以進行安裝。

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. 為您的[!UICONTROL 生產環境]和 (可選) [!UICONTROL 中繼環境]以及[!UICONTROL 開發環境]選取您的沙箱和先前建立的資料流。

   ![AEP Web SDK 擴充功能設定](assets/aepwebsk-extension-datastreams.png)

   選取&#x200B;**[!UICONTROL 「儲存」]**。

如需詳細資訊，請參閱[設定 Adobe Experience Platform Web SDK 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html)。

Web SDK原生包含[!UICONTROL Adobe Experience Cloud ID服務]，因此您不需要將ID服務擴充功能新增至標籤。

### **資料元素**

資料元素是資料字典 (或資料地圖) 的建置組塊。使用資料元素，在行銷和廣告技術之間收集、組織和傳遞資料。您可在標籤中設定從資料層讀取的資料元素，可用來將資料傳送至 Adobe Experience Platform。

資料元素的類型不同。您先設定資料元素，擷取訪客在您的網站上檢視的頁面名稱。

若要定義頁面名稱資料元素：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

2. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

3. 在[!UICONTROL 「新增資料元素」]對話框中：

   - 為您的資料元素命名，例如 `Page Name`。

   - 從&#x200B;**[!UICONTROL 「擴充功能」]**&#x200B;清單中選取[!UICONTROL 「核心」]。

   - 從[!UICONTROL 「資料元素類型」]清單中選取&#x200B;**[!UICONTROL 「頁面資訊」]**。

   - 從[!UICONTROL 「屬性」]清單中選取&#x200B;**[!UICONTROL 「標題」]**。

     ![使用頁面資訊建立資料元素](assets/create-dataelement-1.png)

     或者，您也可以使用資料層變數的值，例如`pageName`和 [!UICONTROL JavaScript 變數] 資料元素類型來定義該資料元素。

     ![使用 JavaScript 變數建立資料元素](assets/create-dataelement-2.png)

   - 選取&#x200B;**[!UICONTROL 「儲存」]**。

您現在想要設定資料元素，以參考由 Adobe Experience Platform Web SDK 自動提供且可透過 Experience Cloud ID 服務擴充功能使用的Experience Cloud ID。

若要定義 ECID 資料元素：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

2. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

3. 在[!UICONTROL 「新增資料元素」]對話框中：

   - 為您的資料元素命名，例如 `ECID`。

   - 從[!UICONTROL 「擴充功能」]清單中選取&#x200B;**[!UICONTROL 「Experience Cloud ID 服務」]**。

   - 從[!UICONTROL 「資料元素類型」]清單中選取 **[!UICONTROL ECID]**。

     ![ECID 資料元素](assets/ecid-dataelement.png)

   - 選取&#x200B;**[!UICONTROL 「儲存」]**。

最後，您現在想要將任何特定資料元素對應至先前定義的結構。您可以定義另一個資料元素，以呈現 XDM 結構。

若要定義 XDM 物件資料元素：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

2. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

3. 在[!UICONTROL 「新增資料元素」]對話框中：

   - 為您的資料元素命名，例如 `XDM - Page View`。

   - 從[!UICONTROL 「擴充功能」]清單中選取&#x200B;**[!UICONTROL 「Adobe Experience Platform Web SDK」]**。

   - 從[!UICONTROL 「資料元素類型」]清單中選取&#x200B;**[!UICONTROL 「XDM 物件」]**。

   - 從[!UICONTROL 「沙箱」]清單中選取您的沙箱。

   - 從[!UICONTROL 「結構」]清單中選取您的結構。

   - 將您的結構中定義的 `identification > core > ecid`屬性對應至 ECID 資料元素。選取圓柱體圖示，即可輕鬆從資料元素清單中挑選 ECID 資料元素。

     ![挑選 ECID 資料元素](assets/pick-ecid-dataelement.png)

     ![對應 ECID 資料元素](assets/map-ecid.png)


   - 將您的結構中定義的 `web > webPageDetails > name`屬性對應至頁面名稱資料元素。

     ![對應頁面名稱元素](assets/map-pagename.png)

   - 選取&#x200B;**[!UICONTROL 「儲存」]**。


### **規則**

Adobe Experience Platform 中的標籤會遵循規則型系統。它們會尋找使用者互動與相關資料。當符合列於您規則中的準則時，規則會觸發您識別的擴充功能、指令碼或用戶端代碼。您可以使用規則，透過 Adobe Experience Platform Web SDK 擴充功能將資料 (例如 XDM 物件) 傳送至 Adobe Experience Platform。

定義規則：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「規則」]**。

1. 選取&#x200B;**[!UICONTROL 「建立新規則」]**。

1. 在[!UICONTROL 「建立規則」]對話框：

   - 為規則命名，例如 `Page View`。

   - 在[!UICONTROL 「事件」]下選取&#x200B;**[!UICONTROL 「+ 新增」]**。

   - 在[!UICONTROL 「事件設定」]對話框：

      - 從&#x200B;**[!UICONTROL 「擴充功能」]**&#x200B;清單中選取[!UICONTROL 「核心」]。

      - 從[!UICONTROL 「事件類型」]清單中選取&#x200B;**[!UICONTROL 「視窗已載入」]**。

        ![規則 – 事件設定](assets/event-windowloaded-pageview.png)

      - 選取&#x200B;**[!UICONTROL 「保留變更」]**。



   - 在[!UICONTROL 「動作」]下方選取&#x200B;**[!UICONTROL 「+ 新增」]**。

   - 在[!UICONTROL 動作設定] 對話框：

      - 從[!UICONTROL 「擴充功能」]清單中選取&#x200B;**[!UICONTROL 「Adobe Experience Platform Web SDK」]**。

      - 從[!UICONTROL 「動作類型」]清單中選取&#x200B;**[!UICONTROL 「傳送事件」]**。

      - 從[!UICONTROL 「類型」]清單中選取&#x200B;**[!UICONTROL 「web.webpagedetails.pageViews」]**。

      - 選取[!UICONTROL 「XDM 資料」]旁的圓柱體圖示，然後從資料元素清單中選擇&#x200B;**[!UICONTROL 「XDM – 頁面檢視」]**。

     ![規則 – 動作設定](assets/action-pageview-xdm.png)

      - 選取&#x200B;**[!UICONTROL 「保留變更」]**。

   - 您的規則應如下所示：

     ![建立規則](assets/rule-pageview.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

以上只是定義規則的範例，此規則會將XDM資料（包含來自其他資料元素的值）傳送至Adobe Experience Platform。

您可以在標籤中以各種方式使用規則來操控變數 (使用您的資料元素)。

如需詳細資訊，請參閱[規則](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html)。

## 建置並發佈您的標籤

定義資料元素和規則後，您必須建置並發佈標籤。 建立程式庫組建時，必須將其指派至一個環境。隨後組建的擴充功能、規則和資料元素會經過編譯，並放入指派的環境中。每個環境都會提供唯一的內嵌程式碼，可讓您將指派的組建整合至您的網站。

若要建置並發佈您的標籤：

1. 從左側邊欄中選取&#x200B;**[!UICONTROL 「發佈流程」]**。

2. 選取&#x200B;**[!UICONTROL 「選擇工作程式庫」]**，然後選取&#x200B;**[!UICONTROL 「新增程式庫…」]**。

3. 在[!UICONTROL 「建立程式庫」]對話框：

   - 為程式庫命名。

   - 從&#x200B;**[!UICONTROL 「環境」]**&#x200B;清單中選取[!UICONTROL 「開發 (開發)」]。

   - 選取&#x200B;**[!UICONTROL 「+ 新增所有變更的資源」]**。

     ![發佈–建立程式庫](assets/create-library-aep.png)

   - 選取&#x200B;**[!UICONTROL 「儲存並建置至開發」]**。

   您的標籤已儲存並為您的開發環境建置。 綠色圓點表示在開發環境中成功建置標籤。

4. 您可以選取&#x200B;**[!UICONTROL 「...」]**&#x200B;來重建程式庫或將程式庫移至中繼環境或生產環境。

   ![發佈 – 建置資料庫](assets/build-library.png)

Adobe Experience Platform 標籤支援簡單到複雜的發佈工作流程，以配合您部署 Adobe Experience Platform Web SDK。

如需詳細資訊，請參閱[發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant)。


## 擷取您的標籤程式碼

最後，您必須在要追蹤的網站上安裝標籤，這表示會將程式碼放置在網站範本的標頭標籤中。

若要取得參考標籤的程式碼：

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「環境」]**。

1. 從環境清單中，選取正確的安裝 (框) 按鈕。

   在[!UICONTROL 「Web 安裝指示」]對話框中，選取指令碼旁的複製按鈕，如下所示：

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![環境](assets/environment.png)

1. 選取&#x200B;**[!UICONTROL 「關閉」]**。

   您可以根據您部署 Adobe Experience Platform Web SDK 的流程，選取其他環境 (中繼、生產)，而非開發環境的程式碼。

   如需詳細資訊，請參閱[環境](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?)。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
