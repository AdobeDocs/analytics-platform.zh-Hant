---
title: 建立連線
description: 說明如何在 Customer Journey Analytics 中建立與 Platform 資料集的連線。
translation-type: tm+mt
source-git-commit: 756c6e7c187b76636cf96d18c949908a97db51ed
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 52%

---


# 建立連線

連線可讓您將資料集從 [!DNL Adobe Experience Platform] 整合到[!UICONTROL 工作區]。若要針對 [!DNL Experience Platform] 資料集製作報表，必須先為 [!DNL Experience Platform] 和[!UICONTROL 工作區]的資料集建立連線。

按一下[這裡](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html)，觀看概觀影片。

>[!IMPORTANT]
>
> 您可以將多個 [!DNL Experience Platform] 資料集合併為單一連線。

1. 請前往 [https://analytics.adobe.com](https://analytics.adobe.com)。

1. 按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;標籤。

1. 按一下右上方的&#x200B;**[!UICONTROL 「建立新連結」]**。

   ![建立連線](assets/create-connection0.png)

1. 在 Experience Platform 中，選擇您要連線之資料集所屬的沙箱。

   Adobe Experience Platform 提供的[沙箱](https://docs.adobe.com/content/help/zh-Hant/experience-platform/sandbox/home.html)可將單一 Platform 例項分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限，您無法一次存取多個沙箱內的資料。選取沙箱後，左側欄會顯示您可以從該沙箱提取的所有資料集。

1. 選取一或多個要拉進 [!UICONTROL Customer Journey Analytics] 的資料集，然後按一下&#x200B;]**「新增」**[!UICONTROL 

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## 設定資料集

在右側，您現在可以設定已新增的資料集。

![設定資料集](assets/create-connection.png)

1. **[!UICONTROL 資料集類型]**: 對於您新增至此連線的每個資料集， [!UICONTROL Customer Journey Analytics] 會根據傳入的資料自動設定資料集類型。

   有 3 種不同的資料集類型：[!UICONTROL 事件]資料、[!UICONTROL 設定檔]資料、[!UICONTROL 查找]資料。

   | 資料集類型 | 說明 | 時間戳記 | 結構 | 人員 ID |
   |---|---|---|---|---|
   | [!UICONTROL 事件] | 代表及時事件的資料 (例如網站造訪、互動、交易、POS 資料、調查資料、廣告曝光數資料等)。例如，這可能是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。若使用事件資料，您可以靈活選擇將哪個 ID 當作人員 ID 使用。 | 系統會自動設定為 [Experience Platform] 中以事件為基礎的結構之預設時間戳記欄位。 | 任何以具有「時間系列」行為的 XDM 類別為依據的內建或自訂結構。例如「XDM 體驗事件」或「XDM 決策事件」。 | 您可以挑選要包含的人員 ID。在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。其中任何一個都可當作人員 ID 使用。範例包括 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。 |
   | [!UICONTROL 查找] | 類似於「分類」檔案。此資料用於查找在事件或設定檔資料中找到的值或索引鍵。例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查找資料。 | 不適用 | 除「XDM 個別設定檔」類別外，任何以具有「記錄」行為的 XDM 類別為基礎的內建或自訂結構。 | 不適用 |
   | [!UICONTROL 設定檔] | 類似於[!UICONTROL 「客戶屬性」] - 用於非變更和非臨時屬性。套用至[!UICONTROL 事件]資料中訪客、使用者或客戶的資料。例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 任何以「XDM 個別設定檔」類別為基礎的內建或自訂模式。 | 您可以挑選要包含的人員 ID。在 [!DNL Experience Platform] 中定義的每個資料集，都有各自專屬的一組一或多個已定義的人員 ID，例如 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。<br>![人員 ID](assets/person-id.png)**請注意&#x200B;**：如果您建立的連線包含具有不同 ID 的資料集，報表會反映出這一點。若要確實合併資料集，您需要使用相同的人員 ID。 |

1. **[!UICONTROL 資料集ID]**: 此ID會自動產生。

1. **[!UICONTROL 時間戳]**: 新增內容至此

1. **[!UICONTROL 架構]**: 這是在 [Adobe Experience Platform中建立資料集時所依據的架構](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/schema/composition.html) 。

1. **[!UICONTROL 人員ID]**: 從可用身份的下拉式清單中選擇人員ID。 這些身分是在Experience Platform的資料集架構中定義。 如需如何將Identity Map當成人員ID的詳細資訊，請參閱以下。

   >[!IMPORTANT]
   >
   >如果沒有人員ID可供選擇，表示架構中尚未定義一或多個人員ID。 觀看 [此影片](https://youtu.be/G_ttmGl_LRU) ，瞭解如何在Experience Platform中定義身分。

1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Enable Connection] dialog.

### 將Identity Map用作人員ID

「客戶歷程分析」現在支援使用Identity Map做為其人員ID的能力。 Identity Map是一種地圖資料結構，可讓某人上傳金鑰->值配對。 密鑰是標識名稱空間，值是保存標識值的結構。 Identity Map存在於每個上載的列／事件上，並會依此填入每一列。

Identity Map適用於任何使用基於 [ExperienceEvent XDM類別之架構的資料集](https://docs.adobe.com/content/help/zh-Hant/experience-platform/xdm/home.html) 。 當您選取要包含在CJA連線中的此類資料集時，您可以選擇欄位作為主要ID或Identity Map:

![](assets/idmap1.png)

如果您選擇Identity Map，您將獲得兩個其他配置選項：

| 選項 | 說明 |
|---|---|
| [!UICONTROL 使用主要 ID 命名空間] | 這會指示CJA在標有primary=true屬性的Identity Map中，以每列尋找識別，並將其用作該列的Person ID。 這表示這是Experience Platform中用於分區的主要關鍵。 它也是CJA訪客ID的主要候選用途（視CJA連線中資料集的設定方式而定）。 |
| [!UICONTROL 命名空間] | （只有當您未使用「主要ID名稱空間」時，才可使用此選項。） 身分名稱空間是 [Adobe Experience Platform Identity Service的元件](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) ，可做為識別相關內容的指標。 如果您指定命名空間，CJA會針對此命名空間索引鍵搜尋每一列的Identity Map，並將該名稱空間下的識別碼當成該列的人員ID。 請注意，由於CJA無法對所有列執行完整資料集掃描以判斷實際存在的名稱空間，所有可能的名稱空間都會列在下拉式清單中。 您需要知道在資料中指定哪些名稱空間； 無法自動偵測到此問題。 |

### Identity Map邊緣案例

下表顯示了當出現邊框時的兩個配置選項，以及它們的處理方式：

| 選項 | Identity Map中沒有ID | 沒有ID標示為主要 | 多個ID標示為主要 | 單一ID標示為主要 | ID標示為主要ID的命名空間無效 |
|---|---|---|---|---|---|
| **已選中「使用主ID命名空間」** | CJA將刪除該行。 | CJA會刪除該行，因為未指定主ID。 | 所有標示為主要的ID（在所有名稱空間下）都會提取到清單中。 然後按字母順序排序； 使用此新排序時，第一個具有其第一個ID的命名空間會用作人員ID。 | 標示為主要的單一ID會用作人員ID。 | 即使命名空間可能無效（AEP中不存在）,CJA仍會使用該命名空間下的主要ID做為人員ID。 |
| **已選擇特定Identity Map命名空間** | CJA將刪除該行。 | 選定名稱空間下的所有ID都會提取到清單中，第一個ID用作「人員ID」。 | 選定名稱空間下的所有ID都會提取到清單中，第一個ID用作「人員ID」。 | 選定名稱空間下的所有ID都會提取到清單中，第一個ID用作「人員ID」。 | 選定名稱空間下的所有ID都會提取到清單中，第一個ID用作「人員ID」。 （在連線建立時，只能選取有效的命名空間，因此無效的命名空間/ID無法用作人員ID） |

## 啟用連接

![啟用連接](assets/create-connection2.png)

1. 要啟用連接，請定義以下設定：

   | 選項 | 說明 |
   |---|---|
   | [!UICONTROL 連線名稱] | 為連線提供說明名稱。無法儲存無名稱的連線。 |
   | [!UICONTROL 說明] | 新增更多詳細資訊，以便區分此連線與其他連線。 |
   | [!UICONTROL 資料集] | 此連線中包含的資料集。 |
   | [!UICONTROL 從今天開始，自動匯入此連線的所有新資料集。] | 如果要建立持續連線，請選擇此選項，如此一來，新增到此連線中資料集的任何新資料批次，都會自動彙整至]工作區[!UICONTROL 。 |
   | [!UICONTROL 匯入所有現有資料] | 選擇此選項並儲存連線時，此連線中所有資料集來自 [!DNL Experience Platform] 的所有現有 (歷史) 資料都會匯入。日後若有任何新資料集新增至這個已儲存的連線，其所有現有歷史資料也會自動匯入。<br>**請注意，一旦儲存此連線，便無法變更這項設定。** |

   **請記住：**

   * 如果連線中所有資料集的歷史資料累積大小超過 15 億列，便會出現一則錯誤訊息，說明無法匯入此數量的歷史資料。但是，如果您要新增包含 10 億列歷史資料的資料集並匯入了這些資料，一週之後再新增另一個相同大小的資料集並匯入其歷史資料，這麼做行得通。
   * 系統會為連線中新增的新資料排定優先順序，因此這些資料的延遲最低。
   * 所有回填 (歷史) 資料的匯入速度都較慢。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

工作流程的下一步是[建立資料檢視](/help/data-views/create-dataview.md)。
