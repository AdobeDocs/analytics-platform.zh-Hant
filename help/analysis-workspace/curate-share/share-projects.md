---
description: 了解在 Analysis Workspace 中如何共用專案。
keywords: Analysis Workspace 共用
title: 共用專案
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '2089'
ht-degree: 76%

---

# 共用專案 {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="共用專案"
>abstract="您可以與組織中的其他使用者共用這些專案角色中的任一個。"



您可以與以下類型的人員共用 Analysis Workspace 專案：

* 您組織中有權存取Customer Journey Analytics的使用者和群組

  您可以共用「編輯」、「複製」或「檢視」存取權

* 您組織中沒有 Customer Journey Analytics 存取權的使用者和群組

  收件者擁有唯讀存取權

* 您組織外部的人員

  收件者擁有唯讀存取權

收件者開啟專案時，系統會反映出您在共用之前套用的任何[監管](curate.md)。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的專案共用](https://video.tv.adobe.com/v/36207/?quality=12&learn=on){target="_blank"}的示範影片。

{{videoaa}}

>[!ENDSHADEBOX]


## 與組織中的使用者及群組共用。 {#Add}

您可以與組織中的現有 Analysis Workspace 使用者或群組共用專案。如本節所述，當您共用專案時，與您共用的使用者必須已擁有Customer Journey Analytics帳戶。

您可以與使用者或群組共用特定角色，也可以共用連結。

* [共用特定的專案角色](#share-a-specific-project-role)

* [共用專案的連結](#share-a-link-to-a-project)

## 共用特定的專案角色

與組織中的使用者和群組共用特定專案角色時，請考慮以下事項：

* 專案角色 (**[!UICONTROL 編輯原始項目]**、**[!UICONTROL 編輯副本]**&#x200B;和&#x200B;**[!UICONTROL 唯讀]**) 會與使用者和特定專案 ID 相連結。專案角色與[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-getting-started)中管理的使用者許可權無關。

* 在Customer Journey Analytics中，群組是由[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/en/docs/core-services/interface/administration/admin-getting-started)中的產品設定檔所定義。 管理員可與任何群組共用，包括&#x200B;*全部*。 非管理員可以與其所屬的任何群組共用，但&#x200B;*全部*&#x200B;除外。

* 獲得多個角色的使用者一律會有最高體驗。如果使用者同時以個人和群組的身分新增，就可能會發生這種情況。 例如，如果使用者以個人身分獲得&#x200B;**[!UICONTROL 編輯原始專案]**&#x200B;角色，並以群組成員身分獲得&#x200B;**[!UICONTROL 唯讀]**&#x200B;角色，則使用者會收到&#x200B;**[!UICONTROL 編輯原始專案]**&#x200B;體驗。

* 獲得&#x200B;**[!UICONTROL 編輯副本]**&#x200B;或&#x200B;**[!UICONTROL 唯讀]**&#x200B;角色的管理員，在開啟專案時會獲得這些有限的體驗。管理員可以透過與自己共用專案並授予編輯角色，將其角色變更為&#x200B;**[!UICONTROL 編輯原始項目]**，如下列程序中所述。

* 如果您選取多個要共用的專案，收件者會新增至每個專案的現有收件者清單。

  例如，專案 A 已有收件者 1、2 和 3 共用，而專案 B 已有收件者 4、5 和 6 共用。

  然後，專案 A 以及 B 有收件者 4 和 7 共用。新的專案 A 共用清單現在為 1、2、3、4 和 7，而新的專案 B 共用清單為 4、5、6 和 7。

若要與組織中的使用者或群組共用特定專案角色：

1. 在 Customer Journey Analytics 中，選取「[!UICONTROL **Workspace**]」索引標籤，然後選取左側面板中的「[!UICONTROL **專案**]」。

1. 選取您要共用的一個或多個專案旁邊的勾選方框，然後選取「[!UICONTROL **共用**]」。

   或

   若只要共用單一專案，您可以開啟要共用的專案，然後選取「**[!UICONTROL 共用]** > **[!UICONTROL 與 Workspace 使用者共用]**」。
如果有未儲存的變更，系統會提示您先儲存專案。

   共用專案對話框會顯示。對話框的「[!UICONTROL **透過連結共用**]」和「[!UICONTROL **設定**]」部份只會在共用單一專案時可見到。

   ![共用專案視窗。](assets/share-proj-modal.png)

1. 在提供的其中一個角色欄位中新增收件者或收件者群組：

   **編輯原始項目：**&#x200B;收件者可以&#x200B;**[!UICONTROL 儲存]**&#x200B;對專案的變更，並以共同所有者的身分操作。如果您想要與其他同事共同管理專案，此角色會很有用。 此角色包括編輯、刪除和修改共用專案的收件者清單。 <br>注意：Analysis Workspace 目前不支援即時共同作業，因此我們建議不要有多名使用者同時編輯一個專案。如果同時儲存專案，則會保留最後一個版本。

   **複製副本：**&#x200B;收件者可以&#x200B;**[!UICONTROL 另存新檔]**，且擁有左側面板的存取權。專案互動不限於此角色。 如果您想要與瞭解組織資料及如何使用Analysis Workspace的使用者共用專案，此角色會很有用。 但您不希望這些使用者修改您的專案。

   **唯讀：**&#x200B;收件者無法&#x200B;**[!UICONTROL 儲存]**&#x200B;或&#x200B;**[!UICONTROL 另存新檔]**，也無法存取左側面板。專案互動也有所限制。如果您想要與整體上較不熟悉您的組織資料結構、Analysis Workspace 或 Customer Journey Analytics 的使用者共用專案，此角色會非常有用。 但您仍希望他們能在安全的環境中使用資料和深入分析，就可以使用此角色。深入了解[唯讀專案體驗](/help/analysis-workspace/curate-share/view-only-projects.md)。

1. (視情況而定) 如果您要共用單一專案，則共用專案時請選擇是否啟用下列選項：

   * **共用嵌入的專案元件：**&#x200B;與所有收件者共用區段、計算量度、日期範圍。共用後，這些元件會出現在收件者 Workspace 的「元件」下拉式選單中。系統不會沿用此設定，此動作僅在單次共用中有效。

   * **設定為收件者的登陸頁面：** 將此頁面設定為收件者的登陸頁面。系統不會沿用此設定，此動作僅在單次共用中有效。

1. 選取「**[!UICONTROL 共用]**」。(如果專案已有人共用，請選取「[!UICONTROL **更新**]」。)

   或

   選取「**[!UICONTROL 監管與共用]**」以自動套用專案監管。(如果專案已共用，選取「**[!UICONTROL 監管與更新]**」)。了解更多有關[專案監管](curate.md)。


## 共用專案的連結

按本節所述共用連結時，請考慮以下事項：

* 使用該連結的收件者須先登入 Customer Journey Analytics，然後才能存取該專案。

* 收件者若未獲指派任何角色而收到專案的[共用連結](/help/analysis-workspace/curate-share/shareable-links.md) (「**[!UICONTROL 共用] > [!UICONTROL 取得專案連結]**」)，則會預設指定其角色。管理員會獲得&#x200B;**[!UICONTROL 編輯原始項目]**，非管理員則會獲得&#x200B;**[!UICONTROL 編輯副本]**。

若要與組織中的使用者共用專案連結：

1. 儲存專案。如果有未儲存的變更，系統會提示您在共用連結之前儲存專案。

1. 選取「**[!UICONTROL 共用]** > **[!UICONTROL 與 Workspace 使用者共用]**」，然後選取「**[!UICONTROL 複製]**」(在「**[!UICONTROL 透過連結共用]**」欄位旁邊)。

   ![共用專案會重點顯示透過連結共用欄位。](assets/share-proj-modal.png)

1. 與組織中的使用者共用連結。例如，您可以將其貼上到電子郵件、內部網站等。

## 與任何人共用專案 (無需登入) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="需要 Experience Cloud 驗證"
>abstract="您的組織要求使用者必須登入 Experience Cloud 才能使用此連結。"


您可以對沒有 Customer Journey Analytics 存取權的人員授予 Analysis Workspace 專案的[唯讀存取權](/help/analysis-workspace/curate-share/view-only-projects.md)。此被授與的存取權可包括：

* 您組織外部的人員

* 您組織內沒有 Customer Journey Analytics 存取權的人員

>[!NOTE]
>
>與沒有 Customer Journey Analytics 存取權的人員共用 Analysis Workspace 專案時，請考慮以下事項：
>
>* Customer Journey Analytics 管理員可以停用以這種方式共用專案的功能，如[偏好設定](/help/analysis-workspace/user-preferences.md)中所述。如果您無法按照本節所述共用專案，就代表您的 Customer Journey Analytics 管理員已停用此功能。
>
>* 具有超過50個展開視覺效果的專案只能與有權存取Customer Journey Analytics的人共用。
>
>* 您與其共用的使用者可以檢視在[監管](curate.md)期間套用至專案的任何區段。
> 
>* 您與之共用的使用者可以變更專案日期範圍。預設會顯示您為專案設定的日期範圍。
>
>* 如果有多位使用者同時嘗試存取所提供的連結，專案可能會變得無法存取。根據預設，每 5 分鐘可以有超過 190 人存取單一連結。如果您的組織達到此限制，請等待 5 分鐘，然後再次嘗試存取該連結。
>
>* 對於 [!DNL Healthcare Shield] 和 [!DNL Privacy & Security Shield] 授權，「[!UICONTROL 與任何人共用]」功能皆需要 Experience Cloud 驗證。對於 [!DNL Healthcare Shield] 客戶，會出現「HIPAA 合規性」警告，但您仍然可以在向 Experience Cloud 進行驗證後使用此功能。

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [與任何人共用](https://video.tv.adobe.com/v/3420093/?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]


若要與任何人共用 Analysis Workspace 專案：

1. 開啟您要共用的 Analysis Workspace 專案。

1. 選取「**[!UICONTROL 共用]** > **[!UICONTROL 與任何人共用]**」。

   如果有未儲存的變更，系統會提示您儲存專案。

   <!-- Add screen shot of new modal -->

1. 如果尚未啟用「**[!UICONTROL 連結使用中]**」選項，請加以啟用。

   選取此選項後，會建立一個可以與任何人共用的專案連結。您可以隨時透過停用此選項來停用對專案的存取權。

   該專案的所有者也是該連結的所有者。只有在專案所有權轉移時，連結所有權才能轉移給其他使用者，如 Analytics 管理員指南中的[轉移使用者資產](/help/tools/asset-transfer/transfer-assets.md)中所述。

1. 選擇是否啟用以下安全選項 (此選項可由您的 Customer Journey Analytics 管理員控制)：

   * **[!UICONTROL 需要 Experience Cloud 驗證]：**

     啟用此選項後，唯一可以存取專案的使用者，就是可以登入 Adobe Experience Cloud 組織 (其中已建立您共用的專案) 的人。但是，您與之共用的使用者不需要擁有 Customer Journey Analytics 的存取權。

     Customer Journey Analytics 管理員可以為公司設定此偏好設定，如[偏好設定](/help/analysis-workspace/user-preferences.md)中所述。視管理員設定此選項的方式而定，您可能會遇到以下情況：

      * 如果此選項未顯示，就代表您的 Customer Journey Analytics 管理員未啟用此功能。

      * 如果已啟用此選項且您無法將其停用，則鎖定的選項表示您的Customer Journey Analytics管理員需要對任何存取Analysis Workspace專案的人進行Experience Cloud驗證。 授權 Healthcare Shield 的組織都需要這樣做。

1. 在「**[!UICONTROL 與任何人共用 (無需登入)]**」欄位旁邊，選取「![連結](/help/assets/icons/Link.svg)」以將連結複製到系統剪貼簿。

1. 與您希望有該專案存取權的人員共用連結。例如，您可以將連結貼上到電子郵件中。

   您與之共用連結的任何人都可以檢視 Analysis Workspace 專案。

1. (選用) 您可以選取「![產生新連結圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)」，以便將先前收到專案連結之使用者的存取權移除。此時會產生一個新連結；您可以與您希望存取該專案的使用者共用該連結。

1. 選取「**[!UICONTROL 關閉]**」以關閉共用對話框。您的變更會自動儲存。

## 查看與您共用的專案

當有人透過[共用特定的專案角色](#share-a-specific-project-role)與您共用專案時，您可以從 [ Analytics 登陸頁面上的專案標籤](/help/getting-started/landing.md#navigate-the-projects-tab)存取共用專案。

當有人透過共用連結（從[共用專案標籤](#share-a-link-to-a-project)或使用[與任何人共用連結](#share-a-project-with-anyone-no-login-required)）與您共用專案時，您必須使用與您共用的連結來存取專案。 例如，該連結可能已在電子郵件、內部網站等中提供。

## 共用嵌入元件

您可以共用專案所屬的嵌入元件。

>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在 Analysis Workspace 中共用嵌入元件](https://video.tv.adobe.com/v/24713/?quality=12&learn=on){target="_blank"}的示範影片。

{{videoaa}}

>[!ENDSHADEBOX]


## 常見問題 {#FAQs}

| 問題 | 回答 |
|---|---|
| 如果兩個編輯者同時儲存專案，會發生什麼情況？ | 不會合併變更，並會保留最後儲存的專案版本。 Analysis Workspace 目前不支援即時共同作業。 |
| 身為管理員，我會有何種專案體驗？ | 置於&#x200B;**[!UICONTROL 編輯復本]**&#x200B;或&#x200B;**[!UICONTROL 唯讀]**&#x200B;角色的管理員，在開啟專案時會收到這些有限的體驗。 如有需要，管理員可隨時透過「**[!UICONTROL 元件] > [!UICONTROL 專案]**」，將其角色增加到&#x200B;**[!UICONTROL 編輯原始項目]**&#x200B;中。 |
| 如果某個收件者以個人身分設定於某個角色，又以群組成員身分設定於另一個角色，會發生什麼情況？ | 如果收件者獲得多個角色，將一律會有較高的體驗。 例如，如果收件者以個人身分獲得&#x200B;**[!UICONTROL 編輯原始版本]**&#x200B;角色，並且以群組成員身分獲得&#x200B;**[!UICONTROL 可以檢視]**&#x200B;角色，則使用者會收到&#x200B;**[!UICONTROL 編輯原始版本]**&#x200B;專案體驗。 |
| 如果收件者開啟了專案連結，將有何體驗？ | 收件者會獲得您在分享模式中為其設定的角色。 收件者若未被指派任何角色，且收到專案的連結(**[!UICONTROL 共用]** > **[!UICONTROL 與Workspace使用者共用]**，然後選取&#x200B;**[!UICONTROL 透過連結共用]**&#x200B;欄位旁的&#x200B;**[!UICONTROL 複製]**)，則會獲得預設角色。 管理員會收到&#x200B;**[!UICONTROL 編輯原始檔案]**，非管理員會收到&#x200B;**[!UICONTROL 編輯復本]**&#x200B;角色。 |
