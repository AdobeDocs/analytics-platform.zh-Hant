---
title: 使用匯整
description: 如何使用拼接
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: true
hidefromtoc: true
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: c4aea74807be15af56413522d9e6fbf5f18a37a0
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 3%

---

# 使用匯整

您可以在已設定為連線一部分的一或多個事件資料集上啟用拼接。 您可以啟用彙整功能的事件資料集數目，會由您已授權的Customer Journey Analytics套件決定。

當您[建立連線](/help/connections/create-connection.md#dataset-settings)或當您[編輯連線](/help/connections/create-connection.md)時，您可以將拼接啟用為事件資料集之[資料集設定](/help/connections/manage-connections.md#edit-a-connection)的一部分。

若要啟用拼接，請在&#x200B;**[!UICONTROL 新增資料集]**&#x200B;或&#x200B;**[!UICONTROL 編輯資料集]**&#x200B;對話方塊的事件資料集區段中：

啟用身分拼接時![身分拼接選項](assets/identity-stitching-ui.png)

1. 選取&#x200B;**[!UICONTROL 啟用身分拼接]**。

   如果您啟用現有事件資料集的彙整功能，**[!UICONTROL 變更人員ID]**&#x200B;對話方塊會顯示由於使用彙整功能而變更人員ID的潛在影響。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   **[!UICONTROL 啟用身分拼接]**&#x200B;對話方塊會摘要拼接身分的結果。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

1. 從&#x200B;**[!UICONTROL 永久ID]**&#x200B;下拉式功能表中選取永久ID。

   如果您為永久ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項:

   * 啟用&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。

1. 從&#x200B;**[!UICONTROL 人員ID]**&#x200B;下拉式功能表中選取人員ID。

   如果您為人員ID選取&#x200B;**[!UICONTROL 身分對應]**，則必須選取名稱空間。 您有兩個選項:

   * 啟用&#x200B;**[!UICONTROL 使用主要身分名稱空間]**&#x200B;以使用主要身分名稱空間。
   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


   如果您為人員ID選取&#x200B;**[!UICONTROL 身分圖表]**，則必須選取名稱空間。

   >[!NOTE]
   >
   >您必須有權使用身分圖表。
   >

   在此之前，會顯示&#x200B;**[!UICONTROL 變更為身分圖表]**&#x200B;對話方塊，以確保您在使用身分圖表進行拼接之前[已完成資料集](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service)的身分圖表設定。 選取&#x200B;**[!UICONTROL 繼續]**&#x200B;以繼續。

   * 從&#x200B;**[!UICONTROL 名稱空間]**&#x200B;下拉式功能表中選取名稱空間。


1. 從&#x200B;**[!UICONTROL 回顧視窗]**&#x200B;下拉式功能表中選取回顧視窗。 可用選項取決於您有權使用的Customer Journey Analytics套件。

一旦您儲存的連線包含已啟用身分拼接的資料集，每個資料集的拼接程式都會在該資料集的資料擷取開始時開始。