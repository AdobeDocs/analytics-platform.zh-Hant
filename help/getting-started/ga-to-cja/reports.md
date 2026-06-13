---
title: Customer Journey Analytics中的GA4報表
description: 找出每個GA4報表區段的Customer Journey Analytics同等專案。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Customer Journey Analytics中的GA4報表

當您知道要檢視哪個GA4報表，並想要在Analysis Workspace中重新建立大致的同等報表時，可使用此頁面作為查詢參考。 報表會依GA4的導覽區段組織。 如需將GA資料移轉至Customer Journey Analytics後可用的進階跨管道報表案例，請參閱[Google Analytics資料報表](/help/use-cases/third-party/ga/report.md)。

## 即時

+++即時

GA4的Realtime報表顯示過去30分鐘內的活動 — 活躍的使用者、引發的事件、使用者的位置、帶動流量的因素及其所在的頁面。

Customer Journey Analytics沒有獨立的即時報表區域。 請改為在Analysis Workspace中建立面板，並啟用&#x200B;**[!UICONTROL 即時重新整理]**&#x200B;切換按鈕（**Ultimate**&#x200B;套件的一部分），以便其視覺效果每分鐘都會更新：

1. 使用您要監視的維度和量度來建置[自由格式](/help/analysis-workspace/c-panels/freeform-panel.md)面板（切換也可在[空白](/help/analysis-workspace/c-panels/blank-panel.md)、[歸因](/help/analysis-workspace/c-panels/attribution.md)和[下一個或上一個專案](/help/analysis-workspace/c-panels/next-previous.md)面板上運作）。 若要映象GA4的即時卡片，請使用&#x200B;**[!UICONTROL 頁面]**、**[!UICONTROL 事件型別]**、**[!UICONTROL 反向連結網域]**&#x200B;或&#x200B;**[!UICONTROL 國家/地區]**&#x200B;作為維度，並將&#x200B;**[!UICONTROL 工作階段]**&#x200B;作為量度。
2. 啟用&#x200B;**[!UICONTROL 即時重新整理]**&#x200B;切換，並選取從&#x200B;**[!UICONTROL 最近15分鐘]**&#x200B;到&#x200B;**[!UICONTROL 最近24小時]**&#x200B;的期間。 資料僅限於滾動式24小時視窗，而面板每分鐘會重新整理一次，最多達30分鐘。

即時報告偏好事件和工作階段層級的資料，且無法使用拼接，因此偏好使用&#x200B;**[!UICONTROL 工作階段]**&#x200B;而非&#x200B;**[!UICONTROL 人員]**。 請參閱[使用即時報告](/help/components/real-time/use-real-time.md)以瞭解完整程式，並參閱[即時報告總覽](/help/components/real-time/real-time.md)以瞭解權益和延遲詳細資料。

+++

## 贏取

+++使用者贏取（首次接觸）

GA4的「使用者贏取」報表使用首次接觸歸因，將每位使用者歸因於首次將他們帶到您網站的頻道、來源和媒體。

在Analysis Workspace中，將&#x200B;**[!UICONTROL 首次接觸]**&#x200B;歸因模型套用至&#x200B;**[!UICONTROL 行銷管道]**&#x200B;維度。 必須先設定行銷管道，才能加以使用。 請參閱[建立行銷管道衍生欄位](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)。

1. 將&#x200B;**[!UICONTROL 行銷管道]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
2. 以滑鼠右鍵按一下量度欄標題，然後選取&#x200B;**[!UICONTROL 使用非預設歸因模型]**。
3. 選取回溯時段適合您分析的&#x200B;**[!UICONTROL 首次接觸]**。

或者，使用[[!UICONTROL 歸因]面板](/help/analysis-workspace/c-panels/attribution.md)進行首次接觸與上次接觸管道效能的並排比較。

+++

+++流量取得（工作階段型）

GA4的「流量贏取」報表會使用工作階段型歸因，將每個工作階段歸因於啟動工作階段的管道、來源和媒體。 您可以依預設管道群組、來源/媒體、反向連結或促銷活動來劃分。

在Analysis Workspace中，具有預設&#x200B;**[!UICONTROL 上次接觸]**&#x200B;歸因模型的&#x200B;**[!UICONTROL 行銷管道]**&#x200B;維度提供工作階段型管道報表：

1. 將&#x200B;**[!UICONTROL 行銷管道]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
2. 將所需的量度拖曳至預設&#x200B;**[!UICONTROL 事件]**&#x200B;量度旁邊。

GA4的劃分會對應至這些Customer Journey Analytics維度：

* **管道**： **[!UICONTROL 行銷管道]**。 Customer Journey Analytics沒有內建管道群組 — 使用&#x200B;**[!UICONTROL 行銷管道]**&#x200B;功能範本將其定義為[衍生欄位](/help/data-views/derived-fields/derived-fields.md)，或使用Analytics來源聯結器時從Adobe Analytics結轉規則（請參閱[使用行銷管道維度](/help/use-cases/aa-data/marketing-channels.md)）。
* **Source /媒體與反向連結**： **[!UICONTROL 反向連結網域]**&#x200B;與&#x200B;**[!UICONTROL 反向連結型別]**。
* **促銷活動**： GA4的`utm_*`引數不會自動收集 — 每個引數都必須在實作期間對應至XDM欄位，才會顯示為維度。 如果促銷活動值以追蹤代碼的形式送達，請使用&#x200B;**[!UICONTROL 追蹤代碼]**&#x200B;維度。

+++

+++歸因和轉換路徑

GA4的「歸因」報表（在Advertising底下）會顯示不同管道對轉換的貢獻，並容許進行模型比較和轉換路徑分析。

在Analysis Workspace中，使用[[!UICONTROL 歸因]面板](/help/analysis-workspace/c-panels/attribution.md)：

1. 選取「面板」圖示，並將&#x200B;**[!UICONTROL 歸因]**&#x200B;面板拖曳至畫布上。
2. 將「**[!UICONTROL 行銷管道]**」維度拖曳至「**[!UICONTROL 新增Dimension]**」方塊。
3. 將您的轉換量度（例如購買事件）拖曳至「**[!UICONTROL 新增量度]**」方塊。
4. 選取「**[!UICONTROL 建置]**」。

[!UICONTROL 歸因面板]會產生模型比較表和[!UICONTROL 管道流量]視覺效果，顯示訪客在轉換前所採用的最上層路徑。 選取&#x200B;**[!UICONTROL 新增模型]**&#x200B;以同時比較多個歸因模型。

+++

## 參與

+++頁面和熒幕

GA4的「頁面和畫面」報表會顯示個別頁面和應用程式畫面的效能度量。

在Analysis Workspace中，將&#x200B;**[!UICONTROL 頁面]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)並新增您想要的量度。 通用量度包括&#x200B;**[!UICONTROL 工作階段]**、**[!UICONTROL 人員]**、**[!UICONTROL 跳出率]**&#x200B;和&#x200B;**[!UICONTROL 每個工作階段逗留時間]**。

若要依URL路徑結構（例如`/blog/`或`/products/`）將頁面分組，如果您的實作定義，請使用&#x200B;**[!UICONTROL 網站區段]**&#x200B;維度，或建立以&#x200B;**[!UICONTROL URL剖析]**&#x200B;函式剖析頁面URL的[衍生欄位](/help/data-views/derived-fields/derived-fields.md)。 如果您維持明確的頁面對區段對應，則[查詢資料集](/help/connections/standard-lookups.md)可以改為提供分組。

+++

+++登陸頁面

GA4的登陸頁面報表會顯示使用者在開始工作階段時到達的頁面。

在Analysis Workspace中，將&#x200B;**[!UICONTROL 登入頁面]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。 **[!UICONTROL 工作階段]**&#x200B;是此維度最相關的量度。

+++

+++事件

GA4的「事件」報表會顯示每個事件引發的次數，並具有事件層級的量度。

在GA4中，事件具有名稱和選用引數（例如，具有引數`video_title`的事件`video_play`）。 在Customer Journey Analytics中，事件名稱的標準維度是&#x200B;**[!UICONTROL 事件型別]** （來源為`xdm.eventType`）。 事件引數對應至其他XDM欄位，其名稱取決於您的實作。

將&#x200B;**[!UICONTROL 事件型別]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)以列出所有事件型別，以及&#x200B;**[!UICONTROL 事件]**&#x200B;量度。

+++

+++重要事件（轉換）

GA4的關鍵事件報告（前身為「轉換」）會依名稱列出每個關鍵事件及其計數 — 在GA4屬性設定中標籤為業務關鍵的事件。

Customer Journey Analytics沒有「關鍵事件」標幟；每個互動都是一個事件，因此沒有可開啟的轉換預設清單。

若要依名稱重新建立GA4的轉換清單，請使用&#x200B;**區段作為列**。 [[!UICONTROL 自由格式表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)無法將量度放在列位置，但可以將區段放在那裡：

1. 對於每個轉換，建立一個區段來隔離其事件 — 例如，`xdm.eventType`等於`commerce.purchases`的事件範圍區段。 在每個區段代表的轉換後為其命名（例如，**購買**）。
2. 將每個轉換區段拖曳至[!UICONTROL 自由格式表格]的列區域，每列一個。
3. 將&#x200B;**[!UICONTROL 事件]**&#x200B;量度新增為資料行。 每一列會顯示轉換的計數，鏡射GA4的機碼事件清單。 請改用&#x200B;**[!UICONTROL 人員]**&#x200B;來計算不重複轉換器。

若要新增轉換率，請建立定義為轉換量度除以&#x200B;**[!UICONTROL 工作階段]**&#x200B;或&#x200B;**[!UICONTROL 人員]**&#x200B;的計算量度（選取量度清單附近的&#x200B;**+**&#x200B;圖示）。

您在此處隔離的每個轉換也可以在資料檢視中定義為可重複使用的量度。 請參閱[通用量度](#common-metrics)下的&#x200B;**自訂事件量度→的關鍵事件**&#x200B;專案，以瞭解如何設定。

+++

## 創造營收

+++電子商務購買

GA4的電子商務購買報表顯示產品層級的購買資料，包括專案、收入和數量。

在Customer Journey Analytics中，電子商務報表會搭配購買量度使用&#x200B;**[!UICONTROL Product]**&#x200B;維度。 此報表要求您的實作傳送XDM商務資料（例如`xdm.commerce.purchases`、`xdm.commerce.order`和`xdm.productListItems`）。

1. 將&#x200B;**[!UICONTROL Product]**&#x200B;維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。
2. 將&#x200B;**[!UICONTROL 訂單]**、**[!UICONTROL 收入]**&#x200B;和&#x200B;**[!UICONTROL 單位]**&#x200B;等電子商務量度與預設的&#x200B;**[!UICONTROL 事件]**&#x200B;量度拖曳。

+++

+++購買歷程(funnel)

GA4的Purchase journey報告會顯示使用者在您購物funnel中的移動方式，例如從加入購物車到開始結帳再到購買，以及他們在哪裡下車。

在Analysis Workspace中，使用[**[!UICONTROL 流失]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL 流失]**&#x200B;視覺效果拖曳至畫布上。
2. 找出&#x200B;**[!UICONTROL 頁面]**&#x200B;維度，並將其展開以顯示個別頁面值。
3. 將第一個funnel步驟（例如產品頁面）拖曳至第一個&#x200B;**[!UICONTROL 新增接觸點]**&#x200B;位置。
4. 繼續為每個步驟新增接觸點。

流失視覺效果接受任何維度、量度或區段作為接觸點，而不僅僅是頁面，因此它符合GA4的事件型漏斗，並延伸至混合事件、頁面和區段的序列。

+++

+++促銷活動

GA4的促銷活動報表會顯示內部促銷活動（橫幅、精選版位）如何促進產品互動。

在Customer Journey Analytics中，促銷資料需要您擷取XDM結構描述欄位中的促銷曝光次數和點按次數。 收集之後，請建立[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)，其中包含含有曝光與點按量度的促銷活動名稱維度。 與您的Customer Journey Analytics管理員合作，確認您的資料檢視中有哪些促銷活動資料可用。

+++

+++發佈者廣告

GA4的「發佈者廣告」報錶針對發佈者貨幣化的屬性，顯示來自Google Ad Manager或AdMob的廣告收入。

Customer Journey Analytics沒有原生發佈商廣告收入整合。 若要報告此資料，請使用來源聯結器或直接資料擷取，將來自廣告營利平台（例如Google Ad Manager或AdMob）的收入數字擷取至Adobe Experience Platform作為資料集。 擷取之後，資料即可在Customer Journey Analytics中報告。

+++

## 保留

+++保留率概述

GA4的「保留概觀」報告結合多種保留檢視 — 新的與回訪的使用者，以及顯示多少使用者隨著時間回訪的同類群組圖表。

**新使用者與回訪使用者**：使用&#x200B;**[!UICONTROL 第一個工作階段]**&#x200B;和&#x200B;**[!UICONTROL 回訪工作階段]**&#x200B;區段，作為[[!UICONTROL 自由格式表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中的資料列：

1. 從「元件」面板將&#x200B;**[!UICONTROL 第一個工作階段]**&#x200B;區段拖曳至表格的列區域，然後將&#x200B;**[!UICONTROL 傳回工作階段]**&#x200B;區段拖曳至其下方。
2. 將您想要的量度與預設&#x200B;**[!UICONTROL 事件]**&#x200B;量度一併新增。
3. 若要分析時間趨勢，請將[**[!UICONTROL 線條]**](/help/analysis-workspace/visualizations/line.md)視覺效果拖曳至表格上方，然後按住Ctrl鍵並按一下(Windows)或按住Cmd鍵並按一下(Mac)每列，以反白顯示兩個區段。

**一段時間內的保留率**：使用[**[!UICONTROL 同類群組表格]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL 同類群組表格]**&#x200B;拖曳至畫布上。
2. 將&#x200B;**[!UICONTROL 人員]**&#x200B;量度拖曳至[包含]和[回訪條件]欄位，然後選取[建置]&#x200B;**&#x200B;**。

[!UICONTROL 同類群組表格]會依初始期間將使用者分組，並追蹤後續期間的回訪行為；包含、回訪及詳細程度條件皆可設定。

+++

## 使用者

+++人口統計細節

GA4的人口統計詳細資料報告涵蓋使用者特徵 — 年齡、性別和興趣（由Google訊號提供技術支援，要求使用者登入已啟用個人化的Google帳戶） — 以及位置（國家、地區、城市）和語言。

**位置**&#x200B;直接對應到Customer Journey Analytics維度：在[[!UICONTROL 自由格式表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)中使用&#x200B;**[!UICONTROL 國家]**、**[!UICONTROL 地區]**&#x200B;或&#x200B;**[!UICONTROL 城市]**，或使用[[!UICONTROL 地圖]](/help/analysis-workspace/visualizations/map.md)視覺效果以取得地理概觀（將&#x200B;**[!UICONTROL 人員]**&#x200B;量度拖曳至&#x200B;**[!UICONTROL 新增量度]**&#x200B;位置並選取&#x200B;**[!UICONTROL 組建]**）。

**年齡、性別和興趣**&#x200B;需要第一方資料。 如果您的組織透過CRM、登錄檔單或同義式調查收集人口統計資料，請將其擷取為[設定檔資料集](/help/connections/create-connection.md#profile-dataset)，並將其加入事件資料。 此方法產生的資料比GA4推斷的Google Signals模型更可靠，因為它使用經同意的第一方屬性。

+++

+++技術詳細資訊

GA4的技術報告會顯示瀏覽器、作業系統、熒幕解析度和裝置類別。

在Analysis Workspace中，下列維度對應至GA4的技術維度，每個維度都源自標準XDM欄位：

| GA4技術維度 | Analysis Workspace維度 | XDM欄位 |
|---|---|---|
| 瀏覽器 | **[!UICONTROL 瀏覽器]** | `xdm.environment.browserDetails.name` |
| 作業系統 | **[!UICONTROL 作業系統]** | `xdm.environment.operatingSystem` |
| 熒幕解析度 | **[!UICONTROL 監視器解析度]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| 裝置類別（行動裝置、桌上型電腦、平板電腦） | **[!UICONTROL 行動裝置型別]** | `xdm.device.type` |
| 裝置型號 | **[!UICONTROL 行動裝置]** | `xdm.device.model` |

從「元件」面板將這些維度拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)。

>[!NOTE]
>
>由於現代瀏覽器已減少使用者代理字串中的詳細資訊，因此完整且準確的值取決於是否要在您的網頁SDK設定中收集[使用者代理使用者端提示](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/use-cases/client-hints)。

+++

## 探索

+++自由格式探索

GA4的自由格式探索是空白畫布表格，具有可供設定的列、欄和選用的圖表覆蓋圖。

Analysis Workspace的[**[!UICONTROL 自由格式表格]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)是直接的對等專案，也是大多數Workspace專案的基礎。 將任何維度拖曳至列、將任何量度拖曳至欄，並將任何區段拖曳至表格上方的區段拖放區域。

如需GA4 Explore與Workspace之間的術語對應，請參閱[Analysis Workspace快速入門](home.md#getting-started-in-analysis-workspace)。

+++

+++funnel探索

GA4的Funnel探索會定義一系列步驟，並測量每個步驟的完成和流失。

在Analysis Workspace中，使用[**[!UICONTROL 流失]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL 流失]**&#x200B;視覺效果拖曳至畫布上。
2. 將代表您第一個步驟的維度、量度或區段拖曳至第一個&#x200B;**[!UICONTROL 新增接觸點]**&#x200B;位置。
3. 繼續為序列中的每個後續步驟新增接觸點。

由於任何維度、量度或區段都可做為接觸點，因此[!UICONTROL 流失]會符合GA4的事件型漏斗，並延伸至混合事件、頁面和區段的跨管道序列。

+++

+++路徑探索

GA4的路徑探索（Universal Analytics稱為此使用者流程）可視覺化使用者導覽的頁面或事件順序。

在Analysis Workspace中，使用[**[!UICONTROL 流量]**](/help/analysis-workspace/visualizations/c-flow/flow.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL 流量]**&#x200B;視覺效果拖曳至畫布上。
2. 從您要路徑處理的維度中拖曳一個值（例如&#x200B;**[!UICONTROL Page]**&#x200B;或&#x200B;**[!UICONTROL 事件型別]**&#x200B;值）至流程中心。
3. 視覺效果會顯示使用者在該時間點之前和之後所做的動作。

[!UICONTROL 流量]視覺效果為互動式 — 選取任何節點，可往任一方向進一步展開路徑。 您可以使用任何維度，以便在頁面、事件、行銷管道或自訂連結上建立路徑。

+++

+++區段重疊

GA4的區段重疊探索會顯示多個使用者區段如何相交，並以文氏圖表呈現。

在Analysis Workspace中，使用[**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL Venn]**&#x200B;視覺效果拖曳至畫布上。
2. 從「元件」面板最多拖曳三個區段至視覺效果。

文氏圖表顯示交集大小，下方的[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)顯示基礎資料。

+++

+++同類群組探索

GA4的同類群組探索會根據共用特徵（通常是贏取日期）將使用者分組，並追蹤他們在一段時間內的行為。

在Analysis Workspace中，使用[**[!UICONTROL 同類群組表格]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)視覺效果：

1. 選取「視覺效果」圖示，並將&#x200B;**[!UICONTROL 同類群組表格]**&#x200B;拖曳至畫布上。
2. 將&#x200B;**[!UICONTROL 人員]**&#x200B;量度拖曳至「包含」和「回訪條件」欄位。
3. 選取「**[!UICONTROL 建置]**」。

[!UICONTROL 同類群組表格]會依人員的初始期間將其分組，並追蹤後續期間的回訪行為。 依預設，它會在贏取日期進行同類群組，但包含、回訪和詳細程度條件皆可設定。

+++

+++使用者總管

GA4的使用者總管會顯示個別使用者、其工作階段歷史記錄和事件的時間表。

Customer Journey Analytics以兩種方式支援人員層級分析：

* **已啟用拼接**：建立特定人員ID值的區段範圍，並將其套用至任何Workspace專案。 **[!UICONTROL 人員]**&#x200B;容器會跨工作階段和管道隔離該個人的拼接活動。
* **原始事件資料**：在Adobe Experience Platform UI中使用&#x200B;**資料集預覽**&#x200B;來檢查原始XDM事件記錄。 此檢視對於實作驗證和偵錯個別事件非常有用。

+++

+++使用者期限

GA4的使用者期限探索會測量每位使用者在其與您的企業整個關係中的累計價值和參與度，而不是在固定的日期範圍內。 它結合歷史期限量度與Google對購買機率、流失機率和預測收入的機器學習預測。

這些功能會將兩個部分對應至Customer Journey Analytics：

**歷史存留期值**&#x200B;可以原生達成。 由於Customer Journey Analytics會針對您的完整資料保留期間製作報表，因此您可以設定較長的日期範圍，並彙總每個人在該回顧期間的累計收入及參與度。 使用拼接或永續性人員ID，**[!UICONTROL 人員]**&#x200B;容器會將該活動繫結至個人，且計算量度會表示每個人的值。 結果不是無限的生命週期，而是可以設定的長回顧期，約略算一個。

**未內建預測性存留期值**。 Customer Journey Analytics沒有產品內購買機率、流失率或預測收入模型。 若要使用預測性分數，請從外部計算這些分數（例如，在CRM或資料科學工作流程中），並將這些分數當作設定檔資料集引入Customer Journey Analytics，然後以維度或量度的形式呈現這些分數。 Adobe建議您與實施顧問合作，共同設計此方法。

+++

## 通用量度

+++使用中的使用者→人員

GA4的&#x200B;**作用中使用者**&#x200B;會計入日期範圍內至少有一個參與工作階段的使用者。

在Customer Journey Analytics中，最接近的對等值為&#x200B;**[!UICONTROL 人員]**，這是日期範圍內不重複人員ID的計數。 [!UICONTROL 人員]包含所有已識別的人員，無論參與程度為何，因此對於具有大量被動流量的網站，其通常會高於GA4的主動使用者。

如需更密切的行為比較，請套用[參與工作階段區段](compare-data.md#engaged-sessions)，將[!UICONTROL 人員]量度範圍設定為符合您參與條件的使用者。

+++

+++計算量度→參與工作階段

GA4的&#x200B;**參與工作階段**&#x200B;會計算持續10秒或更多秒、有2次或更多頁面檢視，或至少包含一個關鍵事件的工作階段。

Customer Journey Analytics沒有內建參與工作階段量度 — 您將其定義為擷取參與條件的區段，然後與&#x200B;**[!UICONTROL 工作階段]**&#x200B;量度搭配使用。 請參閱[參與工作階段](compare-data.md#engaged-sessions)以瞭解建議的方法，以及如何從中得出參與率。

+++

+++計算量度→參與率

GA4的&#x200B;**參與率**&#x200B;是參與工作階段的百分比：參與工作階段除以工作階段總數。

在Customer Journey Analytics中，根據參與工作階段定義將其建置為計算量度。 如需逐步指示，請參閱[參與的工作階段](compare-data.md#engagement-rate)。

+++

+++平均參與時間→每個工作階段逗留時間

GA4的&#x200B;**平均參與時間**&#x200B;是測量參與工作階段期間，瀏覽器或應用程式在前景的平均時間。

在Customer Journey Analytics中，使用&#x200B;**[!UICONTROL 工作階段持續時間（秒）]**，測量工作階段中從第一個事件到最後一個事件的經過時間。 此元件包含使用者可能未主動參與的期間，因此值可以與GA4的測量不同。 這是最接近的內建對等專案。

+++

+++事件計數→事件

GA4的&#x200B;**事件計數**&#x200B;是任何事件的記錄總次數。

在Customer Journey Analytics中，相等的量度是&#x200B;**[!UICONTROL 事件]** — 資料集中所選日期範圍和套用區段的事件記錄總數。

+++

+++工作階段→工作階段

GA4的&#x200B;**工作階段**&#x200B;和Customer Journey Analytics的&#x200B;**[!UICONTROL 工作階段]**&#x200B;都會測量日期範圍內的工作階段數。 計數可能會因工作階段定義規則不同而有所差異。 請參閱[為什麼GA4和Customer Journey Analytics資料不同](compare-data.md#sessions)以取得詳細資料。

+++

+++套用至人員→首次工作階段區段的新使用者

GA4的&#x200B;**新使用者**&#x200B;會計入其首次工作階段在所選日期範圍內的使用者。

在Analysis Workspace中：

1. 在「元件」面板中找到&#x200B;**[!UICONTROL 第一個工作階段]**&#x200B;區段。
2. 將其拖曳至[[!UICONTROL 自由表格]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)上方的區段放置區。
3. 使用&#x200B;**[!UICONTROL 人員]**&#x200B;量度來計算不重複的新人員。

+++

+++跳出率→跳出率（含警告）

GA4的&#x200B;**跳出率**&#x200B;是未參與的工作階段百分比（少於10秒、無主要事件、少於2次頁面檢視）。 這是參與率的反比。

Customer Journey Analytics的&#x200B;**[!UICONTROL 跳出率]**&#x200B;量度預設使用不同的定義，並可根據資料檢視設定。 這些差異會產生截然不同的數字，以測量不同的行為。

若要在Customer Journey Analytics中逼近GA4的跳出率，請建置參與率量度，並使用定義為`1 - Engagement Rate`的第二個計算量度將其反轉。 如需逐步建置，請參閱[參與的工作階段](compare-data.md#engagement-rate)。

請參閱[為何GA4與Customer Journey Analytics資料不同](compare-data.md#bounce-rate)，以取得定義差異的詳細說明。

+++

+++關鍵事件→自訂事件量度

GA4的&#x200B;**關鍵事件** （以前稱為Conversions）是指定為GA4屬性組態中重要商業結果的事件。

在Customer Journey Analytics中，轉換是在資料檢視中設定的自訂事件量度。 任何XDM事件都可以公開為量度，而量度可以設定為有條件地在XDM欄位值上增加 — 例如，**[!UICONTROL 購買]**&#x200B;量度，當`xdm.eventType`等於`commerce.purchases`時增加。 在Analysis Workspace的「元件」面板中，依相關量度的標籤來找出相關量度；此名稱會反映管理員的設定方式。

若要重現GA4的關鍵事件&#x200B;*報告* （每個轉換及其計數的清單），請參閱此頁面上[參與](#engagement)下的&#x200B;**關鍵事件（轉換）**&#x200B;專案。

+++

>[!MORELIKETHIS]
>
>* [報告Google Analytics資料](/help/use-cases/third-party/ga/report.md)
