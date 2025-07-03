---
description: 瞭解如何使用Debugger來疑難排解Analysis Workspace中專案的問題。
keywords: Analysis Workspace
feature: Workspace Basics
title: 專案偵錯工具
role: User
source-git-commit: ae8c1fb127accae53ab9363a8cceedd5221a245b
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 3%

---

# 專案偵錯工具

專案偵錯工具可協助您和Adobe支援人員疑難排解您在Analysis Workspace中的專案問題。 Adobe支援可能會要求您啟用Debugger，以疑難排解您透過Adobe支援提出的票證。 問題的範例是視覺效果的載入時間或視覺效果中損壞的元件。

>[!NOTE]
>
>若要使用偵錯工具，您必須擁有&#x200B;**編輯**&#x200B;或&#x200B;**複製** [專案](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-25744)的存取權。
>


## 啟用偵錯工具

>[!IMPORTANT]
>
>在啟用除錯工具之前，請先儲存您的專案。
>

若要啟用除錯程式：

1. 從Analysis Workspace專案功能表選取&#x200B;**[!UICONTROL 說明]** > **[!UICONTROL 啟用偵錯工具]**。
1. 在&#x200B;**[!UICONTROL 啟用偵錯工具]**&#x200B;對話方塊中選取&#x200B;**[!UICONTROL 確定]**。
1. 瀏覽器提示您重新載入頁面或網站時確認。


## 使用偵錯工具

當您啟用除錯工具時，專案中的所有視覺效果都會有一個額外的![錯誤](/help/assets/icons/Bug.svg)圖示。

若要針對特定視覺效果使用除錯程式：

1. 在視覺效果頂端選取![錯誤](/help/assets/icons/Bug.svg)。

   ![偵錯工具內容功能表](assets/debugger-context-menu.png)

1. 從內容功能表中選取適當的動作。 可用的動作取決於視覺效果，並指明您要執行的偵錯型別。 例如，如果您選取&#x200B;**[!UICONTROL 異常]**，您想要偵錯視覺效果中的異常功能。
1. 從子功能表中選取時間戳記。
1. 會開啟&#x200B;**[!UICONTROL Oberon XML]**&#x200B;偵錯視窗，其中包含視覺效果所執行之特定功能的詳細資料。 如需異常請求輸出的範例，請參閱下文。

   ![輸出偵錯要求](assets/debugger-oberon.png)

   詳細資訊如下：

   * **[!UICONTROL 要求時間戳記]**
   * **[!UICONTROL 回應時間戳記]**
   * **[!UICONTROL 要求時間]**
   * **[!UICONTROL 佇列時間]**
   * **[!UICONTROL 伺服器處理時間]**
   * **[!UICONTROL 查閱時間]**
   * **[!UICONTROL 複雜度]**
   * **[!UICONTROL 月邊界]**
   * **[!UICONTROL 欄]**
   * **[!UICONTROL 區段]**
   * **[!UICONTROL XML]** **[!UICONTROL 要求]**&#x200B;和&#x200B;**[!UICONTROL 回應]**
   * **[!UICONTROL cURL要求]**
   * **[!UICONTROL JSON]** **[!UICONTROL 要求]**&#x200B;和&#x200B;**[!UICONTROL 回應]**

1. 使用![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 將所有欄位複製到剪貼簿]**，將所有偵錯資訊複製到剪貼簿。 將資訊貼到您偏好的編輯器或工具中。 資訊包含：

   * XML (請求)
   * XML (回應)
   * JSON (請求)
   * JSON (回應)
   * Curl 請求

1. 在![cURL請求](/help/assets/icons/Copy.svg)下使用&#x200B;**[!UICONTROL 複製]** **[!UICONTROL 複製到剪貼簿]**，將請求複製到剪貼簿。
1. 將游標暫留在任何&#x200B;**[!UICONTROL 要求]**&#x200B;或&#x200B;**[!UICONTROL 回應]**&#x200B;文字區域上以顯示並選取![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 複製到剪貼簿]**，將該文字區域（XML或JSON）的內容複製到剪貼簿。

1. 交換您已複製以及哪個Adobe支援請求的任何資訊，以疑難排解Analysis Workspace專案中的視覺效果。

1. 選取&#x200B;**[!UICONTROL 取消]**&#x200B;以關閉&#x200B;**[!UICONTROL Oberon XML]**&#x200B;偵錯視窗並返回您的專案。

針對您想要疑難排解的任何其他視覺效果，重複上述步驟。

## 停用偵錯工具

>[!IMPORTANT]
>
>在停用偵錯工具之前，請儲存您對專案所做的任何變更，並且要將其保留在偵錯練習中。
>

若要停用除錯程式：

1. 從Analysis Workspace專案功能表選取&#x200B;**[!UICONTROL 說明]** > **[!UICONTROL 停用偵錯工具]**。
1. 在&#x200B;**[!UICONTROL 停用偵錯工具]**&#x200B;對話方塊中選取&#x200B;**[!UICONTROL 確定]**。
1. 瀏覽器提示您重新載入頁面或網站時確認。



