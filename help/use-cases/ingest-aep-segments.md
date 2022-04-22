---
title: 將AEP觀眾吸引到Customer Journey Analytics
description: 說明如何將AEP觀眾錄入Customer Journey Analytics以進一步分析。
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 2%

---


# 將AEP觀眾吸引到Customer Journey Analytics(CJA)

(AEP文檔經理說，Brandon, fyi, &#39;Unified Profile&#39;是「即時客戶配置」的過時術語。 在AEP文檔集中找不到任何UP文檔。)

本使用案例探討了將Adobe Experience Platform(AEP)觀眾引入CJA的臨時手動方式。 這些受眾可能是在AEP段生成器或Adobe Audience Manager或其他工具中建立的，並儲存在即時客戶配置檔案(RTCP)中。 受眾包括人員ID、配置檔案ID等清單。 並將它們帶入CJA Workspace進行分析。

## 先決條件

* Adobe Experience Platform 的存取權 (AEP)，特別是即時客戶概要資訊。
* Customer Journey Analytics 的存取權
* 是否能夠編寫自定義代碼？
* 還有什麼。

## 步驟1:在即時客戶配置檔案中選擇受眾 {#audience}

Adobe Experience Platform [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP)通過組合來自多個渠道（包括線上、離線、CRM和第三方）的資料，讓您查看每個客戶的整體視圖。 RTCP中的受眾可能來自不同來源。 選擇一個或多個觀眾。

## 步驟2:為導出建立配置檔案聯合資料集

為了將訪問群體導出到可以與CJA建立連接的資料集，您需要建立其架構為Profile的資料集 [聯合架構](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas)。
聯合架構由多個共用同一類且已為配置檔案啟用的架構組成。 聯合架構使您能夠看到共用同一類的架構中包含的所有欄位的合併。 即時客戶配置檔案使用聯合方案為每個客戶建立一個整體視圖。

## 第3步：通過API調用將受眾導出到資料集 {#export}

在將受眾引入CJA之前，需要將其導出到AEP中的資料集。 這只能使用分段API完成，特別是 [導出作業API終結點](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en)。 您可以建立導出作業並將結果放在您在步驟2中建立的Profile Union AEP資料集中。

## 第4步：編輯導出輸出

在為受眾建立導出作業時，我們只需「人員ID」和「受眾ID」即可在CJA中執行報告。 但是，標準導出作業包含更多資料，因此我們需要編輯此輸出以刪除無關資料。

下面是Profile union資料集中導出輸出的示例， **先** 任何編輯：

![未編輯的輸出](assets/export-unedited.png)

請注意下列事項：

* 受眾ID包含在 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`。
* 狀態必須是「已實現」或「已輸入」，但不是「已退出」。 將&quot;exted&quot;替換為&quot;blank&quot;。

這是可以發送到CJA的Profile資料集的格式。

![已編輯的輸出](assets/export-edited.png)

以下是需要顯示的資料元素：

* `_aresprodvalidation`:引用您的組織ID。 你的會不一樣。
* `personID`:在這種情況下，友好名稱
* `audienceMembershipIdList` 字串欄位：受眾ID
* 為受眾添加友好名稱(`audienceMembershipIdName`)，例如

   ![友好的受眾名稱](assets/audience-name)

## 第5步：在CJA中建立到此配置檔案資料集的連接

[建立連線](/help/connections/create-connection.md)

## 步驟6:建立資料視圖

添加 `audienceMembershipIdName` 和 `personID` 到資料視圖。

## 第7步：工作區中的報告

您現在可以報告 `audienceMembershipIdName` 和 `personID` 的子菜單。
螢幕截圖會很棒。

要執行的操作：

為您處理屬於多個受眾的人時編寫更多步驟。




