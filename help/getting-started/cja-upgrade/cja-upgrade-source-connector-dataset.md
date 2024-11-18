---
title: 將Analytics來源聯結器資料集新增至連線
description: 瞭解如何將Analytics來源聯結器資料集新增至連線
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 27%

---

# 將Analytics來源聯結器資料集新增至連線

>[!NOTE]
> 
>必須先完成所有先前的升級步驟，才能依照本頁面的步驟操作。 您可以依照[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)操作，也可以依照[Adobe Analytics為您的組織動態產生的升級步驟操作，以Customer Journey Analytics升級問卷](https://gigazelle.github.io/cja-ttv/)。
>
>完成此頁面上的步驟後，請繼續依照建議的升級步驟或動態產生的升級步驟操作。

## 瞭解Analytics來源聯結器如何將歷史資料帶入Customer Journey Analytics

您可以使用Analytics來源聯結器將Adobe Analytics報告套裝資料匯入Adobe Experience Platform。 然後，這些資料即可用作Customer Journey Analytics中的歷史資料。

此程式假設您要在升級至Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)時[建立XDM結構描述，因為您想要根據貴組織的需求以及您使用的特定平台應用程式量身打造的簡化結構描述。

若要使用Analytics來源聯結器將歷史資料帶入Customer Journey Analytics，您需要：

1. [為Analytics來源聯結器建立XDM結構描述](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. [建立Analytics來源聯結器和對應欄位](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)

1. 將Analytics來源聯結器資料集新增至連線，如下所述。

## 將Analytics來源聯結器資料集新增至連線

在您[為歷史資料](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)建立Analytics來源聯結器後，系統會自動為Analytics資料建立資料集。

您需要將此自動建立的資料集新增至您為Web SDK實作建立的相同連線。 這麼做會將Analytics資料帶入與您Web SDK資料相同的Customer Journey Analytics資料檢視。

若要將自動建立的資料集新增至您為Web SDK實作建立的相同連線：

1. 在 Customer Journey Analytics 中選取&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

1. 選取您[為您的Web SDK實作](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)建立的連線。

1. 選取&#x200B;**[!UICONTROL 編輯]**。

   ![編輯連線](assets/connection-add-dataset.png)

1. 選取右上角的&#x200B;**[!UICONTROL 新增資料集]**。

   ![編輯連線](assets/connection-add-dateset2.png)

1. 捲動至或搜尋在您建立Analytics來源聯結器時自動建立的資料集。

   此資料集的名稱是報表套裝的名稱，後面接著`midValues`。 例如︰`My report suite midValues`

1. 選取資料集名稱旁的核取方塊，然後選取&#x200B;**[!UICONTROL 下一步]**。

   ![編輯連線](assets/connection-add-dataset3.png)

1. 指定下列資訊：

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | 設定 | 說明 |
   | --- | --- |
   | **[!UICONTROL 人員 ID]** | 僅適用於事件和輪廓資料集。從可用身分識別的下拉式清單中選取人員 ID。這些身分識別是在 Experience Platform 的資料集結構中所定義。 若要了解如何以「身分對應」作為人員 ID，請參閱以下說明。<p>如果沒有人員 ID 可以選擇，表示綱要中尚未定義一或多個人員 ID。有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。 <p>所選人員 ID 的值會區分大小寫。例如，`abc123` 和 `ABC123` 是兩個不同的值。 |
   | **[!UICONTROL 時間戳記]** | 僅適用於事件和摘要資料集，系統會自動將此設定設為 Experience Platform 中以事件為基礎的結構描述之預設時間戳記欄位。 |
   | **[!UICONTROL 時區]** | 僅適用於摘要資料。為時間序列摘要資料選取適當的時區。 |
   | **[!UICONTROL 資料來源類型]** | 選取資料來源類型。<br/>資料來源的類型包括： <ul><li>[!UICONTROL 網頁資料]</li><li>[!UICONTROL 行動應用程式資料]</li><li>[!UICONTROL POS 資料]</li><li>[!UICONTROL CRM 資料]</li><li>[!UICONTROL 調查資料]</li><li>[!UICONTROL 呼叫中心資料]</li><li>[!UICONTROL 產品資料]</li><li> [!UICONTROL 帳戶資料]</li><li> [!UICONTROL 交易資料]</li><li>[!UICONTROL 客戶回饋資料]</li><li> [!UICONTROL 其他]</li></ul>該欄位用於調查正在使用之資料來源的類型。 |

   {style="table-layout:auto"}

1. 在&#x200B;**[!UICONTROL 匯入新資料]**&#x200B;區段中，保留&#x200B;**[!UICONTROL 匯入所有新資料]**&#x200B;選項停用。

   由於您正在將Analytics來源聯結器資料集用於歷史資料，因此您不希望未來將收集的資料帶入此資料集。

1. 在&#x200B;**[!UICONTROL 資料集回填]**&#x200B;區段中，選取&#x200B;**[!UICONTROL 要求回填]**。

1. 輸入開始和結束日期，或選取行事曆圖示![行事曆](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)，以定義要包含回填的期間。

   Analytics來源聯結器會為生產沙箱匯入13個月的資料（無論大小）。 非生產沙箱中的回填時間為3個月。

   >[!IMPORTANT]
   >
   >指定要求回填的日期時請務必明確。 結束日期應該是您首次開始透過Web SDK實作收集資料的日期。
   >
   >或者，您可以選擇您首次開始透過Web SDK實作收集資料當日後不久的日期，然後使用區段來篩選掉重疊的資料。

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. 選取&#x200B;**[!UICONTROL 佇列回填]**。

1. 選取&#x200B;**[!UICONTROL 新增資料集]**，然後選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存連線。

1. 繼續執行[建議的升級步驟](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[動態產生的升級步驟](https://gigazelle.github.io/cja-ttv/)。
