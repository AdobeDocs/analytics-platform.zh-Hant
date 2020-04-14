---
title: 建立連線
description: 說明如何在客戶歷程分析中建立與平台資料集的連線。
translation-type: tm+mt
source-git-commit: 7fdda3a4171400ba018fe31b492737553c575998

---


# 建立連線

連接可讓您將資料集整合 [!DNL Adobe Experience Platform] 到 [!UICONTROL Workspace]中。 為了報告資料集， [!DNL Experience Platform] 您首先必須在和中的資料集之間建立 [!DNL Experience Platform] 連接 [!UICONTROL Workspace]。

按一 [下這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) ，即可檢視影片總覽。

>[!IMPORTANT] 您可以將多個資 [!DNL Experience Platform] 料集合併為單一連線。

1. 請至 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 按一 **[!UICONTROL Create new connection]** 下右上角的。

![建立連線](assets/create-connection.png)

1. 左側欄顯示您可從中提取 [!DNL Experience Platform] 的所有資料集。 選取一或多個您要拉進的資料集，然後按 [!UICONTROL Customer Journey Analytics] 一下 **[!UICONTROL Add]**。 （如果您有許多資料集可供選擇，則可使用資料集清單上方的搜尋列來搜尋正確的資料集。）

1. 接著，針對您新增至此連線的每個資料集， [!UICONTROL Customer Journey Analytics] 會根據傳入的資料自動設定資料集類型。 有3種不同的資料集類型：資 [!UICONTROL Event] 料、 [!UICONTROL Profile] 資料和資 [!UICONTROL Lookup] 料。

   | 資料集類型 | 說明 | 時間戳記 | 結構 | 人員 ID |
   |---|---|---|---|---|
   | [!UICONTROL Event] | 代表及時事件的資料（例如，網站瀏覽、互動、交易、POS資料、調查資料、廣告曝光資料等）。 這是典型的點按流資料，包含客戶ID或Cookie ID，以及時間戳記。 透過事件資料，我們允許您使用任何您想要的ID。 | 將設定為時間戳。 | 此數 [!DNL Experience Platform] 據集類型所基於的模式。 | 不適用 |
   | [!UICONTROL Lookup] | 類似於「分類」檔案。 此資料用於尋找在您的事件或描述檔資料中找到的值或索引鍵。 例如，您可以上傳將事件資料中的數值ID對應至產品名稱的查閱資料。 | 不適用 | 此數 [!DNL Experience Platform] 據集類型所基於的模式。 | 不適用 |
   | [!UICONTROL Profile] | 類似於 [!UICONTROL Customer Attributes] -用於非更改和非臨時屬性。 資料中套用至訪客、使用者或客戶的 [!UICONTROL Event] 資料。 例如，可讓您上傳有關客戶的CRM資料。 | 不適用 | 此數 [!DNL Experience Platform] 據集類型所基於的模式。 | 您可以選擇要包含的人員ID。 定義在中的每個資 [!DNL Experience Platform] 料集都有自己定義的一或多個人員ID集，例如Cookie ID、銜接ID、使用者ID、追蹤代碼等。<br>![人](assets/person-id.png)**員&#x200B;**:如果您建立的連線包含不同ID的資料集，報表會反映這一點。 要真正合併資料集，您需要使用相同的人員ID。 |

1. 按一下 **[!UICONTROL Next]** 將帶您進入對話 [!UICONTROL Create Connection] 框。

   ![建立連線](assets/create-connection2.png)

1. 在對話 [!UICONTROL Create Connection] 方塊中，定義下列設定：

   | 欄位 | 說明 |
   |---|---|
   | [!UICONTROL Name Connection] | 為連接指定描述性名稱。 無法在沒有名稱的情況下保存連接。 |
   | [!UICONTROL Description] | 添加更多詳細資訊以區分此連接和其他連接。 |
   | [!UICONTROL Datasets] | 此連接中包含的資料集。 |
   | [!UICONTROL Automatically import all new datasets in this connection, beginning today.] | 如果要建立持續連接，請選擇此選項，以便添加到此連接中資料集的任何新資料批自動流入 [!UICONTROL Workspace]。 |
   | [!UICONTROL Import all existing data] | 當您選擇此選項並保存連接時，將導入此連接中所有資料集的 [!DNL Experience Platform] 所有現有（歷史）資料。 未來，新增至此儲存連線之任何新資料集的所有現有歷史資料也會自動匯入。 <br>**請注意，一旦儲存此連線，便無法變更此設定。** |

   **請記住：**

   * 如果連接中所有資料集的歷史資料累積大小超過15億行，則會出現一條錯誤消息，指出您無法導入此數量的歷史資料。 但是，如果您要新增包含10億列歷史資料的資料集，並匯入該資料，一週後，新增另一個大小相同的資料集並匯入其歷史資料，這將會奏效。
   * 我們將連線中新增的新資料排定優先順序，因此這些資料的延遲最低。
   * 任何回填（歷史）資料的匯入速率會變慢。

1. 按一下 **[!UICONTROL Save]**.

工作流程的下一步是建 [立資料檢視](/help/data-views/create-dataview.md)。
