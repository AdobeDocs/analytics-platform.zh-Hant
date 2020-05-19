---
title: 建立連線
description: 說明如何在 Customer Journey Analytics 中建立與 Platform 資料集的連線。
translation-type: tm+mt
source-git-commit: 204eb143d513b9b73fad020efabe6891a1253608
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 68%

---


# 建立連線

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

按一下[這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html)，觀看概覽影片。

>[!IMPORTANT] 您可以將多個 [!DNL Experience Platform] 資料集合併為單一連線。

1. 請前往 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 按一 **[!UICONTROL 下右上方的]** 「建立新連線」。

   ![建立連線](assets/create-connection.png)

1. 在Experience Platform中選擇沙盒，其中包含您要建立連線的資料集。

   Adobe Experience Platform提供 [沙盒](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) ，可將單一Platform執行個體分割為不同的虛擬環境，以協助開發和發展數位體驗應用程式。 您可以將沙盒視為包含資料集的「資料孤島」。 沙盒可用來控制資料集的存取。 您無法跨沙盒存取資料。 選取沙盒後，左側導軌會顯示該沙盒中可從中擷取的所有資料集。

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (如果有很多資料集可選擇，可使用資料集清單上方的搜尋列來搜尋合適的資料集。)

1. Next, for each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | 資料集類型 | 說明 | 時間戳記 | 結構 | 人員 ID |
   |---|---|---|---|---|
   | [!UICONTROL 事件] | 代表及時事件的資料 (例如網站造訪、互動、交易、POS 資料、調查資料、廣告曝光數資料等)。例如，這可能是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。若使用事件資料，您可以靈活選擇將哪個 ID 當作人員 ID 使用。 | 系統會自動設定為 [Experience Platform] 中以事件為基礎的結構之預設時間戳記欄位。 | 任何以具有「時間系列」行為的 XDM 類別為依據的內建或自訂結構。例如「XDM 體驗事件」或「XDM 決策事件」。 | 您可以挑選要包含的人員 ID。在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。其中任何一個都可當作人員 ID 使用。範例包括 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。 |
   | [!UICONTROL 查找] | 類似於「分類」檔案。此資料用於查找在事件或設定檔資料中找到的值或索引鍵。例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查找資料。 | 不適用 | 除「XDM 個別設定檔」類別外，任何以具有「記錄」行為的 XDM 類別為基礎的內建或自訂結構。 | 不適用 |
   | [!UICONTROL 設定檔] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. 例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 任何以「XDM 個別設定檔」類別為基礎的內建或自訂模式。 | 您可以挑選要包含的人員 ID。在 [!DNL Experience Platform] 中定義的每個資料集，都有各自專屬的一組一或多個已定義的人員 ID，例如 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。<br>![人員 ID](assets/person-id.png)**請注意&#x200B;**：如果您建立的連線包含具有不同 ID 的資料集，報表會反映出這一點。若要確實合併資料集，您需要使用相同的人員 ID。 |

1. 按一下 **[!UICONTROL 下一步]** ，轉至「創 [!UICONTROL 建連接」對話框] 。

   ![建立連線](assets/create-connection2.png)

1. In the [!UICONTROL Create Connection] dialog, define these settings:

   | 欄位 | 說明 |
   |---|---|
   | [!UICONTROL 名稱連接] | 為連線提供說明性名稱。無法儲存無名稱的連線。 |
   | [!UICONTROL 說明] | 新增更多詳細資訊，以便將此連線與其他連線區分開來。 |
   | [!UICONTROL 資料集] | 此連線中包含的資料集。 |
   | [!UICONTROL 從此連接中自動導入所有新資料集，從今天開始。] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL 匯入所有現有資料] | 選擇此選項並儲存連線時，此連線中所有資料集來自 [!DNL Experience Platform] 的所有現有 (歷史) 資料都會匯入。日後若有任何新資料集新增至這個已儲存的連線，其所有現有歷史資料也會自動匯入。<br>**請注意，一旦儲存此連線，便無法變更這項設定。** |

   **請記住：**

   * 如果連線中所有資料集的歷史資料累積大小超過 15 億列，便會出現一則錯誤訊息，說明無法匯入此數量的歷史資料。但是，如果您要新增包含 10 億列歷史資料的資料集並匯入了這些資料，一週之後再新增另一個相同大小的資料集並匯入其歷史資料，這麼做行得通。
   * 系統會為連線中新增的新資料排定優先順序，因此這些資料的延遲最低。
   * 所有回填 (歷史) 資料的匯入速度都較慢。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

工作流程的下一步是[建立資料檢視](/help/data-views/create-dataview.md)。
