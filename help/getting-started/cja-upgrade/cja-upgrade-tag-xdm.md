---
title: 將XDM資料收集邏輯新增至您的標籤
description: 瞭解如何將XDM資料收集邏輯新增至您的標籤
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: ccc6df56771cd9f83bbd7a8570e32d7ed63a0ced
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 48%

---

# 將XDM資料收集邏輯新增至您的標籤

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

在[建立標籤並新增Web SDK擴充功能](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)後，您必須根據您想要追蹤網站及傳送資料至Adobe Experience Platform的方式，使用資料元素和規則來設定標籤。 為標籤設定資料元素和規則後，您就可以建置並發佈標籤。

## 設定資料元素

資料元素是資料字典 (或資料地圖) 的建置組塊。使用資料元素，在行銷和廣告技術之間收集、組織和傳遞資料。您可在標籤中設定從資料層讀取的資料元素，可用來將資料傳送至 Adobe Experience Platform。

資料元素的類型不同。首先，設定資料元素以擷取訪客在您的網站上檢視的頁面名稱。 然後，設定參照Experience CloudID的資料元素。 最後，定義XDM物件資料元素。

### 頁面名稱資料元素

若要定義頁面名稱資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在[!UICONTROL 建立資料元素]對話方塊中，指定下列資訊：

   * **[!UICONTROL Name]**：資料元素的名稱。 例如 `Page Name`。

   * **[!UICONTROL 延伸模組]**：從清單中選取&#x200B;**[!UICONTROL 核心]**。

   * **[!UICONTROL 資料元素型別]**：從清單中選取&#x200B;**[!UICONTROL 頁面資訊]**。

   * **[!UICONTROL 屬性]**：從清單中選取&#x200B;**[!UICONTROL 標題]**。

     ![使用頁面資訊建立資料元素](assets/create-dataelement-1.png)

     或者，您也可以使用資料層變數的值，例如`pageName`和 [!UICONTROL JavaScript 變數] 資料元素類型來定義該資料元素。

     ![使用 JavaScript 變數建立資料元素](assets/create-dataelement-2.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   您現在想要設定資料元素，以參考由 Adobe Experience Platform Web SDK 自動提供且可透過 Experience Cloud ID 服務擴充功能使用的Experience Cloud ID。

1. 繼續使用[ECID資料元素](#ecid-data-element)。

### ECID資料元素

若要定義 ECID 資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在[!UICONTROL 建立資料元素]對話方塊中，指定下列資訊：

   * **[!UICONTROL Name]**：資料元素的名稱。 例如 `ECID`。

   * **[!UICONTROL 延伸模組]**：從清單中選取&#x200B;**[!UICONTROL Experience Cloud識別碼服務]**。

   * **[!UICONTROL 資料元素型別]**：從清單中選取&#x200B;**[!UICONTROL ECID]**。

     ![ECID 資料元素](assets/ecid-dataelement.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續使用[XDM物件資料元素](#xdm-object-data-element)。

### XDM物件資料元素

最後，您現在想要將任何特定資料元素對應至先前定義的結構。您可以定義另一個資料元素，以呈現 XDM 結構。

若要定義 XDM 物件資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在[!UICONTROL 建立資料元素]對話方塊中，指定下列資訊：

   * **[!UICONTROL Name]**：資料元素的名稱。 例如 `XDM - Page View`。

   * **[!UICONTROL 擴充功能]**：從清單中選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

   * **[!UICONTROL 資料元素型別]**：從清單中選取&#x200B;**[!UICONTROL XDM物件]**。

   * **[!UICONTROL 沙箱]**：從清單中選取您的沙箱。

   * **[!UICONTROL 結構描述]**：從清單中選取您的結構描述。

1. 將您的結構中定義的 `identification > core > ecid`屬性對應至 ECID 資料元素。選取圓柱體圖示，即可輕鬆從資料元素清單中挑選 ECID 資料元素。

   ![挑選 ECID 資料元素](assets/pick-ecid-dataelement.png)

   ![對應 ECID 資料元素](assets/map-ecid.png)


1. 將您的結構中定義的 `web > webPageDetails > name`屬性對應至頁面名稱資料元素。

   ![對應頁面名稱元素](assets/map-pagename.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續[設定規則](#configure-rules)。

## **設定規則**

Adobe Experience Platform 中的標籤會遵循規則型系統。它們會尋找使用者互動與相關資料。當符合列於您規則中的準則時，規則會觸發您識別的擴充功能、指令碼或用戶端代碼。您可以使用規則，透過 Adobe Experience Platform Web SDK 擴充功能將資料 (例如 XDM 物件) 傳送至 Adobe Experience Platform。

定義規則：

>[!NOTE]
>
>下列步驟是定義規則的範例，此規則會將包含其他資料元素值的XDM資料傳送至Adobe Experience Platform。
>
>您可以在標籤中以各種方式使用規則來操控變數 (使用您的資料元素)。
>
>如需詳細資訊，請參閱[規則](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html)。

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「規則」]**。

1. 選取&#x200B;**[!UICONTROL 「建立新規則」]**。

1. 在[!UICONTROL 建立規則]對話方塊中，指定下列資訊：

   * **[!UICONTROL 名稱]**：規則的名稱。 例如 `Page View`。

   * **[!UICONTROL 事件]**：選取&#x200B;**[!UICONTROL +新增]**。 然後，在[!UICONTROL 事件組態]對話方塊中，指定下列資訊。 完成時，請選取&#x200B;**[!UICONTROL 保留變更]**。

      * **[!UICONTROL 延伸模組]**：從清單中選取&#x200B;**[!UICONTROL 核心]**。

      * **[!UICONTROL 事件型別]**：從清單中選取&#x200B;**[!UICONTROL 載入的視窗]**。

        ![規則 – 事件設定](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 動作]**：選取&#x200B;**[!UICONTROL +新增]**。 然後，在[!UICONTROL 動作組態]對話方塊中，指定下列資訊。 完成時，請選取&#x200B;**[!UICONTROL 保留變更]**。

      * **[!UICONTROL 擴充功能]**：從清單中選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

      * **[!UICONTROL 動作型別]**：從清單中選取&#x200B;**[!UICONTROL 傳送事件]**。

      * **[!UICONTROL 型別]**：從清單中選取&#x200B;**[!UICONTROL web.webpagedetails.pageViews]**。

      * **[!UICONTROL XDM資料]**：選取圓柱圖示，然後從資料元素清單中選取&#x200B;**[!UICONTROL XDM — 頁面檢視]**。

        ![規則 – 動作設定](assets/action-pageview-xdm.png)

        您的規則應如下所示：

        ![建立規則](assets/rule-pageview.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

## 建置並發佈您的標籤

定義資料元素和規則後，您必須建置並發佈標籤。 建立程式庫組建時，必須將其指派至一個環境。隨後組建的擴充功能、規則和資料元素會經過編譯，並放入指派的環境中。每個環境都會提供唯一的內嵌程式碼，可讓您將指派的組建整合至您的網站。

Adobe Experience Platform標籤支援從簡單到複雜的發佈工作流程，應該能配合您的Adobe Experience Platform Web SDK部署。 如需詳細資訊，請參閱[發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant)。

若要建置並發佈您的標籤：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 從左側邊欄中選取&#x200B;**[!UICONTROL 「發佈流程」]**。

1. 選取&#x200B;**[!UICONTROL 「選擇工作程式庫」]**，然後選取&#x200B;**[!UICONTROL 「新增程式庫…」]**。

1. 在[!UICONTROL 建立程式庫]對話方塊中，指定下列資訊：

   * **[!UICONTROL 名稱]**：程式庫的名稱。

   * **[!UICONTROL 環境]**：從清單中選取&#x200B;**[!UICONTROL 開發（開發）]**。

1. 選取&#x200B;**[!UICONTROL 「+ 新增所有變更的資源」]**。

   ![發佈–建立程式庫](assets/create-library-aep.png)

1. 選取&#x200B;**[!UICONTROL 「儲存並建置至開發」]**。

   您的標籤已儲存並為您的開發環境建置。 綠色圓點表示在開發環境中成功建置標籤。

1. 您可以選取&#x200B;**[!UICONTROL 「...」]**&#x200B;來重建程式庫或將程式庫移至中繼環境或生產環境。

   ![發佈 – 建置資料庫](assets/build-library.png)

