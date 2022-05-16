---
title: 建立連線
description: 說明如何在 Customer Journey Analytics 中建立與 Platform 資料集的連線。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: bbb5da146c0c444f97c9b98940afee01d66bd36d
workflow-type: tm+mt
source-wordcount: '2081'
ht-degree: 69%

---

# 建立連線

2022年5月，Customer Journey Analytics(CJA)正在啟動新的「連接」工作流。 以下是新功能的概述：

* 建立連接時，可以啟用滾動資料保留窗口。
* 您可以添加到連接並從連接中刪除資料集。 (刪除資料集會將其從連接中刪除，並影響任何關聯的資料視圖和基礎Analysis Workspace項目。)
* 您可以啟用並請求每個資料集的回填資料。
* 您可以編輯資料集，例如，請求其他回填。
* 可以按資料集導入現有資料。

## 建立和配置連接 {#create-connection}

1. 在CJA中，按一下「連接」頁籤。
1. 按一下「建立新連接」。

   ![連接設定](assets/create-conn1.png)

1. 配置連接設定。

   | 設定 | 說明 |
   | --- | --- |
   | 連線名稱 | 輸入連接的唯一名稱。 |
   | 連線說明 | 描述此連接的目的。 |
   | 沙箱 | 在 Experience Platform 中，選擇您要連線之資料集所屬的沙箱。<p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)可將單一 Platform 例項分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。您可以將沙箱視為包含資料集的「資料庫」。 沙箱可用於控制資料集的存取權限，<p>選取沙箱後，左側欄會顯示您可以從該沙箱提取的所有資料集。 |
   | 啟用滾動資料窗口 | 此設定允許您在連接級別將CJA資料保留定義為月（1個月、3個月、6個月等）的滾動窗口。<p>資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。配置檔案或查找資料集不存在滾動資料窗口設定，因為沒有適用的時間戳。 但是，如果連接包含任何配置檔案或查找資料集（除一個或多個事件資料集外），則該資料將保留在同一時間段。<p> 主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。 |
   | 添加資料集（請參閱下面） | 如果資料集清單中未顯示任何資料集，則添加資料集。 |
   | 資料集名稱 | 選取一或多個要拉進 Customer Journey Analytics 的資料集，然後按一下&#x200B;**[!UICONTROL 「新增」]**<p>(如果有很多資料集可選擇，可使用資料集清單上方的「搜尋資料集」搜尋列，搜尋合適的資料集)。 |
   | 上次更新時間 | 僅對於事件資料集，此設定將自動設定為Experience Platform中基於事件的架構的預設時間戳欄位。 &quot;N/A&quot;表示此資料集不包含任何資料。 |
   | 結構描述 | 這是 [架構](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en) 根據資料集在Adobe Experience Platform建立。 |
   | 資料集類型 | 對於添加到此連接的每個資料集，Customer Journey Analytics會根據傳入的資料自動設定資料集類型。 有 3 種不同的資料集類型：事件資料、設定檔資料、查詢資料。有關資料集類型的說明，請參閱下表。 |
   | 人員 ID | 從可用標識的下拉清單中選擇人員ID。 這些身分識別是在 Experience Platform 的資料集結構中所定義。若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>重要提示：如果沒有人員ID可供選擇，則表示在架構中未定義一個或多個人員ID。 [這部影片](https://www.youtube.com/watch?v=G_ttmGl_LRU)會說明如何在 Experience Platform 中定義身分識別。 |
   | 金鑰 | 僅用於查找資料集（如_id）。 |
   | 比對索引鍵 | 僅用於查找資料集（如_id）。 |
   | 匯入新資料 | 設定為開啟或關閉。 |
   | 回填資料 |  |
   | 回填狀態 | 指示是否正在處理任何回填資料。 |

## 添加和配置資料集 {#add-dataset}

新工作流允許您在建立連接時添加Experience Platform資料集。

1. 在「連接設定」對話框中，按一下 **[!UICONTROL 添加資料集]**。
1. 選擇一個或多個資料集並按一下 **[!UICONTROL 下一個]**。

   請注意，至少需要有一個事件資料集作為連接的一部分。
1. 現在，逐個配置資料集。

   ![配置資料集](assets/add-dataset.png)

   | 設定 | 說明 |
   | --- | --- |
   | 人員 ID | 從可用標識的下拉清單中選擇人員ID。 這些身分識別是在 Experience Platform 的資料集結構中所定義。若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>如果沒有人員 ID 可以選擇，表示結構中尚未定義一或多個人員 ID。這部影片會說明如何在 Experience Platform 中定義身分識別。 |
   | 時間戳記 | 僅對於事件資料集，此設定將自動設定為Experience Platform中基於事件的架構的預設時間戳欄位。 |
   | 匯入新資料 | 如果要建立持續連線，請選擇此選項，如此一來，新增到此連線中資料集的任何新資料批次，都會自動彙整至 Analysis Workspace。可以設定為「開啟」或「關閉」。 |
   | 資料集回填 | 按一下 **[!UICONTROL 請求回填]** 以回填歷史資料。<ul><li>您可以逐個回填每個資料集。</li><li>系統會優先處理新增至連線中資料集的新資料，因此新資料的延遲最低。</li><li>所有回填 (歷史) 資料的匯入速度都會比較慢。延遲受您擁有的歷史資料量的影響。</li><li>Adobe Analytics Source Connector 最多可匯入 13 個月資料 (不論資料量多寡)。</li></ul> |
   | 回填狀態 | 可能的狀態指標有：<ul><li>成功</li><li>X回填處理</li><li>關閉</li></ul> |
   | 資料集 ID | 此ID將自動生成。 |
   | 說明 | 建立此資料集時給予的說明。 |
   | 資料集大小 | 資料集的大小。 |
   | 結構描述 | 這是在Adobe Experience Platform建立資料集時基於的架構。 |
   | 資料集 | 資料集的名稱。 |
   | 預覽: `<dataset name>` | 預覽包含日期、我的ID和標識符列的資料集。 |
   | 移除 | 從連接中刪除此資料集。 |

## 連線預覽 {#preview}

要預覽已建立的連接，請按一下 **[!UICONTROL 連接預覽]** 中。

![連線預覽](assets/create-conn4.png)

此預覽包含列出連接配置的列數。 顯示的列類型取決於您的單個資料集。

## 資料集類型 {#dataset-types}

對於添加到此連接的每個資料集， [!UICONTROL Customer Journey Analytics] 根據傳入的資料自動設定資料集類型。

>[!IMPORTANT]
>
>您需要添加至少一個事件資料集作為連接的一部分。

有 3 種不同的資料集類型：[!UICONTROL 事件]資料、[!UICONTROL 設定檔]資料、[!UICONTROL 查詢]資料。

| 資料集類型 | 說明 | 時間戳記 | 結構描述 | 人員 ID |
|---|---|---|---|---|
| [!UICONTROL 事件] | 代表及時事件的資料 (例如網站造訪、互動、交易、POS 資料、調查資料、廣告曝光數資料等)。例如，這可能是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。若使用事件資料，您可以靈活選擇將哪個 ID 當作人員 ID 使用。 | 系統會自動設定為 [!UICONTROL Experience Platform] 中以事件為基礎的結構之預設時間戳記欄位。 | 任何以具有「時間系列」行為的 XDM 類別為依據的內建或自訂結構。例如「XDM 體驗事件」或「XDM 決策事件」。 | 您可以挑選要包含的人員 ID。在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。其中任何一個都可當作人員 ID 使用。範例包括 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。 |
| [!UICONTROL 查詢] | 在事件或設定檔資料中找到值或索引鍵後，可使用此資料進一步查詢。例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。如需範例，請參閱這個[使用案例](/help/use-cases/b2b.md)。 | 不適用 | 除「XDM 個別設定檔」類別外，任何以具有「記錄」行為的 XDM 類別為基礎的內建或自訂結構。 | 不適用 |
| [!UICONTROL 設定檔] | 套用至[!UICONTROL 事件]資料中訪客、使用者或客戶的資料。例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 任何以「XDM 個別設定檔」類別為基礎的內建或自訂模式。 | 您可以挑選要包含的人員 ID。在 [!DNL Experience Platform] 中定義的每個資料集，都有各自專屬的一組一或多個已定義的人員 ID，例如 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。<br>![人員 ID ](assets/person-id.png)**請注意**：如果您建立的連線包含具有不同 ID 的資料集，報表會反映出這一點。若要確實合併資料集，您需要使用相同的人員 ID。 |

## 以「身分對應」作為人員 ID {#id-map}

Customer Journey Analytics 現在可支援以「身分對應」作為人員 ID。「身分對應」是一種允許使用者上傳索引鍵/值組的對應資料結構。索引鍵是身分識別命名空間，值是保存身分識別值的結構。「身分對應」存在於每個上傳的列/事件，並會相應填入每一列。

只要資料集所使用的結構屬於 [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 類別，一律適用「身分對應」。當您選擇要在 CJA 連線中包含這類資料集，您就可以選擇使用一個欄位作為主要 ID，也可以使用「身分對應」：

![](assets/idmap1.png)

如果您選取「身分對應」，系統會提供另外兩個設定選項：

| 選項 | 說明 |
|---|---|
| [!UICONTROL 使用主要 ID 命名空間] | 這會指示 CJA 在標示 primary=true 屬性的「身分對應」中逐列尋找身分識別，作為該列的人員 ID。也就是說，這會是在 Experience Platform 中劃分資料的主要索引鍵，也是 CJA 訪客 ID 的主要候選項目 (取決於 CJA 連線的資料集設定方式)。 |
| [!UICONTROL 命名空間] | (未使用「主要 ID 命名空間」時，才能使用此選項)身分識別命名空間是 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant) 的元件，用途是作為身分識別相關內容的指標。如果您指定命名空間，CJA 會針對此命名空間索引鍵搜尋每一列的「身分對應」，並使用該命名空間底下的身分識別，作為該列的人員 ID。請注意，CJA 無法執行涵蓋所有列的完整資料集掃描，據以判斷哪些命名空間實際存在，下拉式清單會列出所有可能的命名空間。您需知道資料中指定的命名空間，系統無法自動偵測。 |

### 「身分對應」邊緣案例 {#id-map-edge}

下表提供邊緣案例出現時的兩個設定選項及其處理方式：

| 選項 | 「身分對應」中沒有 ID | 沒有 ID 標示為主要 | 多個 ID 標示為主要 | 單一 ID 標示為主要 | 標示為主要的 ID 具有無效的命名空間 |
|---|---|---|---|---|---|
| **[!UICONTROL 已勾選「使用主要 ID 命名空間」]** | CJA 會捨棄該列。 | 未指定主要 ID，CJA 會捨棄該列。 | 系統會擷取所有命名空間下標示為主要的 ID，彙整成清單，並依字母排序；重新排序後，系統會將第一個命名空間的第一個 ID 視為人員 ID。 | 以標示為主要的單一 ID 作為人員 ID。 | 即使命名空間可能無效 (不在 AEP 中)，CJA 仍會以該命名空間下的主要 ID 作為人員 ID。 |
| **[!UICONTROL 已選取特定「身分對應」命名空間]** | CJA 會捨棄該列。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。(建立連線時只能選取有效的命名空間，因此不可能使用無效的命名空間/ID 作為人員 ID)。 |

### 計算每日事件平均數量

連線中的每個資料集都必須完成這項計算。

1. 前往 [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant)，並建立新查詢。

   查詢如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   此範例中，「analytics_demo_data」是資料集名稱。

1. 執行 `Show Tables` 查詢即可顯示 AEP 中的所有資料集。
