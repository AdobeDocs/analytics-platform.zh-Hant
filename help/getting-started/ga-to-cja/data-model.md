---
title: GA4資料模型如何對應至Customer Journey Analytics
description: 瞭解GA4的事件型資料模型如何在Customer Journey Analytics中轉譯為XDM結構描述和資料集。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# GA4資料模型如何對應至Customer Journey Analytics

GA4和Customer Journey Analytics都是事件型平台，因此它們之間的資料模型轉換比Universal Analytics更直接。 瞭解GA4的事件和引數如何對應至Customer Journey Analytics的XDM欄位和資料集，讓您更輕鬆地解譯報告並與您的實作團隊合作。

## GA4的事件型資料模型

GA4中的每個互動都是&#x200B;**事件**：具名動作，包含提供內容的可選的&#x200B;**引數**&#x200B;集合。 頁面檢視、工作階段或目標沒有單獨的物件型別 — 它們都是事件。

| GA4事件型別 | 範例 |
|---|---|
| 自動收集 | `page_view`, `session_start`, `first_visit`, `scroll` |
| 增強的測量 | `file_download`, `video_start`, `form_submit` |
| 建議 | `purchase`, `add_to_cart`, `sign_up` |
| 自訂 | 您定義的任何事件名稱 |

每個事件最多可包含25個引數。 例如，`purchase`事件通常包含`transaction_id`、`value`、`currency`和`items`作為引數。

## Customer Journey Analytics如何儲存資料

Customer Journey Analytics從&#x200B;**Adobe Experience Platform**&#x200B;取得資料。 Platform中的資料儲存在&#x200B;**資料集**&#x200B;中，每個資料集都符合使用&#x200B;**體驗資料模型(XDM)**&#x200B;建立的&#x200B;**結構描述**。 XDM是Adobe用以呈現客戶體驗資料的開放標準。

Customer Journey Analytics中使用三種資料集型別：

| CJA資料集型別 | GA4等同專案 | 它儲存的內容 |
|---|---|---|
| [!UICONTROL 事件資料集] | GA4事件資料流 | 時間序列互動（頁面檢視、點按、購買） |
| [!UICONTROL 設定檔資料集] | GA4使用者屬性 | 個人層級屬性（CRM欄位、忠誠度狀態、人口統計） |
| [!UICONTROL 查詢資料集] | 用作參考表格的GA4自訂維度 | 索引鍵值參考資料（產品目錄、行銷活動名稱） |

Customer Journey Analytics沒有eVar、prop或成功事件。 所有維度和量度都直接來自XDM結構描述欄位。 不重複維度值的數量沒有限制。

## 自動收集的事件

GA4透過其SDK自動收集一組事件。 下表將這些事件對應至其XDM或Customer Journey Analytics對應專案。

| GA4自動收集事件 | XDM / Customer Journey Analytics對等函式 |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` （標準XDM欄位） |
| `session_start` | 工作階段開始（自動，根據資料檢視工作階段定義） |
| `first_visit` | [!UICONTROL 第一個工作階段]區段 |
| `scroll` | 自訂事件（需要明確的實作對應） |
| `click` | `xdm.web.webInteraction`欄位（需要實作） |
| `video_start` / `video_complete` | 媒體收集結構欄位（使用Adobe串流媒體服務） |
| `purchase` | `xdm.commerce.purchases`， `xdm.commerce.order` （標準XDM商務結構描述） |
| `add_to_cart` | `xdm.commerce.productListAdds` （標準XDM商務結構描述） |

>[!NOTE]
>
>使用網頁SDK實作時，有數個GA4的增強型測量事件（例如捲動、檔案下載或視訊）需要對應XDM欄位。 自動收集的方式與GA4的SDK處理方式不同。

## 自訂事件和引數

在GA4中，自訂事件具有名稱和最多25個引數。 在Customer Journey Analytics中，自訂事件對應到實作期間定義的自訂XDM結構描述欄位：

* **事件名稱**&#x200B;會成為XDM欄位中的欄位值（通常是[`xdm.eventType`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent)）。
* 每個&#x200B;**引數**&#x200B;會變成個別的XDM結構描述欄位。 當[設定資料檢視](/help/data-views/component-settings/overview.md)時，任何XDM欄位都可以公開為維度或量度。

>[!NOTE]
>
>貴組織自訂事件的特定XDM欄位路徑是在網頁SDK實作期間決定。 在建立報告之前，請與您的實作團隊合作，瞭解您的特定欄位對應。 如需詳細資訊，請參閱[架構您的結構描述](../cja-upgrade/cja-upgrade-schema-architect.md)。

## 使用者屬性

GA4使用者屬性是在使用者上設定的持續屬性（例如，`membership_tier`或`account_type`）。 在Customer Journey Analytics中，這些對應到Platform中的&#x200B;**設定檔資料集**。

設定檔資料集是從事件資料中單獨擷取，並使用共用人員ID在Customer Journey Analytics中聯結至該資料集。 用於此內容的常見人員ID包括客戶ID或電子郵件雜湊。 加入後，這些設定檔屬性就能與事件層級的資料一併作為Analysis Workspace中的維度使用。

此方法可讓Customer Journey Analytics比GA4的使用者屬性模型擁有更多彈性：GA4限制您只能使用其SDK中定義的使用者屬性，而Customer Journey Analytics設定檔資料集可包含任何系統的任何屬性（CRM、忠誠度平台、支援記錄），前提是它共用可加入的識別碼。

如果您的組織仍需將GA資料帶入Adobe Experience Platform，請參閱[擷取Google Analytics歷史資料](/help/use-cases/third-party/ga/backfill.md)和[設定適用於管理員的串流的Google Analytics資料](/help/use-cases/third-party/ga/streaming.md)。
