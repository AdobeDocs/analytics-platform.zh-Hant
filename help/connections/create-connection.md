---
title: 建立或編輯連線
description: 說明如何在 Customer Journey Analytics 中建立或編輯與 Experience Platform 資料集的連線。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: f93919fda3bbf24fc71c1ff42b62e52f7ddd7a9d
workflow-type: tm+mt
source-wordcount: '3301'
ht-degree: 84%

---

# 建立或編輯連線

透過輔助工作流程，建立連線和編輯工作流程體驗可將所有資料集和連線組態設定彙整到畫面中央處。它提供詳細的資料集選擇、設定和檢閱體驗。可讓您指定資料集類型、大小、綱要、資料集 ID、批次狀態、回填狀態、人員 ID 等重要資訊，以降低連線設定錯誤的風險。以下是功能概觀：

* 當您建立連線時，可以啟用滾動資料保留時間窗口。
* 您可以在連線中新增及移除資料集。 (移除資料集會將其從連線中移除，並影響任何關聯的資料檢視及基礎 Analysis Workspace 專案。)
* 您可以為每個資料集啟用及請求回填資料。
* 例如，您可以編輯資料集來請求另一次回填。
* 您可以為每個資料集匯入現有的資料。

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

## 先決條件

您可以新增至連線的最大資料集數量上限為 100。該組合取決於您公司購買的 Customer Journey Analytics 套件。

如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

| **選取**&#x200B;套件 | **基礎**&#x200B;套件 |
| --- | --- |
| 事件/設定檔/查詢/摘要資料集的任意組合，最多可新增100個 | 每個連線一個事件資料集 |
|  | 每個連線最多99個設定檔、查詢或摘要資料集 |

{style="table-layout:auto"}

## 建立和設定連線 {#create-connection}

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 選取&#x200B;**[!UICONTROL 「建立新連線」]**。

   ![無標題連線設定](assets/create-conn1.png)

1. 進行連線設定。

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 連線名稱]** | 為連線輸入唯一名稱。 |
   | **[!UICONTROL 連線說明]** | 說明此連線的用途。 |
   | **[!UICONTROL 沙箱]** | 在 Experience Platform 中，選擇您要連線之資料集所屬的沙箱。<p>Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sandbox/home)可將單一 Platform 執行個體分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。 您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限。<p>當您選取沙箱後，左側欄會顯示您可以從該沙箱提取的所有資料集。 |
   | **[!UICONTROL 啟用滾動資料時間窗口]** | 勾選這個核取方塊可讓您在連線層級將 Customer Journey Analytics 資料保留定義為以月為單位的滾動時段 (1 個月、3 個月、6 個月等)。<p>資料保留是以事件資料集時間戳記為基礎，僅適用於事件資料集。由於無適用的時間戳記，因此基本資料或查詢資料集不存在滾動資料時間窗口設定。不過，如果您的連線在一個或多個事件資料集之外還包含任何設定檔或查詢資料集，則會為相同時段保留該資料。<p> 主要優點在於您只會儲存或報告適用且實用的資料，並刪除不再實用的舊資料。這有助於您未超過合約限制，並減少超額使用費用的風險。<p>如果您保留預設值（未勾選），Adobe Experience Platform資料保留設定會取代保留期間。 如果您在 Experience Platform 中有 25 個月的資料，Customer Journey Analytics 會透過回填取得 25 個月的資料。如果您在 Platform 中刪除其中 10 個月的資料，Customer Journey Analytics 則會保留剩餘 15 個月的資料。 |
   | **[!UICONTROL 新增資料集]** (請參閱底下) | 如果沒有資料集出現在您的資料集清單中，請新增資料集。 |
   | **[!UICONTROL 資料集名稱]** | 選取一個或多個要拉進 Customer Journey Analytics 中的資料集，然後選取「**[!UICONTROL 新增]**」。<p>(如果有很多資料集可選擇，可使用資料集清單上方的「搜尋資料集」搜尋列，搜尋合適的資料集)。 |
   | **[!UICONTROL 上次更新時間]** | 僅適用於事件資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的綱要中的預設時間戳記欄位。 「不適用」代表此資料集不含任何資料。 |
   | **[!UICONTROL 記錄數]** | Experience Platform 中資料集的上個月記錄總數。 |
   | **[!UICONTROL 綱要]** | 在 Adobe Experience Platform 中建立資料集所根據的[綱要](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/schema/composition)。 |
   | **[!UICONTROL 資料集類型]** | Customer Journey Analytics 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定資料集類型。 有 3 種不同的資料集類型：事件資料、個人基本資料和查詢資料。 請參閱下表提供的資料集類型說明。 |
   | **[!UICONTROL 粒度]** | 資料集中的資料粒度；僅適用於摘要資料集。 |
   | **[!UICONTROL 資料來源類型]** | 資料集的資料來源型別。 不適用於摘要資料集。 |
   | **[!UICONTROL 人員 ID]** | 從可用身分識別的下拉式清單中選取人員 ID。這些身分識別是在 Experience Platform 的資料集結構中所定義。 若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>重要事項：如果沒有人員 ID 可供選擇，表示結構描述中尚未定義一個或多個人員 ID。請觀看[這部影片](https://www.youtube.com/watch?v=G_ttmGl_LRU)，了解如何在 Experience Platform 中定義身分識別。 |
   | **[!UICONTROL 索引鍵]** | 僅適用於查詢資料集 (例如 _id)。 |
   | **[!UICONTROL 比對索引鍵]** | 僅適用於查詢資料集 (例如 _id)。 |
   | **[!UICONTROL 匯入新資料]** | 設定為開啟或關閉。 |
   | **[!UICONTROL 回填資料]** | 您可以要求回填資料集中的資料。 例如，您可以要求回填最近 7 天的資料。正確設定資料集並測試您的連線。 如果一切正常，您就能放心回填剩餘的資料。<p>此外，您也可以啟用按資料集匯入新資料。 |
   | **[!UICONTROL 回填狀態]** | 此狀態指示是否有任何回填資料在處理中。 |

   {style="table-layout:auto"}

## 新增及設定資料集 {#add-dataset}

當您建立連線時，新工作流程可讓您新增 Experience Platform 資料集。

1. 在「連線設定」對話框中，選取「**[!UICONTROL 新增資料集]**」。

1. 在「[!UICONTROL 選取資料集]」步驟中，您會看到 Experience Platform 資料集的清單。

   ![選取資料集](assets/select-datasets.png)

   對於每個資料集，清單會顯示：

   | 欄 | 說明 |
   |---|---|
   | 資料集 | 資料集的名稱。選取名稱即可將您導向 Experience Platform 中的資料集。選取「![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)」可顯示含有資料集更多詳細資訊的快顯視窗。您可以選取[在Platform中編輯] ****，直接在Experience Platform中編輯資料集。 |
   | 資料集類型 | 資料集型別：事件、設定檔、查詢或摘要。 |
   | 記錄數量 | Experience Platform 中資料集的上個月記錄總數。 |
   | 結構描述 | 資料集的結構描述。 選取名稱可將您導向 Experience Platform 中的結構描述。 |
   | 上一個批次 | Experience Platform 中擷取之上一個批次的狀態。請參閱[批次狀態](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/batch/troubleshooting#batch-states)以了解更多資訊。 |
   | 資料集 ID | 資料集的 ID。 |
   | 上次更新時間 | 資料集的最後更新時間戳記。 |


1. 選取一或多個資料集，然後選取「**[!UICONTROL 下一步]**」。連線中必須至少包含一個事件資料集。
   * 若要變更資料集清單中顯示的欄，請選取「![欄位設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)」並選取要在「[!UICONTROL 自訂表格]」對話框中顯示的欄。
   * 要搜尋特定資料集，請使用搜尋欄位「![搜尋](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)」。
   * 要讓所選資料集切換為顯示或隱藏，請選取「![選取](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg)」「**[!UICONTROL 隱藏已選取]**」或者「**[!UICONTROL 顯示已選取]**」。
   * 要將已選取資料集清單中的資料集刪除，請使用「![關閉](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)」。要刪除所有已選取的資料集，請選取「**[!UICONTROL 全部清除]**」。




1. 現在，請逐一設定資料集。

   ![設定資料集](assets/add-dataset.png)

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 人員 ID]** | 僅適用於事件和設定檔資料集。從可用身分識別的下拉式清單中選取人員 ID。這些身分識別是在 Experience Platform 的資料集結構中所定義。 若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>如果沒有人員 ID 可以選擇，表示綱要中尚未定義一或多個人員 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選人員 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。 |
   | **[!UICONTROL 時間戳記]** | 僅適用於事件和摘要資料集，系統會自動將此設定設為Experience Platform中以事件為基礎的結構之預設時間戳記欄位。 |
   | **[!UICONTROL 索引鍵]** | 僅適用於查詢資料集。用於查詢資料集的索引鍵。 |
   | **[!UICONTROL 比對索引鍵]** | 僅適用於查詢資料集。要加入其中一個事件資料集的索引鍵。如果這是空白的清單，您可能尚未新增或設定事件資料集。 |
   | **[!UICONTROL 時區]** | 僅適用於摘要資料。 選取時間序列摘要資料的適當時區。 |
   | **[!UICONTROL 資料來源類型]** | 選取資料來源類型。<br/>資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |
   | **[!UICONTROL 匯入新資料]** | 如果要建立持續連線，請啟用此選項。 在持續連線中，新增到資料集的新資料批次會自動在Workspace中使用。 |
   | **[!UICONTROL 資料集回填]** | 啟用&#x200B;**[!UICONTROL 回填所有現有資料]**&#x200B;以確保所有現有資料都已回填。<br/><br/>選取「**[!UICONTROL 要求回填]**」以回填特定期間的歷史資料。您最多可以定義 10 個資料集回填期間。<ol><li>透過輸入開始和結束資料或使用 ![日曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)選取日期來定義期間。</li><li>選取「**[!UICONTROL 將回填排入佇列]**」將回填加入清單，或選取「**[!UICONTROL 取消]**」以取消。</li></ol>對於每個項目，選取 ![編輯](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)以編輯期間，或選取 ![刪除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg)以刪除該項目。<br/><br/>關於回填：<ul><li>您可以個別回填每個資料集。</li><li>系統會優先處理新增至連線中資料集的新資料，因此新資料的延遲最低。</li><li>所有回填 (歷史) 資料的匯入速度都會比較慢。歷史資料多寡會影響延遲長度。</li><li>Analytics 來源連接器可為生產沙箱可匯入最多 13 個月的資料 (不論資料量多寡)。非生產沙箱的回填期限制為 3 個月。</li></ul> |
   | **[!UICONTROL 轉換資料集]** | 對於特定B2B查詢資料集，您可以啟用資料集轉換，以適當的B2B人員型報表案例。 請參閱[轉換資料集以進行 B2B 查詢](transform-datasets-b2b-lookups.md)，了解更多資訊。 |
   | **[!UICONTROL 回填狀態]** | 可能的狀態指標包括：<ul><li>成功</li><li>正在處理 X 個回填</li><li>關閉</li></ul> |
   | **[!UICONTROL 資料集 ID]** | 此 ID 是自動產生的。 |
   | **[!UICONTROL 說明]** | 建立資料集時為其提供的說明。 |
   | **[!UICONTROL 資料集大小]** | 資料集的大小。 |
   | **[!UICONTROL 綱要]** | 在 Adobe Experience Platform 中建立資料集所根據的綱要。 |
   | **[!UICONTROL 資料集]** | 資料集的名稱。 |
   | **[!UICONTROL 預覽：*資料集名稱&#x200B;*]** | 預覽包含日期、我的 ID 和識別碼等欄的資料集。 |
   | **[!UICONTROL 移除]** | 您可以刪除或移除資料集並變更人員 ID，而不需要刪除整個連線。 刪除或移除可減少資料擷取的相關成本，以及重新建立整個連線和相關資料檢視的繁複流程。 |

   {style="table-layout:auto"}

## 連線預覽 {#preview}

若要預覽您已建立的連線，請在「連線設定」對話框中選取&#x200B;**[!UICONTROL 連線預覽]**。

![連線預覽](assets/create-conn4.png)

此預覽包含列出連線設定的一些欄。顯示的欄類型取決於您的個別資料集。

## 資料集類型 {#dataset-types}

[!UICONTROL Customer Journey Analytics] 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定資料集類型。

>[!IMPORTANT]
>
>將至少一個事件或摘要資料集新增為連線的一部分。

有不同的資料集型別： [!UICONTROL 事件]資料、[!UICONTROL 設定檔]資料、[!UICONTROL 查詢]資料和[!UICONTROL 摘要]資料。

| 資料集類型 | 說明 | 時間戳記 | 綱要 | 人員 ID |
|---|---|---|---|---|
| **[!UICONTROL 事件]** | 代表及時事件的資料。 例如網站造訪、互動、交易、POS資料、調查資料、廣告曝光數資料等。 此資料可能是典型的點按資料流資料，包含客戶ID或Cookie ID以及時間戳記。 若使用事件資料，您可以靈活選擇將哪個ID當作人員ID使用。 | 系統會自動設定為 [!UICONTROL Experience Platform] 中，以事件為基礎的綱要之預設時間戳記欄位。 | 任何以具有「時間系列」行為的 XDM 類別為依據的內建或自訂結構。 例如「XDM 體驗事件」或「XDM 決策事件」。 | 您可以挑選要包含的人員 ID。 在 Experience Platform 中定義的每個資料集綱要，都可以有各自專屬的一組一或多個已定義且與身分命名空間相關聯的身分。任何一個識別碼都可當做人員 ID 使用。範例包括 Cookie ID、彙整 ID、使用者 ID、追蹤程式碼等。 |
| **[!UICONTROL 查詢]** | 您可以將資料集新增為所有資料集型別內的欄位查詢：設定檔、查詢和事件資料集（後者一律受支援）。 這項額外功能擴充了Customer Journey Analytics的功能，可支援包括B2B在內的複雜資料模型。 此資料用於尋找在事件、設定檔或查詢資料中找到的值或索引鍵。您最多可以新增兩個查詢層級。(請注意：[衍生欄位](/help/data-views/derived-fields/derived-fields.md)不能當做連線中尋找的對應索引鍵。)例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。如需範例，請參閱[B2B使用案例](/help/use-cases/b2b/b2b.md)。 | 不適用 | 除「XDM 個別設定檔」類別外，任何以具有「記錄」行為的 XDM 類別為基礎的內建或自訂結構。 | 不適用 |
| **[!UICONTROL 設定檔]** | 套用至[!UICONTROL 事件]人員、使用者或客戶的資料。例如，您可上傳有關客戶的 CRM 資料。 | 不適用 | 任何以「XDM 個別設定檔」類別為基礎的內建或自訂模式。 | 您可以挑選要包含的人員 ID。 在[!DNL Experience Platform]中定義的每個資料集（摘要資料集除外）都有自己的一組定義的一或多個人員ID。 例如，Cookie ID、拼接ID、使用者ID、追蹤代碼等。<br>![人員 ID ](assets/person-id.png)**請注意**：如果您建立的連線包含具有不同 ID 的資料集，報告會反映出這一點。若要合併資料集，您需要使用相同的人員 ID。 |
| **摘要** | 未繫結至個別人員ID的時間序列資料。 摘要資料代表不同彙總層級的彙總資料，例如促銷活動。 您可以在Customer Journey Analytics中使用此資料來支援各種使用案例。 如需詳細資訊，請參閱[摘要資料](/help/data-views/summary-data.md)。 | 自動設為Experience Platform中以事件為基礎的摘要度量結構中的預設時間戳記欄位。 僅支援每小時或每日粒度。 | 任何以「XDM摘要量度」類別為基礎的內建或自訂結構。 | 不適用 |

{style="table-layout:auto"}

## 使用數值欄位做為查閱鍵和查閱值 {#numeric}

如果您想將成本或邊界等數值欄位新增到字串鍵欄位，此查詢功能會很實用。它允許數值做為查閱的一部分，當成鍵或值。 在您的查閱綱要中，您可能會有繫結到 (舉例來說) 您的產品名稱、COGS、行銷活動行銷成本或利潤等的數值。 以下是 Adobe Experience Platform 中的查閱綱要範例：

![查閱綱要](assets/schema.png)

系統現在支援將這些值當做量度或維度引進 Customer Journey Analytics 報告中。當您設定連線並提取查閱資料集時，可以編輯資料集以選取[!UICONTROL 「索引鍵」]和[!UICONTROL 「相符的索引鍵」]：

![編輯資料集](assets/lookup-dataset.png)

當您根據此連線設定資料檢視時，您會將數值作為元件新增到資料檢視中。 然後，任何根據此資料檢視的項目都可以報告這些數值。

## 以「身分對應」作為人員 ID {#id-map}

Customer Journey Analytics 支援以「身分對應」作為人員 ID。 「身分對應」是一種允許使用者上傳索引鍵 -> 值組的對應資料結構。 索引鍵是身分命名空間，值是保存身分識別值的結構。 「身分對應」存在於每個上傳的列/事件，並會相應填入每一列。

只要資料集所使用的結構屬於 [ExperienceEvent XDM](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home) 類別，一律適用「身分對應」。 當您選擇要在 Customer Journey Analytics 連線中包含這類資料集，您就可以選擇使用一個欄位作為主要 ID，也可以使用「身分對應」：

![](assets/idmap1.png)

如果您選取「身分對應」，系統會提供另外兩個設定選項：

| 選項 | 說明 |
|---|---|
| **[!UICONTROL 使用主要 ID 命名空間]** | 此選項會指示Customer Journey Analytics在標示`primary=true`屬性的「身分對應」中尋找身分，並將該身分作為該列的人員ID。 此身分識別是在 Experience Platform 中劃分資料的主要索引鍵，此身分識別也是當做 Customer Journey Analytics 人員 ID 的主要候選者 (取決於資料集在 Customer Journey Analytics 連線中的設定方式)。 |
| **[!UICONTROL 命名空間]** | (未使用「主要 ID 命名空間」時，才能使用此選項)身分識別名稱空間是[Experience Platform身分識別服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/features/namespaces)的元件。 名稱空間可做為身分相關內容的指標。 如果您指定命名空間，Customer Journey Analytics 會針對此命名空間索引鍵搜尋每一列的「身分對應」，並使用該命名空間底下的身分識別，作為該列的人員 ID。由於 Customer Journey Analytics 無法對所有列執行完整的資料集掃描，以判斷哪些命名空間實際存在，因此下拉式清單會列出所有可能的命名空間。了解資料中指定了哪些命名空間；系統不會自動偵測這些命名空間。 |

{style="table-layout:auto"}

### 「身分對應」邊緣案例 {#id-map-edge}

下表提供邊緣案例出現時的兩個設定選項及其處理方式：

| 選項 | 「身分對應」中沒有 ID | 多個 ID，沒有一個標示為主要 | 多個 ID 標示為主要 | 單一 ID，不一定標示為主要 | ID 標示為主要的無效命名空間 |
|---|---|---|---|---|---|
| **[!UICONTROL 已勾選「使用主要 ID 命名空間」]** | Customer Journey Analytics 會刪除該列。 | Customer Journey Analytics 會刪除該列，因為未指定主要 ID。 | 系統會擷取所有命名空間下標示為主要的 ID，彙整成清單，並依字母排序；重新排序後，系統會將第一個命名空間的第一個 ID 視為人員 ID。 | 做為人員 ID 的單一 ID。 | 即使命名空間可能無效 (不存在於 Adobe Experience Platform 中)，Customer Journey Analytics 也會使用該命名空間下的主要 ID 做為人員 ID。 |
| 已選取&#x200B;**[!UICONTROL 特定「身分對應」命名空間]** | Customer Journey Analytics 會刪除該列。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 (建立連線時只能選取有效的命名空間，因此不可能使用無效的命名空間/ID 作為人員 ID)。 |

{style="table-layout:auto"}

## 計算每日事件平均數量 {#average-number}

連線中的每個資料集都要完成這項計算。

1. 前往 [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home)，並建立查詢。

   查詢如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   在此範例中，「analytics_demo_data」是資料集名稱。

2. 若要顯示 Adobe Experience Platform 中的所有資料集，請執行 `Show Tables` 查詢。


## 大型查詢資料集的演算法修剪

在建立連線時，可以新增大型資料集以進行查詢。例如代表產品目錄的資料集，以便在建立報告和視覺效果時查詢描述性的產品資訊。如此大的查詢資料集可能會超過目前以護欄方式實施的最大 1000 萬個唯一查詢，導致跳過其他的資料。

您可以要求對大型查詢資料集進行演算法修剪。此演算法修剪僅保留查詢資料集中與事件資料集內索引鍵相符的資料。這樣，您便不需要載入整個未修剪的查詢資料集。舊的或不常用的項目被刪除，這可能會對報告產生輕微影響，但會帶來顯著的好處。該演算法會回顧 90 天並每週更新。

請聯絡您的 Adob&#x200B;&#x200B;e 支援團隊，取得更多資訊並啟用此功能。
