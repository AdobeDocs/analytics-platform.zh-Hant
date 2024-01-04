---
title: 擷取和使用批次資料
description: 說明如何在 Customer Journey Analytics 中擷取和使用批次資料
solution: Customer Journey Analytics
feature: Basics
exl-id: dd46adee-821f-489c-9350-abcfffe7cc3c
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1948'
ht-degree: 87%

---

# 擷取和使用批次資料

本快速入門指南說明如何將批次資料擷取至 Adobe Experience Platform，然後在 Customer Journey Analytics 中使用該資料。

若要完成此操作，您必須：

- 在 Adobe Experience Platform 中&#x200B;**設定結構和資料集**，定義您要收集的資料的模型 (結構)，以及實際收集資料的位置 (資料集)。

- **使用工作流程**，輕鬆將批次資料上傳至 Adobe Experience Platform 中已設定的資料集。

- 在 Customer Journey Analytics 中&#x200B;**設定連線**。此連線應 (至少) 包含您的 Adobe Experience Platform 資料集。

- 在 Customer Journey Analytics 中&#x200B;**設定資料檢視**，定義您要在 Analysis Workspace 中使用的量度和維度。

- 在 Customer Journey Analytics 中&#x200B;**設定專案**，建立您的報告和視覺效果。

>[!NOTE]
>
>本快速入門手冊是一份簡化的指南，說明如何將批次資料擷取至Adobe Experience Platform並用於Customer Journey Analytics。 強烈建議在提及時研究其他資訊。

## 設定結構和資料集

若要將資料擷取至 Adobe Experience Platform，您必須先定義要收集的資料。所有擷取至 Adobe Experience Platform 的資料都必須符合標準的非正常結構，才能由下游能力和功能識別並處理。體驗資料模型 (XDM) 是以結構形式提供此結構的標準框架。

定義結構後，您可以使用一個或多個資料集來儲存及管理資料收集。資料集是資料集合（通常是表格）的儲存和管理結構，其中包含結構（欄）和欄位（列）。

擷取至 Adobe Experience Platform 的所有資料都必須符合預先定義的結構，才能以資料集形式持續保存。

### 設定結構

為了快速上手，您需要收集一些忠誠度資料，例如忠誠度 ID、忠誠度點數和忠誠度狀態。
您必須先定義用來模型化此資料的結構描述。

若要設定您的結構：

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取[!UICONTROL 「資料管理」]中的&#x200B;**[!UICONTROL 「結構」]**。

1. 選取 **[!UICONTROL 建立結構描述]**..
1. 在建立架構精靈的選取類別步驟中：

   1. 選取 **[!UICONTROL 個別設定檔]**.

      ![建立結構](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    體驗事件結構描述是用來建立 _行為_ 的設定檔（像是場景名稱、要新增至購物車的推播按鈕）。 個別設定檔結構可用來建立設定檔&#x200B;_屬性_ (例如姓名、電子郵件、性別) 模型。

   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。


1. 在 [!UICONTROL 名稱和稽核步驟] 的 [!UICONTROL 建立結構描述] 精靈：

   1. 輸入 **[!UICONTROL 結構描述顯示名稱]** 適用於您的結構描述和（選用） a **[!UICONTROL 說明]**.

      ![命名結構](./assets/create-pr-schema-wizard-step-2.png)

   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 在範例結構描述的結構標籤中：

   1. 在[!UICONTROL 「欄位群組」]中選取&#x200B;**[!UICONTROL 「+ 新增」]**。

      ![新增欄位群組](./assets/add-field-group-button.png)

      欄位群組是可重複使用的物件和屬性集合，可讓您輕鬆擴充結構。

   1. 在[!UICONTROL 「新增欄位群組」]對話框中，從清單中選取&#x200B;**[!UICONTROL 「忠誠度詳細資料」]**&#x200B;欄位群組。

      ![AEP Web SDK ExperienceEvent 欄位群組](./assets/loyalty-fieldgroup.png)

      您可以選取預覽按鈕，以查看屬於此欄位群組之欄位的預覽。

      ![AEP Web SDK ExperienceEvent 欄位群組預覽](./assets/loyalty-fieldgroup-preview.png)

      選取&#x200B;**[!UICONTROL 「返回」]**&#x200B;來關閉預覽。

   1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. 在[!UICONTROL 「結構」]面板中，選取結構名稱旁的 **[!UICONTROL +]**。

   ![範例結構新增欄位按鈕](./assets/example-loalty-schema-plus.png)

1. 在[!UICONTROL 「欄位屬性」]面板中，輸入 `Identification` 作為名稱，**[!UICONTROL 「識別」]**&#x200B;作為[!UICONTROL 顯示名稱]，選取&#x200B;**[!UICONTROL 「物件」]**&#x200B;作為[!UICONTROL 類型]，並選取&#x200B;**[!UICONTROL 「設定檔核心 v2」]**&#x200B;作為[!UICONTROL 欄位群組]。

   ![識別物件](./assets/identifcation-loyalty-field.png)

   識別物件會將識別功能新增至結構描述。 在您的情況下，您需要使用批次資料中的電子郵件地址來識別忠誠度資訊。

   選取&#x200B;**[!UICONTROL 「套用」]**&#x200B;將此物件加入您的結構。

1. 在剛剛新增的識別物件中選取&#x200B;**[!UICONTROL 「電子郵件」]**&#x200B;欄位，然後在[!UICONTROL 「欄位屬性」]面板中，選取&#x200B;**[!UICONTROL 「身分」]**&#x200B;和[!UICONTROL 「身分命名空間」]的&#x200B;**[!UICONTROL 「電子郵件」]**。

   ![指定電子郵件作為身分](./assets/specify-email-loyalty-id.png)

   您正在指定電子郵件地址作為 Adobe Experience Platform Identity 服務可用於結合 (拼接) 設定檔的身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在電子郵件屬性中。

   選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 選擇結構的根層級 (具備結構名稱)，然後選取&#x200B;**[!UICONTROL 「設定檔」]**&#x200B;切換。

   系統會提示您啟用設定檔的結構。啟用後，根據此結構將資料擷取至資料集時，該資料就會合併至即時客戶設定檔中。

   如需詳細資訊，請參閱[啟用結構以用於即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant#profile)。

   >[!IMPORTANT]
   >
   >    儲存啟用設定檔的結構後，便無法再為設定檔停用該結構。

   ![啟用設定檔結構](./assets/enable-for-profile.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

您已建立最小結構，以建立可內嵌至 Adobe Experience Platform 的忠誠度資料模型。該結構可讓您使用電子郵件地址來識別設定檔。透過啟用設定檔的結構，即可確保將批次檔案中的資料新增至即時客戶設定檔。

請參閱[在 UI 中建立和編輯結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有關向結構添加和刪除欄位群組和個別欄位的詳細資訊。

### 設定資料集

您已使用您的結構定義資料模型。您現在必須定義建構以儲存和管理該資料，這會透過資料集完成。

若要設定您的資料集：

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取[!UICONTROL 「資料管理」]中的&#x200B;**[!UICONTROL 「資料集」]**。

2. 選取&#x200B;**[!UICONTROL 「建立資料集」]**。

   ![建立資料集](./assets/create-dataset.png)

3. 選取&#x200B;**[!UICONTROL 「從結構建立資料集」]**。

   ![從結構建立資料集](./assets/create-dataset-from-schema.png)

4. 選取您先前建立的結構並選取&#x200B;**[!UICONTROL 「下一個」]**。

5. 為資料集命名，並 (可選) 提供說明。

   ![命名資料集](./assets/name-your-datatest.png)

6. 選取&#x200B;**[!UICONTROL 「完成」]**。

7. 選取&#x200B;**[!UICONTROL 「設定檔」]**&#x200B;切換。

   系統會提示您啟用設定檔的資料集。資料集一經啟用，即可透過擷取的資料豐富即時客戶設定檔。

   >[!IMPORTANT]
   >
   >只有當資料集所遵循的結構同樣啟用設定檔時，您才能啟用設定檔的資料集。

   ![啟用設定檔結構](./assets/loyalty-dataset-profile.png)

請參閱[資料集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant)，了解如何檢視、預覽、建立、刪除資料集的詳細資訊。以及為即時客戶設定檔啟用資料集的方法。


## 使用工作流程

您可以使用工作流程功能將批次資料上傳至 Adobe Experience Platform。您使用的批次檔案範例為 CSV 檔案，其中包含下列內容：

```
email,loyaltyID,points,status
abrocking0@blog.com,793406,82.16,Silver
wnichol1@ycombinator.com,988654,40.39,Gold
paisbett2@slideshare.net,444897,91.25,Bronze
bdiamant3@xinhuanet.com,239658,57.87,Gold
ppales4@nsw.gov.au,365384,82.71,Silver
...
```

若要使用工作流程：

1. 在 Platform UI 中，自左側邊欄中選取&#x200B;**[!UICONTROL 「工作流程」]**。

2. 選取&#x200B;**[!UICONTROL 「將 CSV 對應至 XDM 結構」]**。選取&#x200B;**[!UICONTROL 「啟動」]**。

   ![將 CSV 對應至 XDN](./assets/workflow-mapcsvtoxdm.png)

3. 在[!UICONTROL 「將 CSV 對應至 XDM 結構」]畫面，在[!UICONTROL 資料流詳細資訊]步驟：

   選取&#x200B;**[!UICONTROL 「現有資料集」]**，請從資料集清單中選取資料集，並命名您的[!UICONTROL 資料流名稱]。

   ![資料流](./assets/workflow-dataflowdetail.png)

   選取&#x200B;**[!UICONTROL 「下一步」]**。

4. 在[!UICONTROL 選擇資料]步驟：

   拖放或選取&#x200B;**[!UICONTROL 「選擇檔案」]**&#x200B;來選取含有忠誠度資料的 CSV 檔案。您會看到忠誠度資料的預覽。

   ![選擇資料](./assets/workflow-selectdata.png)

   選取&#x200B;**[!UICONTROL 「下一步」]**。

5. 在[!UICONTROL 對應]步驟：

   將您的資料從 CSV 檔案對應至結構中的資料。使用 AI 時，工作流程功能會嘗試自動將批次資料欄位對應至結構欄位。

   ![對應您的資料](./assets/workflow-dataflow-mapping.png)

   您可以使用&#x200B;**[!UICONTROL 「預覽資料」]**&#x200B;查看已對應資料的預覽。

   ![預覽對應](./assets/workflow-dataflow-mapping-preview.png)

6. 選取&#x200B;**[!UICONTROL 「完成」]**&#x200B;開始將批次資料擷取至 Adobe Experience Platform。

另請參閱 [將CSV檔案對應至現有的XDM結構描述](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema.html) 有關下列專案的詳細資訊：

- 當您的傳入資料與XDM結構描述不相容時，如何對應資料。
- 使用對應範本，
- 使用計算欄位以確保您的批次資料符合結構描述預期，
- 及更多內容。


## 設定連線

若要在 Customer Journey Analytics 中使用 Adobe Experience Platform 資料，您可以建立連線，其中包含設定結構、資料集和工作流程所產生的資料。

連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對這些資料集製作報表，必須先為Adobe Experience Platform和工作區的資料集建立連線。

若要建立連線，請執行以下操作：

1. 在 Customer Journey Analytics UI 中，選取頂部導覽中的&#x200B;**[!UICONTROL 「連線」]**。

2. 選取&#x200B;**[!UICONTROL 「建立新連線」]**。

3. 在[!UICONTROL 「無標題連線」]畫面中：

   在[!UICONTROL 「連線設定」]中為連線命名並提供說明。

   從[!UICONTROL 「資料設定」]的[!UICONTROL 「沙箱」]清單中選取正確沙箱，並從[!UICONTROL 「每日事件平均數」]清單中選取每日事件數。

   ![連線設定](./assets/cja-connections-1.png)

   選取&#x200B;**[!UICONTROL 「新增資料集」]**。

   在[!UICONTROL 新增資料集]的[!UICONTROL 選取資料集]步驟：

   - 選取您先前建立的資料集 (`Example Loyalty Dataset`) 和您要加入連線的任何其他資料集。

     ![新增資料集](./assets/cja-connections-2.png)

   - 選取&#x200B;**[!UICONTROL 「下一步」]**。

   在[!UICONTROL 新增資料集]的[!UICONTROL 資料集設定]步驟：

   - 對於每個資料集：

      - 在 Adobe Experience Platform 中，從資料集結構描述中所定義的可用身分中選取[!UICONTROL 人員 ID]。

      - 從[!UICONTROL 「資料來源類型」]清單中選取正確的資料來源。如果您指定&#x200B;**[!UICONTROL 「其他」]**，請為您的資料來源新增說明。

      - 根據您的偏好設定，設定&#x200B;**[!UICONTROL 匯入所有新資料]**&#x200B;和&#x200B;**[!UICONTROL 資料集回填現有資料]**。

     ![設定資料集](./assets/cja-connections-3.png)

   - 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

   選取&#x200B;**[!UICONTROL 「儲存」]**。

如需如何建立和管理連線，以及如何選取和合併資料集的詳細資訊，請參閱[連線概觀](../connections/overview.md)。

## 設定資料檢視

資料檢視是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。它指定 Analysis Workspace 中可用的所有維度和量度，以及這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

若要建立資料檢視，請執行以下操作：

1. 在 Customer Journey Analytics UI 中，選取頂部導覽中的&#x200B;**[!UICONTROL 「資料檢視」]**。

2. 選取&#x200B;**[!UICONTROL 「建立新的資料檢視」]**。

3. 在[!UICONTROL 設定]步驟：

   從[!UICONTROL 「連線」]清單中選取您的連線。

   為連線命名，並 (可選) 提供說明。

   ![資料檢視設定](./assets/cja-dataview-1.png)

   選取&#x200B;**[!UICONTROL 「儲存並繼續」]**。

4. 在[!UICONTROL 元件]步驟：

   將您要納入的任何結構欄位和/或標準元件新增至[!UICONTROL 量度]或[!UICONTROL 維度]元件框。

   ![資料檢視元件](./assets/cja-dataview-2.png)

   選取&#x200B;**[!UICONTROL 「儲存並繼續」]**。

5. 在[!UICONTROL 設定]步驟：

   ![資料檢視設定](./assets/cja-dataview-3.png)

   保留設定原樣並選取&#x200B;**[!UICONTROL 「儲存並完成」]**。

如需如何建立和編輯資料檢視、可在資料檢視中使用哪些元件，以及如何使用篩選器和工作階段設定的詳細資訊，請參閱[資料檢視概觀](../data-views/data-views.md)。


## 設定專案

Analysis Workspace 是彈性的瀏覽器工具，可讓您根據資料快速建立分析及分享見解。您可以使用工作區專案合併資料元件、表格和視覺效果，進行分析並與貴組織的任何人分享。

若要建立專案，請執行以下操作：

1. 在 Customer Journey Analytics UI 中，選取頂部導覽中的&#x200B;**[!UICONTROL 「專案」]**。

2. 在左側導覽中選取&#x200B;**[!UICONTROL 「專案」]**。

3. 選取&#x200B;**[!UICONTROL 「建立專案」]**。

   ![工作區專案](./assets/cja-projects-1.png)

   選取&#x200B;**[!UICONTROL 「空白專案」]**。

   ![工作區 – 空白專案](./assets/cja-projects-2.png)

4. 從清單中選取您的資料檢視。

   ![工作區選取資料檢視](./assets/cja-projects-3.png)。

5. 若要建立您的第一個報表，請開始將維度和量度拖放至 [!UICONTROL 自由表格] 在 [!UICONTROL 面板]. 例如，拖曳 `Program Points Balance`和 `Page View` 做為量度 而 `email` 作為維度，快速概覽已造訪過您網站且屬於收集忠誠點數之忠誠計劃一部分的設定檔。

   ![工作區 – 第一份報告](./assets/cja-projects-5.png)

如需如何使用元件、視覺效果和面板建立專案和建立分析的詳細資訊，請參閱 [Analysis Workspace 概觀](../analysis-workspace/home.md)。

>[!SUCCESS]
>
>您已完成所有步驟。從定義您要收集的忠誠度資料 (結構)，以及要將其儲存在 Adobe Experience Platform 中的何處 (資料集) 開始，您已設定工作流程，將忠誠度資料批次上傳至資料集。您已在 Customer Journey Analytics 中定義連線，以使用擷取的忠誠度資料和其他資料。您的資料檢視定義可讓您指定要使用的維度和量度，最後，您建立了第一個可視覺化和分析資料的專案。
