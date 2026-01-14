---
title: 建立您的結構描述以便與 Customer Journey Analytics 搭配使用
description: 瞭解如何設計XDM結構描述，充分發揮Customer Journey Analytics的彈性，同時支援來自Adobe Analytics的實用移轉路徑。
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 5808de9b39d3c8fa5632755958ddb887c081b203
workflow-type: tm+mt
source-wordcount: '1467'
ht-degree: 9%

---

# 建立您的結構描述以便與 Customer Journey Analytics 搭配使用 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="建立結構描述"
>abstract="在您的組織內討論資料收集的需求，並確定您想要如何建置在 Adobe Experience Platform 內使用的結構描述。之所以顯示這個步驟，是因為您要使用推薦流程，即使用針對您組織量身打造的結構描述。正確執行此步驟極為重要，因為組織內所有團隊均遵循一個結構描述，可以十分輕鬆地完成資料攝取。<br><br>將組織中所有相關方整合以便遵循統一的結構描述，預估要花費 1-2 個月時間。這個時間段極度依賴所要協調的團隊數量，以及要遵循的維度 + 量度數量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe建議在實作[Adobe Experience Platform資料彙集](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/xdm/home)時，為Customer Journey Analytics建立自訂[Experience Data Model](https://experienceleague.adobe.com/en/docs/experience-platform/collection/home) (XDM)結構描述。 建立此結構描述通常會在觸及任何實作變更或程式碼之前完成。 自訂結構描述可讓您設計簡潔、組織特定的資料合約，而不繼承Adobe Analytics的限制。 請參閱[選擇您的Customer Journey Analytics結構描述](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)，以進一步瞭解貴組織可用的結構描述型別。

結構描述旨在完善您想要長期建構資料的方式。 對結構描述進行變更的成本很高，因為它們會影響資料收集、驗證和下游服務。 您可以隨著業務需求允許逐漸新增到結構描述；但是，一旦資料開始流入，結構描述欄位就無法移除。

## 比較結構描述與資料檢視

Customer Journey Analytics的資料管道包含個別的資料收集區和資料詮釋區。 從Adobe Analytics升級時，嘗試在XDM中重新建立prop和eVar的行為是一種常見的錯誤。 請改用網頁SDK來收集資料，並使用[資料檢視](/help/data-views/data-views.md)來判斷資料在報表中的解譯方式。

| 圖層 | 主要用途 | 彈性 | 屬於什麼 | 不屬於 |
|---|---|---|---|---|
| **XDM結構描述** | 定義所收集資料的持久結構和意義 | 剛性；被視為不可變資料點 | 事件和實體形狀、欄位含義、關係、允許值、跨管道重複使用 | 編號的「槽」(eVar1/prop1)、歸因/持續性邏輯、報表專用因應措施 |
| **資料檢視** | 定義收集到的資料在分析中的行為方式 | 彈性；可自由修改，並可回溯性地重新解讀資料 | 元件設定、歸因和持續性行為、衍生欄位、篩選量度、計算量度 | 欄位的基本意義；該意義在結構描述中應該穩定 |

## 比較方案與Adobe Analytics資料彙集

Customer Journey Analytics使用的Experience Data Model可大幅提高其他大多數Analytics解決方案(包括Adobe Analytics)的彈性。 建立穩固的結構描述是貴組織避免執行其他Analytics產品中存在的限制的機會。

| Adobe Analytics的常見習慣 | XDM + Customer Journey Analytics中更好的方法 |
|---|---|
| 圍繞著編號位置(`eVar1`-`eVar250`， `prop1`-`prop75`)進行設計 | 建立具有穩定含義的欄位（例如，`search.term`、`content.category`、`user.membershipTier`）並一致地重複使用它們 |
| 將持續性/配置/到期編碼到資料模型中 | 擷取結構描述中的永續性事實；在資料檢視層級套用歸因和持續性行為 |
| 在多個變數中複製相同的值以達成報告行為 | 將值儲存一次，並在資料檢視中建立多個元件（維度/量度） |
| 針對您可能會想要的每個計數建立唯一的「量度欄位」 | 擷取正確事實一次（通常為列舉/布林值/字串），然後在資料檢視中將量度定義為篩選計數 |
| 設計變數以「預先解決」報表 | 設計您的結構描述以擷取事實，並使用資料檢視解決報告語意 |

## 使用通用屬性建立方案

當您標準化出現在許多事件中的一組可重複使用的屬性時，就有可能建立跨管道的統一結構描述。 部分範例包括：

* **體驗內容：**&#x200B;網站/應用程式名稱、環境、地區設定、頻道、品牌
* **歷程內容：**&#x200B;行銷活動識別碼、反向連結內容、實驗識別碼
* **使用者狀態：**&#x200B;登入狀態、成員等級、帳戶型別
* **互動詳細資料：**&#x200B;互動名稱/型別、UI區域、元素標籤、錯誤類別

關鍵是將欄位代表的內容標準化，而不管頻道為何。 避免跨管道以不同方式建立相同的概念模型，除非它們真正代表不同的概念。 例如，避免將網頁促銷活動ID和行動促銷活動ID設為個別的結構描述欄位，或許是明智的做法。 個別的結構描述欄位會使得跨管道建立廣告支出資料回報的難度增加。 如果報表中需要區分，您可以依管道分段或串連多個欄位以提供該區分。 相同的結構欄位可用於任何數量的維度或量度。

若要支援多個管道，同時保留單一結構描述策略，實用方式是使用&#x200B;**核心+擴充功能**&#x200B;模式：

* **核心：**&#x200B;廣泛適用於不同管道和團隊的欄位
* **擴充功能：**&#x200B;頻道或網域特定欄位群組，僅於需要時適用（網頁互動、商務、行動生命週期、伺服器端細節）

此模式支援單一組織結構描述策略，不會強制團隊填入不必要的欄位。

## 偏好適合的標準欄位群組

Adobe建議在符合您需求的地方使用標準化的欄位群組，並使用自訂欄位進行延伸以取得組織特定的概念。

標準欄位群組通常可協助您：

* 使用已知欄位語意減少歧義
* 更輕鬆地跨團隊校準
* 支援跨Adobe Experience Platform應用程式的互通性

自訂欄位適用於以下情況：

* 您的組織有無法完全對應至標準欄位的概念
* 您需要其他屬性以滿足報告、治理或啟用要求
* 您想要代表特定企業分類法（例如，內部內容類別）

## 決定如何計算量度

在Adobe Analytics中，許多團隊會將`events`變數視為追蹤量度的唯一方法。 在Customer Journey Analytics中，您可以根據您需要計算的專案及您想要解譯的方式，以多種方式追蹤量度。

在架構架構時，請遵循事實。 例如，`error.type = "validation"`，`user.isLoggedIn = true`，`checkout.step = "shipping"`。 將資料檢視中的量度定義為這些事實的計數和篩選計數。 例如：

* `checkout.step` （列舉/字串）可以支援：
   * 「結帳：到達運送步驟」（在`checkout.step == "shipping"`處計數）
   * 「結帳：已達付款步驟」
* `error.type` （列舉/字串）可以支援：
   * 「驗證錯誤」
   * 「授權錯誤」
* `user.isLoggedIn` （布林值）可以支援：
   * 「已驗證的工作階段」
   * 「已驗證的轉換」

>[!TIP]
>
>在決定某個專案是否應該在結構描述中作為專用欄位與稍後是衍生欄位時，如果永續性事實廣泛有用且穩定，則偏好擷取結構描述中的永續性事實。 您可以在收集資料後，使用衍生欄位來更正或改變資料的外觀。

## 在轉換期間與Adobe Analytics保持同位功能，免除方案包袱

有些組織在升級至Customer Journey Analytics時需要繼續Adobe Analytics報告。 您可以透過下列方法，維護同位檢查，而無須將Analytics特有的成品引入長期結構描述設計中：

1. **使用Adobe Analytics可辨識且自動對應的XDM欄位路徑：**&#x200B;當您透過Edge Network將可辨識的XDM欄位傳送至Adobe Analytics時，這些欄位會[自動對應](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/aep-edge/xdm-var-mapping)，無需額外設定。
1. **使用組織特定概念的自訂XDM欄位：**&#x200B;任何未自動對應至Analytics變數的XDM欄位都會轉送為Adobe Analytics中的[內容資料變數](https://experienceleague.adobe.com/zh-hant/docs/analytics/implementation/vars/page-vars/contextdata)。
1. **使用Adobe Analytics處理規則將這些內容資料變數對應至prop/eVars：** [處理規則](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview)最終可讓您將任何自訂XDM欄位對應至任何eVar或prop。 此概念支援Adobe Analytics中的同位檢查報告，同時保持您的結構描述整潔且以Customer Journey Analytics為中心。

## 識別利害關係人並定義所有權

在同意並維護欄位含義時，結構描述設計會成功。 雖然組織結構不盡相同，但下列角色通常會參與：

* **Analytics管理員/分析員**：定義報表問題、驗證欄位是否代表有意義的概念，以及檢閱資料檢視中的分析語意。
* **開發人員/實作擁有者**：確保能夠使用Web SDK可靠地收集欄位，並與資料層/應用程式檢測一致。
* **資料架構師/工程師**：確保結構描述一致性、跨網域重複使用，以及與下游服務的相容性。
* **隱私權/控管利害關係人**：檢閱資料最小化、同意期望和資料使用限制。

定義結構描述變更的清除擁有者。 穩定的架構具有嚴格的變更控制，可防止下游中斷並減少重工。 請考慮使用追蹤治理工作流程或工具，將請求大眾化並管理一段時間的變更控制。

## 隱私權與治理考量事項

結構描述設計應根據您組織的隱私權政策，反映隱私權和管理期望。 架構架構時，請考量下列幾點：

* 僅收集您支援已定義使用案例所需的專案。
* 確保同意和資料使用需求可反映在您的收集策略中。 如需詳細資訊，請參閱[使用Web SDK處理客戶同意資料](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/consent/sdk)。
* 考慮如何在Adobe Experience Platform治理工具中標籤和控制敏感欄位。 如需詳細資訊，請參閱[Adobe Customer Journey Analytics和資料控管](/help/privacy/privacy-overview.md)。

## 後續步驟

當您建立並同意結構描述架構後，就可以開始在Adobe Experience Platform中建立它。 如需詳細資訊，請參閱[建立要與Customer Journey Analytics搭配使用的自訂結構描述](cja-upgrade-schema-create.md)。
