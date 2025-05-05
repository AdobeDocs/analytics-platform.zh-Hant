---
title: 拼接概述
description: 彙整概述
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: c27d5f44243e2cda252ac6a484a70964f0999dfc
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 15%

---

# 拼接概述

>[!NOTE]
>
>您必須有&#x200B;**Select**&#x200B;封裝或更高版本（適用於[欄位式拼接](fbs.md)）或&#x200B;**Prime**&#x200B;封裝或更高版本（適用於[圖形式拼接](gbs.md)），才能使用本節中說明的功能。 如果您不確定自己擁有哪一種 Customer Journey Analytics 套件，請聯絡您的管理員。

身分拼接（或簡單地說，拼接）是一項強大的功能，可提升事件資料集對於跨管道分析的適用性。 跨管道分析是Customer Journey Analytics可以處理的主要使用案例，可讓您根據通用識別碼（人員ID），順暢地合併和執行來自不同管道的多個資料集的報告。

合併人員 ID 相似的資料集時，系統會跨裝置和管道套用原本的歸因。例如，某位使用者先透過桌上型電腦上的廣告造訪您的網站，但後來遇到訂單問題，於是他打電話給您的客戶服務團隊，期能解決問題。透過跨管道分析，您可以將客服中心事件歸因於使用者原本點選的廣告。

遺憾的是，並非所有屬於Customer Journey Analytics中連線的事件型資料集都已填入足夠的資料，可立即支援此歸因。 尤其以網頁或行動為基礎的體驗資料集，通常沒有可用於所有事件的實際人員ID資訊。

拼接功能允許在一個資料集的列內重新輸入身分，確保每個事件都可使用人員ID （拼接的ID）。 拼接會檢視已驗證和未驗證工作階段的使用者資料，以決定可用作拼接ID的共同暫時ID （人員ID）值。 此金鑰重設允許將不同的記錄解析為單一彙整ID，以便在人員層級而不是裝置或Cookie層級進行分析。

Customer Journey Analytics支援兩種彙整型別： [欄位式彙整](fbs.md)和[圖表式彙整](gbs.md)。

## 先決條件

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法正確進行跨管道分析。

使用拚接前，請確認您的組織已做好下列準備：

- 拼接包括合併已驗證和未驗證的使用者資料。 在事件資料集上啟用連結之前，請確定您遵守適用的法律和法規，包括取得必要的一般使用者許可權。 有關詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。

- 將所需的資料匯入Adobe Experience Platform：

   - 如需Adobe Analytics資料，請參閱[在Customer Journey Analytics中利用Adobe Analytics報表套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)。
   - 如為其他類型資料，請參閱 Adobe Experience Platform 文件中的[建立結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/tutorials/create-schema-ui)和[匯入資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)。

如果在定義Customer Journey Analytics連線時，將一或多個拼接資料集與其他資料集（例如客服中心資料）結合，即可受益於跨管道分析。 此連線設定假設其他資料集每一列都包含人員ID，類似於拼接ID。


## 限制

>[!IMPORTANT]
>
>
>- 將您對來源事件資料集結構描述所做的任何變更也套用至新拼接資料集結構描述，否則這會中斷拼接的資料集。
>
>- 如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。
>
>- 資料使用標籤不會自動傳播到拼接的資料集結構描述。 如果您已將資料使用標籤套用至來源資料集結構描述，則需要手動將這些資料使用標籤套用至拼接的資料集結構描述。 如需詳細資訊，請參閱[在Experience Platform中管理資料使用標籤](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/labels/overview)。

拚接是一項具突破性的完善功能，但其使用方式有所限制。

- 僅支援事件資料集。其他資料集概不支援，例如查詢資料集。
- 拼接不會以任何方式轉換用於拼接的欄位。 拼接使用指定欄位中的值，因為該值存在於資料湖中未拼接的資料集中。
- 拚接程序區分大小寫。例如，如果有時在欄位中出現「Bob」一詞，有時又出現「BOB」一詞，則這些id會被視為兩個不同的人。

請勿將拼接與下列混淆：

- 兩個或多個資料集的合併。 拼接僅適用於一個資料集。 設定Customer Journey Analytics連線，並在連線的所選資料集中選取相同的人員ID，會造成資料集合併。

- 兩個資料集的聯結。 在Customer Journey Analytics中，聯結通常用於Analysis Workspace中的查閱或分類。 雖然銜接使用連線功能，但程式本身涉及的不只是連線。

>[!MORELIKETHIS]
>
>[以欄位為基礎的彙整](fbs.md)
>[以圖表為基礎的彙整](gbs.md)
>[使用拼接](use-stitching.md)
>[彙整](faq.md)的常見問題集

