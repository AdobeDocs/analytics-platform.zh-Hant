---
title: 建立連線
description: 說明如何在 Customer Journey Analytics 中建立與 Platform 資料集的連線。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 7bcfedb472c26605e53805a09ef827fd20a1f986
workflow-type: tm+mt
source-wordcount: '2605'
ht-degree: 60%

---

# 建立連線

最近在Customer Journey Analytics中啟動新的「連線」工作流程。 透過輔助工作流程，新的連線建立和編輯工作流程體驗可將所有資料集和連線組態設定彙整到畫面中央處。  您提供詳細的資料集選擇、設定和檢閱體驗，以及資料集型別、大小、結構描述、資料集ID、批次狀態、回填狀態、人員ID等重要資訊，以降低連線設定錯誤的風險。 以下是新功能總覽：

* 當您建立連線時，可以啟用滾動資料保留時間窗口。
* 您可以在連線中新增及移除資料集。 (移除資料集會將其從連線中移除，並影響任何關聯的資料檢視及基礎 Analysis Workspace 專案。)
* 您可以為每個資料集啟用及請求回填資料。
* 例如，您可以編輯資料集來請求另一次回填。
* 您可以為每個資料集匯入現有的資料。

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## 建立和設定連線 {#create-connection}

1. 在 Customer Journey Analytics 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 按一下&#x200B;**[!UICONTROL 建立新連線]**。

   ![連線設定](assets/create-conn1.png)

1. 進行連線設定。

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 連線名稱]** | 為連線輸入唯一名稱。 |
   | **[!UICONTROL 連線說明]** | 說明此連線的用途。 |
   | **[!UICONTROL 沙箱]** | 在 Experience Platform 中，選擇您要連線之資料集所屬的沙箱。<p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)可將單一 Platform 執行個體分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。 您可以將沙箱視為內含資料集的「資料獨立單位」。 沙箱可用於控制對資料集的存取。<p>當您選取沙箱後，左側欄會顯示您可以從該沙箱提取的所有資料集。 |
   | **[!UICONTROL 啟用滾動資料時間窗口]** | 勾選此核取方塊後，您可以在連線層級將Customer Journey Analytics資料保留定義為以月為單位的滾動時段（1個月、3個月、6個月等）。<p>資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此基本資料或查詢資料集不存在滾動資料時間窗口設定。不過，如果您的連線包含任何設定檔或查詢資料集（一或多個事件資料集除外），則會為相同時段保留該資料。<p> 主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。<p>如果您保留預設值（未勾選），保留期間會由Adobe Experience Platform資料保留設定取代。 如果您的Experience Platform中有25個月的資料，則Customer Journey Analytics會透過回填取得25個月的資料。 如果您在Platform中刪除其中10個月，Customer Journey Analytics將保留剩餘15個月。 |
   | **[!UICONTROL 新增資料集]** (請參閱底下) | 如果沒有資料集出現在您的資料集清單中，請新增資料集。 |
   | **[!UICONTROL 資料集名稱]** | 選取一或多個要拉進Customer Journey Analytics的資料集，然後按一下 **[!UICONTROL 新增]**.<p>（如果有很多資料集可選擇，可使用資料集清單上方的「搜尋資料集」搜尋列，搜尋合適的資料集）。 |
   | **[!UICONTROL 上次更新時間]** | 僅適用於事件資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的結構描述中的預設時間戳記欄位。 「不適用」代表此資料集不含任何資料。 |
   | **[!UICONTROL 結構描述]** | 此 [綱要](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hant) 根據在Adobe Experience Platform中建立的資料集。 |
   | **[!UICONTROL 資料集類型]** | Customer Journey Analytics 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定資料集類型。 有 3 種不同的資料集類型：事件資料、個人基本資料和查詢資料。 請參閱下表提供的資料集類型說明。 |
   | **[!UICONTROL 人員 ID]** | 從可用身分識別的下拉式清單中選取人員ID。 這些身分識別是在 Experience Platform 的資料集結構中所定義。 若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>重要事項：如果沒有人員 ID 可供選擇，表示結構描述中尚未定義一個或多個人員 ID。 請觀看[這部影片](https://www.youtube.com/watch?v=G_ttmGl_LRU)，了解如何在 Experience Platform 中定義身分識別。 |
   | **[!UICONTROL 索引鍵]** | 僅適用於查詢資料集 (例如 _id)。 |
   | **[!UICONTROL 相符的索引鍵]** | 僅適用於查詢資料集 (例如 _id)。 |
   | **[!UICONTROL 匯入新資料]** | 設定為開啟或關閉。 |
   | **[!UICONTROL 回填資料]** | 您可以要求根據事件時間戳記，將資料回填到資料集。 舉例來說，您可以要求回填最近 7 天的資料、設定適用的人員 ID，並測試連線是否設定正確。 如果一切正常，您就能放心回填剩餘的資料。<p>此外，您也可以啟用按資料集匯入新資料。 例如，啟用匯入新資料僅供查看資料用途。 |
   | **[!UICONTROL 回填狀態]** | 指出是否有任何回填資料在處理中。 |

   {style="table-layout:auto"}

## 新增及設定資料集 {#add-dataset}

當您建立連線時，新工作流程可讓您新增 Experience Platform 資料集。

1. 在「連線設定」對話框中，按一下&#x200B;**[!UICONTROL 新增資料集]**。

2. 選取一個或多個資料集，然後按&#x200B;**[!UICONTROL 下一步]**。連線中必須至少包含一個事件資料集。

3. 現在請逐一設定資料集。

   ![設定資料集](assets/add-dataset.png)

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 人員 ID]** | 從可用身分識別的下拉式清單中選取人員ID。 這些身分識別是在 Experience Platform 的資料集結構中所定義。 若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>如果沒有人員 ID 可以選擇，表示結構中尚未定義一或多個人員 ID。 請觀看這部影片，了解如何在 Experience Platform 中定義身分識別。 |
   | **[!UICONTROL 時間戳記]** | 僅適用於事件資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的結構描述中的預設時間戳記欄位。 |
   | **[!UICONTROL 資料來源類型]** | 選取資料來源型別。 <br/>資料來源型別包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>此欄位用於調查使用中的資料來源型別。 |
   | **[!UICONTROL 匯入新資料]** | 如果您要建立持續連線，請選取此選項，如此一來，新增到此連線中資料集的任何新資料批次都會自動流入工作區。 可設為 [!UICONTROL 開啟] 或 [!UICONTROL 關閉]. |
   | **[!UICONTROL 資料集回填]** | 選取 **[!UICONTROL 請求回填]** 以回填歷史資料。<ul><li>您可以個別回填每個資料集。</li><li>您會優先處理新增至連線中資料集的新資料，因此這些新資料的延遲最低。</li><li>所有回填 (歷史) 資料的匯入速度都會比較慢。 延遲會受您有多少歷史資料所影響。</li><li>Adobe Analytics來源聯結器最多可匯入13個月的生產沙箱資料（不論大小）。 非生產沙箱中的回填限製為3個月。</li></ul> |
   | **[!UICONTROL 回填狀態]** | 可能的狀態指標包括：<ul><li>成功</li><li>正在處理 X 個回填</li><li>關閉</li></ul> |
   | **[!UICONTROL 資料集 ID]** | 此 ID 是自動產生的。 |
   | **[!UICONTROL 說明]** | 建立資料集時為其提供的說明。 |
   | **[!UICONTROL 資料集大小]** | 資料集的大小。 |
   | **[!UICONTROL 結構描述]** | 在Adobe Experience Platform中建立資料集所根據的結構描述。 |
   | **[!UICONTROL 資料集]** | 資料集的名稱。 |
   | **[!UICONTROL 預覽]**：`<dataset name>` | 預覽包含日期、我的ID和識別碼等欄的資料集。 |
   | **[!UICONTROL 移除]** | 您可以刪除或移除資料集並變更人員 ID，而不需要刪除整個連線。 刪除或移除可減少資料擷取的相關成本，以及重新建立整個連線和相關資料檢視的繁複程式。 |

   {style="table-layout:auto"}

## 連線預覽 {#preview}

若要預覽您已建立的連線，請在「連線設定」對話框中按一下&#x200B;**[!UICONTROL 連線預覽]**。

![連線預覽](assets/create-conn4.png)

此預覽包含一些列有連線設定的欄。 顯示的欄類型取決於您的個別資料集。

## 資料集類型 {#dataset-types}

對於您新增至此連線的每個資料集， [!UICONTROL Customer Journey Analytics] 會根據傳入的資料自動設定資料集型別。

>[!IMPORTANT]
>
>您必須將至少一個事件資料集新增為連線的一部分。

有三種不同的資料集型別： [!UICONTROL 事件] 資料， [!UICONTROL 設定檔] 資料，以及 [!UICONTROL 查詢] 資料。

| 資料集類型 | 說明 | 時間戳記 | 結構描述 | 人員 ID |
|---|---|---|---|---|
| **[!UICONTROL 事件]** | 代表及時事件的資料（例如網站造訪、互動、交易、POS資料、調查資料、廣告曝光數資料等）。 例如，此資料可能是典型的點按資料流資料，包含客戶ID或Cookie ID以及時間戳記。 若使用事件資料，您可以靈活選擇將哪個 ID 當作人員 ID 使用。 | 系統會自動設定為 [!UICONTROL Experience Platform] 中以事件為基礎的結構之預設時間戳記欄位。 | 任何以具有「時間系列」行為的 XDM 類別為依據的內建或自訂結構。 例如「XDM 體驗事件」或「XDM 決策事件」。 | 您可以挑選要包含的人員 ID。 在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。 這些身分中的任何一個都可當作人員ID使用。 範例包括Cookie ID、拼接ID、使用者ID、追蹤代碼等。 |
| **[!UICONTROL 查詢]** | 您現在可以將資料集新增為所有資料集型別中的欄位查詢：設定檔、查詢和事件資料集（後者一律支援）。 這項額外功能擴充了CJA支援複雜資料模型（包括B2B CDP）的能力。 此資料用於查詢在事件、設定檔或查詢資料中找到的值或索引鍵。 您最多可以新增兩個查閱層級。 (請注意 [衍生欄位](/help/data-views/derived-fields/derived-fields.md) 不能用作連線中查閱的相符索引鍵。) 例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。另請參閱 [B2B使用案例](/help/use-cases/b2b/b2b.md) 例如。 | 不適用 | 除「XDM 個別設定檔」類別外，任何以具有「記錄」行為的 XDM 類別為基礎的內建或自訂結構。 | 不適用 |
| **[!UICONTROL 設定檔]** | 套用至下列位置中個人、使用者或客戶的資料： [!UICONTROL 事件] 資料。 例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 任何以「XDM 個別設定檔」類別為基礎的內建或自訂模式。 | 您可以挑選要包含的人員 ID。 中定義的每個資料集 [!DNL Experience Platform] 有自己的一組一或多個已定義的人員ID，例如Cookie ID、彙整ID、使用者ID、追蹤代碼等。<br>![個人ID ](assets/person-id.png)**注意**：如果您建立的連線包含具有不同ID的資料集，報表會反映這一點。 若要確實合併資料集，您需要使用相同的人員 ID。 |

{style="table-layout:auto"}

## 使用數值欄位做為查閱鍵和查閱值 {#numeric}

如果您想要將成本或利潤等數值欄位新增至字串鍵欄位，此查詢功能會很有用。 它允許數值做為查閱的一部分，當成鍵或值。 在您的查閱結構描述中，您可能會有繫結到 (舉例來說) 您的產品名稱、COGS、行銷活動行銷成本或利潤等的數值。 以下是 Adobe Experience Platform 中的查閱結構描述範例：

![查閱結構描述](assets/schema.png)

您現在支援將這些值當做量度或維度引入Customer Journey Analytics報表。 當您設定連線並提取查閱資料集時，可以編輯資料集以選取[!UICONTROL 「索引鍵」]和[!UICONTROL 「相符的索引鍵」]：

![編輯資料集](assets/lookup-dataset.png)

當您根據此連線設定資料檢視時，您會將數值作為元件新增到資料檢視中。 然後，任何根據此資料檢視的項目都可以報告這些數值。

## 以「身分對應」作為人員 ID {#id-map}

Customer Journey Analytics 支援以「身分對應」作為人員 ID。 「身分對應」是一種允許使用者上傳索引鍵 -> 值組的對應資料結構。 索引鍵是身分識別命名空間，值是保存身分識別值的結構。 「身分對應」存在於每個上傳的列/事件，並會相應填入每一列。

只要資料集所使用的結構屬於 [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 類別，一律適用「身分對應」。 當您選取要包含在Customer Journey Analytics連線中的資料集時，您可選擇選取欄位作為主要ID或身分對應：

![](assets/idmap1.png)

如果您選取「身分對應」，系統會提供另外兩個設定選項：

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 使用主要 ID 命名空間]** | 此選項會指示Customer Journey Analytics在標示primary=true屬性的「身分對應」中逐列尋找身分識別，並將該身分識別當作該列的人員ID。 此身分識別是用於Experience Platform分割的主要金鑰。 此外，此身分識別也是Customer Journey Analytics人員ID的主要候選專案(取決於Customer Journey Analytics連線中資料集的設定方式)。 |
| **[!UICONTROL 命名空間]** | (未使用「主要 ID 命名空間」時，才能使用此選項)身分識別命名空間是 [ Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html) 的元件，用途是作為身分識別相關內容的指標。 如果您指定名稱空間，Customer Journey Analytics會針對此名稱空間索引鍵搜尋每一列的「身分對應」，然後使用該名稱空間底下的身分識別作為該列的人員ID。 由於Customer Journey Analytics無法對所有列執行完整的資料集掃描，以判斷哪些名稱空間存在，因此下拉式清單中會顯示所有可能的名稱空間。 您必須知道資料中指定了哪些名稱空間，系統不會自動偵測這些名稱空間。 |

{style="table-layout:auto"}

### 「身分對應」邊緣案例 {#id-map-edge}

下表提供邊緣案例出現時的兩個設定選項及其處理方式：

| 選項 | 「身分對應」中沒有 ID | 多個 ID，沒有一個標示為主要 | 多個 ID 標示為主要 | 單一 ID，不一定標示為主要 | ID 標示為主要的無效命名空間 |
|---|---|---|---|---|---|
| **[!UICONTROL 已勾選「使用主要 ID 命名空間」]** | Customer Journey Analytics會捨棄該列。 | 資料列會被Customer Journey Analytics捨棄，因為未指定主要ID。 | 系統會擷取所有命名空間下標示為主要的 ID，彙整成清單，然後會依字母排序；有了新的排序，第一個名稱空間及其第一個ID會用作人員ID。 | 作為個人 ID 的單一 ID。 | 即使名稱空間可能無效(不在Adobe Experience Platform中)，Customer Journey Analytics仍會使用該名稱空間下的主要ID作為人員ID。 |
| **[!UICONTROL 已選取特定「身分對應」命名空間]** | Customer Journey Analytics會捨棄該列。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 (建立連線時只能選取有效的命名空間，因此不可能使用無效的命名空間/ID 作為人員 ID)。 |

{style="table-layout:auto"}

## 計算每日事件平均數量 {#average-number}

連線中的每個資料集都會完成這項計算。

1. 前往 [Adobe Experience Platform查詢服務](https://experienceleague.adobe.com/docs/experience-platform/query/home.html) 和建立查詢。

   查詢如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   此範例中，「analytics_demo_data」是資料集名稱。

2. 若要顯示Adobe Experience Platform中存在的所有資料集，請執行 `Show Tables` 查詢。
