---
title: 透過Adobe Experience Platform Edge Network Server API內嵌資料
description: 說明如何透過Adobe Experience Platform Edge Network Server API和Edge Network將資料擷取到Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: 6bfb7254-5bb7-45c6-86a2-0651a0d222fa
role: Admin
source-git-commit: 59da35ddbdf06da354af4ab469a357caae41bd26
workflow-type: tm+mt
source-wordcount: '2351'
ht-degree: 59%

---

# 透過Adobe Experience Platform Edge Network Server API內嵌資料

本快速入門手冊說明如何使用Adobe Experience Platform Edge Network Server API和Edge Network，將追蹤資料從IoT裝置、機上盒、遊戲主機、案頭應用程式等裝置直接擷取到Adobe Experience Platform。 然後將這些資料用於Customer Journey Analytics。

若要完成此作業，您必須：

- 在 Adobe Experience Platform 中&#x200B;**設定結構和資料集**，定義您要收集的資料的模型 (結構)，以及實際收集資料的位置 (資料集)。

- **設定資料流**&#x200B;以設定 Adobe Experience Platform Edge Network，將收集的資料路由至您在 Adobe Experience Platform 中設定的資料集。

- **使用伺服器API** 將資料從案頭、遊戲主機、IoT裝置或機上盒上執行的應用程式或遊戲直接傳送至資料流。

- **部署和驗證**。有一個讓您可反複進行開發程式的環境，一旦一切通過驗證，就可在您的生產環境中上線發佈。

- 在 Customer Journey Analytics 中&#x200B;**設定連線**。此連線應 (至少) 包含您的 Adobe Experience Platform 資料集。

- 在 Customer Journey Analytics 中&#x200B;**設定資料檢視**，定義您要在 Analysis Workspace 中使用的量度和維度。

- 在 Customer Journey Analytics 中&#x200B;**設定專案**，建立您的報告和視覺效果。

>[!NOTE]
>
>本快速入門手冊是一本簡化的指南，說明如何將從IoT裝置、機上盒、遊戲主機或桌上型電腦上執行的應用程式或遊戲所收集的資料擷取到Adobe Experience Platform中，並用於Customer Journey Analytics。 強烈建議在提及時研究其他資訊。


## 設定結構和資料集

若要將資料內嵌至Adobe Experience Platform，您必須先定義要收集哪些資料。 所有擷取至 Adobe Experience Platform 的資料都必須符合標準的非正常結構，才能由下游能力和功能識別並處理。Experience Data Model (XDM)是標準架構，提供結構形式的結構。

定義結構後，您可以使用一個或多個資料集來儲存及管理資料收集。資料集是資料集合（通常是表格）的儲存和管理結構，其中包含結構（欄）和欄位（列）。

擷取至 Adobe Experience Platform 的所有資料都必須符合預先定義的結構，才能以資料集形式持續保存。

### 設定結構

您想要從在主機上玩遊戲的設定檔追蹤一些最低限度的資料，例如身分識別、分數、進度和其他資訊。
您必須先定義用來模型化此資料的結構描述。

若要設定您的結構：

1. 在 Adobe Experience Platform UI 的左側邊欄中，選取[!UICONTROL 「資料管理」]中的&#x200B;**[!UICONTROL 「結構」]**。

1. 選取 **[!UICONTROL 建立結構描述]**..
1. 在建立架構精靈的選取類別步驟中：

   1. 選取 **[!UICONTROL 體驗事件]**.

      ![建立結構](./assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    體驗事件結構描述是用來建立 _行為_ 的設定檔（像是場景名稱、要新增至購物車的推播按鈕）。 個別設定檔結構可用來建立設定檔&#x200B;_屬性_ (例如姓名、電子郵件、性別) 模型。

   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。


1. 在 [!UICONTROL 名稱和稽核步驟] 的 [!UICONTROL 建立結構描述] 精靈：

   1. 輸入 **[!UICONTROL 結構描述顯示名稱]** 適用於您的結構描述和（選用） a **[!UICONTROL 說明]**.

      ![命名結構](./assets/create-ee-schema-wizard-step-2.png)

   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 在範例結構描述的結構標籤中：

   1. 在[!UICONTROL 「欄位群組」]中選取&#x200B;**[!UICONTROL 「+ 新增」]**。

      ![新增欄位群組](./assets/add-field-group-button.png)

      欄位群組是可重複使用的物件和屬性集合，可讓您輕鬆擴充結構。

   1. 在 [!UICONTROL 新增欄位群組] 對話方塊中，選取 **[!UICONTROL 閃爍的光]** 欄位群組。 此欄位群組的建立是為了追蹤使用者在主機上玩名為Blinding Light的虛構遊戲的進度。

      ![遮光燈欄位群組](assets/schema-fieldgroup-blindinglight.png)

      您可以選取預覽按鈕，以查看屬於此欄位群組之欄位的預覽，例如 `scores > afterMatch`。

      ![遮色燈欄位群組預覽](assets/schema-fieldgroup-blindinglight-preview.png)

      選取&#x200B;**[!UICONTROL 「返回」]**&#x200B;來關閉預覽。

   1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. 選取 **[!UICONTROL +]** 位於結構描述名稱旁。

   ![範例結構新增欄位按鈕](./assets/example-gamingschema-plus.png)

1. 在 [!UICONTROL 欄位屬性] 面板，輸入 `identification` 作為 [!UICONTROL 欄位名稱]， **[!UICONTROL 識別]** 作為 [!UICONTROL 顯示名稱]，選取 **[!UICONTROL 物件]** 作為 [!UICONTROL 型別] 並選取 **[!UICONTROL ExperienceEvent Core v2.1]** 作為 [!UICONTROL 欄位群組].

   >[!NOTE]
   >
   >如果該欄位群組無法使用，請尋找另一個包含身分欄位的欄位群組。 或 [建立新的欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en) 和 [新增身分欄位](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=en#define-a-identity-field) (按讚 `ecid`， `crmId`，以及您所需的其他欄位群組)並選取該新欄位群組。

   ![識別物件](./assets/identification-field-gaming.png)

   識別物件會將識別功能新增至結構描述。 在您的案例中，您想要使用Experience CloudID和電子郵件地址來識別玩遊戲的設定檔，以便登入遊戲主機。 有許多其他屬性可用來追蹤您的人員身分。

   選取&#x200B;**[!UICONTROL 「套用」]**&#x200B;將此物件加入您的結構。

1. 在剛剛新增的識別物件中選取 **[!UICONTROL ecid]** 欄位，然後在右側面板的[!UICONTROL 「身分命名空間」]清單中，選取&#x200B;**[!UICONTROL 「身分」]**&#x200B;和&#x200B;**[!UICONTROL 「主要身分」]**&#x200B;和 **[!UICONTROL ECID]**。

   ![指定 ECID 作為身分](./assets/specify-identity-gaming.png)

   您正在指定 Experience Cloud Identity 作為 Adobe Experience Platform Identity 服務可用於結合 (拼接) 設定檔行為與相同 ECID 的主要身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在 ecid 屬性中。

1. 在剛剛新增的識別物件中選取&#x200B;**[!UICONTROL 「電子郵件」]**&#x200B;欄位，然後在[!UICONTROL 「欄位屬性」]面板的[!UICONTROL 「身分命名空間」]清單中選取&#x200B;**[!UICONTROL 「身分」]**&#x200B;和&#x200B;**[!UICONTROL 「電子郵件」]**。

   ![指定電子郵件作為身分](./assets/specify-email-identity-gaming.png)

   您正在指定電子郵件地址作為 Adobe Experience Platform Identity 服務可用於結合 (拼接) 設定檔行為的另一個身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在電子郵件屬性中。

   選取&#x200B;**[!UICONTROL 「儲存」]**。

1. 選取顯示結構名稱之結構的根元素，然後選取&#x200B;**[!UICONTROL 「設定檔」]**&#x200B;切換。

   系統會提示您啟用設定檔的結構。啟用後，根據此結構將資料擷取至資料集時，該資料就會合併至即時客戶設定檔中。

   如需詳細資訊，請參閱[啟用結構以用於即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant#profile)。

   >[!IMPORTANT]
   >
   >    儲存啟用設定檔的結構後，便無法再為設定檔停用該結構。

   ![啟用設定檔結構](./assets/enable-for-profile.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

您已建立最低架構模型，以模擬您可以從遊戲擷取的資料。 該結構可讓您使用 Experience Cloud Identity 和電子郵件地址來識別設定檔。為設定檔啟用結構描述後，即可確保從主機遊戲擷取的資料會新增至即時客戶設定檔。

在行為資料旁邊，您還可以從主控台擷取設定檔屬性資料（例如登入主控台的設定檔詳細資訊）。

若要擷取設定檔資料，您可以：

- 根據 XDM 個別設定檔架構類別建立結構。

- 將「設定檔核心 v2」欄位群組新增至結構。

- 根據「設定檔核心 v2」欄位群組新增識別物件。

- 將Experience CloudID定義為主要識別碼，並將電子郵件定義為識別碼。

- 啟用該設定檔結構

請參閱[在 UI 中建立和編輯結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有關向結構添加和刪除欄位群組和個別欄位的詳細資訊。

### 設定資料集

您已使用您的結構定義資料模型。您現在必須定義結構，才能使用資料集儲存及管理該資料。

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
   >    只有當資料集所遵循的結構同樣啟用設定檔時，您才能啟用設定檔的資料集。

   ![啟用設定檔結構](./assets/aepwebsdk-dataset-profile.png)

請參閱[資料集 UI 指南](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant)，了解如何檢視、預覽、建立、刪除資料集的詳細資訊。以及為即時客戶設定檔啟用資料集的方法。

## 設定資料流

資料流代表實作Adobe Experience Platform Web和Mobile SDK以及Adobe Experience Platform Edge Network伺服器API時的伺服器端設定。 使用Adobe Experience Platform SDK和Edge Network Server API收集資料時，資料會傳送至Adobe Experience Platform Edge Network。 是決定要將資料轉送至哪些服務的資料流。

在設定中，您想要將從遊戲中收集的資料傳送到Adobe Experience Platform中的資料集。

若要設定您的資料流：

1. 在 Adobe Experience Platform UI 中，從左側邊欄的[!UICONTROL 「資料收集」]中選取&#x200B;**[!UICONTROL 「資料流」]**。

2. 選取「**[!UICONTROL 新資料流]**」。

3. 命名並描述您的資料流。從[!UICONTROL 「事件結構」]清單中選取您的結構。

   ![新資料流](./assets/new-datastream.png)

4. 選取&#x200B;**[!UICONTROL 「儲存」]**。

5. 選取&#x200B;**[!UICONTROL 「新增服務」]**。

6. 在[!UICONTROL 「新增服務畫面」]中：

   1. 從[!UICONTROL 「服務」]清單中選取&#x200B;**[!UICONTROL 「Adobe Experience Platform」]**。

   2. 確保已選取&#x200B;**[!UICONTROL 「啟用」]**。

   3. 從[!UICONTROL 「事件資料集」]清單中選取您的資料集。

      ![資料流 AEP 服務](./assets/datastream-aep-service.png)

   4. 保留其他設定並選取&#x200B;**[!UICONTROL 「儲存」]**&#x200B;以儲存資料流。

您的資料流現在已設定為將從遊戲中收集的資料轉送到Adobe Experience Platform中的資料集。

請參閱[資料流概觀](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=en)，了解如何設定資料流以及如何處理敏感資料的詳細資訊。

## 使用Edge Network Server API

在遊戲開發中，您可以視情況將相關呼叫新增至Adobe Experience Platform Edge Network Server API。

例如，若要更新播放器的分數，您可使用：

```
curl -X POST "https://server.adobedc.net/ee/v2/interact?dataStreamId={DATASTREAM_ID}"
-H "Authorization: Bearer {TOKEN}"
-H "x-gw-ims-org-id: {ORG_ID}"
-H "x-api-key: {API_KEY}"
-H "Content-Type: application/json"
-d '{
   "event": {
      "xdm": {
         "identityMap": {
            "Email_LC_SHA256": [
               {
                  "id": "0c7e6a405862e402eb76a70f8a26fc732d07c32931e9fae9ab1582911d2e8a3b",
                  "primary": true
               }
            ]
         },
         "eventType": "game.scoreUpdate",
         "{sandbox}": {
            "scores": {
               "afterMatch": 132391",
            }
         },
         "timestamp": "2021-08-09T14:09:20.859Z"
      }
   }
}'
```

在範例POST請求中， `{DATASTREAM_ID}` 指向您先前設定的範例資料流的識別碼。 `{sandbox}` 是沙箱的唯一名稱，用於識別自訂遮光欄位群組的路徑。

另請參閱 [互動式資料收集](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/interactive-data-collection.html?lang=en) 和 [非互動式資料集合](https://experienceleague.adobe.com/docs/experience-platform/edge-network-server-api/data-collection/non-interactive-data-collection.html?lang=en) 有關如何使用Edge Network Server API的詳細資訊。

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

   - 選取您先前建立的資料集和/或您要納入連線中的其他相關資料集

   - 選取&#x200B;**[!UICONTROL 「下一步」]**。

   在[!UICONTROL 新增資料集]的[!UICONTROL 資料集設定]步驟：

   - 對於每個資料集：

      - 在 Adobe Experience Platform 中，從資料集結構描述中所定義的可用身分中選取[!UICONTROL 人員 ID]。

      - 從[!UICONTROL 「資料來源類型」]清單中選取正確的資料來源。如果您指定&#x200B;**[!UICONTROL 「其他」]**，請為您的資料來源新增說明。

      - 根據您的偏好設定，設定&#x200B;**[!UICONTROL 匯入所有新資料]**&#x200B;和&#x200B;**[!UICONTROL 資料集回填現有資料]**。

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

5. 若要建立您的第一個報表，請開始將維度和量度拖放至 [!UICONTROL 自由表格] 在 [!UICONTROL 面板].

如需如何使用元件、視覺效果和面板建立專案和建立分析的詳細資訊，請參閱 [Analysis Workspace 概觀](../analysis-workspace/home.md)。

>[!SUCCESS]
>
>您已完成所有步驟。首先定義您要收集哪些資料（結構描述），以及要將資料儲存在Adobe Experience Platform中的何處（資料集）。 您已在Edge Network上設定資料串流，以確保資料可轉送至該資料集。 接著您使用Edge Network Server API將該資料傳送至資料流。 您定義了Customer Journey Analytics連線，以便使用您的遊戲資料和其他資料。 您的資料檢視定義可讓您指定要使用的維度和量度，並最終建立您的第一個專案，以視覺化呈現和分析您的遊戲資料。
