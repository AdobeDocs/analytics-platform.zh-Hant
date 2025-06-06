---
title: 使用來源連接器擷取和使用資料
description: 說明如何使用 Customer Journey Analytics 中的來源連接器擷取和使用資料
solution: Customer Journey Analytics
feature: Basics
exl-id: 813d3213-86b3-431a-821c-174e5e36d032
role: Admin
source-git-commit: bc2c959497230d7672d43d5cd409ca62d4627d6a
workflow-type: tm+mt
source-wordcount: '2049'
ht-degree: 77%

---

# 使用來源連接器擷取和使用資料

本快速入門指南說明如何使用資料提供者的來源連接器將資料擷取至 Adobe Experience Platform，然後在 Customer Journey Analytics 中使用該資料。

若要完成此操作，您必須：

- 在 Adobe Experience Platform 中&#x200B;**設定結構和資料集**，定義您要收集的資料的模型 (結構)，以及實際收集資料的位置 (資料集)。

- 在 Adobe Experience Platform 中&#x200B;**使用來源連接器**，將資料匯入已設定的資料集。

- 在 Customer Journey Analytics 中&#x200B;**設定連線**。此連線應 (至少) 包含您的 Adobe Experience Platform 資料集。

- 在 Customer Journey Analytics 中&#x200B;**設定資料檢視**，定義您要在 Analysis Workspace 中使用的量度和維度。

- 在 Customer Journey Analytics 中&#x200B;**設定專案**，建立您的報告和視覺效果。



>[!NOTE]
>
>本快速入門手冊是一份簡化的指南，說明如何使用來源聯結器將資料擷取至Adobe Experience Platform，並在Customer Journey Analytics中使用。 強烈建議在提及時研究其他資訊。


## 設定結構和資料集

若要將資料內嵌至Adobe Experience Platform，您必須先定義要收集哪些資料。 所有擷取至 Adobe Experience Platform 的資料都必須符合標準的非正常結構，才能由下游能力和功能識別並處理。體驗資料模型(XDM)是標準架構，以結構描述的形式提供結構。

定義結構後，您可以使用一個或多個資料集來儲存及管理資料收集。資料集是資料集合（通常是表格）的儲存和管理結構，其中包含結構（欄）和欄位（列）。

擷取至 Adobe Experience Platform 的所有資料都必須符合預先定義的結構，才能以資料集形式持續保存。

### 設定結構

為了快速上手，您需要收集一些忠誠度資料，例如忠誠度 ID、忠誠度點數和忠誠度狀態。
您必須先定義用來模型化此資料的結構描述。

若要設定您的結構：

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取[!UICONTROL 「資料管理」]中的&#x200B;**[!UICONTROL 「結構」]**。

1. 選取&#x200B;**[!UICONTROL 建立結構描述]**。
.
1. 在建立架構精靈的選取類別步驟中：

   1. 選取&#x200B;**[!UICONTROL 個別設定檔]**。

      ![使用選取的個別設定檔建立結構描述視窗](./assets/create-pr-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    體驗事件結構描述可用來建立設定檔&#x200B;_行為_ (例如場景名稱、推播按鈕至新增至購物車) 模型。個體設定檔結構描述可用來建立設定檔&#x200B;_屬性_ (例如姓名、電子郵件、性別) 模型。

   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。


1. 在「[!UICONTROL 建立結構描述]」精靈的「[!UICONTROL 命名和審查步驟]」中：

   1. 輸入您結構描述的&#x200B;**[!UICONTROL 結構描述顯示名稱]**&#x200B;與 (選用) **[!UICONTROL 說明]**。

      ![建立結構描述視窗，顯示用來命名結構描述](./assets/create-pr-schema-wizard-step-2.png)的欄位

   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 在範例結構描述的結構標籤中：

   1. 在[!UICONTROL 「欄位群組」]中選取&#x200B;**[!UICONTROL 「+ 新增」]**。

      ![建立顯示[新增]欄位群組的結構描述視窗](./assets/add-field-group-button.png)

      欄位群組是可重複使用的物件和屬性集合，可讓您輕鬆擴充結構。

   1. 在[!UICONTROL 「新增欄位群組」]對話框中，從清單中選取&#x200B;**[!UICONTROL 「忠誠度詳細資料」]**&#x200B;欄位群組。

      ![AEP Web SDK ExperienceEvent 欄位群組](./assets/loyalty-fieldgroup.png)

      您可以選取預覽按鈕，以查看屬於此欄位群組之欄位的預覽。

      ![AEP Web SDK ExperienceEvent 欄位群組預覽](./assets/loyalty-fieldgroup-preview.png)

      選取&#x200B;**[!UICONTROL 「返回」]**&#x200B;來關閉預覽。

   1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. 在[!UICONTROL 「結構」]面板中，選取結構名稱旁的 **[!UICONTROL +]**。

   ![範例結構新增欄位按鈕](./assets/example-loalty-schema-plus.png)

1. 在[!UICONTROL 「欄位屬性」]面板中，輸入 `Identification` 作為名稱，**[!UICONTROL 「識別」]**&#x200B;作為[!UICONTROL 顯示名稱]，選取&#x200B;**[!UICONTROL 「物件」]**&#x200B;作為[!UICONTROL 類型]，並選取&#x200B;**[!UICONTROL 「輪廓核心 v2」]**&#x200B;作為[!UICONTROL 欄位群組]。

   ![識別物件](./assets/identifcation-loyalty-field.png)

   此識別物件會將識別功能新增至結構描述。 在您的情況下，您會想要使用批次資料中的電子郵件地址來識別忠誠度資訊。

   選取&#x200B;**[!UICONTROL 「套用」]**&#x200B;將此物件加入您的結構。

1. 在剛剛新增的身分識別物件中選取&#x200B;**[!UICONTROL 「電子郵件」]**&#x200B;欄位，然後在[!UICONTROL 「欄位屬性」]面板中，選取&#x200B;**[!UICONTROL 「身分識別」]**&#x200B;和[!UICONTROL 「身分識別命名空間」]的&#x200B;**[!UICONTROL 「電子郵件」]**。

   ![指定電子郵件作為身分識別](./assets/specify-email-loyalty-id.png)

   您將電子郵件地址指定為 Adobe Experience Platform Identity 服務可用於結合 (拼接) 輪廓行為的身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在電子郵件屬性中。

1. 選擇結構的根層級 (具備結構名稱)，然後選取&#x200B;**[!UICONTROL 「輪廓」]**&#x200B;切換。

   系統會提示您啟用輪廓的結構。啟用後，根據此結構將資料攝取至資料集時，該資料就會合併至即時客戶設定檔中。

   如需詳細資訊，請參閱[啟用結構以用於即時客戶輪廓](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant#profile)。

   >[!IMPORTANT]
   >
   >    儲存啟用輪廓的結構後，便無法再為輪廓停用該結構。

   ![啟用輪廓結構](./assets/enable-for-profile.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

您已建立最小結構，以建立可內嵌至 Adobe Experience Platform 的忠誠度資料模型。該結構可讓您使用電子郵件地址來識別輪廓。透過啟用輪廓的結構，即可確保將來自串流來源的資料新增至即時客戶輪廓。

請參閱[在 UI 中建立和編輯結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=zh-Hant)，了解有關向結構添加和刪除欄位群組和個別欄位的詳細資訊。

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

   系統會提示您啟用設定檔的資料集。資料集一經啟用，即可透過攝取的資料豐富即時客戶設定檔。

   >[!IMPORTANT]
   >
   >    只有當資料集所遵循的結構同樣啟用設定檔時，您才能啟用設定檔的資料集。

   ![啟用輪廓結構](./assets/loyalty-dataset-profile.png)

請參閱[資料集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant)，了解如何檢視、預覽、建立、刪除資料集的詳細資訊。以及為即時客戶輪廓啟用資料集的方法。


## 使用來源連接器

您需根據從何處接收忠誠度資料，挑選 Adobe Experience Platform 中可用的相關來源連接器。

您可以從多種來源擷取資料。 以下只是眾多可用來源中的幾個：

- Adobe應用程式(來源聯結器包括[Adobe Analytics](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/analytics)、[Adobe Audience Manager](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/audience-manager)等)

- 雲端儲存空間(來源聯結器包括[Amazon S3](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/cloud-storage/s3)、[Azure Blob](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/cloud-storage/blob)等)

- 資料庫(來源聯結器包含[Snowflake](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/databases/snowflake)、[Microsoft SQL Server](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/databases/sql-server)等)

若要設定來源連接器，請執行以下操作：

1. 在Adobe Experience Platform中，從左側邊欄的[!UICONTROL CONNECTIONS]中選取&#x200B;**[!UICONTROL 來源]**。

1. 從可用的來源聯結器清單中選取您的來源聯結器。

   每個連接器都遵循類似的工作流程：

   1. **[!UICONTROL 驗證]**。您提供驗證詳細資訊以存取資料來源。

   1. **[!UICONTROL 選取資料]**：選取要擷取的來源資料。

   1. **[!UICONTROL 資料流詳細資料]**：您提供了資料流的其他詳細資料，例如名稱和要使用的資料集。

   1. **[!UICONTROL 對應]**：將傳入的來源資料欄位對應至與您所選資料集關聯之結構中的屬性。

   1. **[!UICONTROL 排程]**：如果可用，您可以排程資料擷取。

   1. **[!UICONTROL 檢閱]**：您會看到來源連接器定義的檢閱。

1. 每個聯結器都提供詳細檔案。 若要存取此文件：

   1. 在連接器圖格上，選取[!UICONTROL 「設定」]或[!UICONTROL 「新增資料」]旁邊的&#x200B;**[!UICONTROL 「...」]**。

      ![檢視文件](./assets/sourceconnector-documentation.png)

   1. 選取&#x200B;**[!UICONTROL 「檢視文件」]**。

如需如何使用Adobe Analytics來源聯結器的詳細資訊，請參閱[從傳統Adobe Analytics擷取及使用資料](./analytics.md)。

如需如何使用HTTP API來源聯結器的資訊，請參閱[擷取及使用串流資料](./streaming.md)。

請參閱[來源連接器概觀](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hant#terms-and-conditions)，了解來源連接器 (包括每個連接器的詳細資訊連結) 的概述。


## 設定連線

若要在 Customer Journey Analytics 中使用 Adobe Experience Platform 資料，您可以建立連線，其中包含設定結構、資料集和工作流程所產生的資料。

連線可讓您將資料集從 Adobe Experience Platform 整合到工作區。若要針對這些資料集製作報表，必須先為Adobe Experience Platform和Workspace中的資料集建立連線。

若要建立連線，請執行以下操作：

1. 在Customer Journey Analytics UI中，選取頂端功能表中的&#x200B;**[!UICONTROL 連線]** （選擇性的從&#x200B;**[!UICONTROL 資料管理]**）。

1. 選取&#x200B;**[!UICONTROL 「建立新連線」]**。

1. 在&#x200B;**[!UICONTROL 「無標題連線」]**&#x200B;畫面中：

   1. 在&#x200B;**[!UICONTROL 「連線設定」]**&#x200B;中為連線命名並提供說明。

   1. 從&#x200B;**[!UICONTROL 「資料設定」]**&#x200B;的&#x200B;**[!UICONTROL 「沙箱」]**&#x200B;清單中選取正確沙箱，並從&#x200B;**[!UICONTROL 「每日事件平均數」]**&#x200B;清單中選取每日事件數。

      ![連線設定](./assets/cja-connections-1.png)

   1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

1. 在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;的&#x200B;**[!UICONTROL 選取資料集]**&#x200B;步驟：

   1. 選取您先前建立的資料集 (`Example Loyalty Dataset`) 和您要加入連線的任何其他資料集。

      ![新增資料集](./assets/cja-connections-2.png)

   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。

1. 在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;的&#x200B;**[!UICONTROL 資料集設定]**&#x200B;步驟：

   對於每個資料集：

   1. 在 Adobe Experience Platform 中，從資料集結構描述中所定義的可用身分識別中選取[!UICONTROL 人員 ID]。

   1. 從[!UICONTROL 「資料來源類型」]清單中選取正確的資料來源。如果您指定&#x200B;**[!UICONTROL 「其他」]**，請為您的資料來源新增說明。

   1. 根據您的偏好設定，設定&#x200B;**[!UICONTROL 匯入所有新資料]**&#x200B;和&#x200B;**[!UICONTROL 資料集回填現有資料]**。

      ![設定資料集](./assets/cja-connections-3.png)

   1. 選取&#x200B;**[!UICONTROL 「新增資料集」]**。

   1. 選取&#x200B;**[!UICONTROL 「儲存」]**。

建立[連線](/help/connections/overview.md)之後，您可以執行各種管理工作，例如[選取並合併資料集](/help/connections/combined-dataset.md)、[檢查連線資料集的狀態和資料擷取的狀態](/help/connections/manage-connections.md)等等。

## 設定資料檢視

資料檢視是特定於 Customer Journey Analytics 的容器，可讓您決定如何詮釋來自連線的資料。它指定 Analysis Workspace 中可用的所有維度和量度，以及這些維度和量度從哪些欄取得資料。資料檢視是為了在 Analysis Workspace 中報告資料而定義的。

若要建立資料檢視，請執行以下操作：

1. 在Customer Journey Analytics UI中，選取頂端功能表中的&#x200B;**[!UICONTROL 資料檢視]** （可選擇從&#x200B;**[!UICONTROL 資料管理]**&#x200B;進行）。

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

請參閱[資料檢視總覽](../data-views/data-views.md)，以取得如何建立和編輯資料檢視、資料檢視中有哪些元件可供使用，以及如何使用區段和工作階段設定的詳細資訊。


## 設定專案

Analysis Workspace 是彈性的瀏覽器工具，可讓您根據資料快速建立分析及分享見解。您可以使用工作區專案合併資料元件、表格和視覺效果，進行分析並與貴組織的任何人分享。

若要建立專案，請執行以下操作：

1. 在Customer Journey Analytics UI中，選取頂端功能表中的&#x200B;**[!UICONTROL 專案]**。

2. 在左側導覽中選取&#x200B;**[!UICONTROL 「專案」]**。

3. 選取&#x200B;**[!UICONTROL 「建立專案」]**。

   ![工作區專案](./assets/cja-projects-1.png)

   選取&#x200B;**[!UICONTROL 「空白專案」]**。

   ![工作區 – 空白專案](./assets/cja-projects-2.png)

4. 從清單中選取您的資料檢視。

   ![工作區選取資料檢視](./assets/cja-projects-3.png)。

5. 若要建立您的第一個報表，請開始將維度和量度拖放至[!UICONTROL 面板]中的[!UICONTROL 自由表格]。 例如，拖曳 `Program Points Balance`和 `Page View` 做為量度 而 `email` 作為維度，快速概覽已造訪過您網站且屬於收集忠誠點數之忠誠計劃一部分的輪廓。

   ![工作區 – 第一份報告](./assets/cja-projects-5.png)

如需如何使用元件、視覺效果和面板建立專案和建立分析的詳細資訊，請參閱 [Analysis Workspace 概觀](../analysis-workspace/home.md)。

>[!SUCCESS]
>
>您已完成所有步驟。從定義您要收集的忠誠度資料 (結構)，以及要將其儲存在 Adobe Experience Platform 中的何處 (資料集) 開始，您已設定適當的來源連接器，以提供忠誠度資料。您已在 Customer Journey Analytics 中定義連線，以使用擷取的忠誠度資料和其他資料。您的資料檢視定義可讓您指定要使用的維度和量度，最後，您建立了第一個可視覺化和分析資料的專案。
