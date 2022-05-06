---
title: 將AEP觀眾吸引到Customer Journey Analytics
description: 說明如何將AEP觀眾錄入Customer Journey Analytics以進一步分析。
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 490a754270922481ebd893514c530a0667d9d6e4
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 1%

---

# 將AEP觀眾吸引到Customer Journey Analytics(CJA)

本使用案例探討了將Adobe Experience Platform(AEP)觀眾引入CJA的臨時手動方式。 這些受眾可能是在AEP段生成器或Adobe Audience Manager或其他工具中建立的，並儲存在即時客戶配置檔案(RTCP)中。 受眾包括一組配置檔案ID以及任何適用的屬性/事件等。 並將它們帶入CJA Workspace進行分析。

## 先決條件

* Adobe Experience Platform 的存取權 (AEP)，特別是即時客戶概要資訊。
* 訪問建立/管理AEP架構和資料集。
* 訪問AEP查詢服務（以及編寫SQL的能力）或執行一些輕量轉換的其他工具。
* Customer Journey Analytics 的存取權. 您需要成為CJA產品管理員才能建立/修改CJA連接和資料視圖。
* 能夠使用AdobeAPI（分段，可選的其他）

## 步驟1:在即時客戶配置檔案中選擇受眾 {#audience}

Adobe Experience Platform [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP)通過組合來自多個渠道（包括線上、離線、CRM和第三方）的資料，讓您查看每個客戶的整體視圖。

RTCP中的受眾可能來自不同來源。 選擇一個或多個觀眾，以加入CJA。

## 步驟2:為導出建立配置檔案聯合資料集

為了將訪問群體導出到最終可以添加到CJA中連接的資料集，您需要建立其架構為Profile的資料集 [聯合架構](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas)。

聯合架構由多個共用同一類且已為配置檔案啟用的架構組成。 聯合架構使您能夠看到共用同一類的架構中包含的所有欄位的合併。 即時客戶配置檔案使用聯合方案為每個客戶建立一個整體視圖。

## 第3步：通過API調用將受眾導出到Profile Union資料集 {#export}

在將受眾引入CJA之前，需要將其導出到AEP資料集。 這只能使用分段API完成，特別是 [導出作業API終結點](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en)。

可以使用您選擇的受眾ID建立導出作業，並將結果放在您在步驟2中建立的Profile Union AEP資料集中。 雖然您可以導出受眾的各種屬性/事件，但您只需導出與要利用的CJA連接中使用的人員ID欄位匹配的特定配置檔案ID欄位（請參見步驟5中的下面）。

## 第4步：編輯導出輸出

需要將導出作業的結果轉換為單獨的Profile資料集，以便被引入CJA。  此轉換可以使用AEP查詢服務或您選擇的另一個轉換工具來完成。  我們只需配置檔案ID（與CJA中的人員ID匹配）和一個或多個觀眾ID即可在CJA中進行報告。 但是，標準導出作業包含更多資料，因此我們需要編輯此輸出以刪除無關資料，並移動一些內容。  此外，在將已轉換的資料添加到模式/資料集之前，還需要先建立模式/資料集。

下面是Profile union資料集中導出輸出的示例， **先** 任何編輯：

![未編輯的輸出](assets/export-unedited.png)

請注意下列事項：

* 受眾ID包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`。
* 狀態必須是「已實現」或「已輸入」，但不是「已退出」。

這是可以發送到CJA的Profile資料集的格式。

![已編輯的輸出](assets/export-edited.png)

以下是需要顯示的資料元素：

* `_aresprodvalidation` 字串欄位：引用您的組織ID。 你的會不一樣。
* `personID` 字串欄位：這是Profile資料集上標準的XDM架構欄位，用於標識該人。 使用導出中的「配置檔案ID」。
* `audienceMembershipId` 字串欄位：導出的受眾ID。  注：可以根據需要（從您自己的架構）命名此欄位。
* 為受眾添加友好名稱(`audienceMembershipIdName`)，例如

   ![友好的受眾名稱](assets/audience-name.png)

* 如果需要，請添加其他受眾元資料。

## 第5步：將此配置檔案資料集添加到CJA中的現有連接

您可以建立新連接，但大多數客戶都希望將其添加到現有連接中。 受眾ID「豐富」CJA中的現有資料。

[建立連線](/help/connections/create-connection.md)

## 步驟6:修改現有（或建立新）CJA資料視圖

添加 `audienceMembershipId`。 `audienceMembershipIdName` 和 `personID` 的子菜單。

## 第7步：工作區中的報告

您現在可以報告 `audienceMembershipId`。 `audienceMembershipIdName` 和 `personID` 的子菜單。

## 其他附註

* 您應該在常規節奏上執行此過程，以便在CJA中不斷刷新觀眾資料。
* 可以在單個CJA連接中導入多個受眾。 這給過程增加了額外的複雜性，但是是可能的。 要使此操作正常，您需要對以上流程進行一些修改：
   1. 在RTCP中為受眾集合中的每個所需受眾執行此過程。
   1. 執行導出作業輸出的轉換時，需要建立 `audienceMembershipId(s)`，因為單個CJA人員ID可能屬於多個受眾。 在將來的某個時刻， CJA將支援配置檔案資料集中的陣列/對象陣列。 一旦支援了這些內容，則使用 `audienceMembershipId` 或 `audienceMembershipIdName` 是最好的選擇。 在中間，為導出作業輸出中的每個配置檔案ID提取所有當前受眾ID（狀態為「已實現」或「已輸入」），並將它們置於逗號分隔的值字串中(即， `<id1>,<id2>,...`)。  如果有狀態為「exted」的訪問群ID，請確保該ID不在清單中。  如果要維護與ID的友好名稱關聯，可將其附加到清單中每個ID的末尾（以及任何其他元資料）。
   1. 在資料視圖中，使用 `audienceMembershipId` 欄位，將逗號分隔的值字串轉換為陣列。 注：陣列中當前有10個值的限制。
   1. 現在可以報告此新維 `audienceMembershipIds` 在CJA工作區中。
