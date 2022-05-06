---
title: 建立連線
description: 說明如何在 Customer Journey Analytics 中建立與 Platform 資料集的連線。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 5ca6c92f1d06cb5a388fa37f232ee0b870f14f33
workflow-type: tm+mt
source-wordcount: '1992'
ht-degree: 89%

---

# 建立連線

連線可讓您將資料集從 [!DNL Adobe Experience Platform] 整合到 [!UICONTROL Analysis Workspace]。若要針對 [!DNL Experience Platform] 資料集製作報表，必須先為 [!DNL Experience Platform] 和 [!UICONTROL Analysis Workspace] 的資料集建立連線。

以下是影片概觀：

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## 必要權限

若要建立 CJA 連線，您需要在 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) 中設定以下權限：

Adobe Experience Platform：
* 資料模型製作：檢視結構描述、管理結構描述
* 資料管理：檢視資料集、管理資料集
* 資料擷取：管理來源

Customer Journey Analytics
* 產品管理員存取權

>[!IMPORTANT]
>
>您可以將多個 [!DNL Experience Platform] 資料集合併到單一連線中。

## 選取沙箱和資料集

1. 移至 [https://analytics.adobe.com](https://analytics.adobe.com) 並使用您的 Adobe ID 登入。

1. 按一下 [!DNL Customer Journey Analytics] 圖示。

1. 按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

1. 按一下右上方的&#x200B;**[!UICONTROL 「建立新連結」]**。

   ![建立連線](assets/create-connection0.png)

1. 在 Experience Platform 中，選擇您要連線之資料集所屬的沙箱。

   Adobe Experience Platform 提供的[沙箱](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hant)可將單一 Platform 例項分割成個別的虛擬環境，以利開發及改進數位體驗應用程式。您可將沙箱視為內含資料集的「資料獨立單位」。沙箱可用於控制資料集的存取權限，選取沙箱後，左側欄會顯示您可以從該沙箱提取的所有資料集。

   >[!IMPORTANT]
   >
   >您無法一次存取多個沙箱內的資料。也就是說，您只能合併位於同一個沙箱中的資料集。

1. 選取一或多個要拉進 [!UICONTROL Customer Journey Analytics] 的資料集，然後按一下&#x200B;**[!UICONTROL 「新增」]**

   (如果有很多資料集可選擇，可使用資料集清單上方的&#x200B;**[!UICONTROL 「搜尋資料集」]**&#x200B;搜尋列，搜尋合適的資料集)。

## 設定資料集

現在您可以在右側設定您所新增的資料集。

![設定資料集](assets/create-connection.png)

1. **[!UICONTROL 資料集類型]**：[!UICONTROL Customer Journey Analytics] 會針對您新增至此連線的各個資料集，根據傳入的資料自動設定資料集類型。

>[!IMPORTANT]
>
>    您需要添加至少一個事件資料集作為連接的一部分。


    有 3 種不同的資料集類型：[!UICONTROL 事件]資料、[!UICONTROL 設定檔]資料、[!UICONTROL 查詢]資料。
    
    |資料集類型|描述|時間戳|架構|人員ID|
    |—|—|
    | [!UICONTROL 事件] |表示時間事件的資料（例如，Web訪問、交互、交易、POS資料、調查資料、廣告印象資料等）。 例如，這可能是典型的點按資料流資料，包含客戶 ID 或 Cookie ID 以及時間戳記。若使用事件資料，您可以靈活選擇將哪個 ID 當作人員 ID 使用。|自動設定為基於事件架構的預設時間戳欄位 [!UICONTROL Experience Platform]。 |任何基於具有「時間系列」行為的XDM類的內置或自定義架構。 例如「XDM 體驗事件」或「XDM 決策事件」。|您可以選擇要包括的人員ID。 在 Experience Platform 中定義的每個資料集結構，都可以有各自專屬的一組一或多個已定義且與身分識別命名空間相關聯的身分。其中任何一個都可當作人員 ID 使用。範例包括 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。|
    | [!UICONTROL 查找] |此資料用於查找在事件或配置檔案資料中找到的值或鍵。 例如，您可以上傳將事件資料中的數值 ID 對應至產品名稱的查詢資料。有關示例，請參見[此用例](/help/use-cases/b2b.md)。 |不適用 |任何基於具有「Record」行為的XDM類的內置或自定義架構，「XDM Individual Profile」類除外。 |不適用 |
    | [!UICONTROL 配置檔案] |應用於以下站點的訪問者、用戶或客戶的資料 [!UICONTROL 事件] 資料。 例如，您可上傳有關客戶的 CRM 資料。|不適用 |任何基於「XDM Individual Profile」類的內置或自定義架構。 |您可以選擇要包括的人員ID。 在  [!DNL Experience Platform]  中定義的每個資料集，都有各自專屬的一組一或多個已定義的人員 ID，例如 Cookie ID、拼接 ID、使用者 ID、追蹤代碼等。&lt;br>![人員ID](assets/person-id.png)**注**:如果建立包含具有不同ID的資料集的連接，則報告將反映這一點。 要真正合併資料集，您需要使用相同的人員ID。 |

1. **[!UICONTROL 資料集 ID]**：此 ID 會自動產生。

1. **[!UICONTROL 時間戳記]**：僅適用於事件資料集，系統會自動將此設定設為 [!UICONTROL Experience Platform] 中以事件為基礎的結構之預設時間戳記欄位。

1. **[!UICONTROL 結構]**：這是在 Adobe Experience Platform 中建立資料集時所依據的[結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=zh-Hant)。

1. **[!UICONTROL 人員 ID]**：您可從可用身分識別的下拉式清單中選取人員 ID。這些身分識別是在 Experience Platform 的資料集結構中所定義。若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。

   >[!IMPORTANT]
   >
   >如果沒有人員 ID 可以選擇，表示結構中尚未定義一或多個人員 ID。[這部影片](https://youtu.be/G_ttmGl_LRU)會說明如何在 Experience Platform 中定義身分識別。

1. 按&#x200B;**[!UICONTROL 「下一步」]**，前往[!UICONTROL 「啟用連線」]對話框。

### 以「身分對應」作為人員 ID

Customer Journey Analytics 現在可支援以「身分對應」作為人員 ID。「身分對應」是一種允許使用者上傳索引鍵/值組的對應資料結構。索引鍵是身分識別命名空間，值是保存身分識別值的結構。「身分對應」存在於每個上傳的列/事件，並會相應填入每一列。

只要資料集所使用的結構屬於 [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 類別，一律適用「身分對應」。當您選擇要在 CJA 連線中包含這類資料集，您就可以選擇使用一個欄位作為主要 ID，也可以使用「身分對應」：

![](assets/idmap1.png)

如果您選取「身分對應」，系統會提供另外兩個設定選項：

| 選項 | 說明 |
|---|---|
| [!UICONTROL 使用主要 ID 命名空間] | 這會指示 CJA 在標示 primary=true 屬性的「身分對應」中逐列尋找身分識別，作為該列的人員 ID。也就是說，這會是在 Experience Platform 中劃分資料的主要索引鍵，也是 CJA 訪客 ID 的主要候選項目 (取決於 CJA 連線的資料集設定方式)。 |
| [!UICONTROL 命名空間] | (未使用「主要 ID 命名空間」時，才能使用此選項)身分識別命名空間是 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant) 的元件，用途是作為身分識別相關內容的指標。如果您指定命名空間，CJA 會針對此命名空間索引鍵搜尋每一列的「身分對應」，並使用該命名空間底下的身分識別，作為該列的人員 ID。請注意，CJA 無法執行涵蓋所有列的完整資料集掃描，據以判斷哪些命名空間實際存在，下拉式清單會列出所有可能的命名空間。您需知道資料中指定的命名空間，系統無法自動偵測。 |

### 「身分對應」邊緣案例

下表提供邊緣案例出現時的兩個設定選項及其處理方式：

| 選項 | 「身分對應」中沒有 ID | 沒有 ID 標示為主要 | 多個 ID 標示為主要 | 單一 ID 標示為主要 | 標示為主要的 ID 具有無效的命名空間 |
|---|---|---|---|---|---|
| **[!UICONTROL 已勾選「使用主要 ID 命名空間」]** | CJA 會捨棄該列。 | 未指定主要 ID，CJA 會捨棄該列。 | 系統會擷取所有命名空間下標示為主要的 ID，彙整成清單，並依字母排序；重新排序後，系統會將第一個命名空間的第一個 ID 視為人員 ID。 | 以標示為主要的單一 ID 作為人員 ID。 | 即使命名空間可能無效 (不在 AEP 中)，CJA 仍會以該命名空間下的主要 ID 作為人員 ID。 |
| **[!UICONTROL 已選取特定「身分對應」命名空間]** | CJA 會捨棄該列。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。 | 系統會擷取您所選命名空間下的所有 ID，彙整成清單，並將第一個 ID 視為人員 ID。(建立連線時只能選取有效的命名空間，因此不可能使用無效的命名空間/ID 作為人員 ID)。 |

## 啟用連線

![啟用連線](assets/create-connection2.png)

1. 若要啟用連線，請為整個連線定義下列設定，即連線中的所有資料集：

   | 選項 | 說明 |
   | --- | --- |
   | [!UICONTROL 連線名稱] | 為連線提供說明名稱。無法儲存無名稱的連線。 |
   | [!UICONTROL 說明] | 新增更多詳細資訊，以便區分此連線與其他連線。 |
   | [!UICONTROL 資料集] | 此連線中包含的資料集。 |
   | [!UICONTROL 從今天開始，自動匯入此連線的所有新資料集。] | 如果要建立持續連線，請選擇此選項，如此一來，新增到此連線中資料集的任何新資料批次，都會自動彙整至 ]Analysis Workspace[!UICONTROL 。 |
   | [!UICONTROL 匯入所有現有資料] | 在您選擇此選項並儲存連線後，此連線中所有資料集來自 [!DNL Experience Platform] 的所有現有 (歷史) 資料都會匯入或回填。日後若有任何新資料集新增至這個已儲存的連線，其所有現有歷史資料也會自動匯入。另請參閱下方的[回填歷史資料](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hant#backfill-historical-data)。<br>**請注意，一旦儲存此連線，便無法變更這項設定。** |
   | [!UICONTROL 每日事件平均數量] | 您必須為連線中的所有資料集指定要匯入的每日事件平均數量 (新資料&#x200B;**和**&#x200B;回填資料)。在下拉式選單中選取任一選項。這樣一來，Adobe 就可以為此資料分配足夠的空間。<br>如果您不清楚公司要匯入的每日事件平均數量，可以在 [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hant) 中執行簡單的 SQL 查詢加以了解。<br>請參閱下方的「計算每日事件平均數量」。 |

1. 按一下&#x200B;**[!UICONTROL 「儲存及建立資料檢視」]**。如需相關文件，請參閱[建立資料檢視](/help/data-views/create-dataview.md)。

### 回填歷史資料

**[!UICONTROL 「匯入所有現有資料」]**&#x200B;可讓您回填歷史資料。請記住以下事項：

* 目前已移除回填 (歷史資料匯入) 限制。過去，您可以自行回填最多 25 億列的資料，若超過這個數字便需有工程技術介入。現在，您可以自行回填資料，沒有任何限制。
* 系統會優先處理新增至連線中資料集的新資料，因此新資料的延遲最低。
* 所有回填 (歷史) 資料的匯入速度都會比較慢。延遲會受您擁有的歷史資料數量，以及所選&#x200B;**[!UICONTROL 「每日事件平均數量」]**&#x200B;設定影響。舉例來說，如果您每天有超過 10 億列資料，還有 3 年的歷史資料，可能就需要數週的時間才能完全匯入。反過來說，如果您每天的資料量少於 100 萬列，而且只有 1 週的歷史資料，則不需 1 小時就能完成匯入作業。
* 回填作業適用於整個連線，並非只是個別適用於各個資料集。
* [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/ingest-data-from-adobe-analytics.html?lang=zh-Hant) 最多可匯入 13 個月資料 (不論資料量多寡)。

### 計算每日事件平均數量

連線中的每個資料集都必須完成這項計算。

1. 前往 [Adobe Experience Platform Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/home.html)，並建立新查詢。

   查詢如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   此範例中，「analytics_demo_data」是資料集名稱。

1. 執行 `Show Tables` 查詢即可顯示 AEP 中的所有資料集。
