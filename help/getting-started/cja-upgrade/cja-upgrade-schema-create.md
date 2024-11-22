---
title: 建立結構描述以進行Customer Journey Analytics
description: 瞭解從Adobe Analytics升級為Customer Journey Analytics時的建議路徑
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
source-git-commit: 8bcc6b3b2a1e6f75bd0c868f77a375913412f988
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 46%

---

# 建立XDM結構描述以與您的Customer Journey Analytics Web SDK實作搭配使用

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

>[!IMPORTANT]
>
>在開始建立XDM結構描述之前，請與您的資料團隊和整個組織的其他利害關係人合作，找出您組織適用於Customer Journey Analytics的理想結構描述設計以及您使用的其他Adobe Experience Platform應用程式。 如需詳細資訊，請參閱[架構您的結構描述以搭配Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)使用。

Adobe建議在升級至Customer Journey Analytics時，建立自訂體驗資料模型(XDM)結構描述。 自訂結構描述可讓您根據組織需求以及您使用的特定平台應用程式量身打造簡化的結構描述。 當需要變更結構描述時，您不必在數千個未使用的欄位中篩選，以尋找需要更新的欄位。

## 建立結構

您定義的XDM結構描述代表您收集到Adobe Experience Platform中的資料模式。

若要建立自訂綱要：

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. 在Adobe Experience Platform的左側邊欄中，選取[!UICONTROL 資料管理]中的&#x200B;**[!UICONTROL 結構描述]**。

1. 選取&#x200B;**[!UICONTROL 建立結構描述]**。

1. 在建立結構描述精靈的&#x200B;**[!UICONTROL 選取類別]**&#x200B;步驟中：

   1. 選取&#x200B;**[!UICONTROL 體驗事件]**。

      ![建立強調體驗事件的結構描述](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    體驗事件結構描述可用來模型化設定檔的&#x200B;_行為_ （像是場景名稱、要新增至購物車的推播按鈕）。 個體輪廓結構可用來建立輪廓&#x200B;_屬性_ (例如姓名、電子郵件、性別) 模型。

   1. 選取&#x200B;**[!UICONTROL 「下一步」]**。


1. 在[!UICONTROL 建立結構描述]精靈的[!UICONTROL 名稱和檢閱步驟]中：

   1. 為您的結構描述輸入&#x200B;**[!UICONTROL 結構描述顯示名稱]**&#x200B;和（選擇性） **[!UICONTROL 描述]**。

      ![建立結構描述視窗，顯示結構描述欄位的名稱](assets/create-ee-schema-wizard-step-2.png)

   1. 選取&#x200B;**[!UICONTROL 「完成」]**。

1. 新增包含您要納入結構描述中任何欄位的所有欄位群組。

   欄位群組是可重複使用的物件和屬性集合，可讓您輕鬆擴充結構。

   1. 在&#x200B;**[!UICONTROL 欄位群組]**&#x200B;區段中，選取&#x200B;**[!UICONTROL +新增]**。

      ![新增欄位群組](assets/add-field-group-button.png)

   1. 在[!UICONTROL 「新增欄位群組」]對話框中，從清單中選取&#x200B;**[!UICONTROL 「AEP Web SDK ExperienceEvent」]**&#x200B;欄位群組。

      ![AEP Web SDK ExperienceEvent 欄位群組](assets/select-aepwebsdk-experienceevent.png)

      您可以選取預覽按鈕，以查看屬於此欄位群組之欄位的預覽，例如 `web > webPageDetails > name`。

      ![AEP Web SDK ExperienceEvent 欄位群組預覽](assets/aepwebsdk-experiencevent-preview.png)

      選取&#x200B;**[!UICONTROL 「返回」]**&#x200B;來關閉預覽。

   1. （選擇性）選取您要包含的任何其他欄位群組。

   1. 選取&#x200B;**[!UICONTROL 「新增欄位群組」]**。

1. （可選）如果您有要包含在結構描述中的自訂欄位，請建立自訂欄位群組，並將自訂欄位新增到欄位群組中。

   1. 在&#x200B;**[!UICONTROL 欄位群組]**&#x200B;區段中，選取&#x200B;**[!UICONTROL +新增]**。

      ![新增欄位群組](assets/add-field-group-button.png)

   1. 在[!UICONTROL 新增欄位群組]對話方塊中，選取&#x200B;**[!UICONTROL 建立新欄位群組]**。

   1. 指定顯示名稱和選擇性說明，然後選取&#x200B;**[!UICONTROL 新增欄位群組]**。

1. 在[!UICONTROL 「結構」]面板中，選取結構名稱旁的 **[!UICONTROL +]**。

   ![範例結構新增欄位按鈕](assets/example-schema-plus.png)

1. 在[!UICONTROL 「欄位屬性」]面板中，輸入 `Identification` 作為名稱，**[!UICONTROL 「識別」]**&#x200B;作為[!UICONTROL 顯示名稱]，選取&#x200B;**[!UICONTROL 「物件」]**&#x200B;作為[!UICONTROL 類型]，並選取&#x200B;**[!UICONTROL 「ExperienceEvent 核心 v2.1」]**&#x200B;作為[!UICONTROL 欄位群組]。

   >[!NOTE]
   >
   >如果該欄位群組無法使用，請尋找另一個包含身分欄位的欄位群組。 或者[建立新欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html)和[新增新的身分識別欄位](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) （例如`ecid`、`crmId`和其他您需要的欄位）至欄位群組，並選取該新欄位群組。

   ![識別物件](assets/identification-field.png)

   識別物件會將識別功能新增至結構描述。 對於您的情況，您想要使用Experience CloudID和電子郵件地址來識別造訪您網站的設定檔。 有許多其他屬性可用來追蹤您的人員身分識別（例如客戶ID、忠誠度ID）。

   選取&#x200B;**[!UICONTROL 「套用」]**&#x200B;將此物件加入您的結構。

1. 在剛剛新增的識別物件中選取 **[!UICONTROL ecid]** 欄位，然後在右側面板的[!UICONTROL 「身分命名空間」]清單中，選取&#x200B;**[!UICONTROL 「身分」]**&#x200B;和&#x200B;**[!UICONTROL 「主要身分」]**&#x200B;和 **[!UICONTROL ECID]**。

   ![指定 ECID 作為身分](./assets/specify-identity.png)

   您將 Experience Cloud Identity 指定為 Adobe Experience Platform Identity 服務可用於組合 (拼接) 具有相同 ECID 的輪廓的行為的主要身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在 ecid 屬性中。

1. 在剛剛新增的識別物件中選取&#x200B;**[!UICONTROL 「電子郵件」]**&#x200B;欄位，然後在[!UICONTROL 「欄位屬性」]面板的[!UICONTROL 「身分命名空間」]清單中選取&#x200B;**[!UICONTROL 「身分」]**&#x200B;和&#x200B;**[!UICONTROL 「電子郵件」]**。

   ![指定電子郵件作為身分](./assets/specify-email-identity.png)

   您將電子郵件地址指定為 Adobe Experience Platform Identity 服務可用於結合 (拼接) 輪廓行為的另一個身分。

   選取&#x200B;**[!UICONTROL 「套用」]**。您會看到指紋圖示出現在電子郵件屬性中。

   選取&#x200B;**[!UICONTROL 「儲存」]**。

1. （選擇性）如果要將Customer Journey Analytics與RTCDP整合，請選取顯示結構描述名稱的結構描述根元素，然後選取&#x200B;**[!UICONTROL 設定檔]**&#x200B;引數。

   系統會提示您啟用輪廓的結構。啟用後，根據此結構將資料攝取至資料集時，該資料就會合併至即時客戶輪廓中。

   如需詳細資訊，請參閱[啟用結構以用於即時客戶輪廓](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile)。

   >[!IMPORTANT]
   >
   >為設定檔啟用結構描述後，無法為設定檔停用它。

   ![啟用輪廓結構](./assets/enable-for-profile.png)

1. 選取&#x200B;**[!UICONTROL 「儲存」]**，即可儲存您的結構。

   您已建立最小結構，以建立可從您網站擷取的資料的模型。該結構可讓您使用 Experience Cloud Identity 和電子郵件地址來識別輪廓。透過啟用輪廓的結構，即可確保將從您網站擷取的資料新增至即時客戶輪廓。

   除了行為資料之外，您也可以從您的網站擷取輪廓屬性資料 (例如訂閱電子報的輪廓詳細資訊)。

   若要擷取此輪廓資料，您可以：

   * 根據 XDM 個體輪廓架構類別建立結構。

   * 將「輪廓核心 v2」欄位群組新增至結構。

   * 根據「輪廓核心 v2」欄位群組新增識別物件。

   * 將Experience CloudID定義為主要識別碼，並將電子郵件定義為識別碼。

   * 啟用該輪廓結構

   請參閱[在 UI 中建立和編輯結構](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html)，了解有關向結構添加和刪除欄位群組和個別欄位的詳細資訊。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
