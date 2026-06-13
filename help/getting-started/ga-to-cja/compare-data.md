---
title: 為何GA4和Customer Journey Analytics資料不同
description: 瞭解GA4與Customer Journey Analytics之間的資料為何不同，以及如何稽核差異。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 7e4b9a2f-1c5d-4b8a-e3f9-6d2c8b7a4051
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 1300
ht-degree: 0%

---


# 為何GA4和Customer Journey Analytics資料不同

GA4和Customer Journey Analytics通常會針對相同時段和相同表觀量度報告不同的數字。 不同的資料收集方法、量度定義、身分模型和工作階段規則都會造成差異。 此頁面說明最常見的差異來源，並為稽核無法解釋的差距提供指引。

## 參與的工作階段

GA4會將工作階段視為&#x200B;**參與** （如果工作階段持續10秒以上）、包含至少一個主要事件，或有2次以上的頁面檢視。 此單一定義支援多個GA4量度，包括參與率、跳出率和活躍使用者背後的參與臨界值。

Customer Journey Analytics沒有內建的參與工作階段量度或維度；您可以定義參與以符合您的業務。 Adobe建議建立區段來擷取您的參與條件，並在參與關係重要的地方重複使用該區段。 您的管理員也可以將此定義提升至資料檢視中的量度，讓每個人都可以使用。

制定您自己的條件時，請挑選能真正指出網站值的訊號。 參與的三個常見建置區塊包括：

* **持續時間**：工作階段長度下限，例如10秒以上
* **深度**：事件或頁面檢視的最小數量，例如2個或更多
* **動作**：存在轉換或金鑰事件，例如註冊或購買

您可以將它們與`OR`結合，這樣，如果工作階段符合任一條件（如GA4那樣），工作階段即計為參與，或者將它們與`AND`結合，以符合更嚴格的要求。 如果目標為與GA4同位，請從預設值開始，然後從那裡調整。

### 參與率

一旦您有了參與工作階段的定義，參與率就是參與工作階段的份額。 若要將其建置為計算量度：

1. 在Analysis Workspace中，選取量度清單附近的&#x200B;**[!UICONTROL +]**&#x200B;圖示以開啟計算量度產生器。
2. 將其命名為「參與率」，並將格式設定為&#x200B;**[!UICONTROL 百分比]**。
3. 將公式定義為參與工作階段區段除以&#x200B;**[!UICONTROL 工作階段]**。
4. 選取&#x200B;**[!UICONTROL 「儲存」]**。

### 跳出率

在GA4中，跳出與參與工作階段相反，因此GA4的跳出率等於`1 - Engagement Rate`。 在Customer Journey Analytics中使用該公式將其建置為第二個計算量度。

Customer Journey Analytics也提供內建的&#x200B;**[!UICONTROL 跳出率]**&#x200B;量度，但其預設定義不同：它會計算只記錄單一事件的工作階段，這與GA4對許多網站的定義在方向相反。 比較GA4的跳出率與預設[!UICONTROL 跳出率]量度（而非您的`1 - Engagement Rate`計算），會產生截然不同的數字。

>[!TIP]
>
>Customer Journey Analytics中的工作階段定義可根據資料檢視來設定。 如果對等是貴組織的報告要求，則可以調整彈回和參與定義，以符合GA4的標準（10秒持續時間、2次以上頁面檢視或關鍵事件）。

## 工作階段

GA4和Customer Journey Analytics都預設為30分鐘的非活動逾時，且兩者都會讓工作階段透過午夜和工作階段中間的促銷活動變更進行。 （Universal Analytics會在這兩種情況下重設工作階段，因此這些工作階段會成為混淆的常見來源，但GA4和Customer Journey Analytics之間並沒有差異。） 有差異的規則包括：

| 規則 | GA4 | Customer Journey Analytics |
|---|---|---|
| 閒置逾時 | 全屬性範圍可調整（預設為30分鐘，最長7小時55分鐘） | 可依資料檢視設定 |
| 工作階段開始事件 | 僅限`session_start` （自動） | 可設定；任何事件都可以啟動工作階段 |
| 工作階段結束事件 | 無 | 可設定；任何事件都可以結束工作階段 |

由於Customer Journey Analytics的工作階段定義可設定，工作階段計數取決於資料檢視的設定方式。 將資料檢視的逾時和工作階段開始事件與您的GA4屬性進行比對，可讓平台之間的工作階段計數更為接近。

## 人員與作用中使用者

GA4的主要使用者量度&#x200B;**作用中的使用者**&#x200B;會計算在日期範圍內至少有一個參與工作階段的使用者。 Customer Journey Analytics中的&#x200B;**[!UICONTROL 人員]**&#x200B;量度會計入日期範圍內的不重複人員ID。

由於下列原因，這些量度可能會有所不同：

* **參與臨界值**： GA4作用中使用者會排除沒有[參與工作階段](#engaged-sessions)的訪客。 Customer Journey Analytics中的[!UICONTROL 人員]量度包含所有人，無論參與程度為何。
* **[!UICONTROL 彙整]**：如果已啟用彙整，在Customer Journey Analytics中，從行動裝置和桌上型電腦造訪過的人可計為一個使用者，但在GA4中可計為兩個使用者。 拼接通常會使[!UICONTROL 人員]量度低於拼接資料集上的GA4使用者。
* **身分模型**： GA4使用階層式身分模型；Customer Journey Analytics使用資料集中定義的任一人員ID。 這些差異會影響個人計數，與拼接無關。

## 身分識別與拼接

GA4使用階層式身分模型來識別使用者：

1. 使用者ID （若由您的實作設定）
2. Google訊號（如果使用者已登入Google帳戶並啟用個人化）
3. 裝置ID （Cookie型使用者端ID）

在大多數實施中，該人員ID是ECID (Experience Cloud ID)。 選用的&#x200B;**[!UICONTROL 拼接]**&#x200B;功能接著便可使用欄位式或圖表式方法來解析跨裝置和跨管道身分，讓行動應用程式工作階段和案頭瀏覽器工作階段與同一個人員建立關聯。

由於不同平台之間的身分解析度不同，因此使用者層級的計數很少完全相符。 這種差異是預期行為，並不表示資料品質有問題。

## 歸因

GA4會套用屬性層級（在「管理員」下）設定的報表歸因模型，預設為資料導向歸因。 和Customer Journey Analytics一樣，GA4會在報告時評估此模型，因此變更它會回溯更新歷史和未來的報告。 但在GA4中，此模型是屬性範圍的模型，只會影響使用事件範圍流量維度的關鍵事件報表（例如Source、Medium和Campaign）。

Customer Journey Analytics也會在報告時套用歸因，但控制更精細。 您可以在下列兩個位置進行設定：

* **資料檢視設定**：可以在資料檢視中的任何量度元件上設定[歸因模型](/help/data-views/component-settings/attribution.md)，以建立該量度在所有報表中的預設值。 預設不會套用任何歸因模型。 您可以將資料檢視設定為包含相同量度的多個復本，每個復本都使用不同的預設歸因模型。
* **元件層級覆寫**：將量度拖曳至[!UICONTROL 自由表格]後，請在其欄標題上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 使用非預設歸因模型]**&#x200B;來覆寫該執行個體的量度。 您也可以將相同的量度拖曳到表格中多次，每一次都使用不同的歸因模型來進行直接的並排比較。

由於GA4預設為資料導向歸因，而Customer Journey Analytics除非您設定模型，否則不會套用任何模型，因此轉換和管道量度在您將兩者對齊前可能會有所不同。 將GA4設定為最後點按模型，並在Customer Journey Analytics中設定相符的最後點按模型，是建立類似基準的最可靠方式。 Customer Journey Analytics中的任何模型變更都會回溯套用至所有歷史資料，而不會重新處理。

## 稽核差異

當數字的差異超出預期時，可以使用三個稽核路徑：

* **Assurance**： Adobe的產品內驗證工具會確認XDM事件正確引發、連線至Edge Network且寫入Platform資料集。 在比較報表編號之前，請先使用此工具驗證您的實施情形。
* **資料集預覽**：在Platform UI中，您可以預覽任何資料集的原始資料列。 將這些與GA4的DebugView或BigQuery匯出進行比較，以驗證欄位層級的正確性。
* **Adobe Consulting**：對於持續且無法解釋的差異，您的Adobe客戶團隊可以與Adobe顧問安排正式的實作稽核。
* **擷取檢閱**：如果您懷疑GA資料匯入Platform的方式（而非報告定義）造成差異，請檢閱[從Google Analytics移轉資料](/help/use-cases/third-party/ga/overview.md)中的擷取設定。
