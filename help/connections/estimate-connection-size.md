---
title: 如何估算 CJA 連線規模
description: 回報 Customer Journey Analytics 目前的使用狀況
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
feature: Connections
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '615'
ht-degree: 100%

---

# 估算連線規模

您可能需要知道 [!UICONTROL Customer Journey Analytics] 中有多少列資料。本主題旨在說明如何回報 [!UICONTROL Customer Journey Analytics] 目前的使用狀況。

1. 在 [!UICONTROL Customer Journey Analytics] 中按一下&#x200B;**[!UICONTROL 「連線」]**&#x200B;索引標籤。
1. 在[!UICONTROL 「編輯連線」]畫面上，選取要決定使用/連線規模的連線。

   ![編輯連線](assets/edit-connection.png)

1. 在左側邊欄選取連線的資料集。在此案例中，我們需要選取「B2B Impression」資料集。

   ![資料集](assets/dataset.png)

1. 按一下名稱旁邊的藍色 (i) 圖示 (即資訊的意思)，您會看到資料集有 3,800 列/個事件。此外，如需確切列數，請按一下預覽表格下方的&#x200B;**[!UICONTROL 「在 Experience Platform 中編輯」]**。這會將您重新導向 [!UICONTROL Adobe Experience Platform] 中的資料集。

   ![AEP 資料集資訊](assets/data-size.png)

1. 請注意，此資料集數量的&#x200B;**[!UICONTROL 「記錄總數」]**&#x200B;為 3,830 筆記錄，資料大小為 388.59 KB。

1. 對連線中的其他資料集重複執行第 1 步到第 5 步，並加總記錄數量/列數。最終的總和就是您連線的使用情形量度。這是您要從 [!UICONTROL Adobe Experience Platform] 擷取的連線資料集列數。

## 決定擷取列數

[!UICONTROL Customer Journey Analytics] 中實際擷取的事件數端視您的連線組態設定而定。此外，如果您選取錯誤的人員 ID，或資料集中的某些列無法使用此 ID，[!UICONTROL Customer Journey Analytics] 就會忽略這些列。若要決定實際擷取的事件列數，請執行下列步驟：

1. 儲存連線後，在不使用任何篩選器的情況下，建立相同連線的資料檢視。
1. 建立 Analysis Workspace 專案並選取正確的資料檢視。建立自由表格，並拖放具有&#x200B;**[!UICONTROL 「年」]**&#x200B;維度的&#x200B;**[!UICONTROL 「事件數」]**&#x200B;量度。在日期選取行事曆中選擇夠大的日期範圍，以涵蓋連線中的所有資料。這可讓您查看擷取至 [!UICONTROL Customer Journey Analytics] 的事件數。

   ![Analysis Workspace 專案](assets/event-number.png)

   >[!NOTE]
   >
   >這可讓您查看從事件資料集擷取的事件數，但不包含設定檔和查詢類型資料集。如需設定檔和查詢資料集的相關數據，請按照「估算連線規模」的第 1 步至第 3 步操作，加總所有數字即可得到此連線的總列數。

## 診斷不一致

在部分情況下，您可能會發現連線所擷取的事件總數與 [!UICONTROL Adobe Experience Platform] 資料集中的列數不同。在此範例中，資料集「B2B Impression」有 7,650 列，但資料集在 [!UICONTROL Adobe Experience Platform] 中僅有 3,830 列。數據不一致有幾個原因，您可採取下列步驟加以診斷：

1. 依&#x200B;**[!UICONTROL 「Platform 資料集 ID」]**&#x200B;劃分此維度，您會發現兩個大小相同，但&#x200B;**[!UICONTROL 「Platform 資料集 ID」]**&#x200B;不同的資料集。每個資料集有 3,825 筆記錄，表示有 5 筆記錄缺少人員 ID 或時間戳記，導致 [!UICONTROL Customer Journey Analytics] 忽略了這些記錄：

   ![劃分](assets/data-size2.png)

1. 此外，如果查看 [!UICONTROL Adobe Experience Platform]，會發現沒有 ID 為「5f21c12b732044194bffc1d0」的資料集，這是因為最初建立連線時，有人從 [!UICONTROL Adobe Experience Platform] 中刪除了這個資料集。之後，雖然有人將資料集重新新增至 [!UICONTROL Customer Journey Analytics]，但 [!UICONTROL Adobe Experience Platform] 產生的 [!UICONTROL Platform 資料集 ID] 不同。

深入了解在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[刪除資料集和連線可能造成的後果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hant#implications-of-deleting-data-components)。
