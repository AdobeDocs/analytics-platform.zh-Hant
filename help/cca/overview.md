---
title: 跨管道分析概觀
description: 重新輸入多個資料集的人員 ID，以彙整人員。
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: bfaf76fa5f225e9aa3153fc4ee10c5be8f3164e7
workflow-type: ht
source-wordcount: '1159'
ht-degree: 100%

---


# 跨管道分析概觀

**歷程 IQ：跨管道分析**&#x200B;功能可讓您重新輸入資料集的人員 ID，順利合併多個資料集。跨管道分析功能會檢視已驗證和未驗證工作階段的使用者資料，以產生拼接 ID。使用跨管道分析，您可以回答下列問題：

* 有多少人在某個管道開始體驗，但在不同管道結束體驗？
* 有多少人與我的品牌互動？他們使用的裝置數量與類型為何？他們互相重疊的程度？
* 人們會在行動裝置上開始工作，稍後再移至桌上型電腦完成工作的頻率為何？登陸在一部裝置上的行銷活動點進次數，是否會導致在其他位置上的轉換？
* 如果將跨裝置歷程列入考量，我對行銷活動成效的理解會有何改變？我的漏斗分析會有何改變？
* 使用者在裝置間移動最常採取的路徑為何？他們在哪裡退出？他們在哪裡獲得成功？
* 多部裝置使用者的行為與單一裝置使用者的行為有何不同？

合併人員 ID 相似的資料集時，系統會跨裝置和管道套用原本的歸因。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站，但後來遇到訂單問題，於是他打電話給您的客戶服務團隊，期能解決問題。透過跨管道分析，您可以將客服中心事件歸因於使用者原本點擊的廣告。

## 先決條件

>[!IMPORTANT]
>
>若未滿足所有先決條件，可能導致您無法建立跨管道分析連線，或在合併資料集時成效不佳。

使用跨管道分析前，請確認您的組織已做好下列準備：

* Adobe Experience Platform 中，一個資料集必須具有兩個可協助識別人員的欄：
   * **永久 ID**，每列都會顯示這個識別碼，例如 Adobe Analytics AppMeasurement 資料庫產生的人員 ID。
   * **暫時 ID**，僅部分列會顯示這個識別碼，例如人員驗證後雜湊的使用者名稱或電子郵件地址。您可以使用幾乎所有偏好的識別碼，但前提是該識別碼在相同事件上必須至少顯示為指定的永久 ID 一次。
* 在另一個資料集 (例如客服中心資料) 中，每列都包含一個暫時 ID。此人員 ID 的格式必須與其他資料集中的暫時 ID 格式類似。
* 此功能可讓您彙整資料集，包括合併的已驗證和未驗證使用者資料。合併資料集前，請務必遵守適用的法律和法規，包括取得必要的使用者權限。

## 限制

>[!IMPORTANT]
>
>對全域事件資料集綱要所做的任何變更，都必須同時套用至新拼接資料集綱要，否則將會中斷拼接的資料集。
>
>此外，如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。

跨管道分析是一項具突破性的完善功能，但使用方式上有所限制。

* 目前，金鑰重設功能僅限於一個步驟 (永久 ID 改成暫時 ID)。不支援多步驟重設金鑰 (例如從永久 ID 改成暫時 ID，之後又改成另一個暫時 ID)。
* 僅支援事件資料集。其他資料集概不支援，例如查詢資料集。
* 不支援您組織中使用的自訂 ID 地圖。
* 不支援跨裝置私人圖片。
* 跨管道分析不會以任何方式轉換用於彙整的欄位。以欄位為基礎的彙整使用指定欄位中的值，因為該值存在於資料湖中未彙整的資料集中。彙整流程區分大小寫。例如，如果有時在欄位中出現「Bob」一詞，有時又出現「BOB」一詞，則這些人將被視為兩個不同的人。
* 由於欄位式拚接區分大小寫，因此對於透過 Analytics 來源連接器產生的 Analytics 資料集，Adobe 建議檢閱適用於暫時 ID 欄位的所有 VISTA 規則或處理規則，以確保這些規則不會引入相同 ID 的新形式。例如，您應確保沒有任何 VISTA 或處理規則僅在一部分事件中，將小寫字母引入暫時 ID 欄位。
* 以欄位為基礎的彙整不會合併或串連欄位。
* 暫時 ID 欄位應包含單一 ID 類型 (即來自單一命名空間的 ID)。例如，暫時 ID 欄位不應包含登入 ID 和電子郵件 ID 的組合。
* 如果針對同一永久 ID 發生了具有相同時間戳記的多個事件，但暫時 ID 欄位中的值不同，則以欄位為基礎的彙整將根據字母順序進行選擇。因此，如果永久 ID A 有兩個具有相同時間戳記的事件，且其中一個事件指定 Bob、另一個事件指定 Ann，則以欄位為基礎的彙整會選擇 Ann。
* 如果某個裝置由多人共用，並且使用者之間的切換總數超過 50.000，CCA 將停止為該裝置拼接資料。

## 啟用跨管道分析

符合所有先決條件並了解限制後，貴組織就能按照下列步驟，在 Customer Journey Analytics 中開始使用。

1. 將所需的資料匯入 Adobe Experience Platform。如為 Adobe Analytics 資料，請參閱[在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。如為其他類型資料，請參閱 Adobe Experience Platform 文件中的[建立綱要](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hant)和[匯入資料](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hant)。
1. 請聯絡 Adobe 客戶支援，提供下列資訊：
   * 跨管道分析啟用申請
   * 您要重設金鑰之資料集的資料集 ID
   * 所需資料集的永久 ID 欄名稱 (顯示於每列的識別碼)
   * 所需資料集的暫時 ID 欄名稱 (資料集間的人員識別碼連結)
   * 您的[重播](replay.md)頻率和回顧時間長度偏好設定，選項包括每週重播一次，回顧期間為 7 天，或每天重播一次，回顧期間為 1 天。
   * 沙箱名稱。
1. Adobe 客戶支援將與 Adobe 工程部門合作，以便在收到您的請求後啟用跨管道分析。啟用後，Adobe Experience Platform 會顯示一個包含新人員 ID 欄的新的重設金鑰資料集。Adobe 客戶支援可提供新資料集 ID 和人員 ID 欄名稱。
1. 首次打開時，Adobe 將提供回填的彙整資料，其回溯時間可追溯到上個月初 (最多 60 天)。為了執行此回填，暫時性 ID 必須在未回溯的時間中存在於未彙整的資料中。
1. 使用新產生的資料集和您要加入的其他資料集，在 Customer Journey Analytics 中[建立或編輯連線](/help/connections/create-connection.md)。為每個資料集選擇正確的人員 ID。
1. 根據連線[建立資料檢視](/help/data-views/create-dataview.md)。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

設定資料檢視後，Customer Journey Analytics 中的分析功能就會像 Customer Journey Analytics 的其他分析功能一樣，除了當下之外，資料都會跨管道和裝置運作。
