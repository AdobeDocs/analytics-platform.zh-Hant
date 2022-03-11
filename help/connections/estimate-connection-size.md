---
title: 如何估算 CJA 連線規模
description: 回報 Customer Journey Analytics 目前的使用狀況
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: 966274d433d8495d32823d74c5f72107bb5f383a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 48%

---

# 估算連線規模

您可能需要知道 [!UICONTROL Customer Journey Analytics] 中有多少列資料。要準確瞭解組織的事件資料記錄（資料行）使用情況，請執行以下操作 **組織建立的每個連接**。

1. 在 [!UICONTROL Customer Journey Analytics] 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。

   您現在可以看到所有當前連接的清單。

1. 按一下每個連接名稱以進入連接管理器。

1. 將 **[!UICONTROL 可用事件資料記錄]** 為建立的所有連接。 （根據連接大小，可能需要一段時間才能顯示該數字。）

   ![事件資料](assets/event-data.png)

1. 一旦您擁有了所有事件資料行的總和，請查找您公司與Adobe簽署的Customer Journey Analytics合同中的「資料行」權利。

   這為您提供了銷售訂單中授權的最大資料行數。 如果步驟3產生的資料行數大於此數，則您將產生超量。

1. 要糾正此情況，您有以下幾種選擇：

   * 更改 [資料保留設定](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=zh-Hant#set-rolling-window-for-connection-data-retention)。
   * [刪除任何未使用的連接](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
   * [刪除AEP中的資料集](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)。
   * 請與Adobe客戶經理聯繫，以許可其他容量。

## 關於使用超額

使用限制由Adobe定期監控和強制執行。 「資料行」是指可用於Customer Journey Analytics內分析的每日平均資料行。

例如，假設您的合同賦予您100萬行資料。 假設在使用Customer Journey Analytics的第1天，您上載了200萬行資料。 在第2天，您將刪除100萬行，並將許可證期限的剩餘部分的使用量保持在承諾的最大值（即100萬行資料）。 根據您的合同條款，您在第1天仍可能會按比例支付超額使用費，因為您超出了您的「資料行」許可證權利。

## 診斷不一致

在部分情況下，您可能會發現連線所擷取的事件總數與 [!UICONTROL Adobe Experience Platform] 資料集中的列數不同。在此範例中，資料集「B2B Impression」有 7,650 列，但資料集在 [!UICONTROL Adobe Experience Platform] 中僅有 3,830 列。數據不一致有幾個原因，您可採取下列步驟加以診斷：

1. 依&#x200B;**[!UICONTROL 「Platform 資料集 ID」]**&#x200B;劃分此維度，您會發現兩個大小相同，但&#x200B;**[!UICONTROL 「Platform 資料集 ID」]**&#x200B;不同的資料集。每個資料集有 3,825 筆記錄，表示有 5 筆記錄缺少人員 ID 或時間戳記，導致 [!UICONTROL Customer Journey Analytics] 忽略了這些記錄：

   ![劃分](assets/data-size2.png)

1. 此外，如果查看 [!UICONTROL Adobe Experience Platform]，會發現沒有 ID 為「5f21c12b732044194bffc1d0」的資料集，這是因為最初建立連線時，有人從 [!UICONTROL Adobe Experience Platform] 中刪除了這個資料集。之後，雖然有人將資料集重新新增至 Customer Journey Analytics，但 [!UICONTROL Adobe Experience Platform] 產生的 [!UICONTROL Platform 資料集 ID] 不同。

深入了解在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[刪除資料集和連線可能造成的後果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)。
