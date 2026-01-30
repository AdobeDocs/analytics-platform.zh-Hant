---
title: 拼接概觀
description: 拼接概觀
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 89%

---

# 拼接概觀

>[!NOTE]
>
>你必須擁有「**精選**」或更高版本的套裝 (針對[欄位型拼接](fbs.md)) 或者「**Prime**」或更高版本的套裝 (針對[圖表型拼接](gbs.md))，方能使用本節所述的功能。如果您不確定自己擁有哪一種 Customer Journey Analytics 套裝，請聯絡您的管理員。

身分拼接 (或簡稱拼接) 是強大的功能，可提高事件資料集的適用性，以進行跨管道分析。跨管道分析是 Customer Journey Analytics 的主要使用案例。此功能讓您可以根據共同識別碼 (個人 ID)，順暢地將來自不同管道的多個資料集進行合併，並執行報告。

合併個人 ID 相似的資料集時，系統會跨裝置和管道延續原本的歸因。例如：某位使用者透過桌上型電腦上的廣告造訪您的網站。使用者購買產品，但隨後此使用者的訂單發生問題。然後，使用者會向您的客戶服務團隊致電，來協助解決此問題。透過跨管道分析，您可以將呼叫中心事件歸因於此使用者原本點按的廣告。

很遺憾，並非所有屬於 Customer Journey Analytics 中連線的事件型資料集均已填入足夠的資料，可立即用於支援此歸因。尤其以網頁型或行動型體驗資料集，通常在所有事件均無實際個人 ID 資訊。

「拼接」功能可在一個資料集的列內重新輸入身分，來確保每個事件均可使用個人 ID (拼接 ID)。「拼接」功能會查看已驗證和未經驗證工作階段的使用者資料，以判斷可用作拼接 ID 的共同暫時 ID (個人 ID) 值。此重新輸入的動作可將不同的記錄解析為單一拼接 ID，以便在人員層級進行分析，而非在裝置或 Cookie 層級進行。

Customer Journey Analytics 支援兩種拼接類型：[欄位型拼接](fbs.md)和[圖表型拼接](gbs.md)。

## 先決條件

>[!IMPORTANT]
>
>未能滿足所有先決條件，可能導致無法正確進行跨管道分析。

使用拼接前，請確認您的組織已做好下列準備：

- 拼接包含合併經過驗證和未經驗證的使用者資料。在事件資料集上啟動拼接前，請務必遵守適用的法律和法規，包括取得必要的使用者權限。更多詳細資訊，請參閱[在 UI 中定義身分識別欄位](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/ui/fields/identity)。

- 將所需資料匯入 Adobe Experience Platform：

   - 如為 Adobe Analytics 資料，請參閱「[在 Customer Journey Analytics 中利用 Adobe Analytics 報告套裝資料](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)」。
   - 如為其他類型資料，請參閱 Adobe Experience Platform 文件中的[建立結構描述](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/tutorials/create-schema-ui)和[收錄資料](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/ingestion/home)。

如果您在定義 Customer Journey Analytics 連線時，將一個或多個拼接資料集與其他資料集 (例如呼叫中心資料) 結合，則可以獲得跨通路分析的優勢。此連線設定假設其他資料集的每一行都已包含一個個人 ID，與拼接 ID 類似。

## 啟用拼接

您可以透過兩種方式啟用「拼接」功能：

- [要求啟用拼接](/help/stitching/use-stitching.md) （已棄用）。 在核准後，系統就會為您已請求拼接的資料集建立重複的資料集。 此重複資料集包含具有拼接識別碼的其他欄。 您必須建立新連線或編輯包含拼接資料集的現有連線，才能在Customer Journey Analytics中使用拼接資料。
- [在連線介面](/help/stitching/use-stitching-ui.md)中啟用拼接。 當您在「連線」介面中設定資料集的拼接時，拼接會在「即時」發生，也就是在Customer Journey Analytics中從該資料集中擷取資料期間。

## 限制

>[!IMPORTANT]
>
>
>- 將對來源事件資料集結構描述所做的任何變更也套用至新拼接的資料集結構描述。
>
>- 如果您移除來源資料集，拼接的資料集將停止處理並被系統移除。
>
>- 資料使用標籤不會自動傳播到拼接資料集結構描述。如果您已將資料使用標籤套用至來源資料集結構描述，則需要將這些資料使用標籤手動套用至拼接資料集結構描述。如需更多資訊，請參閱[在 Experience Platform 中管理資料使用標籤](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/data-governance/labels/overview)。

拼接是一項具突破性的完善功能，但使用方式上有所限制。

- 僅支援事件資料集。其他資料集概不支援，例如查詢資料集。
- 拼接不會以任何方式改變用於拼接的欄位。拼接使用指定欄位中的值，因為該值存在於資料湖中未拼接的資料集中。
- 拼接程序區分大小寫。例如，如果有時在欄位中出現「Bob」一詞，有時又出現「BOB」一詞，這些 ID 將被視為兩個不同的人。

請勿將拼接與以下動作混淆：

- 兩個或多個資料集的合併。拼接僅適用於一個資料集。資料集合併是因為在設定 Customer Journey Analytics 連線時，選取了該連線中所選資料集內的相同個人 ID。

- 兩個資料集的結合。在 Customer Journey Analytics 中，結合通常用於 Analysis Workspace 中的尋找或分類。儘管拼接也使用到結合的功能，但過程本身涉及的不僅僅是結合。


## Journey Optimizer 資料集

拼接支援以下自動產生的 Journey Optimizer 資料集：

- AJO 歷程步驟事件
- AJO 傳入活動事件資料集
- AJO 表面資料集
- AJO 訊息回饋事件資料集* AJO 推播追蹤體驗事件資料集
- AJO 電子郵件追蹤體驗事件資料集
- AJO BCC 回饋事件資料集
- AJO 即時活動回饋事件資料集
- AJO ExD 決策事件資料集

>[!MORELIKETHIS]
>
>[欄位型拼接](fbs.md)
>[圖表型拼接](gbs.md)
>[使用拼接](use-stitching.md)
>[驗證拼接](validate.md)
>[拼接常見問題](faq.md)

