---
title: 將 XDM 資料彙集邏輯新增至您的標記
description: 瞭解如何將XDM資料收集邏輯新增至您的標籤
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: bb87226ee4b9acc433031f41997d403d49f48db3
workflow-type: tm+mt
source-wordcount: '1697'
ht-degree: 31%

---

# 將 XDM 資料彙集邏輯新增至您的標記 {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="將 XDM 資料彙集邏輯新增至您的標記"
>abstract="在網站上安裝Loader標籤後，您可以新增規則和資料元素以填入XDM物件並傳送給Adobe。 Adobe建議維護解決方案設計檔案，以追蹤標籤的設定方式。<br><br>此步驟需要大量工作，因為需要為屬性設定所有Analytics邏輯。 預計將花費一個月或更長時間建立正確的標籤規則、測試這些規則，並在您的網站上部署。"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

在[建立標籤並新增Web SDK擴充功能](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)後，您必須根據您想要追蹤網站及傳送資料至Adobe Experience Platform的方式，使用資料元素和規則來設定標籤。 為標籤設定資料元素和規則後，您就可以建置並發佈標籤。

## 設定資料元素

資料元素是資料字典 (或資料地圖) 的建置組塊。使用資料元素，在行銷和廣告技術之間收集、組織和傳遞資料。您可以在標籤中設定可從資料層讀取的資料元素，並可將資料傳送至Adobe Experience Platform。 （如需資料元素的詳細資訊，請參閱標籤檔案中的[資料元素](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/data-elements)。）

以下各節將說明建議的資料元素以及您可以設定的其他常見資料元素。

有多種型別的資料元素。 您可能會想要設定的兩個常見資料元素：一個擷取訪客在您的網站上檢視的頁面名稱，另一個擷取造訪您網站的每個訪客的Experience CloudID。

設定這兩個資料元素後，您可以針對要擷取的特定資料設定其他資料元素。

最後，在您定義所有想要的資料元素後，您需要將資料元素指派給您先前建立的[結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。 為此，您需要定義XDM資料元素，其可提供XDM結構的表示方式。

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### 建立建議的資料元素

以下各節說明如何建立適用於大多陣列織的通用資料元素。

#### 頁面名稱資料元素

適用於大多陣列織的通用資料元素是資料元素，可擷取人員正在檢視的頁面名稱。

若要建立page name資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 在&#x200B;**[!UICONTROL 標籤屬性]**&#x200B;頁面上，從屬性清單中選取您新建立的標籤以開啟它。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在&#x200B;**[!UICONTROL 建立資料元素]**&#x200B;對話方塊中，指定下列資訊：

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

#### ECID資料元素

適用於大多陣列織的通用資料元素是資料元素，可擷取造訪您網站的每個人的Experience CloudID。

若要建立ECID資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. （視條件而定）安裝Experience CloudID服務擴充功能（如果尚未安裝）：

   1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「擴充功能」]**。

   1. 預設會選取&#x200B;**[!UICONTROL 已安裝]**&#x200B;標籤。 如果列出&#x200B;**[!UICONTROL Experience Cloud識別碼服務]**&#x200B;圖磚，請跳至步驟5。

   1. 如果未列出&#x200B;**[!UICONTROL Experience CloudID服務]**&#x200B;圖磚，請選取&#x200B;**[!UICONTROL 目錄]**&#x200B;索引標籤。

   1. 在搜尋欄位中，搜尋&#x200B;**[!UICONTROL Experience Cloud識別碼服務]**，然後選取出現時的圖磚

   1. 選取&#x200B;**[!UICONTROL 安裝]** > **[!UICONTROL 儲存]**。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在&#x200B;**[!UICONTROL 建立資料元素]**&#x200B;對話方塊中，指定下列資訊：

   * **[!UICONTROL Name]**：資料元素的名稱。 例如 `ECID`。

   * **[!UICONTROL 延伸模組]**：從清單中選取&#x200B;**[!UICONTROL Experience Cloud識別碼服務]**。

   * **[!UICONTROL 資料元素型別]**：從清單中選取&#x200B;**[!UICONTROL ECID]**。

     ![ECID 資料元素](assets/ecid-dataelement.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續進行[建立其他資料元素](#create-additional-data-elements)。

### 建立其他資料元素

為您要收集的每種資料型別建立資料元素。 使用[Page name資料元素](#page-name-data-element)和[ECID資料元素](#ecid-data-element)中描述的相同程式來建立每個額外的資料元素。

您建立的資料元素在結構描述中應具有關聯欄位。

常見的資料元素會因產業和業務需求而異。 請考量下列依產業組織的常見資料元素：

**零售資料元素**

* 產品

* 購物車新增

* 結帳

**財務資料元素**

* 交易 ID

* 交易日期

* 服務型別

**醫療保健資料元素**

* 提供者ID

* 造訪日期

* 處理型別

在您建立組織實施所需的所有資料元素後，請繼續使用[XDM物件資料元素](#xdm-object-data-element)。

### XDM物件資料元素

最後，您現在想要將您建立的任何資料元素對應至您先前建立的[結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。 為此，請定義XDM物件資料元素，以提供XDM結構的表示方式。

若要定義 XDM 物件資料元素：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在&#x200B;**[!UICONTROL 建立資料元素]**&#x200B;對話方塊中，指定下列資訊：

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

1. 選取&#x200B;**[!UICONTROL 新增規則]**。

1. 在&#x200B;**[!UICONTROL 建立規則]**&#x200B;對話方塊中，指定下列資訊：

   * **[!UICONTROL 名稱]**：規則的名稱。 例如 `Page View`。

   * **[!UICONTROL 事件]**：選取&#x200B;**[!UICONTROL +新增]**。 然後，在&#x200B;**[!UICONTROL 事件組態]**&#x200B;對話方塊中，指定下列資訊。 完成時，請選取&#x200B;**[!UICONTROL 保留變更]**。

      * **[!UICONTROL 延伸模組]**：從清單中選取&#x200B;**[!UICONTROL 核心]**。

      * **[!UICONTROL 事件型別]**：從清單中選取&#x200B;**[!UICONTROL 載入的視窗]**。

        ![規則 – 事件設定](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 動作]**：選取&#x200B;**[!UICONTROL +新增]**。 然後，在[!UICONTROL 動作組態]對話方塊中，指定下列資訊。 完成時，請選取&#x200B;**[!UICONTROL 保留變更]**。

      * **[!UICONTROL 擴充功能]**：從清單中選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**。

      * **[!UICONTROL 動作型別]**：從清單中選取&#x200B;**[!UICONTROL 傳送事件]**。

      * **[!UICONTROL 型別]**：從清單中選取&#x200B;**[!UICONTROL 網頁詳細資訊頁面檢視]**。

      * **[!UICONTROL XDM資料]**：選取圓柱圖示，然後從資料元素清單中選取&#x200B;**[!UICONTROL XDM — 頁面檢視]**。

        ![規則 – 動作設定](assets/action-pageview-xdm.png)

        您的規則應如下所示：

        ![建立規則](assets/rule-pageview.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 針對您想要新增至網站的每個規則重複此程式。

   如需規則的詳細資訊，請參閱標籤檔案中的[規則](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/rules)。

1. 繼續建置並發佈您的標籤](#build-and-publish-your-tag)。[

## 建置並發佈您的標籤

定義資料元素和規則後，您必須建置並發佈標籤。 建立程式庫組建時，必須將其指派至一個環境。隨後組建的擴充功能、規則和資料元素會經過編譯，並放入指派的環境中。每個環境都會提供唯一的內嵌程式碼，可讓您將指派的組建整合至您的網站。

Adobe Experience Platform標籤支援從簡單到複雜的發佈工作流程，應該能配合您的Adobe Experience Platform Web SDK部署。 如需詳細資訊，請參閱[發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant)。

若要建置並發佈您的標籤：

1. 使用您的Adobe ID憑證登入experience.adobe.com 。

1. 在Adobe Experience Platform中，移至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 從左側邊欄中選取&#x200B;**[!UICONTROL 「發佈流程」]**。

1. 選取&#x200B;**[!UICONTROL 新增資料庫]**。

1. 在&#x200B;**[!UICONTROL 建立程式庫]**&#x200B;對話方塊中，指定下列資訊：

   * **[!UICONTROL 名稱]**：程式庫的名稱。

   * **[!UICONTROL 環境]**：從清單中選取&#x200B;**[!UICONTROL 開發（開發）]**。

1. 選取&#x200B;**[!UICONTROL 「+ 新增所有變更的資源」]**。

   ![發佈–建立程式庫](assets/create-library-aep.png)

1. 選取&#x200B;**[!UICONTROL 「儲存並建置至開發」]**。

   您的標籤已儲存並為開發環境建置。 綠色圓點表示在開發環境中成功建置標籤。

1. 您可以選取&#x200B;**[!UICONTROL 「...」]**&#x200B;來重建程式庫或將程式庫移至中繼環境或生產環境。

   ![發佈 – 建置資料庫](assets/build-library.png)
