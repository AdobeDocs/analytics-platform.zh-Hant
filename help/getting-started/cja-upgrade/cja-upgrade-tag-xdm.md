---
title: 將 XDM 資料彙集邏輯新增至您的標記
description: 了解如何新增 XDM 資料收集邏輯至您的標記
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 100%

---

# 將 XDM 資料彙集邏輯新增至您的標記 {#upgrade-tag-xdm}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-xdm"
>title="將 XDM 資料彙集邏輯新增至您的標記"
>abstract="在您的網站上安裝 Loader 標記後，您可以新增規則和資料元素來填入 XDM 物件以傳送至 Adobe。Adobe 建議維護解決方案設計文件，以追蹤您的標記設定。<br><br>此步驟有大量工作，因為其中包含設定您的屬性之所有 Analytics 邏輯。預計需要投入一個月或更長的時間來建立正確的標記規則、進行測試並將其部署至您的網站上。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

[建立標記及新增 Web SDK 擴充功能](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)後，您必須使用資料元件和規則來設定，且要根據您想如何追蹤網站及將資料傳送至 Adobe Experience Platform 來進行。為您的標記設定資料元素和規則後，即可建立和發佈標記。

## 設定資料元素

資料元素是資料字典 (或資料地圖) 的建置組塊。使用資料元素，在行銷和廣告技術之間收集、組織和傳遞資料。您可在標記中設定從資料層讀取的資料元素，且可用來將資料傳送至 Adobe Experience Platform。(有關資料元素的更多資訊，請參閱「標記文件」中的「[資料元素](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/ui/data-elements)」。

以下部分說明建議的資料元素以及您可以設定的其他常見資料元素。

資料元素有各種不同類型。您可能想要設定兩個常見資料元素：一個用來擷取人們在您網站上查看的頁面名稱，另一個用來擷取造訪您網站的每個人的 Experience Cloud ID。

設定這兩個資料元素後，您可以為想要擷取的特定資料設定其他資料元素。

最後，定義好所有想要的資料元素後，您需要將資料元素指派至先前[建立的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。若要這樣做，您要定義 XDM 資料元素，在其中呈現您的 XDM 結構描述。

<!-- Assigning data elements to an XDM object. All of the available XDM objects are based on the schema -->

### 建立建議的資料元素

以下部分說明如何建立適用於大多數組織的通用資料元素。

#### 頁面名稱元素

適用於大多數組織的通用資料元素是擷取人們正在查看的頁面名稱資料元素。

若要建立頁面名稱資料元素：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從「**[!UICONTROL 標記屬性]**」頁面，選取您新建立的標記並開啟。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在「**[!UICONTROL 建立資料元素]**」對話框中，指定以下資訊：

   * **[!UICONTROL 名稱]**：您的資料元素名稱。例如 `Page Name`。

   * **[!UICONTROL 擴充功能]**：從清單中選取「**[!UICONTROL 核心]**」。

   * **[!UICONTROL 資料元素類型]**：從清單中選取「**[!UICONTROL 頁面資訊]**」。

   * **[!UICONTROL 屬性]**：從清單中選取「**[!UICONTROL 標題]**」。

     ![使用頁面資訊建立資料元素](assets/create-dataelement-1.png)

     或者，您也可以使用資料層變數的值，例如`pageName`和 [!UICONTROL JavaScript 變數] 資料元素類型來定義該資料元素。

     ![使用 JavaScript 變數建立資料元素](assets/create-dataelement-2.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

   您現在想要設定資料元素，以參考由 Adobe Experience Platform Web SDK 自動提供且可透過 Experience Cloud ID 服務擴充功能使用的Experience Cloud ID。

1. 繼續進行[ECID 資料元素](#ecid-data-element)。

#### ECID 資料元素

適用於大多數組織的通用資料元素是擷取瀏覽您網站的每個人的 Experience Cloud ID 資料元素。

若要建立 ECID 資料元素：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. (條件) 如果尚未安裝 Experience Cloud ID Service 擴充功能，請安裝：

   1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「擴充功能」]**。

   1. 依預設選取「**[!UICONTROL 已安裝]**」索引標籤。若列有「**[!UICONTROL Experience Cloud ID Service]**」圖磚，請跳至步驟 5。

   1. 若未列有「**[!UICONTROL Experience Cloud ID Service]**」圖磚，請選取「 **[!UICONTROL 目錄]**」索引標籤。

   1. 在搜尋欄位中，搜尋 **[!UICONTROL Experience Cloud ID Service]**，然後在圖磚出現時選取圖磚

   1. 選取「**[!UICONTROL 安裝]** > **[!UICONTROL 儲存]**」。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在「**[!UICONTROL 建立資料元素]**」對話框中，指定以下資訊：

   * **[!UICONTROL 名稱]**：您的資料元素名稱。例如 `ECID`。

   * **[!UICONTROL 擴充功能]**：從清單中選取「**[!UICONTROL Experience Cloud ID 服務]**」。

   * **[!UICONTROL 資料元素類型]**：從清單中選取 **[!UICONTROL ECID]**。

     ![ECID 資料元素](assets/ecid-dataelement.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續[建立附加資料元素](#create-additional-data-elements)。

### 建立附加資料元素

為您想要收集的每種資料類型建立一個資料元素。使用[頁面名稱資料元素](#page-name-data-element)和 [ECID 資料元素](#ecid-data-element)中所述的相同流程來建立每個附加資料元素。

您建立的資料元素應該在您的結構描述中有一個關聯的欄位。

通用資料元素因行業和業務需求而異。考慮使用以下通見資料元素 (按行業排列)：

**零售資料元素**

* 產品

* 購物車新增

* 結帳

**財務資料元素**

* 交易 ID

* 交易日期

* 服務類型

**醫療保健資料元素**

* 服務提供者 ID

* 造訪日期

* 治療類型

為您的實施建立組織所需的全部資料元素後，繼續進行[XDM 物件資料元素](#xdm-object-data-element)。

### XDM 物件資料元素

最後，您現在想要將已建立的任何資料元素對應到您先前[建立的結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)。為此，請定義一個 XDM 物件資料元素，以呈現您的 XDM 結構描述。

若要定義 XDM 物件資料元素：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「資料元素」]**。

1. 選取&#x200B;**[!UICONTROL 「新增資料元素」]**。

1. 在「**[!UICONTROL 建立資料元素]**」對話框中，指定以下資訊：

   * **[!UICONTROL 名稱]**：您的資料元素名稱。例如 `XDM - Page View`。

   * **[!UICONTROL 擴充功能]**：從清單中選取「**[!UICONTROL Adobe Experience Platform Web SDK]**」。

   * **[!UICONTROL 資料元素類型]**：從清單中選取「**[!UICONTROL XDM 物件]**」。

   * **[!UICONTROL 沙箱]**：從清單中選取您的沙箱。

   * **[!UICONTROL 結構描述]**：籨清單中選取您的結構描述。

1. 將您的結構描述中定義的 `identification > core > ecid`屬性對應至 ECID 資料元素。選取圓柱體圖示，即可輕鬆從資料元素清單中挑選 ECID 資料元素。

   ![挑選 ECID 資料元素](assets/pick-ecid-dataelement.png)

   ![對應 ECID 資料元素](assets/map-ecid.png)

1. 將您的結構中定義的 `web > webPageDetails > name`屬性對應至頁面名稱資料元素。

   ![對應頁面名稱元素](assets/map-pagename.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 繼續進行[設定規則](#configure-rules)。

## **設定規則**

Adobe Experience Platform 中的標籤會遵循規則型系統。它們會尋找使用者互動與相關資料。當符合列於您規則中的準則時，規則會觸發您識別的擴充功能、指令碼或用戶端代碼。您可以使用規則，透過 Adobe Experience Platform Web SDK 擴充功能將資料 (例如 XDM 物件) 傳送至 Adobe Experience Platform。

定義規則：

>[!NOTE]
>
>以下步驟是定義規則的範例，此規則會將 XDM 資料 (包含其他資料元素的值) 傳送至 Adobe Experience Platform。
>
>您可以在標籤中以各種方式使用規則來操控變數 (使用您的資料元素)。
>
>如需詳細資訊，請參閱[規則](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html)。

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 選取左側邊欄中的&#x200B;**[!UICONTROL 「規則」]**。

1. 選取「**[!UICONTROL 新增規則]**」。

1. 在「**[!UICONTROL 建立規則]**」對話框中，指定下列資訊：

   * **[!UICONTROL 名稱]**：規則的名稱。例如 `Page View`。

   * **[!UICONTROL 事件]**：選取「**[!UICONTROL + 新增]**」。然後，在「**[!UICONTROL 事件設定]**」對話框中，指定下列資訊。完成後，選取「**[!UICONTROL 保留變更]**」。

      * **[!UICONTROL 擴充功能]**：從清單中選取「**[!UICONTROL 核心]**」。

      * **[!UICONTROL 事件類型]**：從清單中選取「**[!UICONTROL 視窗已載入]**」。

        ![規則 – 事件設定](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL 動作]**：選取「**[!UICONTROL + 新增]**」。然後，在「[!UICONTROL 動作設定]」對話框中，指定下列資訊。完成後，選取「**[!UICONTROL 保留變更]**」。

      * **[!UICONTROL 擴充功能]**：從清單中選取「**[!UICONTROL Adobe Experience Platform Web SDK]**」。

      * **[!UICONTROL 動作類型]**：從清單中選取「**[!UICONTROL 傳送事件]**」。

      * **[!UICONTROL 類型]**：從清單中選取 **[!UICONTROL web.webpagedetails.pageViews]**。

      * **[!UICONTROL XDM 資料]**：選取圓柱體圖示，然後從資料元素清單中選取「**[!UICONTROL XDM – 頁面檢視]**」。

        ![規則 – 動作設定](assets/action-pageview-xdm.png)

        您的規則應如下所示：

        ![建立規則](assets/rule-pageview.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 為要新增至網站的每條規則，重複此程序。

   有關規則的更多資訊，請參閱「標記文件」中的「[規則](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/ui/rules)」。

1. 繼續[建立並發佈您的標記](#build-and-publish-your-tag)。

## 建立並發佈您的標記

定義資料元素和規則後，您必須建立並發佈標記。建立程式庫組建時，必須將其指派至一個環境。隨後組建的擴充功能、規則和資料元素會經過編譯，並放入指派的環境中。每個環境都會提供唯一的內嵌程式碼，可讓您將指派的組建整合至您的網站。

Adobe Experience Platform 標籤支援簡單到複雜的發佈工作流程，以配合您部署 Adobe Experience Platform Web SDK。如需詳細資訊，請參閱[發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant)。

若要建置並發佈您的標籤：

1. 使用您的 Adobe ID 認證登入 experience.adobe.com。

1. 在 Adobe Experience Platform 中，前往「**[!UICONTROL 資料彙集]** > **[!UICONTROL 標記]**」。

1. 從[!UICONTROL 「標籤屬性」]清單中選擇您新建立的標籤，並將其打開。

1. 從左側邊欄中選取&#x200B;**[!UICONTROL 「發佈流程」]**。

1. 選取「**[!UICONTROL 新增資料庫]**」。

1. 在「**[!UICONTROL 建立資料庫]**」對話框中，指定下列資訊：

   * **[!UICONTROL 名稱]**：資料庫的名稱。

   * **[!UICONTROL 環境]**：從清單中選取「**[!UICONTROL 開發 (開發)」]**。

1. 選取&#x200B;**[!UICONTROL 「+ 新增所有變更的資源」]**。

   ![發佈–建立程式庫](assets/create-library-aep.png)

1. 選取&#x200B;**[!UICONTROL 「儲存並建置至開發」]**。

   您的標記已儲存並已針對您的開發環境建立。綠色圓點表示在開發環境中成功建置標籤。

1. 您可以選取&#x200B;**[!UICONTROL 「...」]**&#x200B;來重建程式庫或將程式庫移至中繼環境或生產環境。

   ![發佈 – 建置資料庫](assets/build-library.png)

{{upgrade-final-step}}

