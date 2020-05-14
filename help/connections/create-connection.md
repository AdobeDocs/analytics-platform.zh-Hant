---
title: 建立連線
description: 說明如何在客戶歷程分析中建立與平台資料集的連線。
translation-type: tm+mt
source-git-commit: 4b672b0decfecc5a3c607ad966ebb2ecbf178a96
workflow-type: tm+mt
source-wordcount: '886'
ht-degree: 4%

---


# 建立連線

連線可讓您將資料集整合 [!DNL Adobe Experience Platform] 至 [!UICONTROL Workspace]。 為了報告資料集， [!DNL Experience Platform] 您必須先在資料集和工作區中建立資料集 [!DNL Experience Platform] 的 [!UICONTROL 連線]。

按一 [下這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) ，即可檢視影片總覽。

>[!IMPORTANT] 您可以將多個資 [!DNL Experience Platform] 料集合併為單一連線。

1. 請至 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. Click the **[!UICONTROL Connections]** tab.

1. 按一 **[!UICONTROL 下右上方的]** 「建立新連線」。

   ![建立連線](assets/create-connection.png)

1. 首先，在「 **[!UICONTROL 選取資料集]**」下方，在Experience Platform中選擇一個沙箱  ，其中包含您要建立連線的資料集。
Adobe Experience Platform提供沙 [箱](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) ，可將單一Platform實例分割為獨立的虛擬環境。 您可以將沙 [!UICONTROL 盒視為] 「資料孤島」，其中包含資料集並用來控制對資料集的存取。 請注意，您無法跨沙盒存取 [!UICONTROL 資料]。

1. 選取沙盒後，左側導軌會顯示該沙盒中可從中擷取的所有資料集。 選取一或多個您要納入「客戶歷程分析」的資 [!UICONTROL 料集] ，然後按一 **[!UICONTROL 下「新增」]**。 （如果您有許多資料集可供選擇，則可使用資料集清單上方的搜尋列來搜尋正確的資料集。）

1. 接著，針對您新增至此連線的每個資料集， [!UICONTROL Customer Journey Analytics] 會根據傳入的資料自動設定資料集類型。 有3種不同的資料集類型： [!UICONTROL 事件] 資料、 [!UICONTROL 描述檔資料] 、查 [!UICONTROL 閱資料] 。

   | 資料集類型 | 說明 | 時間戳記 | 結構 | 人員 ID |
   |---|---|---|---|---|
   | [!UICONTROL 事件] | 代表及時事件的資料（例如，網站瀏覽、互動、交易、POS資料、調查資料、廣告曝光資料等）。 例如，這可以是典型的點按流資料（客戶ID或Cookie ID）和時間戳記。 對於事件資料，您可以靈活選擇將哪個ID用作人員ID。 | 會從 [UICONCONTROL Experience Platform中的事件型結構自動設為預設時間戳記欄位]。 | 任何基於具有「時間系列」行為的XDM類的內置或自定義模式。 例如「XDM體驗事件」或「XDM決策事件」。 | 您可以選擇要包含的人員ID。 在Experience Platform中定義的每個資料集架構都可以有其自己的一組一或多個定義與身分名稱空間相關聯的身分識別。 其中任何一個都可用作人員ID。 範例包括Cookie ID、銜接ID、使用者ID、追蹤代碼等。 |
   | [!UICONTROL 查找] | 類似於「分類」檔案。 此資料用於尋找在您的事件或描述檔資料中找到的值或索引鍵。 例如，您可以上傳將事件資料中的數值ID對應至產品名稱的查閱資料。 | 不適用 | 除「XDM個別描述檔」類別外，任何以具有「記錄」行為的XDM類別為基礎的內建或自訂架構。 | 不適用 |
   | [!UICONTROL 設定檔] | 類似於「 [!UICONTROL 客戶屬性] 」 —— 用於非變更和非暫時屬性。 套用至「事件」資料中之訪客、使用者或客戶的 [!UICONTROL 資料] 。 例如，可讓您上傳有關客戶的CRM資料。 | 不適用 | 任何基於「XDM個別配置檔案」類的內置或自定義模式。 | 您可以選擇要包含的人員ID。 定義在中的每個資 [!DNL Experience Platform] 料集都有自己定義的一或多個人員ID集，例如Cookie ID、銜接ID、使用者ID、追蹤代碼等。<br>![人](assets/person-id.png)**員&#x200B;**: 如果您建立的連線包含不同ID的資料集，報表會反映這一點。 若要真正合併資料集，您需要使用相同的人員ID。 |

1. 按一下「 **[!UICONTROL 下一步]** 」(Next [!UICONTROL )將帶您進入「] 建立連接」(Create Connection)對話框。

   ![建立連線](assets/create-connection2.png)

1. 在「建 [!UICONTROL 立連線] 」對話方塊中，定義下列設定：

   | 欄位 | 說明 |
   |---|---|
   | [!UICONTROL 名稱連接] | 為連接指定描述性名稱。 無法在沒有名稱的情況下保存連接。 |
   | [!UICONTROL 說明] | 添加更多詳細資訊以區分此連接和其他連接。 |
   | [!UICONTROL 資料集] | 此連接中包含的資料集。 |
   | [!UICONTROL 從此連接中自動導入所有新資料集，從今天開始。] | 如果要建立持續連接，請選擇此選項，以便添加到此連接中資料集的任何新資料批自動流入 [!UICONTROL Workspace]。 |
   | [!UICONTROL 匯入所有現有資料] | 當您選擇此選項並保存連接時，將導入此連接中所有資料集的 [!DNL Experience Platform] 所有現有（歷史）資料。 未來，新增至此儲存連線之任何新資料集的所有現有歷史資料也會自動匯入。 <br>**請注意，一旦儲存此連線，便無法變更此設定。** |

   **請記住：**

   * 如果連接中所有資料集的歷史資料累積大小超過15億行，則會出現一條錯誤消息，指出您無法導入此數量的歷史資料。 但是，如果您要新增包含10億列歷史資料的資料集，並匯入該資料，一週後，新增另一個大小相同的資料集並匯入其歷史資料，這將會奏效。
   * 我們將連線中新增的新資料排定優先順序，因此這些資料的延遲最低。
   * 任何回填（歷史）資料的匯入速率會變慢。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

工作流程的下一步是建 [立資料檢視](/help/data-views/create-dataview.md)。
